┌─────────────────────────────────────────────────────────────────┐
│                    FLOOR CONTROL SEQUENCE                       │
└─────────────────────────────────────────────────────────────────┘

PHASE 1: USER QUERY
━━━━━━━━━━━━━━━━━━━━
🎤 User: "I need to book a trip to Denver for Christmas"
    ↓
📝 ASR: Transcription complete after 3s silence
    ↓
🧠 Convener: Launches multi-agent dialogue


PHASE 2: AGENT COLLABORATION (Sequential Floor Control)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

🎯 TURN 1: Agent1 (Flight Specialist) - 12 seconds
   ┌────────────────────────────────────────────────┐
   │ sound:agent1-finding-flight                    │
   │ "Checking flight and hotel availability for    │
   │  Denver, Christmas time, two adults..."        │
   │                                                 │
   │ 🎵 Plays to MAIN BRIDGE (all hear)             │
   └────────────────────────────────────────────────┘
          ↓ Floor released

🎯 TURN 2: Agent2 (Event Specialist) - 12 seconds
   ┌────────────────────────────────────────────────┐
   │ sound:agent2-suggest-event                     │
   │ "Hold on! Denver Christmas Music Festival      │
   │  runs during those days. Suggest extending     │
   │  trip by 2 days to cover entire event..."      │
   │                                                 │
   │ 🎵 Plays to MAIN BRIDGE (all hear)             │
   └────────────────────────────────────────────────┘
          ↓ Floor released

🎯 TURN 3: Agent3 (Car Rental Specialist) - 12 seconds
   ┌────────────────────────────────────────────────┐
   │ sound:agent3-check-car                         │
   │ "Copy that. Adjusting rental car search for    │
   │  updated 7-day period. AWD SUV confirmed..."   │
   │                                                 │
   │ 🎵 Plays to MAIN BRIDGE (all hear)             │
   └────────────────────────────────────────────────┘
          ↓ Floor released

🎯 TURN 4: Agent1 (Final Summary) - 12 seconds
   ┌────────────────────────────────────────────────┐
   │ sound:agent1-final-solution                    │
   │ "AI multi-agent collaboration complete.        │
   │  Booked flights, hotel, festival passes,       │
   │  and SUV - all within budget.                  │
   │  Ready to proceed with booking?"               │
   │                                                 │
   │ 🎵 Plays to MAIN BRIDGE (all hear)             │
   └────────────────────────────────────────────────┘
          ↓ Waiting for confirmation


PHASE 3: USER CONFIRMATION
━━━━━━━━━━━━━━━━━━━━━━━━━━
    ⏸️  Wait 3 seconds (audio finishes)
    ↓
🎤 ASR Active: Listening for keywords
    ↓
🎤 User: "Yes, please. Let's move on."
    ↓
🔍 Keyword detected: "yes", "please"
    ↓
⏱️  Wait 2 seconds silence
    ↓
✅ Confirmation validated


PHASE 4: FINAL MESSAGE
━━━━━━━━━━━━━━━━━━━━━
🎯 Agent1 (Confirmation)
   ┌────────────────────────────────────────────────┐
   │ sound:agent1-conf-prompt                       │
   │ "Thank you for your confirmation. Booking      │
   │  is now complete. Details sent to your email.  │
   │  Have a wonderful trip!"                       │
   │                                                 │
   │ 🎵 Plays to MAIN BRIDGE (all hear)             │
   └────────────────────────────────────────────────┘
