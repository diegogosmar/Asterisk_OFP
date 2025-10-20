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

2025-10-20 18:23:48,288 [INFO] ================================================================================
2025-10-20 18:23:48,288 [INFO] 🎙️  Convener OFP LLM Mixed - Echo Safe + OFP JSON Logging
2025-10-20 18:23:48,288 [INFO] ================================================================================
2025-10-20 18:23:48,288 [INFO] [ASR_LISTENER] Listening on port 45001
2025-10-20 18:23:48,289 [INFO] [BRIDGE] Ready, ID=1234
2025-10-20 18:23:48,290 [INFO] [WS] Connected to ARI
2025-10-20 18:23:55,266 [INFO] [STASIS] Start PJSIP/human1-00000002
2025-10-20 18:23:55,269 [INFO] [BRIDGE] Added 1760977435.50 (role: user_default)
2025-10-20 18:23:55,274 [INFO] [SNOOP] ExternalMedia: ASR_EXT_f22d6704 (ULAW 8kHz)
2025-10-20 18:23:55,578 [INFO] [SNOOP] ✅ Capturing 1760977435.50 audio (isolated)
2025-10-20 18:23:55,787 [INFO] [SNOOP] Isolated bridge: ASR_SNOOP_f22d6704 ↔ ASR_EXT_f22d6704 → Deepgram
2025-10-20 18:23:55,788 [INFO] [CONVENER] State: WAITING_FOR_HUMAN (ASR Active)
2025-10-20 18:23:55,790 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:45000-0xffff2c004378
2025-10-20 18:23:55,790 [INFO] [STASIS] Start Snoop/1760977435.50-00000002
🎤 Audio detected! Connecting to Deepgram...

✅ Connected to Deepgram

================================================================================
2025-10-20 18:23:56,397 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20000-0xffff2c0ca778
2025-10-20 18:23:56,400 [INFO] [BRIDGE] Added agent1_fd463bd1 (role: ai_agent)
2025-10-20 18:23:56,503 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20002-0xffff2c186d08
2025-10-20 18:23:56,507 [INFO] [BRIDGE] Added agent2_32a0dec6 (role: ai_agent)
2025-10-20 18:23:56,610 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20004-0xffff2c246198
2025-10-20 18:23:56,612 [INFO] [BRIDGE] Added agent3_887bfcaa (role: ai_agent)
⏳ Welcome to your
2025-10-20 18:23:57,337 [INFO] [ASR] Transcript received but ignored due to mute simulation
⏳ Welcome to your
2025-10-20 18:23:58,037 [INFO] [ASR] Transcript received but ignored due to mute simulation
2025-10-20 18:24:01,272 [INFO] [ASR] Unmuted after welcome message
⏳ Hello.
2025-10-20 18:24:01,522 [INFO] [ASR] Partial: 'Hello.'
⏳ Hello. This is Diego.
2025-10-20 18:24:02,558 [INFO] [ASR] Partial: 'Hello. This is Diego.'
⏳ Hello. This is Diego. I'd like to book
2025-10-20 18:24:03,545 [INFO] [ASR] Partial: 'Hello. This is Diego. I'd like to book'
⏳ Hello. This is Diego. I'd like to book a trip to London
2025-10-20 18:24:04,561 [INFO] [ASR] Partial: 'Hello. This is Diego. I'd like to book a trip to London'
✅ Hello. This is Diego. I'd like to book a
2025-10-20 18:24:05,553 [INFO] [ASR] Final: 'Hello. This is Diego. I'd like to book a'
⏳ trip to London next to San
2025-10-20 18:24:05,584 [INFO] [ASR] Partial: 'trip to London next to San'
⏳ trip to London next summer. Which option
2025-10-20 18:24:06,572 [INFO] [ASR] Partial: 'trip to London next summer. Which option'
✅ trip to London next summer. Which options you have?
2025-10-20 18:24:07,270 [INFO] [ASR] Final: 'trip to London next summer. Which options you have?'
2025-10-20 18:24:10,531 [INFO] [ASR] 3 seconds silence detected. Speech ended.
2025-10-20 18:24:10,532 [INFO] [ASR] Full transcript: 'Hello. This is Diego. I'd like to book a trip to London next summer. Which options you have?'
2025-10-20 18:24:10,532 [INFO] [CONVENER] Starting multi-agent dialogue (LLM mixed mode)
2025-10-20 18:24:10,532 [INFO] [CONVENER] Conversation ID: dfd2c9d4-6aac-4d34-ac67-9a9f262a3515
2025-10-20 18:24:10,533 [INFO] [AGENT0] 🎵 Starting 'Please wait' message asynchronously
2025-10-20 18:24:10,539 [INFO] [AGENT0] ▶️  Playback started: agent0_wait_ee9191
⏳ Yeah.
2025-10-20 18:24:12,040 [INFO] 
================================================================================
2025-10-20 18:24:12,040 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-20 18:24:12,040 [INFO] ================================================================================

2025-10-20 18:24:12,041 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
✅ Please wait while we
2025-10-20 18:24:12,341 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-20 18:24:12,341 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 18:24:12,342 [INFO]            {
2025-10-20 18:24:12,342 [INFO]              "ovon": {
2025-10-20 18:24:12,342 [INFO]                "schema": {
2025-10-20 18:24:12,342 [INFO]                  "version": "0.9.2",
2025-10-20 18:24:12,342 [INFO]                  "url": "https://openvoicenetwork.org/schema/dialog-envelope.json"
2025-10-20 18:24:12,342 [INFO]                },
2025-10-20 18:24:12,342 [INFO]                "conversation": {
2025-10-20 18:24:12,342 [INFO]                  "id": "dfd2c9d4-6aac-4d34-ac67-9a9f262a3515"
2025-10-20 18:24:12,342 [INFO]                },
2025-10-20 18:24:12,342 [INFO]                "sender": {
2025-10-20 18:24:12,343 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 18:24:12,343 [INFO]                },
2025-10-20 18:24:12,343 [INFO]                "events": [
2025-10-20 18:24:12,343 [INFO]                  {
2025-10-20 18:24:12,343 [INFO]                    "to": "https://agent1.asterisk.local",
2025-10-20 18:24:12,343 [INFO]                    "eventType": "grantFloor",
2025-10-20 18:24:12,343 [INFO]                    "parameters": {
2025-10-20 18:24:12,343 [INFO]                      "reason": "Initial booking request requires flight specialist",
2025-10-20 18:24:12,343 [INFO]                      "duration": 12,
2025-10-20 18:24:12,343 [INFO]                      "context": {
2025-10-20 18:24:12,344 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to book a trip to London next summer. Which options you have?",
2025-10-20 18:24:12,344 [INFO]                        "timestamp": "2025-10-20T16:24:12Z"
2025-10-20 18:24:12,344 [INFO]                      }
2025-10-20 18:24:12,344 [INFO]                    }
2025-10-20 18:24:12,344 [INFO]                  }
2025-10-20 18:24:12,344 [INFO]                ]
2025-10-20 18:24:12,344 [INFO]              }
2025-10-20 18:24:12,344 [INFO]            }
2025-10-20 18:24:14,957 [INFO] [OFP_JSON] ✅ agent1 acknowledged grantFloor
2025-10-20 18:24:15,460 [INFO] [AGENT0] ⏹️  Stopped (agent1 ready)
2025-10-20 18:24:15,460 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-20 18:24:15,460 [INFO] [FLOOR] 🎤 Playing LLM audio: agent1_dynamic_15cf4db3
2025-10-20 18:24:15,462 [INFO] [PLAY] 🎵 Started playback: agent1_llm_799c6b
2025-10-20 18:24:15,765 [INFO] [PLAY] ✅ Playback completed in 0.3s
2025-10-20 18:24:15,766 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-20 18:24:16,266 [INFO] 
================================================================================
2025-10-20 18:24:16,267 [INFO] [TURN] Agent: agent2 | Type: stub | Mode: request
2025-10-20 18:24:16,267 [INFO] ================================================================================

2025-10-20 18:24:16,267 [INFO] [OFP_JSON] 📥 Received requestFloor from agent2
2025-10-20 18:24:16,267 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 18:24:16,267 [INFO]            {
2025-10-20 18:24:16,267 [INFO]              "ovon": {
2025-10-20 18:24:16,267 [INFO]                "schema": {
2025-10-20 18:24:16,268 [INFO]                  "version": "0.9.2",
2025-10-20 18:24:16,268 [INFO]                  "url": "https://openvoicenetwork.org/schema/dialog-envelope.json"
2025-10-20 18:24:16,268 [INFO]                },
2025-10-20 18:24:16,268 [INFO]                "conversation": {
2025-10-20 18:24:16,268 [INFO]                  "id": "dfd2c9d4-6aac-4d34-ac67-9a9f262a3515"
2025-10-20 18:24:16,268 [INFO]                },
2025-10-20 18:24:16,269 [INFO]                "sender": {
2025-10-20 18:24:16,269 [INFO]                  "from": "https://agent2.asterisk.local"
2025-10-20 18:24:16,269 [INFO]                },
2025-10-20 18:24:16,269 [INFO]                "events": [
2025-10-20 18:24:16,269 [INFO]                  {
2025-10-20 18:24:16,269 [INFO]                    "to": "https://convener.asterisk.local",
2025-10-20 18:24:16,269 [INFO]                    "eventType": "requestFloor",
2025-10-20 18:24:16,269 [INFO]                    "parameters": {
2025-10-20 18:24:16,269 [INFO]                      "request_reason": "Detected schedule conflict with Christmas festival",
2025-10-20 18:24:16,269 [INFO]                      "priority": "normal"
2025-10-20 18:24:16,270 [INFO]                    }
2025-10-20 18:24:16,270 [INFO]                  }
2025-10-20 18:24:16,270 [INFO]                ]
2025-10-20 18:24:16,270 [INFO]              }
2025-10-20 18:24:16,270 [INFO]            }
2025-10-20 18:24:16,771 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent2...
2025-10-20 18:24:17,172 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent2
2025-10-20 18:24:17,173 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 18:24:17,173 [INFO]            {
2025-10-20 18:24:17,173 [INFO]              "ovon": {
2025-10-20 18:24:17,173 [INFO]                "schema": {
2025-10-20 18:24:17,173 [INFO]                  "version": "0.9.2",
2025-10-20 18:24:17,173 [INFO]                  "url": "https://openvoicenetwork.org/schema/dialog-envelope.json"
2025-10-20 18:24:17,173 [INFO]                },
2025-10-20 18:24:17,173 [INFO]                "conversation": {
2025-10-20 18:24:17,174 [INFO]                  "id": "dfd2c9d4-6aac-4d34-ac67-9a9f262a3515"
2025-10-20 18:24:17,174 [INFO]                },
2025-10-20 18:24:17,174 [INFO]                "sender": {
2025-10-20 18:24:17,174 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 18:24:17,174 [INFO]                },
2025-10-20 18:24:17,174 [INFO]                "events": [
2025-10-20 18:24:17,174 [INFO]                  {
2025-10-20 18:24:17,174 [INFO]                    "to": "https://agent2.asterisk.local",
2025-10-20 18:24:17,174 [INFO]                    "eventType": "grantFloor",
2025-10-20 18:24:17,174 [INFO]                    "parameters": {
2025-10-20 18:24:17,175 [INFO]                      "reason": "Request approved: Detected schedule conflict with Christmas festival",
2025-10-20 18:24:17,175 [INFO]                      "duration": 12,
2025-10-20 18:24:17,175 [INFO]                      "context": {
2025-10-20 18:24:17,175 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to book a trip to London next summer. Which options you have?",
2025-10-20 18:24:17,175 [INFO]                        "timestamp": "2025-10-20T16:24:17Z"
2025-10-20 18:24:17,175 [INFO]                      }
2025-10-20 18:24:17,175 [INFO]                    }
2025-10-20 18:24:17,175 [INFO]                  }
2025-10-20 18:24:17,176 [INFO]                ]
2025-10-20 18:24:17,176 [INFO]              }
2025-10-20 18:24:17,176 [INFO]            }
2025-10-20 18:24:17,182 [INFO] [OFP_JSON] ✅ agent2 acknowledged grantFloor
2025-10-20 18:24:17,683 [INFO] [FLOOR] 🎤 agent2 (stub) takes floor: sound:agent2-suggest-event
2025-10-20 18:24:29,686 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent2
2025-10-20 18:24:30,187 [INFO] 
================================================================================
2025-10-20 18:24:30,187 [INFO] [TURN] Agent: agent3 | Type: stub | Mode: request
2025-10-20 18:24:30,187 [INFO] ================================================================================

2025-10-20 18:24:30,187 [INFO] [OFP_JSON] 📥 Received requestFloor from agent3
2025-10-20 18:24:30,187 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 18:24:30,187 [INFO]            {
2025-10-20 18:24:30,187 [INFO]              "ovon": {
2025-10-20 18:24:30,188 [INFO]                "schema": {
2025-10-20 18:24:30,188 [INFO]                  "version": "0.9.2",
2025-10-20 18:24:30,188 [INFO]                  "url": "https://openvoicenetwork.org/schema/dialog-envelope.json"
2025-10-20 18:24:30,188 [INFO]                },
2025-10-20 18:24:30,188 [INFO]                "conversation": {
2025-10-20 18:24:30,188 [INFO]                  "id": "dfd2c9d4-6aac-4d34-ac67-9a9f262a3515"
2025-10-20 18:24:30,188 [INFO]                },
2025-10-20 18:24:30,188 [INFO]                "sender": {
2025-10-20 18:24:30,188 [INFO]                  "from": "https://agent3.asterisk.local"
2025-10-20 18:24:30,188 [INFO]                },
2025-10-20 18:24:30,189 [INFO]                "events": [
2025-10-20 18:24:30,189 [INFO]                  {
2025-10-20 18:24:30,189 [INFO]                    "to": "https://convener.asterisk.local",
2025-10-20 18:24:30,189 [INFO]                    "eventType": "requestFloor",
2025-10-20 18:24:30,189 [INFO]                    "parameters": {
2025-10-20 18:24:30,189 [INFO]                      "request_reason": "Trip duration changed, need to adjust car rental",
2025-10-20 18:24:30,189 [INFO]                      "priority": "normal"
2025-10-20 18:24:30,190 [INFO]                    }
2025-10-20 18:24:30,190 [INFO]                  }
2025-10-20 18:24:30,190 [INFO]                ]
2025-10-20 18:24:30,190 [INFO]              }
2025-10-20 18:24:30,190 [INFO]            }
2025-10-20 18:24:30,691 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent3...
2025-10-20 18:24:31,092 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent3
2025-10-20 18:24:31,092 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 18:24:31,093 [INFO]            {
2025-10-20 18:24:31,093 [INFO]              "ovon": {
2025-10-20 18:24:31,093 [INFO]                "schema": {
2025-10-20 18:24:31,093 [INFO]                  "version": "0.9.2",
2025-10-20 18:24:31,093 [INFO]                  "url": "https://openvoicenetwork.org/schema/dialog-envelope.json"
2025-10-20 18:24:31,093 [INFO]                },
2025-10-20 18:24:31,093 [INFO]                "conversation": {
2025-10-20 18:24:31,093 [INFO]                  "id": "dfd2c9d4-6aac-4d34-ac67-9a9f262a3515"
2025-10-20 18:24:31,093 [INFO]                },
2025-10-20 18:24:31,093 [INFO]                "sender": {
2025-10-20 18:24:31,093 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 18:24:31,094 [INFO]                },
2025-10-20 18:24:31,094 [INFO]                "events": [
2025-10-20 18:24:31,094 [INFO]                  {
2025-10-20 18:24:31,094 [INFO]                    "to": "https://agent3.asterisk.local",
2025-10-20 18:24:31,094 [INFO]                    "eventType": "grantFloor",
2025-10-20 18:24:31,094 [INFO]                    "parameters": {
2025-10-20 18:24:31,094 [INFO]                      "reason": "Request approved: Trip duration changed, need to adjust car rental",
2025-10-20 18:24:31,094 [INFO]                      "duration": 12,
2025-10-20 18:24:31,094 [INFO]                      "context": {
2025-10-20 18:24:31,094 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to book a trip to London next summer. Which options you have?",
2025-10-20 18:24:31,094 [INFO]                        "timestamp": "2025-10-20T16:24:31Z"
2025-10-20 18:24:31,094 [INFO]                      }
2025-10-20 18:24:31,094 [INFO]                    }
2025-10-20 18:24:31,095 [INFO]                  }
2025-10-20 18:24:31,095 [INFO]                ]
2025-10-20 18:24:31,095 [INFO]              }
2025-10-20 18:24:31,095 [INFO]            }
2025-10-20 18:24:31,105 [INFO] [OFP_JSON] ✅ agent3 acknowledged grantFloor
2025-10-20 18:24:31,605 [INFO] [FLOOR] 🎤 agent3 (stub) takes floor: sound:agent3-check-car
2025-10-20 18:24:43,610 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent3
2025-10-20 18:24:44,111 [INFO] 
================================================================================
2025-10-20 18:24:44,112 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-20 18:24:44,112 [INFO] ================================================================================

2025-10-20 18:24:44,112 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-20 18:24:44,413 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-20 18:24:44,413 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 18:24:44,413 [INFO]            {
2025-10-20 18:24:44,413 [INFO]              "ovon": {
2025-10-20 18:24:44,413 [INFO]                "schema": {
2025-10-20 18:24:44,413 [INFO]                  "version": "0.9.2",
2025-10-20 18:24:44,413 [INFO]                  "url": "https://openvoicenetwork.org/schema/dialog-envelope.json"
2025-10-20 18:24:44,414 [INFO]                },
2025-10-20 18:24:44,414 [INFO]                "conversation": {
2025-10-20 18:24:44,414 [INFO]                  "id": "dfd2c9d4-6aac-4d34-ac67-9a9f262a3515"
2025-10-20 18:24:44,414 [INFO]                },
2025-10-20 18:24:44,414 [INFO]                "sender": {
2025-10-20 18:24:44,414 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 18:24:44,414 [INFO]                },
2025-10-20 18:24:44,414 [INFO]                "events": [
2025-10-20 18:24:44,414 [INFO]                  {
2025-10-20 18:24:44,414 [INFO]                    "to": "https://agent1.asterisk.local",
2025-10-20 18:24:44,414 [INFO]                    "eventType": "grantFloor",
2025-10-20 18:24:44,414 [INFO]                    "parameters": {
2025-10-20 18:24:44,414 [INFO]                      "reason": "Provide final booking summary",
2025-10-20 18:24:44,415 [INFO]                      "duration": 12,
2025-10-20 18:24:44,415 [INFO]                      "context": {
2025-10-20 18:24:44,416 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to book a trip to London next summer. Which options you have?",
2025-10-20 18:24:44,416 [INFO]                        "timestamp": "2025-10-20T16:24:44Z"
2025-10-20 18:24:44,416 [INFO]                      }
2025-10-20 18:24:44,416 [INFO]                    }
2025-10-20 18:24:44,416 [INFO]                  }
2025-10-20 18:24:44,417 [INFO]                ]
2025-10-20 18:24:44,417 [INFO]              }
2025-10-20 18:24:44,417 [INFO]            }
2025-10-20 18:24:48,280 [INFO] [OFP_JSON] ✅ agent1 acknowledged grantFloor
2025-10-20 18:24:48,781 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-20 18:24:48,781 [INFO] [FLOOR] 🎤 Playing LLM audio: agent1_dynamic_bdfde23a
2025-10-20 18:24:48,790 [INFO] [PLAY] 🎵 Started playback: agent1_llm_2097af
2025-10-20 18:24:49,093 [INFO] [PLAY] ✅ Playback completed in 0.3s
2025-10-20 18:24:49,094 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-20 18:24:49,594 [INFO] [CONFIRM] Waiting for user confirmation...
2025-10-20 18:24:52,595 [INFO] [CONFIRM] 🎤 Listening for 'yes', 'ok', or similar + silence...
⏳ Yes, please.
2025-10-20 18:24:59,142 [INFO] [ASR] Partial: 'Yes, please.'
⏳ Yes, please. Let's go on.
2025-10-20 18:25:00,111 [INFO] [ASR] Partial: 'Yes, please. Let's go on.'
✅ Yes, please. Let's go on.
2025-10-20 18:25:00,383 [INFO] [ASR] Final: 'Yes, please. Let's go on.'
2025-10-20 18:25:00,603 [INFO] [CONFIRM] 🟢 Keyword detected: 'yes, please. let's go on.'. Waiting for silence...
2025-10-20 18:25:02,605 [INFO] [CONFIRM] ✅ Confirmed after 2s silence: 'yes, please. let's go on.'
2025-10-20 18:25:02,606 [INFO] [CONFIRM] Playing final message
⏳ Your email.
✅ Your email.
2025-10-20 18:25:12,611 [INFO] [CONVENER] Complete. Cleanup.
2025-10-20 18:25:12,611 [INFO] [CLEANUP] Starting...
2025-10-20 18:25:12,615 [INFO] [CLEANUP] Destroyed snoop bridge
2025-10-20 18:25:12,619 [INFO] [CLEANUP] Hung up 1760977435.50
2025-10-20 18:25:12,622 [INFO] [STASIS] End PJSIP/human1-00000002
2025-10-20 18:25:12,623 [INFO] [STASIS] End UnicastRTP/127.0.0.1:45000-0xffff2c004378
2025-10-20 18:25:12,625 [INFO] [CLEANUP] Hung up ASR_EXT_f22d6704
2025-10-20 18:25:12,626 [INFO] [CLEANUP] Hung up ASR_SNOOP_f22d6704
2025-10-20 18:25:12,628 [INFO] [CLEANUP] Hung up agent1_fd463bd1
2025-10-20 18:25:12,630 [INFO] [STASIS] End Snoop/1760977435.50-00000002
2025-10-20 18:25:12,631 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20000-0xffff2c0ca778
2025-10-20 18:25:12,632 [INFO] [CLEANUP] Hung up agent2_32a0dec6
2025-10-20 18:25:12,633 [INFO] [CLEANUP] Hung up agent3_887bfcaa
2025-10-20 18:25:12,633 [INFO] [CLEANUP] Complete
2025-10-20 18:25:12,634 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20002-0xffff2c186d08
2025-10-20 18:25:12,636 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20004-0xffff2c246198
```
```