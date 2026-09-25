# Architecture

[Home](../README.md)

## Current roles

| System | Responsibility |
| --- | --- |
| Main Windows PC | Ollama inference; voice services used during the isolated voice test |
| Basecamp / core-services | Docker-hosted Open WebUI and supporting homelab services |
| Homelab API | Six GET operations for live status and metric history |
| Prometheus | Historical resource metrics and disk I/O inputs |

Separating the interface from inference allows the services host to stay available independently. Responses requiring Ollama still depend on the main PC being awake, the service running, and the network path working.

Open WebUI connects to Ollama directly. Private connection details are not published. The API supplies live data rather than expecting a knowledge document to describe changing CPU, memory, or process state.

## Evolution

Open WebUI previously ran on a Raspberry Pi. Historical reboot and power-recovery tests belong to that earlier layout. Open WebUI now runs on Basecamp; those old results do not verify recovery of the current deployment.

Voice troubleshooting used a separate development WebUI with its own data while preserving the production instance. This distinction matters when interpreting successful voice tests.

## Boundaries

Image generation is owner-confirmed but its backend placement has not been recovered. No backend is invented in the architecture. This repository also does not claim high availability, Internet-facing hosting, or a fully automated rebuild.
