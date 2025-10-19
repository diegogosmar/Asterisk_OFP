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

2025-10-19 18:55:58,298 [INFO] ================================================================================
2025-10-19 18:55:58,298 [INFO] 🎙️  Convener OFP LLM Mixed - Smart Playback + Agent0
2025-10-19 18:55:58,298 [INFO] ================================================================================
2025-10-19 18:55:58,299 [INFO] [ASR_LISTENER] Listening on port 45001
2025-10-19 18:55:58,299 [INFO] [BRIDGE] Ready, ID=1234
2025-10-19 18:55:58,300 [INFO] [WS] Connected to ARI
2025-10-19 18:56:01,071 [INFO] [STASIS] Start PJSIP/human1-0000000e
2025-10-19 18:56:01,072 [INFO] [BRIDGE] Added 1760892961.310 (role: user_default)
2025-10-19 18:56:01,074 [INFO] [SNOOP] ExternalMedia: ASR_EXT_45000 (ULAW 8kHz)
2025-10-19 18:56:01,379 [INFO] [SNOOP] ✅ Capturing 1760892961.310 audio (isolated)
2025-10-19 18:56:01,588 [INFO] [SNOOP] Isolated bridge: ASR_SNOOP_45000 ↔ ASR_EXT_45000 → Deepgram
2025-10-19 18:56:01,591 [INFO] [CONVENER] State: WAITING_FOR_HUMAN (ASR Active)
2025-10-19 18:56:01,593 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:45000-0xffff84003538
2025-10-19 18:56:01,593 [INFO] [STASIS] Start Snoop/1760892961.310-0000000d
🎤 Audio detected! Connecting to Deepgram...

✅ Connected to Deepgram

================================================================================
2025-10-19 18:56:02,197 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20000-0xffff84015d08
2025-10-19 18:56:02,200 [INFO] [BRIDGE] Added agent1 (role: ai_agent)
2025-10-19 18:56:02,304 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20002-0xffff84022e18
2025-10-19 18:56:02,307 [INFO] [BRIDGE] Added agent2 (role: ai_agent)
2025-10-19 18:56:02,408 [INFO] [STASIS] Start UnicastRTP/127.0.0.1:20004-0xffff8402c078
2025-10-19 18:56:02,411 [INFO] [BRIDGE] Added agent3 (role: ai_agent)
⏳ Hello. This
2025-10-19 18:56:07,755 [INFO] [ASR] Partial: 'Hello. This'
⏳ Hello. This is Diego. I love
2025-10-19 18:56:08,771 [INFO] [ASR] Partial: 'Hello. This is Diego. I love'
✅ Hello. This is Diego. I'd like to book a trip
2025-10-19 18:56:09,778 [INFO] [ASR] Final: 'Hello. This is Diego. I'd like to book a trip'
⏳ to Berlin
2025-10-19 18:56:10,618 [INFO] [ASR] Partial: 'to Berlin'
⏳ to Berlin next summer.
2025-10-19 18:56:11,621 [INFO] [ASR] Partial: 'to Berlin next summer.'
✅ to Berlin next summer.
2025-10-19 18:56:11,927 [INFO] [ASR] Final: 'to Berlin next summer.'
2025-10-19 18:56:15,263 [INFO] [ASR] 3 seconds silence detected. Speech ended.
2025-10-19 18:56:15,264 [INFO] [ASR] Full transcript: 'Hello. This is Diego. I'd like to book a trip to Berlin next summer.'
2025-10-19 18:56:15,264 [INFO] [CONVENER] Starting multi-agent dialogue (LLM mixed mode)
2025-10-19 18:56:15,265 [INFO] [CONVENER] Conversation ID: e1199a3d-9bd0-4662-a220-b67ccd69d8aa
2025-10-19 18:56:15,265 [INFO] [AGENT0] 🎵 Starting 'Please wait' message asynchronously
2025-10-19 18:56:15,270 [INFO] [AGENT0] ▶️  Playback started: agent0_wait_d260fd
2025-10-19 18:56:16,770 [INFO] 
================================================================================
2025-10-19 18:56:16,770 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-19 18:56:16,770 [INFO] ================================================================================

2025-10-19 18:56:16,770 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-19 18:56:17,071 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-19 18:56:19,998 [INFO] [OFP_JSON] ✅ agent1 acknowledged grantFloor
2025-10-19 18:56:20,502 [INFO] [AGENT0] ⏹️  Stopped (agent1 ready)
2025-10-19 18:56:20,502 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-19 18:56:20,502 [INFO] [FLOOR] 🎤 Playing LLM audio: agent1_dynamic_0bf7b82e
2025-10-19 18:56:20,508 [INFO] [PLAY] 🎵 Started playback: agent1_llm_ee3404
2025-10-19 18:56:20,811 [INFO] [PLAY] ✅ Playback completed in 0.3s
2025-10-19 18:56:20,812 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-19 18:56:21,312 [INFO] 
================================================================================
2025-10-19 18:56:21,312 [INFO] [TURN] Agent: agent2 | Type: stub | Mode: request
2025-10-19 18:56:21,313 [INFO] ================================================================================

2025-10-19 18:56:21,313 [INFO] [OFP_JSON] 📥 Received requestFloor from agent2
2025-10-19 18:56:21,813 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent2...
2025-10-19 18:56:22,214 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent2
2025-10-19 18:56:22,221 [INFO] [OFP_JSON] ✅ agent2 acknowledged grantFloor
2025-10-19 18:56:22,722 [INFO] [FLOOR] 🎤 agent2 (stub) takes floor: sound:agent2-suggest-event
2025-10-19 18:56:34,725 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent2
2025-10-19 18:56:35,226 [INFO] 
================================================================================
2025-10-19 18:56:35,227 [INFO] [TURN] Agent: agent3 | Type: stub | Mode: request
2025-10-19 18:56:35,227 [INFO] ================================================================================

2025-10-19 18:56:35,227 [INFO] [OFP_JSON] 📥 Received requestFloor from agent3
2025-10-19 18:56:35,727 [INFO] [CONVENER] 🧠 Evaluating requestFloor from agent3...
2025-10-19 18:56:36,128 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent3
2025-10-19 18:56:36,134 [INFO] [OFP_JSON] ✅ agent3 acknowledged grantFloor
2025-10-19 18:56:36,635 [INFO] [FLOOR] 🎤 agent3 (stub) takes floor: sound:agent3-check-car
2025-10-19 18:56:48,639 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent3
2025-10-19 18:56:49,139 [INFO] 
================================================================================
2025-10-19 18:56:49,140 [INFO] [TURN] Agent: agent1 | Type: llm | Mode: invite
2025-10-19 18:56:49,140 [INFO] ================================================================================

2025-10-19 18:56:49,140 [INFO] [CONVENER] 🧠 Selecting agent1 to speak
2025-10-19 18:56:49,440 [INFO] [OFP_JSON] 📤 Sending grantFloor to agent1
2025-10-19 18:56:52,038 [INFO] [OFP_JSON] ✅ agent1 acknowledged grantFloor
2025-10-19 18:56:52,539 [INFO] [FLOOR] 🤖 agent1 (LLM) generated audio
2025-10-19 18:56:52,539 [INFO] [FLOOR] 🎤 Playing LLM audio: agent1_dynamic_04b99cf2
2025-10-19 18:56:52,547 [INFO] [PLAY] 🎵 Started playback: agent1_llm_98c567
2025-10-19 18:56:52,850 [INFO] [PLAY] ✅ Playback completed in 0.3s
2025-10-19 18:56:52,850 [INFO] [OFP_JSON] 📥 Received yieldFloor from agent1
2025-10-19 18:56:53,351 [INFO] [CONFIRM] Waiting for user confirmation...
2025-10-19 18:56:56,352 [INFO] [CONFIRM] 🎤 Listening for 'yes', 'ok', or similar + silence...
⏳ Yes.
2025-10-19 18:57:01,760 [INFO] [ASR] Partial: 'Yes.'
⏳ Yes, please. Let's go.
2025-10-19 18:57:02,792 [INFO] [ASR] Partial: 'Yes, please. Let's go.'
✅ Yes, please. Let's go on.
2025-10-19 18:57:03,192 [INFO] [ASR] Final: 'Yes, please. Let's go on.'
2025-10-19 18:57:03,361 [INFO] [CONFIRM] 🟢 Keyword detected: 'yes, please. let's go on.'. Waiting for silence...
2025-10-19 18:57:05,363 [INFO] [CONFIRM] ✅ Confirmed after 2s silence: 'yes, please. let's go on.'
2025-10-19 18:57:05,364 [INFO] [CONFIRM] Playing final message
2025-10-19 18:57:15,370 [INFO] [CONVENER] Complete. Cleanup.
2025-10-19 18:57:15,371 [INFO] [CLEANUP] Starting...
2025-10-19 18:57:15,374 [INFO] [CLEANUP] Destroyed snoop bridge
2025-10-19 18:57:15,381 [INFO] [STASIS] End PJSIP/human1-0000000e
2025-10-19 18:57:15,382 [INFO] [CLEANUP] Hung up 1760892961.310
2025-10-19 18:57:15,383 [INFO] [STASIS] End Snoop/1760892961.310-0000000d
2025-10-19 18:57:15,384 [INFO] [CLEANUP] Hung up ASR_EXT_45000
2025-10-19 18:57:15,386 [INFO] [STASIS] End UnicastRTP/127.0.0.1:45000-0xffff84003538
2025-10-19 18:57:15,389 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20000-0xffff84015d08
2025-10-19 18:57:15,390 [INFO] [CLEANUP] Hung up agent1
2025-10-19 18:57:15,391 [INFO] [CLEANUP] Hung up agent2
2025-10-19 18:57:15,393 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20002-0xffff84022e18
2025-10-19 18:57:15,394 [INFO] [STASIS] End UnicastRTP/127.0.0.1:20004-0xffff8402c078
2025-10-19 18:57:15,395 [INFO] [CLEANUP] Hung up agent3
2025-10-19 18:57:15,395 [INFO] [CLEANUP] Complete