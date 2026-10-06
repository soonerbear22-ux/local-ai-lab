# Architecture

[Home](../README.md)

## Placement — canonical synchronization October 6

| System | Responsibility |
| --- | --- |
| Elros — Windows workstation (historically Citadel) | Ollama chat inference and ComfyUI image generation |
| Hornburg / core-services VM 100 | Open WebUI, Open Terminal, Homelab API, Qdrant, document ingestion, supporting services |
| Hornburg / Bombadil (native ai-worker VM 102) | Dedicated embedding service; historical RTX 3060 passthrough / TEI / Qwen3-Embedding-4B; loaded model revision unverified |

The main PC's historically inspected ComfyUI log identifies an AMD Radeon RX 7900 XTX with approximately 24 GB VRAM and 64 GB system RAM. This is historical hardware evidence, distinct from Hornburg's NVIDIA embedding GPU.

## Requests and data flow

Chat requests go from WebUI to Ollama. The historical image integration sends jobs to ComfyUI using an API workflow. A saved editor-format FLUX workflow was inspected; its sanitized copy is included separately.

Knowledge queries go through Homelab API to ai-worker for embeddings, then Qdrant for matching chunks with source metadata. Live operational questions use diagnostic endpoints rather than treating old knowledge as current telemetry.

Documents follow the Samba inbox and systemd ingestion path. The indexed corpus must be verified separately from the source files and ingestion-state records.

## Historical boundaries

Open WebUI previously ran on a Raspberry Pi. Successful power-recovery reports from that era do not establish recovery of the current topology.

Voice troubleshooting used a separate development WebUI. The September 26 inventory did not contain that historical test container, so it is not shown as a current deployed component. The production WebUI remained healthy in the reviewed record.

## Engineer and dependency boundaries

The October 3 canonical observation places a native Python engineer bridge on core-services, with an owner-only local socket and persistent plan receipts. The WebUI tool calls that bridge; it is separate from Homelab API and Open Terminal. No public committed revision is asserted to match its uncommitted deployed additions.

Retrieval depends on Bombadil embeddings and Qdrant; conversational inference depends on Elros and the selected Ollama model. A green API or monitoring endpoint is narrower than model/tool or corpus acceptance. October 4 output showed Qdrant and WebUI running on separate Compose networks, not a new application-readiness test.

Hornburg's native name is verified; Citadel/ai-worker and compatibility Basecamp paths/routes are preserved. Infrastructure inventory, storage and backups belong to [Middle-earth Homelab](https://github.com/soonerbear22-ux/basecamp-homelab/blob/main/docs/current-state.md). Its October 6 projection records all six monitoring directions verified, with reboot and notification acceptance still pending. This does not revalidate AI workloads.
