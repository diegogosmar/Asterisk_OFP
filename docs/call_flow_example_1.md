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

2025-10-20 18:06:08,880 [INFO] ================================================================================
2025-10-20 18:06:08,880 [INFO] 🎙️  Convener OFP LLM Mixed - Smart Playback + Agent0 with ASR mute
2025-10-20 18:06:08,880 [INFO] ================================================================================
2025-10-20 18:06:08,880 [INFO] [ASR_LISTENER] Listening on port 45001
2025-10-20 18:06:08,882 [INFO] [BRIDGE] Ready, ID=1234
2025-10-20 18:06:08,883 [INFO] [WS] Connected to ARI
2025-10-20 18:06:11,870 [INFO] [STASIS] Start PJSIP/human1-00000000
2025-10-20 18:06:11,875 [INFO] [BRIDGE] Added 1760976371.0 (role: user_default)
2025-10-20 18:06:11,880 [INFO] [SNOOP] ExternalMedia: ASR_EXT_55b81916 (ULAW 8kHz)
2025-10-20 18:06:12,185 [INFO] [SNOOP] ✅ Capturing 1760976371.0 audio (isolated)
2025-10-20 18:06:12,395 [INFO] [SNOOP] Isolated bridge: ASR_SNOOP_55b81916 ↔ ASR_EXT_55b81916 → Deepgram
2025-10-20 18:06:12,396 [INFO] [CONVENER] State: WAITING_FOR_HUMAN (ASR Active)
2025-10-20 18:06:12,398 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:45000-0xffff400096e8
2025-10-20 18:06:12,399 [INFO] [STASIS] Start Snoop/1760976371.0-00000000
🎤 Audio detected! Connecting to Deepgram...

2025-10-20 18:06:13,005 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20000-0xffff400d1ca8
2025-10-20 18:06:13,007 [INFO] [BRIDGE] Added agent1_9bc448b9 (role: ai_agent)
✅ Connected to Deepgram

================================================================================
2025-10-20 18:06:13,110 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20002-0xffff40190468
2025-10-20 18:06:13,113 [INFO] [BRIDGE] Added agent2_20d8a134 (role: ai_agent)
2025-10-20 18:06:13,218 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20004-0xffff4024c748
2025-10-20 18:06:13,221 [INFO] [BRIDGE] Added agent3_0c710437 (role: ai_agent)
⏳ To your
2025-10-20 18:06:13,994 [INFO] [ASR] Transcript received but ignored due to mute simulation
2025-10-20 18:06:17,877 [INFO] [ASR] Unmuted after welcome message
⏳ Cool.
2025-10-20 18:06:18,047 [INFO] [ASR] Partial: 'Cool.'
⏳ Hello. This is Diego. I
2025-10-20 18:06:19,035 [INFO] [ASR] Partial: 'Hello. This is Diego. I'
⏳ Hello. This is Diego. I'd like to book a trip
2025-10-20 18:06:20,075 [INFO] [ASR] Partial: 'Hello. This is Diego. I'd like to book a trip'
⏳ Hello. This is Diego. I'd like to book a trip to Denver next
2025-10-20 18:06:21,060 [INFO] [ASR] Partial: 'Hello. This is Diego. I'd like to book a trip to Denver next'
✅ Hello. This is Diego. I'd like to book a trip to Denver next year.
2025-10-20 18:06:21,706 [INFO] [ASR] Final: 'Hello. This is Diego. I'd like to book a trip to Denver next year.'
⏳ Which options do you
2025-10-20 18:06:22,680 [INFO] [ASR] Partial: 'Which options do you'
✅ Which options you have?
2025-10-20 18:06:23,124 [INFO] [ASR] Final: 'Which options you have?'
2025-10-20 18:06:26,559 [INFO] [ASR] 3 seconds silence detected. Speech ended.
2025-10-20 18:06:26,559 [INFO] [ASR] Full transcript: 'Hello. This is Diego. I'd like to book a trip to Denver next year. Which options you have?'
2025-10-20 18:06:26,560 [INFO] [CONVENER] Starting multi-agent dialogue (LLM mixed mode)
2025-10-20 18:06:26,560 [INFO] [CONVENER] Conversation ID: 1ced92a3-b690-4ca1-b801-37b3c7beb535
2025-10-20 18:06:26,560 [INFO] [AGENT0] 🎵 Starting 'Please wait' message asynchronously
2025-10-20 18:06:26,566 [INFO] [AGENT0] ▶️  Playback started: agent0_wait_b33e33
⏳ Please wait while
2025-10-20 18:06:28,067 [INFO] 
================================================================================
2025-10-20 18:06:28,067 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-20 18:06:28,067 [INFO] ================================================================================

2025-10-20 18:06:28,067 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-20 18:06:28,368 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
✅ Please wait while we get you
2025-10-20 18:06:31,591 [INFO] [OFP_JSON] ✅ agent1 acknowledged grantFloor
2025-10-20 18:06:32,095 [INFO] [AGENT0] ⏹️  Stopped (agent1 ready)
2025-10-20 18:06:32,095 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-20 18:06:32,095 [INFO] [FLOOR] 🎤 Playing LLM audio: agent1_dynamic_53fdc6ba
2025-10-20 18:06:32,101 [INFO] [PLAY] 🎵 Started playback: agent1_llm_f78b5f
2025-10-20 18:06:32,405 [INFO] [PLAY] ✅ Playback completed in 0.3s
2025-10-20 18:06:32,405 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-20 18:06:32,906 [INFO] 
================================================================================
2025-10-20 18:06:32,906 [INFO] [TURN] Agent: agent2 | Type: stub | Mode: request
2025-10-20 18:06:32,906 [INFO] ================================================================================

2025-10-20 18:06:32,906 [INFO] [OFP_JSON] 📥 Received requestFloor from agent2
2025-10-20 18:06:33,407 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent2...
2025-10-20 18:06:33,808 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent2
2025-10-20 18:06:33,819 [INFO] [OFP_JSON] ✅ agent2 acknowledged grantFloor
2025-10-20 18:06:34,319 [INFO] [FLOOR] 🎤 agent2 (stub) takes floor: sound:agent2-suggest-event
⏳ During those days.
✅ During those days.
⏳ And if required,
✅ And it requires a minimum
2025-10-20 18:06:46,323 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent2
2025-10-20 18:06:46,824 [INFO] 
================================================================================
2025-10-20 18:06:46,824 [INFO] [TURN] Agent: agent3 | Type: stub | Mode: request
2025-10-20 18:06:46,824 [INFO] ================================================================================

2025-10-20 18:06:46,825 [INFO] [OFP_JSON] 📥 Received requestFloor from agent3
2025-10-20 18:06:47,325 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent3...
2025-10-20 18:06:47,726 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent3
2025-10-20 18:06:47,738 [INFO] [OFP_JSON] ✅ agent3 acknowledged grantFloor
2025-10-20 18:06:48,239 [INFO] [FLOOR] 🎤 agent3 (stub) takes floor: sound:agent3-check-car
2025-10-20 18:07:00,243 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent3
2025-10-20 18:07:00,744 [INFO] 
================================================================================
2025-10-20 18:07:00,744 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-20 18:07:00,744 [INFO] ================================================================================

2025-10-20 18:07:00,744 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-20 18:07:01,045 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-20 18:07:04,474 [INFO] [OFP_JSON] ✅ agent1 acknowledged grantFloor
2025-10-20 18:07:04,975 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-20 18:07:04,976 [INFO] [FLOOR] 🎤 Playing LLM audio: agent1_dynamic_8f2ec07e
2025-10-20 18:07:04,982 [INFO] [PLAY] 🎵 Started playback: agent1_llm_4c56b1
2025-10-20 18:07:05,285 [INFO] [PLAY] ✅ Playback completed in 0.3s
2025-10-20 18:07:05,285 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-20 18:07:05,786 [INFO] [CONFIRM] Waiting for user confirmation...
2025-10-20 18:07:08,787 [INFO] [CONFIRM] 🎤 Listening for 'yes', 'ok', or similar + silence...
⏳ Yes.
2025-10-20 18:07:14,337 [INFO] [ASR] Partial: 'Yes.'
⏳ Yes, please. Let's
2025-10-20 18:07:15,362 [INFO] [ASR] Partial: 'Yes, please. Let's'
✅ Yes, please. Let's move on.
2025-10-20 18:07:15,990 [INFO] [ASR] Final: 'Yes, please. Let's move on.'
2025-10-20 18:07:16,295 [INFO] [CONFIRM] 🟢 Keyword detected: 'yes, please. let's move on.'. Waiting for silence...
2025-10-20 18:07:18,298 [INFO] [CONFIRM] ✅ Confirmed after 2s silence: 'yes, please. let's move on.'
2025-10-20 18:07:18,298 [INFO] [CONFIRM] Playing final message
2025-10-20 18:07:28,304 [INFO] [CONVENER] Complete. Cleanup.
2025-10-20 18:07:28,305 [INFO] [CLEANUP] Starting...
2025-10-20 18:07:28,307 [INFO] [CLEANUP] Destroyed snoop bridge
2025-10-20 18:07:28,315 [INFO] [STASIS] End PJSIP/human1-00000000
2025-10-20 18:07:28,315 [INFO] [CLEANUP] Hung up 1760976371.0
2025-10-20 18:07:28,317 [INFO] [CLEANUP] Hung up ASR_EXT_55b81916
2025-10-20 18:07:28,318 [INFO] [STASIS] End UnicastRTP/127.0.0.1:45000-0xffff400096e8
2025-10-20 18:07:28,318 [INFO] [CLEANUP] Hung up ASR_SNOOP_55b81916
2025-10-20 18:07:28,319 [INFO] [STASIS] End Snoop/1760976371.0-00000000
2025-10-20 18:07:28,321 [INFO] [CLEANUP] Hung up agent1_9bc448b9
2025-10-20 18:07:28,324 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20000-0xffff400d1ca8
2025-10-20 18:07:28,325 [INFO] [CLEANUP] Hung up agent2_20d8a134
2025-10-20 18:07:28,326 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20002-0xffff40190468
2025-10-20 18:07:28,328 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20004-0xffff4024c748
2025-10-20 18:07:28,329 [INFO] [CLEANUP] Hung up agent3_0c710437
2025-10-20 18:07:28,329 [INFO] [CLEANUP] Complete
```
```