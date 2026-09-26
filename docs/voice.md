# Voice integration

[Home](../README.md)

## Historical implementation and result

The isolated voice test used Faster-Whisper `base` for speech recognition, `qwen3:14b` for generation, and Kokoro-FastAPI CPU with `bm_daniel` for speech output on the main PC.

The owner reported improved Daniel playback and cleaner follow-up replies in the separate development WebUI. Browser microphone access used a secure HTTPS context. This remains a historical listening test, not proof of a particular root cause or a production upgrade.

## September 26 observations

The morning review found production Open WebUI healthy and a Windows `kokoro-tts` container running. The historical voice-test container was absent from the inspected core-services inventory even though its saved HTTPS route remained configured.

Current Whisper process state, exact endpoint settings, end-to-end voice behavior, and automatic recovery were not verified. A saved route or a running TTS container does not prove the full pipeline works.

## Next validation

Test microphone capture, transcription, response text, synthesis, and browser playback separately. Use a short fixed utterance and a longer reply. Record results without publishing private recordings. Verify startup after reboot before claiming recovery is complete.
