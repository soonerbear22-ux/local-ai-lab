# Security and publication scope

[Home](../README.md)

Published documentation omits private network addresses, tailnet identifiers, passwords, tokens, configuration databases, and raw chat history.

The inference service, WebUI, voice endpoints, terminal integration, and diagnostic API have different trust requirements. Keep them restricted to intended users and network paths. This portfolio does not assert that an authentication or authorization audit has been completed.

The diagnostic API exposes only GET tools, but its Docker client and host visibility remain privileged. A read-only Docker socket mount does not enforce read-only Docker API access. See the [API security discussion](https://github.com/soonerbear22-ux/homelab-api/blob/main/docs/security.md).

Model-generated instructions and retrieved documents should be treated as untrusted input. Keep terminal access separate from diagnostic-only assistants and review executable actions.
