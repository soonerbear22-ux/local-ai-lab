# Architecture

[Home](../README.md)

## Placement (role naming updated October 3)

| System | Responsibility |
| --- | --- |
| Elros — Windows workstation (historically Citadel) | Ollama chat inference and ComfyUI image generation |
| Hornburg / core-services VM 100 | Open WebUI, Open Terminal, Homelab API, Qdrant, document ingestion, supporting services |
| Hornburg / Bombadil (ai-worker VM 102) | RTX 3060 12 GB passthrough and Qwen3-Embedding-4B through TEI |
| Hornburg / Pi-hole LXC 101 | Separate DNS filtering |
| Hornburg / Arda VM 105 | Dedicated AzerothCore WotLK realm; documented in Basecamp infrastructure repo |

The main PC's ComfyUI log identifies an AMD Radeon RX 7900 XTX with approximately 24 GB VRAM and 64 GB system RAM. This is distinct from Basecamp's NVIDIA embedding GPU.

## Requests and data flow

Chat requests go from WebUI to Ollama. The recorded image integration sends jobs to ComfyUI using an API workflow. A saved editor-format FLUX workflow was inspected; its sanitized copy is included separately.

Knowledge queries go through Homelab API to ai-worker for embeddings, then Qdrant for matching chunks with source metadata. Live operational questions use diagnostic endpoints rather than treating old knowledge as current telemetry.

Documents follow the Samba inbox and systemd ingestion path. The indexed corpus must be verified separately from the source files and ingestion-state records.

## Historical boundaries

Open WebUI previously ran on a Raspberry Pi. Successful power-recovery reports from that era do not establish recovery of the current topology.

Voice troubleshooting used a separate development WebUI. The September 26 inventory did not contain that historical test container, so it is not shown as a current deployed component. The production WebUI remained healthy in the reviewed record.
