┌─────────────────────────────────────────────────────────────────────────┐
│                         USER (PJSIP Phone)                              │
│                         human1                           │
│                         Speaks: "Book flight to Denver for Christmas"  │
└────────────────────────┬────────────────────────────────────────────────┘
                         │ SIP/RTP (ULAW 8kHz)
                         ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                      ASTERISK 20 (Debian)                               │
│  ┌───────────────────────────────────────────────────────────────────┐ │
│  │             (FLOOR) MAIN BRIDGE (ID: 1234) - MIXING                      │ │
│  │                                                                   │ │
│  │  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐        │ │
│  │  │  Human   │  │ Agent1   │  │ Agent2   │  │ Agent3   │        │ │
│  │  │ Channel  │  │ Channel  │  │ Channel  │  │ Channel  │        │ │
│  │  │ (PJSIP)  │  │ (Unicast │  │ (Unicast │  │ (Unicast │        │ │
│  │  │          │  │   RTP)   │  │   RTP)   │  │   RTP)   │        │ │
│  │  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘        │ │
│  │       │             │              │              │              │ │
│  │       └─────────────┴──────────────┴──────────────┘              │ │
│  │                    ALL HEAR EACH OTHER                           │ │
│  └───────────────────────────────────────────────────────────────────┘ │
│                                                                         │
│  ┌───────────────────────────────────────────────────────────────────┐ │
│  │         SNOOP BRIDGE (ISOLATED) - ASR ONLY                        │ │
│  │                                                                   │ │
│  │  ┌──────────────┐        ┌─────────────────┐                    │ │
│  │  │ ASR_SNOOP    │  ←───→ │  ASR_EXT        │                    │ │
│  │  │ (Snoop/...)  │        │  (ExternalMedia)│ → UDP 45000        │ │
│  │  └──────────────┘        └─────────────────┘                    │ │
│  │       ↑                                                          │ │
│  │       │ Spy "in" (human mic only)                               │ │
│  │  ┌────┴──────┐                                                  │ │
│  │  │  Human    │                                                  │ │
│  │  │  Channel  │                                                  │ │
│  │  └───────────┘                                                  │ │
│  └───────────────────────────────────────────────────────────────────┘ │
│                                                                         │
│  - ARI (REST + WebSocket): Port 8088                                   │
│  - Stasis App: "convener"                                              │
│  - PJSIP Endpoint: human1                                              │
└────────┬────────────────────────────┬───────────────────────────────────┘
         │                            │
         │ ARI WebSocket              │ ULAW RTP Stream (human mic)
         │                            │
         ▼                            ▼
┌─────────────────────┐    ┌──────────────────────────────────────────────┐
│  convener_          │    │  deepgram_asr_integrated.py                  │
│  integrated.py      │    │                                              │
│                     │    │  - UDP Server: 45000 (RTP receiver)          │
│  - ARI Client       │    │  - Deepgram WebSocket Client                 │
│  - State Machine    │◄───┤  - RTP Header Parser                         │
│  - Agent Manager    │    │  - Sends transcripts via UDP 45001           │
│  - ASR Listener     │    └──────────────┬───────────────────────────────┘
│    Port: 45001      │                   │
│  - Floor Control    │                   │ WebSocket (Real-time STT)
│                     │                   │
│  ┌───────────────┐  │                   ▼
│  │  AGENT POOL   │  │    ┌──────────────────────────────────────────────┐
│  │               │  │    │   Deepgram API (Cloud)                       │
│  │ ┌───────────┐ │  │    │   - Model: nova-2                            │
│  │ │ Agent1    │ │  │    │   - Encoding: mulaw                          │
│  │ │ Flight    │ │  │    │   - Sample Rate: 8kHz                        │
│  │ │ Specialist│ │  │    │   - Interim + Final Results                  │
│  │ │           │ │  │    │   - Language: en-US                          │
│  │ │ Port:20000│ │  │    └──────────────────────────────────────────────┘
│  │ └───────────┘ │  │
│  │               │  │
│  │ ┌───────────┐ │  │    ┌──────────────────────────────────────────────┐
│  │ │ Agent2    │ │  │    │   rtp-send.py Processes (x3)                 │
│  │ │ Event     │ │  │    │                                              │
│  │ │ Specialist│ │  │    │  agent1-ready-loop.slin → RTP → Port 20000  │
│  │ │           │ │  │    │  agent2-ready-loop.slin → RTP → Port 20002  │
│  │ │ Port:20002│ │  │    │  agent3-ready-loop.slin → RTP → Port 20004  │
│  │ └───────────┘ │  │    │                                              │
│  │               │  │    │  Background audio keeps agents "alive"       │
│  │ ┌───────────┐ │  │    └──────────────────────────────────────────────┘
│  │ │ Agent3    │ │  │
│  │ │ Car Rental│ │  │
│  │ │ Specialist│ │  │
│  │ │           │ │  │
│  │ │ Port:20004│ │  │
│  │ └───────────┘ │  │
│  └───────────────┘  │
└─────────────────────┘
