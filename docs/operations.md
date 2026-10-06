# Operations and troubleshooting

[Home](../README.md)


## Historical V1 baseline and September 27 repair

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

This is a historical observation, not a current Hornburg/AI recovery-time objective. The later Basecamp V1 record documents host reboot recovery; complete voice-service recovery remains unverified.

## September 26 operational changes

The September 26 API observation could retrieve seven infrastructure component groups in one request and report partial failures. Knowledge health checks make real embedding and vector-query requests. The Basecamp GPU was assigned to embeddings, and the main PC handles ComfyUI image jobs.

The knowledge expansion's morning result differed from the September 26 evening index. Compare source filenames, hashes, chunk counts, processed files, and actual retrieval before reingestion. A green Qdrant collection and a nonempty search result do not prove corpus completeness. See [knowledge evidence](knowledge.md).

The earlier inspected daily backup job covered core-services and Pi-hole but excluded ai-worker. The later V1 capture documented coverage for all three guests, superseding that earlier scope. Off-host recovery and isolated restoration were unverified in that September 26 scope. Current infrastructure restore evidence belongs to the Homelab repository; AI application-consistency acceptance remains separate.

## Next operational evidence

Capture sanitized versions, service ownership, startup dependencies, backup scope, a restore test, and current-topology recovery behavior. Avoid publishing configuration databases or raw diagnostic exports that include credentials or private network information.


## October 3 role-name and knowledge notes

Current role names use Hornburg for the Proxmox host, Elros for the Windows workstation, and Bombadil for the AI-worker role. Historical records may still use Basecamp, Citadel, and ai-worker because those names identify underlying hosts/guests or earlier documentation.

The October 3 selected-source check confirmed one recovered operations document in the private semantic knowledge corpus; current corpus completeness remains unverified. Recovery work confirmed that the watched inbox should not be used as an editing workspace: stage documents elsewhere, pause the path watcher when necessary, and move only completed sources into the inbox for deliberate ingestion.

## Canonical operating and recovery limits

Before any separately authorized change, identify actual host/account, nonsecret effective configuration and installed revision. A lost management connection is an access gap, not service failure. Stage completed sources outside the watched inbox; reconcile exact bytes, state and vector generations before retrying a partial ingestion. Do not reset state or Qdrant as a shortcut.

Recovery planning must preserve consistent source/processed/state and Qdrant revisions, embedding configuration, WebUI database/tool/model settings, and engineer source/configuration/receipts and protected approval material. Generic app-data copying does not prove database consistency. Recorded cron/flock supervision does not prove actual bridge reboot recovery. Host/guest restore evidence does not substitute for AI application acceptance.

The historical inventory collector has a narrow container scope; its timer is an alternative to cron, not proof of two active schedulers. Automatic publication was not established. Future closeout should consider affected public repositories alongside canonical updates, while keeping publication, deployment, Project adoption, ingestion and retrieval as separate outcomes. Ongoing workflow creation is the next dedicated job and is not built here.
