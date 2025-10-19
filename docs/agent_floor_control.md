# Floor Control Sequence - Multi-Agent Dialogue Flow

This document illustrates the complete floor control sequence in a multi-agent conversation, showing how agents coordinate to handle a user request through OFP (Open Floor Protocol).

---

## Overview

User Request → ASR Transcription → Multi-Agent Dialogue → User Confirmation → Completion

text

**Total Duration:** ~60 seconds  
**Agents Involved:** 3 specialized agents + 1 orchestrator  
**Protocol:** OFP v1.0.0 (OVON Compliant)

---

## Phase 1: User Query

### User Input

🎤 User: "I need to book a trip to Denver for Christmas"

text

### Processing Pipeline

User Speech
↓
📝 Deepgram ASR (Real-time transcription)
↓
⏱️ 3 seconds silence detected
↓
✅ Full transcript captured
↓
🧠 Convener: Launches multi-agent dialogue

text

**Transcript:**
> "I need to book a trip to Denver for Christmas"

---

## Phase 2: Agent Collaboration

Multi-agent sequential floor control with OFP protocol.

### Turn 1: Agent1 (Flight Specialist)

**Duration:** 12 seconds  
**Mode:** `invite` (Convener selects agent)  
**Audio:** `sound:agent1-finding-flight`

┌─────────────────────────────────────────────────────────┐
│ 🎯 Agent1 - Flight Specialist │
├─────────────────────────────────────────────────────────┤
│ "Checking flight and hotel availability for Denver, │
│ Christmas time, two adults..." │
│ │
│ 🔊 Status: Playing to MAIN BRIDGE (all participants) │
│ 📋 OFP: grantFloor(agent1, reason="Initial booking") │
└─────────────────────────────────────────────────────────┘

text

**OFP Events:**
1. Convener → `grantFloor(agent1)`
2. Agent1 → Plays audio
3. Agent1 → `yieldFloor()`

---

### Turn 2: Agent2 (Event Specialist)

**Duration:** 12 seconds  
**Mode:** `request` (Agent requests floor)  
**Audio:** `sound:agent2-suggest-event`

┌─────────────────────────────────────────────────────────┐
│ 🎯 Agent2 - Event Specialist │
├─────────────────────────────────────────────────────────┤
│ "Hold on! Denver Christmas Music Festival runs during │
│ those days. Suggest extending trip by 2 days to │
│ cover entire event..." │
│ │
│ 🔊 Status: Playing to MAIN BRIDGE (all participants) │
│ 📋 OFP: requestFloor → grantFloor(agent2) │
└─────────────────────────────────────────────────────────┘

text

**OFP Events:**
1. Agent2 → `requestFloor(reason="Schedule conflict detected")`
2. Convener → Evaluates request
3. Convener → `grantFloor(agent2, approved=true)`
4. Agent2 → Plays audio
5. Agent2 → `yieldFloor()`

**Key Insight:** Agent2 detected a conflict and proactively requested to speak!

---

### Turn 3: Agent3 (Car Rental Specialist)

**Duration:** 12 seconds  
**Mode:** `request` (Agent requests floor)  
**Audio:** `sound:agent3-check-car`

┌─────────────────────────────────────────────────────────┐
│ 🎯 Agent3 - Car Rental Specialist │
├─────────────────────────────────────────────────────────┤
│ "Copy that. Adjusting rental car search for updated │
│ 7-day period. AWD SUV confirmed..." │
│ │
│ 🔊 Status: Playing to MAIN BRIDGE (all participants) │
│ 📋 OFP: requestFloor → grantFloor(agent3) │
└─────────────────────────────────────────────────────────┘

text

**OFP Events:**
1. Agent3 → `requestFloor(reason="Duration changed, adjust car")`
2. Convener → `grantFloor(agent3, approved=true)`
3. Agent3 → Plays audio
4. Agent3 → `yieldFloor()`

**Key Insight:** Agent3 adapted to Agent2's modification (5 days → 7 days)!

---

### Turn 4: Agent1 (Final Summary)

**Duration:** 12 seconds  
**Mode:** `invite` (Convener selects for summary)  
**Audio:** `sound:agent1-final-solution`

┌─────────────────────────────────────────────────────────┐
│ 🎯 Agent1 - Flight Specialist (Final Summary) │
├─────────────────────────────────────────────────────────┤
│ "AI multi-agent collaboration complete. Booked │
│ flights, hotel, festival passes, and SUV - all │
│ within budget. Ready to proceed with booking?" │
│ │
│ 🔊 Status: Playing to MAIN BRIDGE (all participants) │
│ 📋 OFP: grantFloor(agent1, reason="Final summary") │
└─────────────────────────────────────────────────────────┘

text

**OFP Events:**
1. Convener → `grantFloor(agent1, reason="Provide final summary")`
2. Agent1 → Plays summary audio
3. Agent1 → `yieldFloor()`

**Summary Includes:**
- ✅ Flights to Denver
- ✅ Hotel accommodation (7 days)
- ✅ Festival passes
- ✅ AWD SUV rental
- ✅ Budget confirmed

---

## Phase 3: User Confirmation

### Waiting Period

⏸️ Wait 3 seconds (audio finishes playing)
↓
🎤 ASR Activated: Listening for confirmation keywords

text

### User Response

🎤 User: "Yes, please. Let's move on."

text

### Keyword Detection

🔍 Keywords detected: ["yes", "please"]
↓
⏱️ Wait 2 seconds for silence
↓
✅ Confirmation validated

text

**Valid Keywords:**
- `yes`, `sure`, `ok`, `okay`
- `proceed`, `confirm`, `correct`
- `go`, `please`

---

## Phase 4: Final Message

### Confirmation Acknowledgment

**Duration:** 10 seconds  
**Audio:** `sound:agent1-conf-prompt`

┌─────────────────────────────────────────────────────────┐
│ 🎯 Agent1 - Confirmation & Completion │
├─────────────────────────────────────────────────────────┤
│ "Thank you for your confirmation. Booking is now │
│ complete. Details sent to your email. Have a │
│ wonderful trip!" │
│ │
│ 🔊 Status: Playing to MAIN BRIDGE (all participants) │
└─────────────────────────────────────────────────────────┘

text

### System Cleanup

📧 Email sent with booking details
↓
🧹 Cleanup: Destroy bridges, hang up channels
↓
✅ Call complete

text

---

## Flow Summary Table

| Phase | Agent | Duration | OFP Event | Audio File |
|-------|-------|----------|-----------|------------|
| **1** | User | 3s | - | (speech input) |
| **2.1** | Agent1 | 12s | `grantFloor` (invite) | `agent1-finding-flight` |
| **2.2** | Agent2 | 12s | `requestFloor` + `grantFloor` | `agent2-suggest-event` |
| **2.3** | Agent3 | 12s | `requestFloor` + `grantFloor` | `agent3-check-car` |
| **2.4** | Agent1 | 12s | `grantFloor` (invite) | `agent1-final-solution` |
| **3** | User | 5s | - | (confirmation) |
| **4** | Agent1 | 10s | `grantFloor` | `agent1-conf-prompt` |

**Total Time:** ~66 seconds

---

## OFP Protocol Events Timeline

Time Event Actor Type
─────────────────────────────────────────────────────────
00:00 User speech begins User -
00:08 Silence detected (3s) ASR -
00:08 grantFloor(agent1) Convener invite
00:20 yieldFloor() Agent1 -
00:20 requestFloor() Agent2 request
00:21 grantFloor(agent2) Convener approved
00:33 yieldFloor() Agent2 -
00:33 requestFloor() Agent3 request
00:34 grantFloor(agent3) Convener approved
00:46 yieldFloor() Agent3 -
00:46 grantFloor(agent1) Convener invite
00:58 yieldFloor() Agent1 -
01:03 Confirmation keyword User -
01:05 grantFloor(agent1) Convener invite
01:15 yieldFloor() Agent1 -
01:15 Call cleanup System -

text

---

## Key Characteristics

### 1. Sequential Floor Control
Each agent speaks one at a time. No interruptions or overlaps.

### 2. OFP Compliance
All agent transitions follow Open Floor Protocol v1.0.0:
- `grantFloor` - Convener gives permission
- `requestFloor` - Agent asks to speak
- `yieldFloor` - Agent releases floor

### 3. Context Awareness
- Agent2 detected schedule conflict
- Agent3 adapted to Agent2's changes
- Agent1 summarized all modifications

### 4. User-Friendly Confirmation
- Natural keyword detection
- 2-second silence validation
- No rigid menu navigation

---

## Technical Notes

### Bridge Configuration
All agents and user are in the same **Asterisk ConfBridge** (ID: `1234`), ensuring:
- Everyone hears all agents
- Single audio stream
- Synchronized playback

### ASR Isolation
User audio is captured via **isolated snoop bridge** to prevent:
- Echo feedback
- Agent audio interfering with transcription
- False positives in speech detection

### Audio Format
- **Sample Rate:** 8kHz
- **Codec:** SLIN16 (signed linear 16-bit)
- **Channel:** Mono

---

## Related Documentation

- [System Architecture](ARCHITECTURE.md)
- [OFP Protocol Implementation](OFP_PROTOCOL.md)
- [Asterisk Stasis Flow](STASIS_FLOW.md)
- [Complete Call Flow Example](CALL_FLOW_EXAMPLE.md)

---

**Result:** A seamless, intelligent multi-agent conversation that feels natural to the user while following strict protocol compliance. 🎯✨