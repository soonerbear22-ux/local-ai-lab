# Model evaluation

[Home](../README.md)

## Recorded model history

The owner reports repeated comparisons across Gemma, DeepSeek, GPT, and Qwen, with a current preference described as “qwen35b.”

Historical Ollama output identifies the local tag as **`qwen3.6:35b`**, with 35.5B parameters and Q4_K_M quantization. This is a recorded local model identifier, not a claim about an official upstream release or download location.

Other recovered installed identifiers include `deepseek-r1:14b`, `qwen3:14b`, `gpt-oss:20b`, and Gemma tags. Installation alone does not establish comparative performance.

The isolated voice test used `qwen3:14b`. Assistant profiles were initially configured with `gpt-oss:20b`; their current individual model assignments have not been re-audited.

## What the evidence supports

Model comparisons occurred more than once, and the owner selected a preferred model. The recovered history does not supply a complete, comparable benchmark dataset. Accordingly, this repository publishes no fabricated throughput, latency, accuracy ranking, or claims of superiority.

## Repeatable benchmark plan

For the next evaluation, record:

| Field | Purpose |
| --- | --- |
| Exact tag and digest | Identify the tested artifact |
| Hardware, runtime, quantization, context size | Make resource constraints explicit |
| Fixed prompt set and output limits | Compare equivalent workloads |
| Cold and warm runs | Separate loading from generation |
| Time to first token, total duration, generated tokens | Describe latency and throughput |
| Tool-call correctness and answer quality rubric | Evaluate useful behavior |
| Several runs and failures | Show variability rather than a best-case result |

Publish sanitized raw results alongside the methodology before adding comparative charts. This plan is not a claim that a standardized suite has already been run.

## September 26 review

No new controlled chat-model benchmark was recovered during this update. Dedicated Qwen3-Embedding-4B retrieval and ComfyUI/FLUX image generation are separate workloads; their validation results do not establish a new ranking of the chat models above.
