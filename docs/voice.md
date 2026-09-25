# Voice integration

[Home](../README.md)

## Recovered implementation

- Speech recognition: Faster-Whisper using the `base` model on the main Windows PC.
- Speech synthesis: Kokoro-FastAPI CPU container on the main PC.
- Selected voice during testing: `bm_daniel`.
- Browser interface: isolated development Open WebUI with separate data.
- Model during that test: `qwen3:14b`.

Production voice exhibited repetition. In the isolated development instance, the owner confirmed Daniel sounded better and remained clean during follow-up testing. This is a bounded test result; it does not prove a single root cause or establish that production was upgraded.

## Browser access

Microphone access required a secure browser context. The history records using Tailscale Serve HTTPS and changing a foreground session to a persistent background mapping. Tailnet addresses and host-specific configuration are excluded.

## Follow-up checks

Verify production behavior separately, document pinned versions, measure STT and TTS latency, and test voice-service startup after reboot. Automatic startup of every voice component is not established by the recovered evidence.
