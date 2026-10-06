# Assistant profiles and image generation

[Home](../README.md)

These are purpose-built Open WebUI profiles assembled through prompts, knowledge, tools, and model selection. They are not newly trained models.

| Profile | Documented configuration |
| --- | --- |
| AI Lab Research Assistant | Research workflow; Open Terminal integration renamed AI Lab Terminal |
| Homelab Diagnostics | Read-only OpenAPI diagnostic operations; terminal disabled |
| 3D Print Design Assistant | Guidance for tolerances, materials, orientation, supports, and fit; OpenSCAD-oriented workflow; printer manual attached; code interpreter enabled; terminal disabled |

The diagnostics and design profiles used `gpt-oss:20b` at creation. The owner's later Qwen preference does not prove every saved profile was changed.

Terminal execution is a separate privilege from reading diagnostic data. A profile having a terminal available does not establish a security boundary on its own.

## Image generation

The September 26 review identifies ComfyUI and FLUX on the main Windows PC, a saved editor workflow, and completed-generation logs. See [image generation](image-generation.md) for the inspected settings, sanitized graph, and verification limits.

An attached printer manual and a design profile do not establish that every model accepts images or that generated designs have been printed and validated.

## Recorded API tool scope

The inspected public Homelab API exposes thirteen operations, including semantic knowledge search, dependency health, Proxmox host/guest/storage telemetry, and a combined audit. Its schema contains routing and interpretation guidance to distinguish stored documentation from live state and avoid diagnosing failures from ambiguous metrics. That schema guidance is not an authorization boundary or proof that every saved profile has refreshed its tool cache.

## Engineer profile — October 3 canonical observation

WebUI profile `homelab-engineer` used `qwen3.6:35b`, native function calling, temperature 0.1, and only `homelab_engineer`; terminal and listed built-ins were disabled. Recorded methods cover inventory, diagnosis, metric history, knowledge search, proposals, plan status and approved recovery. Effective sharing grants and fresh browser acceptance remain unverified.

An isolated fixture supports rejection of forged keys, replay and recovery of healthy Prometheus. Browser confirmation was deferred; only the saved `live_guest_state` model case passed. These are limited dated observations, not full model acceptance or unrestricted execution authority. See [current state](current-state.md).
