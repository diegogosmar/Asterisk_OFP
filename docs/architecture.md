# System Architecture - Complete Technical Overview

This document provides detailed architectural diagrams of the multi-agent AI voice system, showing all components, bridges, and data flows.

---

## High-Level Architecture

┌─────────────────────────────────────────────────────────────┐
│ ENTERPRISE-GRADE CONVERSATIONAL AI PLATFORM │
└─────────────────────────────────────────────────────────────┘

👤 User (SIP Phone)
↓ SIP/RTP (ULAW 8kHz)

📞 Asterisk PBX + ARI (Port 8088)
↓ Audio Routing + Channel Management

🎙️ Deepgram ASR (Real-time Speech-to-Text)
↓ Transcription via WebSocket

🧠 Convener (OFP Orchestrator v1.0.0)
↓ Agent Selection & Floor Control

text
├→ 🎵 Agent0: Async Hold Music
│   -  "Please wait" message
│   -  Auto-stops when Agent1 ready
│   -  Zero perceived latency
│
├→ 🤖 Agent1: Dynamic AI Assistant (LLM)
│   -  OpenAI GPT-4 (reasoning)
│   -  Deepgram TTS (natural voice)
│   -  Context-aware responses
│   -  Greeting + Summary modes
│
├→ 🎭 Agent2: Event Specialist (Stub)
│   -  Prerecorded audio
│   -  Fast response time
│
└→ 🎭 Agent3: Car Rental Specialist (Stub)
    -  Prerecorded audio
    -  Consistent quality
✅ Smart playback completion detection
✅ OFP floor control management
✅ Keyword-based confirmation

text

---

## Detailed Component Architecture

### Layer 1: User Interface

┌───────────────────────────────────────────────────────────┐
│ USER (PJSIP Phone) │
│ │
│ Extension: human1 │
│ Protocol: SIP (PJSIP) │
│ Audio: RTP/ULAW @ 8kHz │
│ │
│ User speaks: "Book flight to Denver for Christmas" │
└─────────────────────────┬─────────────────────────────────┘
│ SIP INVITE + RTP Stream
↓

text

---

### Layer 2: Asterisk PBX Core

┌─────────────────────────────────────────────────────────────┐
│ ASTERISK 20 (Debian) │
├─────────────────────────────────────────────────────────────┤
│ │
│ ┌───────────────────────────────────────────────────────┐ │
│ │ MAIN BRIDGE (ID: 1234) - MIXING │ │
│ │ "THE FLOOR" │ │
│ │ │ │
│ │ ┌──────────┐ ┌──────────┐ ┌──────────┐ │ │
│ │ │ Human │ │ Agent1 │ │ Agent2 │ │ │
│ │ │ Channel │ │ Channel │ │ Channel │ │ │
│ │ │ (PJSIP) │ │(UnicastRTP)│(UnicastRTP)│ │ │
│ │ └────┬─────┘ └────┬─────┘ └────┬─────┘ │ │
│ │ │ │ │ │ │
│ │ └─────────────┴──────────────┘ │ │
│ │ ┌──────────┐ │ │
│ │ │ Agent3 │ │ │
│ │ │ Channel │ │ │
│ │ │(UnicastRTP)│ │ │
│ │ └────┬─────┘ │ │
│ │ │ │ │
│ │ ALL PARTICIPANTS HEAR EACH OTHER │ │
│ │ (Conference call environment) │ │
│ └───────────────────────────────────────────────────────┘ │
│ │
│ ┌───────────────────────────────────────────────────────┐ │
│ │ SNOOP BRIDGE (ISOLATED) - ASR CAPTURE ONLY │ │
│ │ │ │
│ │ ┌──────────────┐ ┌─────────────────┐ │ │
│ │ │ ASR_SNOOP │◄─────►│ ASR_EXT │ │ │
│ │ │(Snoop/human) │ │(ExternalMedia) │ │ │
│ │ └──────┬───────┘ └────────┬────────┘ │ │
│ │ │ │ │ │
│ │ │ Spy "in" │ UDP:45000 │ │
│ │ │ (mic only) │ RTP ULAW │ │
│ │ ┌────▼─────┐ ↓ │ │
│ │ │ Human │ Deepgram ASR │ │
│ │ │ Channel │ │ │
│ │ └──────────┘ │ │
│ │ │ │
│ │ Purpose: Echo-free speech recognition │ │
│ │ - Only captures user microphone │ │
│ │ - Agent audio NOT sent to ASR │ │
│ │ - Prevents false transcriptions │ │
│ └───────────────────────────────────────────────────────┘ │
│ │
│ Configuration: │
│ - ARI Server: http://127.0.0.1:8088 │
│ - WebSocket: ws://127.0.0.1:8088/ari/events │
│ - Stasis App: "convener" │
│ - PJSIP Endpoint: human1 │
└─────────────┬───────────────────┬───────────────────────────┘
│ │
│ ARI WebSocket │ RTP Stream
│ (Events) │ (Human Mic → ASR)
↓ ↓

text

---

### Layer 3: Application Layer

┌─────────────────────────────────────────────────────────────┐
│ convener_integrated.py │
│ (Python Orchestrator) │
├─────────────────────────────────────────────────────────────┤
│ │
│ Core Components: │
│ - ARI Client (WebSocket + REST) │
│ - State Machine (INTRO → WAITING → TALKING → CONFIRM) │
│ - ASR Listener (UDP:45001) │
│ - Agent Manager │
│ - OFP Floor Control │
│ │
│ ┌───────────────────────────────────────────────────────┐ │
│ │ AGENT POOL │ │
│ │ │ │
│ │ ┌─────────────────────────────────────────┐ │ │
│ │ │ Agent0: Hold Music │ │ │
│ │ │ - Type: holdmusic │ │ │
│ │ │ - Audio: agent0-please-wait.slin │ │ │
│ │ │ - Async playback (no RTP channel) │ │ │
│ │ └─────────────────────────────────────────┘ │ │
│ │ │ │
│ │ ┌─────────────────────────────────────────┐ │ │
│ │ │ Agent1: Flight Specialist (LLM) │ │ │
│ │ │ - Type: llm │ │ │
│ │ │ - Port: 20000 (RTP receive) │ │ │
│ │ │ - Loop Audio: agent1-ready-loop.slin │ │ │
│ │ │ - API: http://127.0.0.1:8001/ofp │ │ │
│ │ │ - LLM: OpenAI GPT-4 │ │ │
│ │ │ - TTS: Deepgram Aura │ │ │
│ │ └─────────────────────────────────────────┘ │ │
│ │ │ │
│ │ ┌─────────────────────────────────────────┐ │ │
│ │ │ Agent2: Event Specialist (Stub) │ │ │
│ │ │ - Type: stub │ │ │
│ │ │ - Port: 20002 (RTP receive) │ │ │
│ │ │ - Loop Audio: agent2-ready-loop.slin │ │ │
│ │ │ - Playback: agent2-suggest-event.slin │ │ │
│ │ └─────────────────────────────────────────┘ │ │
│ │ │ │
│ │ ┌─────────────────────────────────────────┐ │ │
│ │ │ Agent3: Car Rental (Stub) │ │ │
│ │ │ - Type: stub │ │ │
│ │ │ - Port: 20004 (RTP receive) │ │ │
│ │ │ - Loop Audio: agent3-ready-loop.slin │ │ │
│ │ │ - Playback: agent3-check-car.slin │ │ │
│ │ └─────────────────────────────────────────┘ │ │
│ └───────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘

text

---

### Layer 4: External Services

┌─────────────────────────────────────────────────────────────┐
│ deepgram_asr_integrated.py │
│ (ASR Service) │
├─────────────────────────────────────────────────────────────┤
│ │
│ - UDP Server: 127.0.0.1:45000 (RTP receiver) │
│ - RTP Header Parser (12-byte strip) │
│ - Deepgram WebSocket Client │
│ - Transcript Sender: UDP:45001 → Convener │
│ │
│ Configuration: │
│ - Model: nova-2 │
│ - Encoding: mulaw │
│ - Sample Rate: 8000 Hz │
│ - Language: en-US │
│ - Features: interim_results, punctuate │
└────────────────────────┬────────────────────────────────────┘
│ WebSocket
↓
┌─────────────────────────────────────────────────────────────┐
│ Deepgram API (Cloud) │
│ │
│ - Real-time Speech-to-Text │
│ - Streaming transcription │
│ - Partial + Final results │
│ - Automatic punctuation │
└─────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────┐
│ agent_llm.py (Agent1) │
│ (Dynamic AI Agent - Flask Server) │
├─────────────────────────────────────────────────────────────┤
│ │
│ - HTTP Server: http://127.0.0.1:8001 │
│ - Endpoint: POST /ofp (OFP message receiver) │
│ - OpenAI GPT-4 API Client │
│ - Deepgram TTS API Client │
│ - Audio File Generator │
│ │
│ Workflow: │
│ 1. Receive grantFloor OFP message │
│ 2. Extract user transcript from context │
│ 3. Generate GPT-4 response │
│ 4. Synthesize speech via Deepgram TTS │
│ 5. Save as agent1_dynamic_*.slin │
│ 6. Return OFP response with audio file path │
└────────────────┬────────────────────┬───────────────────────┘
│ │
↓ ↓
OpenAI API (GPT-4) Deepgram TTS API

┌─────────────────────────────────────────────────────────────┐
│ rtp-send.py (x3 instances) │
│ (Background Audio Loop) │
├─────────────────────────────────────────────────────────────┤
│ │
│ Instance 1: agent1-ready-loop.slin → UDP:20000 │
│ Instance 2: agent2-ready-loop.slin → UDP:20002 │
│ Instance 3: agent3-ready-loop.slin → UDP:20004 │
│ │
│ Purpose: Keep agent channels "alive" with audio loop │
│ Format: SLIN16 (16-bit signed linear, 8kHz) │
│ Mode: --loop (continuous playback) │
└─────────────────────────────────────────────────────────────┘

text

---

## Call Flow Diagram

USER (PJSIP)
↓
extensions.conf: Stasis(convener)
↓
┌───────────────────────────────────────────────────────────┐
│ ASTERISK CORE │
│ │
│ ┌────────────────────────────────────────────────────┐ │
│ │ ARI WebSocket Server (port 8088) │ │
│ │ ws://127.0.0.1:8088/ari/events?app=convener │ │
│ └─────────────────┬──────────────────────────────────┘ │
│ │ │
│ ┌─────────────────▼──────────────────────────────────┐ │
│ │ Stasis Application: "convener" │ │
│ │ │ │
│ │ Active Channels: │ │
│ │ - PJSIP/human1-xxx (user channel) │ │
│ │ - ExternalMedia/agent1 (virtual RTP) │ │
│ │ - ExternalMedia/agent2 (virtual RTP) │ │
│ │ - ExternalMedia/agent3 (virtual RTP) │ │
│ │ - ExternalMedia/ASR_EXT_45000 (ASR receiver) │ │
│ │ - Snoop/1760867641.90-xxx (snoop on human) │ │
│ └────────────────────────────────────────────────────┘ │
│ │
│ ┌────────────────────────────────────────────────────┐ │
│ │ Bridge: 1234 (mixing, type=confbridge) │ │
│ │ │ │
│ │ Participants: │ │
│ │ - human1 (role: user_default) │ │
│ │ - agent1 (role: ai_agent) │ │
│ │ - agent2 (role: ai_agent) │ │
│ │ - agent3 (role: ai_agent) │ │
│ └────────────────────────────────────────────────────┘ │
│ │
│ ┌────────────────────────────────────────────────────┐ │
│ │ Bridge: snoop_bridge (isolated) │ │
│ │ │ │
│ │ Participants: │ │
│ │ - ASR_SNOOP_45000 (spy on human mic) │ │
│ │ - ASR_EXT_45000 (forward to Deepgram) │ │
│ └────────────────────────────────────────────────────┘ │
└───────────────────────────────────────────────────────────┘
│ │ │
│ WebSocket │ RTP │ RTP
│ Events │ Agents │ ASR
↓ ↓ ↓
convener_ rtp-send.py deepgram_asr
integrated.py (x3 agents) _integrated.py

text

---

## Data Flow Summary

### Audio Paths

| Source | Destination | Protocol | Purpose |
|--------|-------------|----------|---------|
| User Mic | Main Bridge | RTP/ULAW 8kHz | Conference audio |
| User Mic | Snoop Bridge | Snoop (spy=in) | ASR capture only |
| Snoop Bridge | Deepgram | RTP/ULAW via UDP:45000 | Speech recognition |
| Agent1-3 | Main Bridge | RTP/SLIN16 8kHz | Agent audio |
| Agent0 | Main Bridge | Asterisk Playback | Hold music |

### Control Paths

| Source | Destination | Protocol | Purpose |
|--------|-------------|----------|---------|
| Asterisk | Convener | WebSocket | ARI events |
| Convener | Asterisk | REST API | Channel control |
| Deepgram ASR | Convener | UDP:45001 | Transcripts |
| Convener | Agent1 (LLM) | HTTP POST | OFP messages |
| Convener | Agent2/3 | (none - stubs) | Internal control |

---

## Port Assignments

| Port | Service | Direction | Protocol |
|------|---------|-----------|----------|
| 5060 | PJSIP | Inbound | SIP |
| 8088 | ARI | Bidirectional | HTTP/WebSocket |
| 8001 | Agent1 (LLM) | Outbound | HTTP |
| 20000 | Agent1 RTP | Outbound | UDP/RTP |
| 20002 | Agent2 RTP | Outbound | UDP/RTP |
| 20004 | Agent3 RTP | Outbound | UDP/RTP |
| 45000 | ASR Input | Inbound | UDP/RTP |
| 45001 | ASR Transcripts | Inbound | UDP/JSON |

---

## Key Architecture Features

### 1. Bridge Isolation
- **Main Bridge:** All participants hear each other (conference call)
- **Snoop Bridge:** Isolated ASR capture (prevents echo)

### 2. Mixed Agent Types
- **Agent0:** Playback-only (no RTP channel needed)
- **Agent1:** Dynamic LLM with GPT-4 + TTS
- **Agent2/3:** Static prerecorded audio (fast, reliable)

### 3. Zero-Latency Design
- Agent0 starts immediately (async hold music)
- Agent1 generates response in background
- Agent0 auto-stops when Agent1 ready
- **Result:** User perceives ZERO wait time

### 4. OFP Compliance
- All agent interactions follow OFP v1.0.0
- Floor control via `grantFloor`, `requestFloor`, `yieldFloor`
- Conversation ID tracking for multi-turn dialogues

---

## Technology Stack Summary

| Layer | Component | Technology |
|-------|-----------|-----------|
| **Telephony** | PBX | Asterisk 20+ |
| **API** | Control Interface | ARI (REST + WebSocket) |
| **Language** | Application Logic | Python 3.10+ |
| **Web Framework** | Agent1 Server | Flask |
| **ASR** | Speech Recognition | Deepgram nova-2 |
| **LLM** | AI Reasoning | OpenAI GPT-4 |
| **TTS** | Speech Synthesis | Deepgram Aura-Asteria |
| **Protocol** | Agent Coordination | OFP v1.0.0 (OVON) |
| **Audio** | Codec | ULAW/SLIN16 @ 8kHz |

---

## Related Documentation

- [Call Flow Example](call_flow_example.md)
- [Asterisk Stasis Flow](convener_stasis_flow.md)

---

**Architecture Status:** Production-ready, fully tested with real telephony infrastructure. 🚀✅