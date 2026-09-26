# Image generation with ComfyUI and FLUX

[Home](../README.md) · [Sanitized editor workflow](../workflows/flux1-dev-editor.example.json)

## Recovered implementation

ComfyUI runs on the main Windows PC. The inspected local version is 0.37.0. Startup output identifies an AMD Radeon RX 7900 XTX with about 24 GB VRAM. The local files include FLUX.1 Dev and Schnell diffusion weights, CLIP-L, a scaled FP8 T5 encoder, and a VAE.

The saved `FLUX1-Dev-OpenWebUI` editor graph selects:

| Setting | Saved value |
| --- | --- |
| Diffusion model | `flux1-dev.safetensors` |
| Text encoders | `clip_l.safetensors`, `t5xxl_fp8_e4m3fn_scaled.safetensors` |
| Text encoder device | CPU |
| VAE | `ae.safetensors` |
| Latent size | 1024 × 1024, batch 1 |
| Sampling | 20 steps, CFG 1, res_multistep, simple scheduler |
| Output | Decoded image saved through SaveImage |

These are inspected saved values, not an optimized recommendation. The graph also retains its recorded ModelSamplingAuraFlow node; it has not been replaced with a different assumed standard workflow.

## Integration and evidence

The project conversation records an Open WebUI image-generation integration and direct ComfyUI use. The owner confirmed a completed image job; the local log contains successful prompt-completion entries. One recorded run took 11 minutes 29 seconds. That is a historical execution observation, not a controlled benchmark or performance promise.

Memory pressure and offloading were part of the latest troubleshooting discussion. The owner reported about 74% system RAM use after completion. A proposed smaller 768 × 768 / 12-step test was not recorded as completed.

## Published artifact

The included JSON is a sanitized copy of the saved **editor workflow**, not a confirmed Open WebUI API-format export. Personal prompt text was replaced with a neutral example, stale model-download metadata was removed, and graph links/settings were preserved. Graph structure was checked locally; no new image was generated to validate the sanitized prompt.

Import into an isolated ComfyUI test workflow and review before use. Export the correct API format and verify WebUI field mappings before changing that integration. Model weights, generated images, private URLs, and installation files are not distributed.
