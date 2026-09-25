# Operations and troubleshooting

[Home](../README.md)

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

This is a historical observation, not a current Basecamp recovery-time objective. Current Basecamp and voice-service recovery still need an explicitly recorded test.

## Next operational evidence

Capture sanitized versions, service ownership, startup dependencies, backup scope, a restore test, and current-topology recovery behavior. Avoid publishing configuration databases or raw diagnostic exports that include credentials or private network information.
