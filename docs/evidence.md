# Evidence record

## Historical V1 baseline and September 27 repair

The Basecamp V1 capture at 01:13 UTC September 27 supersedes the earlier inventory below: **34 distinct sources / 244 points**, including retained validation content, and guest backups covering **100, 101 and 102**. These are dated measurements, not a fresh benchmark or proof of every source's retrieval quality. See the [immutable V1 validation](https://github.com/soonerbear22-ux/basecamp-homelab/blob/v1.0.0/docs/validation-v1.md).

On September 27 local time, the workstation was known as **Citadel**. Open WebUI's saved Ollama URL still referenced an unreachable previous endpoint. After a database backup, updating only that saved connection through the application API restored six models and custom assistants without restarting or resetting WebUI. All 99 chats and the account matched the backup. The disabled OpenAI connection was not an alternate local inference backend. See [the incident and physical installation record](https://github.com/soonerbear22-ux/basecamp-homelab/blob/main/docs/changes/2026-09-27.md).


[Home](../README.md)

Updated September 26, 2026 from project conversations, the knowledge-expansion report/manifests, local ComfyUI files and logs, the deployed API source, and a fresh read-only audit. This is not an exhaustive export of every saved memory.

[Sanitized machine-readable summary](../evidence/2026-09-26-summary.json)

| Capability | Evidence | Limit |
| --- | --- | --- |
| Split chat hosting | Owner confirmation and prior service output | No fresh model-performance run |
| FLUX image generation | Saved editor graph, installed assets, successful ComfyUI logs, owner completion report | Sanitized graph not rerun; WebUI API export not included |
| GPU embeddings | Recorded passthrough and TEI deployment; fresh 2560-dimension embedding request | No throughput benchmark |
| Knowledge expansion | Morning 27-document / 135-chunk report; 28/28 targeted retrieval checks | Historical result |
| September 26 retrieval | Later green collection, 101 points, successful semantic query | Two baseline sources at that observation; not current inventory |
| Infrastructure audit | Seven component groups retrieved, three guests and eleven containers running | Dated state; not recovery/security assurance |
| Voice | Historical listening tests; later partial service inventory | Full current voice path and reboot behavior unverified |
| Assistant profiles | Recorded configuration history | Per-profile model assignments not freshly inspected |

## Historical discrepancy

The morning report recorded 235 points. The later live source inventory found only `homelab-master.md` and `homelab-operations.md`, totaling 101. Processed runbooks survive. The cause and intent of the intervening change are unknown; no reingestion or database alteration was performed in this publication task.

## Next evidence to capture

Reconcile the current source inventory, repeat selected retrieval checks, export a sanitized WebUI image API workflow, record controlled model/image benchmarks, and validate voice and full-topology recovery.


## October 3 knowledge recovery evidence

A controlled Arda document recovery was completed with the automatic inbox watcher paused. The final staged and processed files matched by SHA-256, the ingestion state recorded 23 chunks, and an exact Qdrant source count independently returned 23 points. The watcher was then returned to active state.

The same session removed accidentally indexed recovery material from the private corpus and added a preventive filename guard to the ingester. No recovery codes or other secret values are published here.

## October 6 documentation synchronization

The saved October 4 six-file AI Engineer package and unchanged October 3 audit evidence govern this public projection. September 26 machine-readable evidence and the sanitized editor workflow remain unchanged. No new runtime, model, image, voice, ingestion or recovery test ran.

| Audit | Preserved status |
| --- | --- |
| A01 | PARTIALLY RESOLVED — LIVE RECONFIRMATION REQUIRED |
| A02 | PARTIALLY RESOLVED — SOURCE REACCESS AND LIVE ACCEPTANCE REQUIRED |
| A03 | PARTIALLY RESOLVED — STATIC SOURCE/REVISION AUDIT COMPLETE; LIVE CORPUS RECONCILIATION REQUIRED |

A01 preserves installed/running bridge observations and a later management-access gap; the gap does not prove an outage. A02 preserves two architectural limitations without an exploited-bypass claim. A03 preserves completed static analysis and unresolved runtime/corpus acceptance. Detailed audit/remediation remains paused.

Supporting infrastructure projections were read at `basecamp-homelab` commit `73cc6a3` and `homelab-api` commit `4bbd7a5`; neither repository was modified. Their public sources are not automatic evidence of deployed AI revision correspondence.
