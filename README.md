# Local AI Lab

A working self-hosted AI environment built and operated by Logan: Open WebUI on Basecamp, Ollama and ComfyUI on the Citadel Windows workstation, dedicated GPU embeddings, and tools that retrieve knowledge and inspect the lab.

**Documentation updated October 3, 2026**, including the Arda knowledge recovery and ingestion hardening work. This portfolio distinguishes live observations, historical tests, and unfinished validation.

## Architecture

```mermaid
flowchart LR
    User["User"] --> UI["Open WebUI on Basecamp"]
    UI --> Ollama["Ollama on Citadel Windows workstation"]
    UI --> Comfy["ComfyUI / FLUX on Citadel Windows workstation"]
    UI --> API["Homelab API"]
    API --> Live["Docker / Proxmox / Prometheus"]
    API --> Embed["Qwen3-Embedding-4B on ai-worker"]
    API --> Qdrant["Qdrant on core-services"]
    Inbox["Samba document inbox"] --> Ingest["systemd ingestion"]
    Ingest --> Embed
    Ingest --> Qdrant
```

## Implemented and evidenced

| Area | Current evidence |
| --- | --- |
| Chat | Ollama on the main PC; owner preference is the local tag `qwen3.6:35b` |
| Image generation | ComfyUI 0.37.0, saved FLUX Dev workflow, installed model assets, successful generation logs |
| Dedicated embeddings | RTX 3060 passthrough to ai-worker; Qwen3-Embedding-4B; 2560-dimensional request succeeded |
| Semantic knowledge | Samba ingestion, Qdrant, provenance-bearing search, and health checks |
| Live tools | Thirteen API operations, including Proxmox inventory and a combined audit |
| Specialized assistants | Research, homelab diagnostics, and 3D print design profiles |
| Voice | Historical Faster-Whisper/Kokoro tests; current full path and recovery not revalidated |

The final Basecamp V1 capture recorded 34 sources / 244 points, including retained validation documents. On October 3, the live knowledge pipeline was additionally hardened with a secret-bearing filename guard and a controlled recovery/reingestion workflow for the Arda operations document. Earlier September 26 inventories differed; [the evidence record](docs/evidence.md) preserves those historical observations. Counts are dated measurements, not corpus-quality or uptime guarantees.

Citadel's renamed backend connection was repaired in Open WebUI; six models and custom assistants returned while all 99 chats were preserved. See [operations](docs/operations.md).

## Read the project

- [Architecture](docs/architecture.md)
- [Image generation and workflow snapshot](docs/image-generation.md)
- [Knowledge pipeline and evaluation](docs/knowledge.md)
- [Model evaluation](docs/model-evaluation.md)
- [Voice history and current limits](docs/voice.md)
- [Assistant profiles](docs/assistants.md)
- [Operations](docs/operations.md) · [Security](docs/security.md)
- [Dated evidence](docs/evidence.md)

Related: [Basecamp infrastructure](https://github.com/soonerbear22-ux/basecamp-homelab) · [Homelab API source and tests](https://github.com/soonerbear22-ux/homelab-api)

These are configured integrations and assistant profiles, not newly trained foundation models. No standardized model ranking or hosted-product parity claim is made. Private knowledge contents, endpoints, model weights, and credentials are excluded.
