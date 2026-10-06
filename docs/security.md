# Security and publication scope

[Home](../README.md)

Published documentation omits private network addresses, tailnet identifiers, passwords, tokens, configuration databases, and raw chat history.

The inference service, WebUI, voice endpoints, terminal integration, and diagnostic API have different trust requirements. Keep them restricted to intended users and network paths. This portfolio does not assert that an authentication or authorization audit has been completed.

The diagnostic API exposes only GET tools, but its Docker client and host visibility remain privileged. A read-only Docker socket mount does not enforce read-only Docker API access. See the [API security discussion](https://github.com/soonerbear22-ux/homelab-api/blob/main/docs/security.md).

Model-generated instructions and retrieved documents should be treated as untrusted input. Keep terminal access separate from diagnostic-only assistants and review executable actions.

## Retrieval and image artifacts

The public workflow has a neutral replacement prompt and excludes generated images and model weights. Internal knowledge contains operational facts and stays private; only aggregate validation evidence is published. Returned source text is untrusted content and should not gain execution privileges through a tool-using assistant.

The public API source verifies Proxmox certificates as a publication adaptation. No new deployment correspondence is established here; live trust configuration remains private. The API's expanded read operations do not establish authentication at its inbound boundary or least privilege on upstream credentials.


## Knowledge-ingestion secret guard

On October 3, the ingestion pipeline gained a filename-level guard for common secret-bearing filenames, including password, credential, recovery-code, private-key and environment-file patterns. Matching files are rejected before extraction or embedding.

This control reduces accidental indexing risk but is intentionally described as a heuristic. It does not inspect arbitrary document contents for secrets, so private source review and publication hygiene remain required.

## Bounded engineer approval limits

The engineer bridge is distinct from GET diagnostic tools and terminal access. Preserved A02 evidence supports same-plan denial, but does not durably suppress replacement proposals; execution rechecks several conditions without explicitly rechecking `recover`. Neither finding is described as exploited or a demonstrated bypass. Intended denial scope and recovery-revocation timing remain policy decisions.

Model prompts, retrieved text and TODO entries never authorize execution. Effective sharing/identity grants, browser confirmation and interrupted/concurrent execution acceptance remain unresolved. Historical removal of a sensitive source does not prove credential invalidation or complete historical purge. Private canonical contents, raw receipts and protected approval material are not published.
