# Asterisk OFP - Multi-Agent AI Voice System

Production-ready conversational AI platform built on Asterisk PBX with OFP (Open Voice Network) protocol compliance.

## Overview

This project demonstrates a **multi-agent AI voice system** that orchestrates specialized AI agents in a conference call environment, featuring:

- 🎤 Real-time speech recognition (Deepgram ASR)
- 🤖 Dynamic AI responses (OpenAI GPT-4 + Deepgram TTS)
- 🎵 Zero-latency async hold music
- 📋 OFP v1.0.0 protocol implementation
- 🔄 Smart agent floor control management

## Architecture

![System Architecture](assets/architecture-diagram.png)

The system uses a **mixed agent architecture** combining:
- **Agent0**: Async hold music (fills processing time)
- **Agent1**: Dynamic LLM agent (GPT-4 powered responses)
- **Agent2-3**: Static stub agents (prerecorded audio)

See [Architecture Documentation](docs/ARCHITECTURE.md) for details.

## Key Features

### Zero-Latency User Experience
Agent0 plays "please wait" message asynchronously while Agent1 generates response, eliminating perceived waiting time.

### Smart Playback Management
ARI playback status polling ensures precise audio completion detection without fixed delays.

### OFP Protocol Compliance
Full implementation of Open Voice Network's Open Floor Protocol v0.9.2:
- `grantFloor` - Convener grants speaking permission
- `requestFloor` - Agent requests to speak
- `yieldFloor` - Agent releases floor

## Documentation

- [**System Architecture**](docs/ARCHITECTURE.md) - Complete technical overview
- [**OFP Protocol Implementation**](docs/OFP_PROTOCOL.md) - Floor control protocol
- [**Agent Floor Control**](docs/AGENT_FLOOR_CONTROL.md) - Multi-agent orchestration
- [**Stasis Flow**](docs/STASIS_FLOW.md) - Asterisk ARI integration

## Technology Stack

| Component | Technology |
|-----------|-----------|
| PBX | Asterisk 20+ with ARI |
| Language | Python 3.10+ |
| ASR | Deepgram API |
| LLM | OpenAI GPT-4 |
| TTS | Deepgram Aura |
| Protocol | OFP v0.9.2 (OVON) |
| Audio | SLIN16/ULAW 8kHz |

## Status

🚧 **Documentation Phase**: System is fully functional. Source code will be released soon.

Current release: **Documentation v1.0**

## Use Cases

- Multi-agent customer service systems
- AI-powered call centers
- Voice-based booking assistants
- Conference call orchestration
- Interactive voice response (IVR) systems

## Contributing

Contributions and feedback welcome! Open an issue or submit a PR.

## License

MIT License - see [LICENSE](LICENSE) file

## Author

**Diego Gosmar**
- GitHub: [@diegogosmar](https://github.com/diegogosmar)

## Acknowledgments

- Open Voice Network (OVON) for OFP protocol specification
- Asterisk community for ARI framework
- Deepgram and OpenAI for AI services

---

⭐ Star this repo if you find it useful!
