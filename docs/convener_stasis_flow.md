# Asterisk Stasis Integration - How It Works

This document explains how the Python application integrates with Asterisk using the **Stasis dialplan application** and **ARI (Asterisk REST Interface)**.

---

## Overview

Python Script → ARI WebSocket → Asterisk → Dialplan
↓ ↓
Listening Stasis(convener)
↓ ↓
Receives StasisStart event Channel control transferred
↓
Controls channel via ARI REST API

text

**Key Concept:** Stasis hands off call control from Asterisk dialplan to external applications via ARI.

---

## Step 1: Application Startup

### You manually start the Python script

$ python3 convener_integrated.py

text

### Script execution flow

convener_integrated.py
1. WebSocket connection to Asterisk ARI
ws = create_connection(
"ws://127.0.0.1:8088/ari/events?app=convener&api_key=asterisk:asterisk"
)

2. Connection established
Asterisk logs: "WebSocket connection from 127.0.0.1:xxxxx for app 'convener'"
3. Script enters event loop
while True:
raw = ws.recv()
evt = json.loads(raw)

text
if evt.get("type") == "StasisStart":
    on_stasis_start(evt)
# ... handle other events
text

### What happens in Asterisk

┌─────────────────────────────────────────────────────────┐
│ ASTERISK ARI SERVER │
│ │
│ Port: 8088 │
│ Endpoint: /ari/events │
│ │
│ ✅ WebSocket connection accepted │
│ ✅ Registered listener for app: "convener" │
│ ✅ Ready to send events │
└─────────────────────────────────────────────────────────┘

text

**Script Status:** Waiting for events (infinite loop)

---

## Step 2: User Makes a Call

### User dials extension 100

User's SIP Phone
↓
SIP INVITE to Asterisk
↓
Asterisk receives call

text

### Asterisk dialplan execution

**File:** `/etc/asterisk/extensions.conf`

[from-internal]
exten => 100,1,NoOp(=== Incoming call to extension 100 ===)
same => n,Answer()
same => n,Stasis(convener) ; ← CRITICAL: Hand off to app "convener"
same => n,Hangup()

text

### What `Stasis(convener)` does

┌─────────────────────────────────────────────────────────┐
│ ASTERISK DIALPLAN PROCESSOR │
│ │
│ 1. Execute: Answer() │
│ ✅ Channel answered │
│ │
│ 2. Execute: Stasis(convener) │
│ ❓ "Is anyone listening for app 'convener'?" │
│ ✅ YES! WebSocket from 127.0.0.1:xxxxx │
│ │
│ 3. Transfer control to external app │
│ 📤 Send StasisStart event via WebSocket │
│ ⏸️ Dialplan execution PAUSES here │
│ │
│ Note: Dialplan will NOT execute line "n,Hangup()" │
│ until app returns control │
└─────────────────────────────────────────────────────────┘

text

---

## Step 3: StasisStart Event

### Event sent from Asterisk to Python

**JSON Event Structure:**

{
"type": "StasisStart",
"timestamp": "2025-10-19T18:56:01.071Z",
"application": "convener",
"channel": {
"id": "1760892961.310",
"name": "PJSIP/human1-0000000e",
"state": "Up",
"caller": {
"name": "Human User",
"number": "100"
},
"connected": {
"name": "",
"number": ""
},
"accountcode": "",
"dialplan": {
"context": "from-internal",
"exten": "100",
"priority": 3
},
"creationtime": "2025-10-19T18:56:01.000Z",
"language": "en"
},
"args": [],
"replace_channel": null
}

text

### Python receives and processes event

Event received via WebSocket
def on_stasis_start(evt):
ch = evt.get("channel", {})
cid = ch.get("id") # "1760892961.310"
cname = ch.get("name", "") # "PJSIP/human1-0000000e"

text
logging.info(f"[STASIS] Start {cname}")

# Now we have FULL CONTROL of this channel!
# We can:
# - Add to bridge
# - Play audio
# - Record
# - Snoop
# - Hangup
# - Anything via ARI REST API

# Example: Add channel to conference bridge
add_to_bridge(cid)
text

---

## Step 4: Channel Control

### What your Python app can now do

Once you receive `StasisStart`, the channel is **completely under your control**.

#### Available ARI Operations

┌─────────────────────────────────────────────────────────┐
│ ARI OPERATIONS (via REST API) │
├─────────────────────────────────────────────────────────┤
│ │
│ Channel Management: │
│ - POST /channels/{channelId}/answer │
│ - DELETE /channels/{channelId} (hangup) │
│ - GET /channels/{channelId} (status) │
│ │
│ Bridge Operations: │
│ - POST /bridges (create) │
│ - POST /bridges/{id}/addChannel (add participant) │
│ - DELETE /bridges/{id}/removeChannel │
│ │
│ Media Control: │
│ - POST /channels/{id}/play (play audio) │
│ - POST /channels/{id}/record (record audio) │
│ - POST /channels/{id}/snoop (spy on channel) │
│ │
│ Variables: │
│ - GET /channels/{id}/variable/{var} │
│ - POST /channels/{id}/variable │
│ │
│ And much more... │
└─────────────────────────────────────────────────────────┘

text

#### Example: Add channel to bridge

def add_to_bridge(cid):
"""Add channel to conference bridge"""

text
# REST API call to Asterisk
r = session.post(
    f"http://127.0.0.1:8088/ari/bridges/{BRIDGE_ID}/addChannel",
    params={"channel": cid, "role": "user_default"},
    auth=("asterisk", "asterisk")
)

if r.status_code == 204:
    logging.info(f"[BRIDGE] Added {cid}")
text

---

## Complete Flow Diagram

┌─────────────────────────────────────────────────────────────┐
│ TIMELINE │
└─────────────────────────────────────────────────────────────┘

TIME EVENT ACTOR DETAIL
─────────────────────────────────────────────────────────────────
00:00 Script starts You python3 convener_integrated.py
00:01 WebSocket connects Python ws://127.0.0.1:8088/ari/events
00:01 Listener registered Asterisk App "convener" listener added
00:01 Event loop starts Python while True: ws.recv()

text
    ... (script waiting for calls) ...
01:30 User dials 100 User SIP INVITE
01:30 Dialplan: Answer() Asterisk Channel answered
01:30 Dialplan: Stasis(convener) Asterisk Transfer control
01:30 StasisStart event sent Asterisk → WebSocket
01:30 Event received Python evt["type"] == "StasisStart"
01:30 on_stasis_start() called Python Channel control acquired
01:31 Add to bridge Python ARI REST: POST /bridges/1234/addChannel
01:31 Channel in bridge Asterisk Audio routing active
01:31 Start snoop for ASR Python ARI REST: POST /channels/{id}/snoop
01:32 User speaks User "Book flight to Denver"
01:32 ASR transcribes Deepgram Real-time transcription

text
    ... (multi-agent dialogue) ...
02:45 Call completed Python ARI REST: DELETE /channels/{id}
02:45 StasisEnd event Asterisk → WebSocket
02:45 Cleanup resources Python on_stasis_end()
02:45 Dialplan resumes Asterisk Execute: Hangup()

text

---

## Key Concepts

### 1. Stasis Application Name

The name `"convener"` **must match** in three places:

┌────────────────────────────────────────────────────────┐
│ 1. Dialplan (extensions.conf): │
│ Stasis(convener) │
│ │
│ 2. WebSocket URL: │
│ ws://...?app=convener │
│ │
│ 3. Python script constant: │
│ APP_NAME = "convener" │
└────────────────────────────────────────────────────────┘

text

**Mismatch = Events won't be received!**

### 2. WebSocket vs REST API

┌────────────────────────────────────────────────────────┐
│ WebSocket (ws://127.0.0.1:8088/ari/events) │
│ - Events FROM Asterisk TO Python │
│ - StasisStart, StasisEnd, ChannelStateChange, etc. │
│ - One persistent connection │
│ - Real-time event stream │
└────────────────────────────────────────────────────────┘

┌────────────────────────────────────────────────────────┐
│ REST API (http://127.0.0.1:8088/ari/...) │
│ - Commands FROM Python TO Asterisk │
│ - POST, GET, DELETE operations │
│ - Answer, Hangup, Play, Bridge, Snoop, etc. │
│ - Individual HTTP requests │
└────────────────────────────────────────────────────────┘

text

### 3. Event Types

Common ARI events your script might receive:

| Event Type | When it occurs | Action |
|------------|----------------|--------|
| `StasisStart` | Channel enters Stasis app | Initialize call handling |
| `StasisEnd` | Channel leaves Stasis app | Cleanup resources |
| `ChannelStateChange` | Channel state changes | Monitor call status |
| `ChannelHangupRequest` | User hangs up | Terminate call |
| `PlaybackStarted` | Audio playback begins | Track media |
| `PlaybackFinished` | Audio playback ends | Next action |
| `BridgeCreated` | Bridge created | Confirm bridge ready |
| `ChannelEnteredBridge` | Channel joins bridge | Log participant |
| `ChannelLeftBridge` | Channel leaves bridge | Handle disconnect |

### 4. Control Return to Dialplan

To return control back to Asterisk dialplan:

Method 1: Exit Stasis explicitly
session.post(f"{ARI_HTTP}/channels/{channel_id}/continue")

Method 2: Hangup (most common)
session.delete(f"{ARI_HTTP}/channels/{channel_id}")

text

After this, dialplan will resume at the next priority (line `n,Hangup()`).

---

## Error Handling

### What if WebSocket disconnects?

try:
while True:
raw = ws.recv()
# ... process events
except WebSocketConnectionClosedException:
logging.error("[WS] Connection closed by Asterisk")
# Reconnect logic here
# Or exit and let systemd restart

text

### What if app isn't running when user calls?

User dials 100
↓
Asterisk executes: Stasis(convener)
↓
Asterisk checks: "Is anyone listening for 'convener'?"
↓
❌ NO listener found
↓
Asterisk logs: "No handler for Stasis app 'convener'"
↓
Dialplan continues to next priority: Hangup()
↓
Call ends

text

**Solution:** Keep your script running (use `systemd` or `supervisor` in production).

---

## Production Deployment

### systemd service example

**File:** `/etc/systemd/system/convener.service`

[Unit]
Description=Asterisk Convener OFP Application
After=network.target asterisk.service
Requires=asterisk.service

[Service]
Type=simple
User=asterisk
Group=asterisk
WorkingDirectory=/opt/convener
Environment="PATH=/opt/convener/venv/bin"
ExecStart=/opt/convener/venv/bin/python3 /opt/convener/convener_integrated.py
Restart=always
RestartSec=10

[Install]
WantedBy=multi-user.target

text

### Enable and start

sudo systemctl daemon-reload
sudo systemctl enable convener
sudo systemctl start convener
sudo systemctl status convener

text

Now the script starts automatically with Asterisk and restarts if it crashes.

---

## Debugging Tips

### Check if WebSocket is connected

Show active ARI connections
asterisk -rx "ari show apps"

Output should show:
App: convener
Connections: 1
text

### Monitor ARI events in real-time

Watch Asterisk logs
tail -f /var/log/asterisk/full | grep -i stasis

text

### Test StasisStart manually

From Asterisk CLI
asterisk -rx "channel originate Local/100@from-internal application Stasis convener"

text

This creates a test channel and sends it to your app without needing a real phone.

---

## Summary

┌────────────────────────────────────────────────────────────┐
│ STASIS INTEGRATION │
├────────────────────────────────────────────────────────────┤
│ │
│ 1. Python connects to ARI WebSocket │
│ 2. Asterisk registers app listener │
│ 3. User calls trigger Stasis(convener) in dialplan │
│ 4. Asterisk sends StasisStart event │
│ 5. Python receives event and takes control │
│ 6. Python controls channel via ARI REST API │
│ 7. When done, Python hangs up or returns control │
│ 8. Asterisk resumes dialplan execution │
│ │
│ Result: External app controls calls programmatically! │
└────────────────────────────────────────────────────────────┘

text

**Key Takeaway:** Stasis is the **bridge** between traditional Asterisk dialplan and modern external application control via ARI. Your Python script becomes the "brain" of the call, with full control over routing, media, and logic. 🧠🎯

---

## Related Documentation

- [System Architecture](architecture.md)
- [Asterisk ARI Official Docs](https://docs.asterisk.org/Asterisk-REST-Interface/)
- [Stasis Application](https://wiki.asterisk.org/wiki/display/AST/Asterisk+ARI)

---
 ✅🚀