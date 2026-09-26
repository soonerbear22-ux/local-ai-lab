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

## Current tool scope

Homelab API now exposes thirteen operations, including semantic knowledge search, dependency health, Proxmox host/guest/storage telemetry, and a combined audit. Its schema contains routing and interpretation guidance to distinguish stored documentation from live state and avoid diagnosing failures from ambiguous metrics. That schema guidance is not an authorization boundary or proof that every saved profile has refreshed its tool cache.
