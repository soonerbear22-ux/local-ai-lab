# Knowledge pipeline and retrieval evidence

## Latest recorded baseline and repair

The Basecamp V1 capture at 01:13 UTC September 27 supersedes the earlier inventory below: **34 distinct sources / 244 points**, including retained validation content, and guest backups covering **100, 101 and 102**. These are dated measurements, not a fresh benchmark or proof of every source's retrieval quality. See the [immutable V1 validation](https://github.com/soonerbear22-ux/basecamp-homelab/blob/v1.0.0/docs/validation-v1.md).

On September 27 local time, the workstation was known as **Citadel**. Open WebUI's saved Ollama URL still referenced an unreachable previous endpoint. After a database backup, updating only that saved connection through the application API restored six models and custom assistants without restarting or resetting WebUI. All 99 chats and the account matched the backup. The disabled OpenAI connection was not an alternate local inference backend. See [the incident and physical installation record](https://github.com/soonerbear22-ux/basecamp-homelab/blob/main/docs/changes/2026-09-27.md).


[Home](../README.md) · [Basecamp pipeline](https://github.com/soonerbear22-ux/basecamp-homelab/blob/main/docs/knowledge-pipeline.md)

## Implemented path

Finished documents enter the Windows mapped Samba inbox. A systemd path unit invokes extraction and heading-aware chunking on core-services. Qwen3-Embedding-4B on ai-worker generates 2560-dimensional vectors; Qdrant stores them with source, section, chunk sequence, file type, hash, and ingestion time.

Homelab API exposes semantic search and a dependency-aware health operation. Search returns text and provenance. The health operation makes a real embedding request, reads collection metadata, and performs a vector query.

The ingester supports Markdown/text, text-bearing PDF, and DOCX paragraphs/headings. It does not provide OCR or DOCX table extraction. Its target chunk size is 1400 characters with 200-character overlap for long sections.

## Historical expansion result

At 08:57 UTC on September 26, the verified expansion added 27 documents / 135 chunks, removed one test point, and reported 235 total points. Each new source matched its manifest hash and chunk count. All 28 fixed questions retrieved the expected source in the top five; one also checked a specific fact in returned text.

These are targeted retrieval checks, not an independent benchmark or complete evaluation of generated answers. One provenance section was clarified and reingested during evaluation.

## Earlier September 26 evening check

At 21:42 UTC, the live collection was green and a real semantic query returned a result, but the total was 101. Direct inventory found master knowledge (19 points) and operations knowledge (82 points) only.

The 27 runbook files remain in the processed folder. Their local batch copies, manifests, and morning verification reports remain available privately. Why the live source set changed is unverified. Do not treat the morning 28/28 result as a current pass for those runbooks.

## Reliability limits

The three-second pre-start delay mitigated the tested Samba transfer race but does not prove arbitrary files are complete. Source replacement embeds first, then deletes and upserts separately, leaving a failure window after deletion. A processed file, state entry, or healthy database does not independently prove successful current retrieval.


## October 3 recovery and hardening

The watched inbox is activated by a systemd `DirectoryNotEmpty` path unit, so files can be consumed almost immediately after they appear. During recovery work, the watcher was paused and the replacement document was staged outside the inbox before a deliberate one-time ingest.

The Arda operations document was recovered, rebuilt and reingested. The final controlled ingest produced 23 chunks. The staged and processed copies had matching SHA-256 values, and an exact Qdrant source count also returned 23 points.

A private recovery-code file was discovered in the corpus during the same maintenance session. It was removed from the knowledge tree and its Qdrant points and state entry were deleted. The ingestion script now rejects filenames containing common password, secret, credential, recovery-code, private-key and environment-file indicators before embedding. This is a filename-based preventive control, not full content secret detection.
