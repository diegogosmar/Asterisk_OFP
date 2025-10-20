```
==========================================
  OFP LLM Mixed: agent1=LLM, agent2/3=stub
==========================================

--- Stopping previous instances ---

--- Activating venv ---

--- Starting Mixed Agents ---
🤖 Starting agent1 with LLM...
🎭 Starting agent2 as stub...
🎭 Starting agent3 as stub...
✅ Agents started

--- Verifying agents (after 3s delay) ---
✅ agent1 (LLM) is healthy
✅ agent2 (stub) is running
✅ agent3 (stub) is running

--- Starting Deepgram ASR ---
🎙️  Deepgram ASR - Listening on UDP 45000 @ 8000Hz
⏳ Waiting for audio...


==========================================
  Starting Convener OFP LLM Mixed
  agent1=LLM (dynamic) | agent2/3=stub
==========================================

2025-10-20 19:55:52,479 [INFO] ================================================================================
2025-10-20 19:55:52,479 [INFO] 🎙️  Convener OFP LLM Mixed - Echo Safe + OFP 1.0.0 JSON Logging
2025-10-20 19:55:52,479 [INFO] ================================================================================
2025-10-20 19:55:52,480 [INFO] [ASR_LISTENER] Listening on port 45001
2025-10-20 19:55:52,481 [INFO] [BRIDGE] Ready, ID=1234
2025-10-20 19:55:52,482 [INFO] [WS] Connected to ARI
2025-10-20 19:55:58,856 [INFO] [STASIS] Start PJSIP/human1-00000003
2025-10-20 19:55:58,858 [INFO] [BRIDGE] Added 1760982958.72 (role: user_default)
2025-10-20 19:55:58,862 [INFO] [SNOOP] ExternalMedia: ASR_EXT_14a2f4f3 (ULAW 8kHz)
2025-10-20 19:55:59,166 [INFO] [SNOOP] ✅ Capturing 1760982958.72 audio (isolated)
2025-10-20 19:55:59,373 [INFO] [SNOOP] Isolated bridge: ASR_SNOOP_14a2f4f3 ↔ ASR_EXT_14a2f4f3 → Deepgram
2025-10-20 19:55:59,374 [INFO] [CONVENER] State: WAITING_FOR_HUMAN (ASR Active)
2025-10-20 19:55:59,376 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:45000-0xffff5c002bd8
2025-10-20 19:55:59,376 [INFO] [STASIS] Start Snoop/1760982958.72-00000003
🎤 Audio detected! Connecting to Deepgram...

✅ Connected to Deepgram

================================================================================
2025-10-20 19:55:59,981 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20000-0xffff5c012998
2025-10-20 19:55:59,983 [INFO] [BRIDGE] Added agent1_1c29d13f (role: ai_agent)
2025-10-20 19:56:00,084 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20002-0xffff5c189038
2025-10-20 19:56:00,086 [INFO] [BRIDGE] Added agent2_e2627194 (role: ai_agent)
2025-10-20 19:56:00,189 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20004-0xffff5c247438
2025-10-20 19:56:00,192 [INFO] [BRIDGE] Added agent3_76385345 (role: ai_agent)
⏳ To your
2025-10-20 19:56:00,873 [INFO] [ASR] Transcript received but ignored due to mute simulation
2025-10-20 19:56:04,860 [INFO] [ASR] Unmuted after welcome message
⏳ Hold on.
2025-10-20 19:56:05,055 [INFO] [ASR] Partial: 'Hold on.'
⏳ Hello. This is Diego
2025-10-20 19:56:06,068 [INFO] [ASR] Partial: 'Hello. This is Diego'
⏳ Hello. This is Diego. I'd like to book a
2025-10-20 19:56:07,082 [INFO] [ASR] Partial: 'Hello. This is Diego. I'd like to book a'
⏳ Hello. This is Diego. I'd like to book a trip to San Francisco
2025-10-20 19:56:08,094 [INFO] [ASR] Partial: 'Hello. This is Diego. I'd like to book a trip to San Francisco'
✅ Hello. This is Diego. I'd like to book a trip to San Francisco next
2025-10-20 19:56:08,638 [INFO] [ASR] Final: 'Hello. This is Diego. I'd like to book a trip to San Francisco next'
⏳ Nextiva. Which
2025-10-20 19:56:09,664 [INFO] [ASR] Partial: 'Nextiva. Which'
✅ year. Which options do you have?
2025-10-20 19:56:10,692 [INFO] [ASR] Final: 'year. Which options do you have?'
2025-10-20 19:56:14,065 [INFO] [ASR] 3 seconds silence detected. Speech ended.
2025-10-20 19:56:14,066 [INFO] [ASR] Full transcript: 'Hello. This is Diego. I'd like to book a trip to San Francisco next year. Which options do you have?'
2025-10-20 19:56:14,066 [INFO] [CONVENER] Starting multi-agent dialogue (LLM mixed mode)
2025-10-20 19:56:14,066 [INFO] [CONVENER] Conversation ID: ad785129-34ec-47be-85cc-d61380842c75
2025-10-20 19:56:14,066 [INFO] [AGENT0] 🎵 Starting 'Please wait' message asynchronously
2025-10-20 19:56:14,071 [INFO] [AGENT0] ▶️  Playback started: agent0_wait_35a2cc
⏳ Please wait
2025-10-20 19:56:15,571 [INFO] 
================================================================================
2025-10-20 19:56:15,571 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-20 19:56:15,571 [INFO] ================================================================================

2025-10-20 19:56:15,571 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-20 19:56:15,872 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-20 19:56:15,872 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 19:56:15,873 [INFO]            {
2025-10-20 19:56:15,873 [INFO]              "openFloor": {
2025-10-20 19:56:15,873 [INFO]                "schema": {
2025-10-20 19:56:15,873 [INFO]                  "version": "1.0.0",
2025-10-20 19:56:15,873 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 19:56:15,873 [INFO]                },
2025-10-20 19:56:15,873 [INFO]                "conversation": {
2025-10-20 19:56:15,873 [INFO]                  "id": "ad785129-34ec-47be-85cc-d61380842c75"
2025-10-20 19:56:15,873 [INFO]                },
2025-10-20 19:56:15,873 [INFO]                "sender": {
2025-10-20 19:56:15,873 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 19:56:15,873 [INFO]                },
2025-10-20 19:56:15,873 [INFO]                "events": [
2025-10-20 19:56:15,873 [INFO]                  {
2025-10-20 19:56:15,873 [INFO]                    "to": "https://agent1.asterisk.local",
2025-10-20 19:56:15,873 [INFO]                    "eventType": "grantFloor",
2025-10-20 19:56:15,873 [INFO]                    "parameters": {
2025-10-20 19:56:15,873 [INFO]                      "reason": "Initial booking request requires flight specialist",
2025-10-20 19:56:15,873 [INFO]                      "duration": 12,
2025-10-20 19:56:15,873 [INFO]                      "context": {
2025-10-20 19:56:15,873 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to book a trip to San Francisco next year. Which options do you have?",
2025-10-20 19:56:15,873 [INFO]                        "timestamp": "2025-10-20T17:56:15Z"
2025-10-20 19:56:15,873 [INFO]                      }
2025-10-20 19:56:15,873 [INFO]                    }
2025-10-20 19:56:15,873 [INFO]                  }
2025-10-20 19:56:15,873 [INFO]                ]
2025-10-20 19:56:15,873 [INFO]              }
2025-10-20 19:56:15,873 [INFO]            }
2025-10-20 19:56:15,884 [WARNING] [OFP_JSON] ⚠️ agent1 responded with 500
⏳ Please wait while we put you
✅ Please wait while we put you through.
2025-10-20 19:56:16,387 [INFO] [AGENT0] ⏹️  Stopped (agent1 ready)
2025-10-20 19:56:16,387 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-20 19:56:16,387 [WARNING] [FLOOR] LLM audio not ready, using fallback
2025-10-20 19:56:28,389 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-20 19:56:28,890 [INFO] 
================================================================================
2025-10-20 19:56:28,890 [INFO] [TURN] Agent: agent2 | Type: stub | Mode: request
2025-10-20 19:56:28,890 [INFO] ================================================================================

2025-10-20 19:56:28,890 [INFO] [OFP_JSON] 📥 Received requestFloor from agent2
2025-10-20 19:56:28,891 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 19:56:28,891 [INFO]            {
2025-10-20 19:56:28,891 [INFO]              "openFloor": {
2025-10-20 19:56:28,891 [INFO]                "schema": {
2025-10-20 19:56:28,891 [INFO]                  "version": "1.0.0",
2025-10-20 19:56:28,892 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 19:56:28,892 [INFO]                },
2025-10-20 19:56:28,892 [INFO]                "conversation": {
2025-10-20 19:56:28,892 [INFO]                  "id": "ad785129-34ec-47be-85cc-d61380842c75"
2025-10-20 19:56:28,892 [INFO]                },
2025-10-20 19:56:28,892 [INFO]                "sender": {
2025-10-20 19:56:28,892 [INFO]                  "from": "https://agent2.asterisk.local"
2025-10-20 19:56:28,892 [INFO]                },
2025-10-20 19:56:28,892 [INFO]                "events": [
2025-10-20 19:56:28,893 [INFO]                  {
2025-10-20 19:56:28,893 [INFO]                    "to": "https://convener.asterisk.local",
2025-10-20 19:56:28,893 [INFO]                    "eventType": "requestFloor",
2025-10-20 19:56:28,893 [INFO]                    "parameters": {
2025-10-20 19:56:28,893 [INFO]                      "requestReason": "Detected schedule conflict with Christmas festival",
2025-10-20 19:56:28,893 [INFO]                      "priority": "normal"
2025-10-20 19:56:28,893 [INFO]                    }
2025-10-20 19:56:28,893 [INFO]                  }
2025-10-20 19:56:28,893 [INFO]                ]
2025-10-20 19:56:28,893 [INFO]              }
2025-10-20 19:56:28,893 [INFO]            }
2025-10-20 19:56:29,393 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent2...
2025-10-20 19:56:29,794 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent2
2025-10-20 19:56:29,794 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 19:56:29,795 [INFO]            {
2025-10-20 19:56:29,795 [INFO]              "openFloor": {
2025-10-20 19:56:29,795 [INFO]                "schema": {
2025-10-20 19:56:29,795 [INFO]                  "version": "1.0.0",
2025-10-20 19:56:29,795 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 19:56:29,795 [INFO]                },
2025-10-20 19:56:29,795 [INFO]                "conversation": {
2025-10-20 19:56:29,795 [INFO]                  "id": "ad785129-34ec-47be-85cc-d61380842c75"
2025-10-20 19:56:29,795 [INFO]                },
2025-10-20 19:56:29,795 [INFO]                "sender": {
2025-10-20 19:56:29,795 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 19:56:29,795 [INFO]                },
2025-10-20 19:56:29,795 [INFO]                "events": [
2025-10-20 19:56:29,795 [INFO]                  {
2025-10-20 19:56:29,795 [INFO]                    "to": "https://agent2.asterisk.local",
2025-10-20 19:56:29,795 [INFO]                    "eventType": "grantFloor",
2025-10-20 19:56:29,795 [INFO]                    "parameters": {
2025-10-20 19:56:29,796 [INFO]                      "reason": "Request approved: Detected schedule conflict with Christmas festival",
2025-10-20 19:56:29,796 [INFO]                      "duration": 12,
2025-10-20 19:56:29,796 [INFO]                      "context": {
2025-10-20 19:56:29,796 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to book a trip to San Francisco next year. Which options do you have?",
2025-10-20 19:56:29,796 [INFO]                        "timestamp": "2025-10-20T17:56:29Z"
2025-10-20 19:56:29,796 [INFO]                      }
2025-10-20 19:56:29,796 [INFO]                    }
2025-10-20 19:56:29,796 [INFO]                  }
2025-10-20 19:56:29,796 [INFO]                ]
2025-10-20 19:56:29,796 [INFO]              }
2025-10-20 19:56:29,796 [INFO]            }
2025-10-20 19:56:29,805 [WARNING] [OFP_JSON] ⚠️ agent2 responded with 500
2025-10-20 19:56:30,306 [INFO] [FLOOR] 🎤 agent2 (stub) takes floor: sound:agent2-suggest-event
⏳ Suggest extending
2025-10-20 19:56:42,310 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent2
2025-10-20 19:56:42,811 [INFO] 
================================================================================
2025-10-20 19:56:42,811 [INFO] [TURN] Agent: agent3 | Type: stub | Mode: request
2025-10-20 19:56:42,811 [INFO] ================================================================================

2025-10-20 19:56:42,812 [INFO] [OFP_JSON] 📥 Received requestFloor from agent3
2025-10-20 19:56:42,812 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 19:56:42,812 [INFO]            {
2025-10-20 19:56:42,812 [INFO]              "openFloor": {
2025-10-20 19:56:42,812 [INFO]                "schema": {
2025-10-20 19:56:42,812 [INFO]                  "version": "1.0.0",
2025-10-20 19:56:42,812 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 19:56:42,813 [INFO]                },
2025-10-20 19:56:42,813 [INFO]                "conversation": {
2025-10-20 19:56:42,813 [INFO]                  "id": "ad785129-34ec-47be-85cc-d61380842c75"
2025-10-20 19:56:42,813 [INFO]                },
2025-10-20 19:56:42,813 [INFO]                "sender": {
2025-10-20 19:56:42,813 [INFO]                  "from": "https://agent3.asterisk.local"
2025-10-20 19:56:42,813 [INFO]                },
2025-10-20 19:56:42,813 [INFO]                "events": [
2025-10-20 19:56:42,814 [INFO]                  {
2025-10-20 19:56:42,814 [INFO]                    "to": "https://convener.asterisk.local",
2025-10-20 19:56:42,814 [INFO]                    "eventType": "requestFloor",
2025-10-20 19:56:42,814 [INFO]                    "parameters": {
2025-10-20 19:56:42,814 [INFO]                      "requestReason": "Trip duration changed, need to adjust car rental",
2025-10-20 19:56:42,814 [INFO]                      "priority": "normal"
2025-10-20 19:56:42,814 [INFO]                    }
2025-10-20 19:56:42,814 [INFO]                  }
2025-10-20 19:56:42,814 [INFO]                ]
2025-10-20 19:56:42,814 [INFO]              }
2025-10-20 19:56:42,815 [INFO]            }
2025-10-20 19:56:43,316 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent3...
2025-10-20 19:56:43,717 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent3
2025-10-20 19:56:43,717 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 19:56:43,717 [INFO]            {
2025-10-20 19:56:43,717 [INFO]              "openFloor": {
2025-10-20 19:56:43,717 [INFO]                "schema": {
2025-10-20 19:56:43,717 [INFO]                  "version": "1.0.0",
2025-10-20 19:56:43,717 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 19:56:43,718 [INFO]                },
2025-10-20 19:56:43,718 [INFO]                "conversation": {
2025-10-20 19:56:43,718 [INFO]                  "id": "ad785129-34ec-47be-85cc-d61380842c75"
2025-10-20 19:56:43,718 [INFO]                },
2025-10-20 19:56:43,718 [INFO]                "sender": {
2025-10-20 19:56:43,718 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 19:56:43,718 [INFO]                },
2025-10-20 19:56:43,718 [INFO]                "events": [
2025-10-20 19:56:43,718 [INFO]                  {
2025-10-20 19:56:43,718 [INFO]                    "to": "https://agent3.asterisk.local",
2025-10-20 19:56:43,718 [INFO]                    "eventType": "grantFloor",
2025-10-20 19:56:43,719 [INFO]                    "parameters": {
2025-10-20 19:56:43,719 [INFO]                      "reason": "Request approved: Trip duration changed, need to adjust car rental",
2025-10-20 19:56:43,719 [INFO]                      "duration": 12,
2025-10-20 19:56:43,719 [INFO]                      "context": {
2025-10-20 19:56:43,719 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to book a trip to San Francisco next year. Which options do you have?",
2025-10-20 19:56:43,719 [INFO]                        "timestamp": "2025-10-20T17:56:43Z"
2025-10-20 19:56:43,719 [INFO]                      }
2025-10-20 19:56:43,719 [INFO]                    }
2025-10-20 19:56:43,720 [INFO]                  }
2025-10-20 19:56:43,720 [INFO]                ]
2025-10-20 19:56:43,720 [INFO]              }
2025-10-20 19:56:43,720 [INFO]            }
2025-10-20 19:56:43,728 [WARNING] [OFP_JSON] ⚠️ agent3 responded with 500
2025-10-20 19:56:44,229 [INFO] [FLOOR] 🎤 agent3 (stub) takes floor: sound:agent3-check-car
2025-10-20 19:56:56,237 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent3
2025-10-20 19:56:56,738 [INFO] 
================================================================================
2025-10-20 19:56:56,738 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-20 19:56:56,738 [INFO] ================================================================================

2025-10-20 19:56:56,738 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-20 19:56:57,039 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-20 19:56:57,039 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 19:56:57,040 [INFO]            {
2025-10-20 19:56:57,040 [INFO]              "openFloor": {
2025-10-20 19:56:57,040 [INFO]                "schema": {
2025-10-20 19:56:57,040 [INFO]                  "version": "1.0.0",
2025-10-20 19:56:57,040 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 19:56:57,040 [INFO]                },
2025-10-20 19:56:57,040 [INFO]                "conversation": {
2025-10-20 19:56:57,040 [INFO]                  "id": "ad785129-34ec-47be-85cc-d61380842c75"
2025-10-20 19:56:57,040 [INFO]                },
2025-10-20 19:56:57,040 [INFO]                "sender": {
2025-10-20 19:56:57,040 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 19:56:57,040 [INFO]                },
2025-10-20 19:56:57,040 [INFO]                "events": [
2025-10-20 19:56:57,040 [INFO]                  {
2025-10-20 19:56:57,040 [INFO]                    "to": "https://agent1.asterisk.local",
2025-10-20 19:56:57,040 [INFO]                    "eventType": "grantFloor",
2025-10-20 19:56:57,040 [INFO]                    "parameters": {
2025-10-20 19:56:57,040 [INFO]                      "reason": "Provide final booking summary",
2025-10-20 19:56:57,040 [INFO]                      "duration": 12,
2025-10-20 19:56:57,041 [INFO]                      "context": {
2025-10-20 19:56:57,041 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to book a trip to San Francisco next year. Which options do you have?",
2025-10-20 19:56:57,041 [INFO]                        "timestamp": "2025-10-20T17:56:57Z"
2025-10-20 19:56:57,041 [INFO]                      }
2025-10-20 19:56:57,041 [INFO]                    }
2025-10-20 19:56:57,041 [INFO]                  }
2025-10-20 19:56:57,041 [INFO]                ]
2025-10-20 19:56:57,041 [INFO]              }
2025-10-20 19:56:57,041 [INFO]            }
2025-10-20 19:56:57,048 [WARNING] [OFP_JSON] ⚠️ agent1 responded with 500
2025-10-20 19:56:57,549 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-20 19:56:57,549 [WARNING] [FLOOR] LLM audio not ready, using fallback
⏳ Okay.
2025-10-20 19:57:09,555 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-20 19:57:10,055 [INFO] [CONFIRM] Waiting for user confirmation...
2025-10-20 19:57:13,057 [INFO] [CONFIRM] 🎤 Listening for 'yes', 'ok', or similar + silence...
⏳ Yeah.
2025-10-20 19:57:16,292 [INFO] [ASR] Partial: 'Yeah.'
⏳ Yes, please. Let's
2025-10-20 19:57:17,315 [INFO] [ASR] Partial: 'Yes, please. Let's'
✅ Yes, please. Let's move on.
2025-10-20 19:57:18,018 [INFO] [ASR] Final: 'Yes, please. Let's move on.'
2025-10-20 19:57:18,063 [INFO] [CONFIRM] 🟢 Keyword detected: 'yes, please. let's move on.'. Waiting for silence...
2025-10-20 19:57:20,065 [INFO] [CONFIRM] ✅ Confirmed after 2s silence: 'yes, please. let's move on.'
2025-10-20 19:57:20,065 [INFO] [CONFIRM] Playing final message
2025-10-20 19:57:30,073 [INFO] [CONVENER] Complete. Cleanup.
2025-10-20 19:57:30,073 [INFO] [CLEANUP] Starting...
2025-10-20 19:57:30,077 [INFO] [CLEANUP] Destroyed snoop bridge
2025-10-20 19:57:30,079 [INFO] [CLEANUP] Hung up 1760982958.72
2025-10-20 19:57:30,086 [INFO] [STASIS] End PJSIP/human1-00000003
2025-10-20 19:57:30,087 [INFO] [CLEANUP] Hung up ASR_EXT_14a2f4f3
2025-10-20 19:57:30,088 [INFO] [STASIS] End UnicastRTP/127.0.0.1:45000-0xffff5c002bd8
2025-10-20 19:57:30,089 [INFO] [STASIS] End Snoop/1760982958.72-00000003
2025-10-20 19:57:30,091 [INFO] [CLEANUP] Hung up agent1_1c29d13f
2025-10-20 19:57:30,093 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20000-0xffff5c012998
2025-10-20 19:57:30,093 [INFO] [CLEANUP] Hung up agent2_e2627194
2025-10-20 19:57:30,095 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20002-0xffff5c189038
2025-10-20 19:57:30,096 [INFO] [CLEANUP] Hung up agent3_76385345
2025-10-20 19:57:30,096 [INFO] [CLEANUP] Complete
2025-10-20 19:57:30,097 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20004-0xffff5c247438
```
```