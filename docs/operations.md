# Operations and troubleshooting

[Home](../README.md)


## Latest recorded baseline and repair

The Basecamp V1 capture at 01:13 UTC September 27 supersedes the earlier inventory below: **34 distinct sources / 244 points**, including retained validation content, and guest backups covering **100, 101 and 102**. These are dated measurements, not a fresh benchmark or proof of every source's retrieval quality. See the [immutable V1 validation](https://github.com/soonerbear22-ux/basecamp-homelab/blob/v1.0.0/docs/validation-v1.md).

On September 27 local time, the workstation was known as **Citadel**. Open WebUI's saved Ollama URL still referenced an unreachable previous endpoint. After a database backup, updating only that saved connection through the application API restored six models and custom assistants without restarting or resetting WebUI. All 99 chats and the account matched the backup. The disabled OpenAI connection was not an alternate local inference backend. See [the incident and physical installation record](https://github.com/soonerbear22-ux/basecamp-homelab/blob/main/docs/changes/2026-09-27.md).

## Diagnostic sequence

1. Check the interface and inference host independently.
2. Confirm Ollama lists the intended model and that the saved profile uses the exact tag.
3. Test connectivity from the WebUI host, not only from the inference PC.
4. Separate static knowledge retrieval from live tool results.
5. Refresh OpenAPI discovery after adding an operation and test in a fresh conversation.
6. Reproduce voice issues in the isolated instance before changing production.

A recorded “model not found” investigation examined the model list and WebUI connection settings. A separate tool integration investigation showed that an existing conversation could retain an old tool schema; a fresh conversation exposed the newly added disk operation.

## Recovery evidence

In the earlier Raspberry Pi + Windows topology, the owner reported successful simultaneous reboot and power-off recovery. The complete power recovery took roughly five minutes and required Windows login without manual service starts.

This is a historical observation, not a current Basecamp recovery-time objective. The later Basecamp V1 record documents host reboot recovery; complete voice-service recovery remains unverified.

## September 26 operational changes

The current API can retrieve seven infrastructure component groups in one request and report partial failures. Knowledge health checks make real embedding and vector-query requests. The Basecamp GPU is assigned to embeddings, and the main PC handles ComfyUI image jobs.

The knowledge expansion's morning result differs from the current index. Compare source filenames, hashes, chunk counts, processed files, and actual retrieval before reingestion. A green Qdrant collection and a nonempty search result do not prove corpus completeness. See [knowledge evidence](knowledge.md).

The earlier inspected daily backup job covered core-services and Pi-hole but excluded ai-worker. The later V1 capture documented coverage for all three guests, superseding that earlier scope. Off-host recovery and isolated restoration remain unverified.

## Next operational evidence

Capture sanitized versions, service ownership, startup dependencies, backup scope, a restore test, and current-topology recovery behavior. Avoid publishing configuration databases or raw diagnostic exports that include credentials or private network information.
