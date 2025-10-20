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
✅ agent2 (stub) is healthy
✅ agent3 (stub) is healthy

--- Starting Deepgram ASR ---
🎙️  Deepgram ASR - Listening on UDP 45000 @ 8000Hz
⏳ Waiting for audio...


==========================================
  Starting Convener OFP LLM Mixed
  agent1=LLM (dynamic) | agent2/3=stub
==========================================

2025-10-20 20:56:30,190 [INFO] ================================================================================
2025-10-20 20:56:30,190 [INFO] 🎙️  Convener OFP LLM Mixed - Echo Safe + OFP 1.0.0 JSON Logging
2025-10-20 20:56:30,191 [INFO] ================================================================================
2025-10-20 20:56:30,191 [INFO] [ASR_LISTENER] Listening on port 45001
2025-10-20 20:56:30,192 [INFO] [BRIDGE] Ready, ID=1234
2025-10-20 20:56:30,192 [INFO] [WS] Connected to ARI
2025-10-20 20:56:33,077 [INFO] [STASIS] Start PJSIP/human1-00000007
2025-10-20 20:56:33,079 [INFO] [BRIDGE] Added 1760986593.164 (role: user_default)
2025-10-20 20:56:33,083 [INFO] [SNOOP] ExternalMedia: ASR_EXT_5a3e360a (ULAW 8kHz)
2025-10-20 20:56:33,387 [INFO] [SNOOP] ✅ Capturing 1760986593.164 audio (isolated)
2025-10-20 20:56:33,597 [INFO] [SNOOP] Isolated bridge: ASR_SNOOP_5a3e360a ↔ ASR_EXT_5a3e360a → Deepgram
2025-10-20 20:56:33,597 [INFO] [CONVENER] State: WAITING_FOR_HUMAN (ASR Active)
2025-10-20 20:56:33,600 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:45000-0xffff2c305a28
2025-10-20 20:56:33,600 [INFO] [STASIS] Start Snoop/1760986593.164-00000007
🎤 Audio detected! Connecting to Deepgram...

2025-10-20 20:56:34,207 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20000-0xffff2c0c1fb8
2025-10-20 20:56:34,210 [INFO] [BRIDGE] Added agent1_96862342 (role: ai_agent)
✅ Connected to Deepgram

================================================================================
2025-10-20 20:56:34,311 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20002-0xffff2c17eee8
2025-10-20 20:56:34,315 [INFO] [BRIDGE] Added agent2_c9bb5a14 (role: ai_agent)
2025-10-20 20:56:34,417 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20004-0xffff2c23e9f8
2025-10-20 20:56:34,421 [INFO] [BRIDGE] Added agent3_90afa285 (role: ai_agent)
⏳ Welcome to
2025-10-20 20:56:35,159 [INFO] [ASR] Transcript received but ignored due to mute simulation
✅ Welcome to your
2025-10-20 20:56:35,649 [INFO] [ASR] Transcript received but ignored due to mute simulation
2025-10-20 20:56:39,081 [INFO] [ASR] Unmuted after welcome message
⏳ This is
2025-10-20 20:56:40,647 [INFO] [ASR] Partial: 'This is'
⏳ Hello. This is Diego. I'd like to organize
2025-10-20 20:56:41,658 [INFO] [ASR] Partial: 'Hello. This is Diego. I'd like to organize'
⏳ Hello. This is Diego. I'd like to organize a trip to New
2025-10-20 20:56:42,656 [INFO] [ASR] Partial: 'Hello. This is Diego. I'd like to organize a trip to New'
✅ Hello. This is Diego. I'd like to organize a trip to New York.
2025-10-20 20:56:43,123 [INFO] [ASR] Final: 'Hello. This is Diego. I'd like to organize a trip to New York.'
⏳ Next Christmas.
2025-10-20 20:56:44,124 [INFO] [ASR] Partial: 'Next Christmas.'
✅ Next Christmas.
2025-10-20 20:56:44,443 [INFO] [ASR] Final: 'Next Christmas.'
⏳ Options do you
2025-10-20 20:56:45,443 [INFO] [ASR] Partial: 'Options do you'
✅ Options do you have?
2025-10-20 20:56:45,964 [INFO] [ASR] Final: 'Options do you have?'
2025-10-20 20:56:49,157 [INFO] [ASR] 3 seconds silence detected. Speech ended.
2025-10-20 20:56:49,157 [INFO] [ASR] Full transcript: 'Hello. This is Diego. I'd like to organize a trip to New York. Next Christmas. Options do you have?'
2025-10-20 20:56:49,158 [INFO] [CONVENER] Starting multi-agent dialogue (LLM mixed mode)
2025-10-20 20:56:49,158 [INFO] [CONVENER] Conversation ID: 93873f0d-1d7b-4ad6-a6cd-c9e8bcd2124e
2025-10-20 20:56:49,158 [INFO] [AGENT0] 🎵 Starting 'Please wait' message asynchronously
2025-10-20 20:56:49,163 [INFO] [AGENT0] ▶️  Playback started: agent0_wait_4b90ec
2025-10-20 20:56:50,664 [INFO] 
================================================================================
2025-10-20 20:56:50,664 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-20 20:56:50,664 [INFO] ================================================================================

2025-10-20 20:56:50,664 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-20 20:56:50,965 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-20 20:56:50,965 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 20:56:50,965 [INFO]            {
2025-10-20 20:56:50,965 [INFO]              "openFloor": {
2025-10-20 20:56:50,965 [INFO]                "schema": {
2025-10-20 20:56:50,965 [INFO]                  "version": "1.0.0",
2025-10-20 20:56:50,965 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 20:56:50,965 [INFO]                },
2025-10-20 20:56:50,965 [INFO]                "conversation": {
2025-10-20 20:56:50,965 [INFO]                  "id": "93873f0d-1d7b-4ad6-a6cd-c9e8bcd2124e"
2025-10-20 20:56:50,965 [INFO]                },
2025-10-20 20:56:50,965 [INFO]                "sender": {
2025-10-20 20:56:50,965 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 20:56:50,965 [INFO]                },
2025-10-20 20:56:50,965 [INFO]                "events": [
2025-10-20 20:56:50,965 [INFO]                  {
2025-10-20 20:56:50,965 [INFO]                    "to": "https://agent1.asterisk.local",
2025-10-20 20:56:50,965 [INFO]                    "eventType": "grantFloor",
2025-10-20 20:56:50,966 [INFO]                    "parameters": {
2025-10-20 20:56:50,966 [INFO]                      "reason": "Initial booking request requires flight specialist",
2025-10-20 20:56:50,966 [INFO]                      "duration": 12,
2025-10-20 20:56:50,966 [INFO]                      "context": {
2025-10-20 20:56:50,966 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to organize a trip to New York. Next Christmas. Options do you have?",
2025-10-20 20:56:50,966 [INFO]                        "timestamp": "2025-10-20T18:56:50Z"
2025-10-20 20:56:50,966 [INFO]                      }
2025-10-20 20:56:50,966 [INFO]                    }
2025-10-20 20:56:50,966 [INFO]                  }
2025-10-20 20:56:50,966 [INFO]                ]
2025-10-20 20:56:50,966 [INFO]              }
2025-10-20 20:56:50,967 [INFO]            }
2025-10-20 20:56:53,449 [INFO] [OFP_JSON] ✅ agent1 acknowledged grantFloor
2025-10-20 20:56:53,953 [INFO] [AGENT0] ⏹️  Stopped (agent1 ready)
2025-10-20 20:56:53,953 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-20 20:56:53,953 [INFO] [FLOOR] 🎤 Playing LLM audio: agent1_dynamic_55b93035
2025-10-20 20:56:53,955 [INFO] [PLAY] 🎵 Started playback: agent1_llm_6c4755
2025-10-20 20:56:54,259 [INFO] [PLAY] ✅ Playback completed in 0.3s
2025-10-20 20:56:54,259 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-20 20:56:54,760 [INFO] 
================================================================================
2025-10-20 20:56:54,760 [INFO] [TURN] Agent: agent2 | Type: stub | Mode: request
2025-10-20 20:56:54,760 [INFO] ================================================================================

2025-10-20 20:56:54,760 [INFO] [OFP_JSON] 📥 Received requestFloor from agent2
2025-10-20 20:56:54,761 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 20:56:54,761 [INFO]            {
2025-10-20 20:56:54,761 [INFO]              "openFloor": {
2025-10-20 20:56:54,761 [INFO]                "schema": {
2025-10-20 20:56:54,761 [INFO]                  "version": "1.0.0",
2025-10-20 20:56:54,761 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 20:56:54,761 [INFO]                },
2025-10-20 20:56:54,761 [INFO]                "conversation": {
2025-10-20 20:56:54,761 [INFO]                  "id": "93873f0d-1d7b-4ad6-a6cd-c9e8bcd2124e"
2025-10-20 20:56:54,761 [INFO]                },
2025-10-20 20:56:54,761 [INFO]                "sender": {
2025-10-20 20:56:54,761 [INFO]                  "from": "https://agent2.asterisk.local"
2025-10-20 20:56:54,761 [INFO]                },
2025-10-20 20:56:54,761 [INFO]                "events": [
2025-10-20 20:56:54,761 [INFO]                  {
2025-10-20 20:56:54,761 [INFO]                    "to": "https://convener.asterisk.local",
2025-10-20 20:56:54,761 [INFO]                    "eventType": "requestFloor",
2025-10-20 20:56:54,761 [INFO]                    "parameters": {
2025-10-20 20:56:54,762 [INFO]                      "requestReason": "Detected schedule conflict with Christmas festival",
2025-10-20 20:56:54,762 [INFO]                      "priority": "normal"
2025-10-20 20:56:54,762 [INFO]                    }
2025-10-20 20:56:54,762 [INFO]                  }
2025-10-20 20:56:54,762 [INFO]                ]
2025-10-20 20:56:54,762 [INFO]              }
2025-10-20 20:56:54,762 [INFO]            }
2025-10-20 20:56:55,263 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent2...
2025-10-20 20:56:55,664 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent2
2025-10-20 20:56:55,664 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 20:56:55,664 [INFO]            {
2025-10-20 20:56:55,664 [INFO]              "openFloor": {
2025-10-20 20:56:55,664 [INFO]                "schema": {
2025-10-20 20:56:55,664 [INFO]                  "version": "1.0.0",
2025-10-20 20:56:55,664 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 20:56:55,664 [INFO]                },
2025-10-20 20:56:55,664 [INFO]                "conversation": {
2025-10-20 20:56:55,664 [INFO]                  "id": "93873f0d-1d7b-4ad6-a6cd-c9e8bcd2124e"
2025-10-20 20:56:55,664 [INFO]                },
2025-10-20 20:56:55,664 [INFO]                "sender": {
2025-10-20 20:56:55,664 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 20:56:55,665 [INFO]                },
2025-10-20 20:56:55,665 [INFO]                "events": [
2025-10-20 20:56:55,665 [INFO]                  {
2025-10-20 20:56:55,665 [INFO]                    "to": "https://agent2.asterisk.local",
2025-10-20 20:56:55,665 [INFO]                    "eventType": "grantFloor",
2025-10-20 20:56:55,665 [INFO]                    "parameters": {
2025-10-20 20:56:55,665 [INFO]                      "reason": "Request approved: Detected schedule conflict with Christmas festival",
2025-10-20 20:56:55,665 [INFO]                      "duration": 12,
2025-10-20 20:56:55,665 [INFO]                      "context": {
2025-10-20 20:56:55,665 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to organize a trip to New York. Next Christmas. Options do you have?",
2025-10-20 20:56:55,665 [INFO]                        "timestamp": "2025-10-20T18:56:55Z"
2025-10-20 20:56:55,665 [INFO]                      }
2025-10-20 20:56:55,665 [INFO]                    }
2025-10-20 20:56:55,665 [INFO]                  }
2025-10-20 20:56:55,665 [INFO]                ]
2025-10-20 20:56:55,665 [INFO]              }
2025-10-20 20:56:55,666 [INFO]            }
2025-10-20 20:56:55,670 [INFO] [OFP_JSON] ✅ agent2 acknowledged grantFloor
2025-10-20 20:56:56,170 [INFO] [FLOOR] 🎤 agent2 (stub) takes floor: sound:agent2-suggest-event
2025-10-20 20:57:08,174 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent2
2025-10-20 20:57:08,675 [INFO] 
================================================================================
2025-10-20 20:57:08,675 [INFO] [TURN] Agent: agent3 | Type: stub | Mode: request
2025-10-20 20:57:08,675 [INFO] ================================================================================

2025-10-20 20:57:08,675 [INFO] [OFP_JSON] 📥 Received requestFloor from agent3
2025-10-20 20:57:08,675 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 20:57:08,675 [INFO]            {
2025-10-20 20:57:08,675 [INFO]              "openFloor": {
2025-10-20 20:57:08,675 [INFO]                "schema": {
2025-10-20 20:57:08,675 [INFO]                  "version": "1.0.0",
2025-10-20 20:57:08,675 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 20:57:08,675 [INFO]                },
2025-10-20 20:57:08,675 [INFO]                "conversation": {
2025-10-20 20:57:08,675 [INFO]                  "id": "93873f0d-1d7b-4ad6-a6cd-c9e8bcd2124e"
2025-10-20 20:57:08,675 [INFO]                },
2025-10-20 20:57:08,675 [INFO]                "sender": {
2025-10-20 20:57:08,676 [INFO]                  "from": "https://agent3.asterisk.local"
2025-10-20 20:57:08,676 [INFO]                },
2025-10-20 20:57:08,676 [INFO]                "events": [
2025-10-20 20:57:08,676 [INFO]                  {
2025-10-20 20:57:08,676 [INFO]                    "to": "https://convener.asterisk.local",
2025-10-20 20:57:08,676 [INFO]                    "eventType": "requestFloor",
2025-10-20 20:57:08,676 [INFO]                    "parameters": {
2025-10-20 20:57:08,676 [INFO]                      "requestReason": "Trip duration changed, need to adjust car rental",
2025-10-20 20:57:08,676 [INFO]                      "priority": "normal"
2025-10-20 20:57:08,676 [INFO]                    }
2025-10-20 20:57:08,676 [INFO]                  }
2025-10-20 20:57:08,676 [INFO]                ]
2025-10-20 20:57:08,676 [INFO]              }
2025-10-20 20:57:08,676 [INFO]            }
2025-10-20 20:57:09,177 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent3...
2025-10-20 20:57:09,578 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent3
2025-10-20 20:57:09,578 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 20:57:09,578 [INFO]            {
2025-10-20 20:57:09,578 [INFO]              "openFloor": {
2025-10-20 20:57:09,578 [INFO]                "schema": {
2025-10-20 20:57:09,578 [INFO]                  "version": "1.0.0",
2025-10-20 20:57:09,578 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 20:57:09,578 [INFO]                },
2025-10-20 20:57:09,578 [INFO]                "conversation": {
2025-10-20 20:57:09,578 [INFO]                  "id": "93873f0d-1d7b-4ad6-a6cd-c9e8bcd2124e"
2025-10-20 20:57:09,578 [INFO]                },
2025-10-20 20:57:09,578 [INFO]                "sender": {
2025-10-20 20:57:09,578 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 20:57:09,578 [INFO]                },
2025-10-20 20:57:09,579 [INFO]                "events": [
2025-10-20 20:57:09,579 [INFO]                  {
2025-10-20 20:57:09,579 [INFO]                    "to": "https://agent3.asterisk.local",
2025-10-20 20:57:09,579 [INFO]                    "eventType": "grantFloor",
2025-10-20 20:57:09,579 [INFO]                    "parameters": {
2025-10-20 20:57:09,579 [INFO]                      "reason": "Request approved: Trip duration changed, need to adjust car rental",
2025-10-20 20:57:09,579 [INFO]                      "duration": 12,
2025-10-20 20:57:09,579 [INFO]                      "context": {
2025-10-20 20:57:09,579 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to organize a trip to New York. Next Christmas. Options do you have?",
2025-10-20 20:57:09,579 [INFO]                        "timestamp": "2025-10-20T18:57:09Z"
2025-10-20 20:57:09,579 [INFO]                      }
2025-10-20 20:57:09,579 [INFO]                    }
2025-10-20 20:57:09,579 [INFO]                  }
2025-10-20 20:57:09,579 [INFO]                ]
2025-10-20 20:57:09,579 [INFO]              }
2025-10-20 20:57:09,579 [INFO]            }
2025-10-20 20:57:09,586 [INFO] [OFP_JSON] ✅ agent3 acknowledged grantFloor
2025-10-20 20:57:10,086 [INFO] [FLOOR] 🎤 agent3 (stub) takes floor: sound:agent3-check-car
2025-10-20 20:57:22,091 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent3
2025-10-20 20:57:22,592 [INFO] 
================================================================================
2025-10-20 20:57:22,592 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-20 20:57:22,592 [INFO] ================================================================================

2025-10-20 20:57:22,592 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-20 20:57:22,893 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-20 20:57:22,893 [INFO] [OFP_JSON] 📄 Envelope:
2025-10-20 20:57:22,893 [INFO]            {
2025-10-20 20:57:22,893 [INFO]              "openFloor": {
2025-10-20 20:57:22,893 [INFO]                "schema": {
2025-10-20 20:57:22,893 [INFO]                  "version": "1.0.0",
2025-10-20 20:57:22,893 [INFO]                  "url": "https://github.com/open-voice-interoperability/openfloor-docs/tree/main/schemas/ConversationEnvelope/1.0.0/conversation-envelope-schema.json"
2025-10-20 20:57:22,893 [INFO]                },
2025-10-20 20:57:22,893 [INFO]                "conversation": {
2025-10-20 20:57:22,894 [INFO]                  "id": "93873f0d-1d7b-4ad6-a6cd-c9e8bcd2124e"
2025-10-20 20:57:22,894 [INFO]                },
2025-10-20 20:57:22,894 [INFO]                "sender": {
2025-10-20 20:57:22,894 [INFO]                  "from": "https://convener.asterisk.local"
2025-10-20 20:57:22,894 [INFO]                },
2025-10-20 20:57:22,894 [INFO]                "events": [
2025-10-20 20:57:22,894 [INFO]                  {
2025-10-20 20:57:22,894 [INFO]                    "to": "https://agent1.asterisk.local",
2025-10-20 20:57:22,894 [INFO]                    "eventType": "grantFloor",
2025-10-20 20:57:22,894 [INFO]                    "parameters": {
2025-10-20 20:57:22,894 [INFO]                      "reason": "Provide final booking summary",
2025-10-20 20:57:22,894 [INFO]                      "duration": 12,
2025-10-20 20:57:22,894 [INFO]                      "context": {
2025-10-20 20:57:22,895 [INFO]                        "userRequest": "Hello. This is Diego. I'd like to organize a trip to New York. Next Christmas. Options do you have?",
2025-10-20 20:57:22,895 [INFO]                        "timestamp": "2025-10-20T18:57:22Z"
2025-10-20 20:57:22,895 [INFO]                      }
2025-10-20 20:57:22,895 [INFO]                    }
2025-10-20 20:57:22,895 [INFO]                  }
2025-10-20 20:57:22,895 [INFO]                ]
2025-10-20 20:57:22,895 [INFO]              }
2025-10-20 20:57:22,895 [INFO]            }
2025-10-20 20:57:25,534 [INFO] [OFP_JSON] ✅ agent1 acknowledged grantFloor
2025-10-20 20:57:26,035 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-20 20:57:26,035 [INFO] [FLOOR] 🎤 Playing LLM audio: agent1_dynamic_bc3d3b59
2025-10-20 20:57:26,043 [INFO] [PLAY] 🎵 Started playback: agent1_llm_7b269e
2025-10-20 20:57:26,347 [INFO] [PLAY] ✅ Playback completed in 0.3s
2025-10-20 20:57:26,347 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-20 20:57:26,848 [INFO] [CONFIRM] Waiting for user confirmation...
2025-10-20 20:57:29,849 [INFO] [CONFIRM] 🎤 Listening for 'yes', 'ok', or similar + silence...
✅ Yes, please.
2025-10-20 20:57:36,121 [INFO] [ASR] Final: 'Yes, please.'
2025-10-20 20:57:36,356 [INFO] [CONFIRM] 🟢 Keyword detected: 'yes, please.'. Waiting for silence...
⏳ Let's move on.
2025-10-20 20:57:37,050 [INFO] [ASR] Partial: 'Let's move on.'
✅ Let's move on.
2025-10-20 20:57:37,225 [INFO] [ASR] Final: 'Let's move on.'
2025-10-20 20:57:39,360 [INFO] [CONFIRM] ✅ Confirmed after 2s silence: 'yes, please. let's move on.'
2025-10-20 20:57:39,360 [INFO] [CONFIRM] Playing final message
2025-10-20 20:57:49,364 [INFO] [CONVENER] Complete. Cleanup.
2025-10-20 20:57:49,364 [INFO] [CLEANUP] Starting...
2025-10-20 20:57:49,370 [INFO] [CLEANUP] Destroyed snoop bridge
2025-10-20 20:57:49,372 [INFO] [CLEANUP] Hung up 1760986593.164
2025-10-20 20:57:49,377 [INFO] [STASIS] End PJSIP/human1-00000007
2025-10-20 20:57:49,378 [INFO] [CLEANUP] Hung up ASR_EXT_5a3e360a
2025-10-20 20:57:49,379 [INFO] [STASIS] End UnicastRTP/127.0.0.1:45000-0xffff2c305a28
2025-10-20 20:57:49,380 [INFO] [CLEANUP] Hung up ASR_SNOOP_5a3e360a
2025-10-20 20:57:49,381 [INFO] [STASIS] End Snoop/1760986593.164-00000007
2025-10-20 20:57:49,383 [INFO] [CLEANUP] Hung up agent1_96862342
2025-10-20 20:57:49,385 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20000-0xffff2c0c1fb8
2025-10-20 20:57:49,386 [INFO] [CLEANUP] Hung up agent2_c9bb5a14
2025-10-20 20:57:49,388 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20002-0xffff2c17eee8
2025-10-20 20:57:49,389 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20004-0xffff2c23e9f8
2025-10-20 20:57:49,390 [INFO] [CLEANUP] Hung up agent3_90afa285
2025-10-20 20:57:49,390 [INFO] [CLEANUP] Complete
```
```