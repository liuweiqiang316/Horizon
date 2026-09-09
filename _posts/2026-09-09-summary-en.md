---
layout: default
title: "Horizon Summary: 2026-09-09 (EN)"
date: 2026-09-09
lang: en
---

> From 36 items, 2 important content pieces were selected

---

**Technology News**
1. [OpenAI Claims Navier–Stokes Resolution](#item-tech-news-1) ⭐️ 9.0/10
2. [vLLM 0.29.0 makes Model Runner V2 default](#item-tech-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI Claims Navier–Stokes Resolution](https://simonwillison.net/2026/Sep/8/on-navier-stokes/) ⭐️ 9.0/10

Simon Willison links to OpenAI’s claim that an unreleased model produced a resolution of the Navier–Stokes existence and smoothness problem, one of the seven Millennium Prize Problems carrying a $1,000,000 prize since May 24, 2000. OpenAI said it began evaluating open Millennium Prize problems on September 1 after hearing rumors of major results, launched agents that reached a Navier–Stokes resolution on September 5 after about 88 hours, and then completed Lean formalization and verification using GPT‑6 Astra in another 17 hours. The company reported 4.9 million agent messages and about 300 billion output tokens across attempted problems, including 2.7 million messages and roughly 130 billion output tokens for Navier–Stokes; Willison notes that 300 billion GPT‑6 Astra output tokens at public API prices would cost about $15,000,000, though the internal model’s cost structure is unknown. The result is entangled with accusations from NYU professor Tristan Buckmaster, who said he and Levent Alpöge of Anthropic had worked on related problems for nearly a year using Claude and Codex, had a breakthrough on August 15, and later learned OpenAI had started a related effort after information about their work circulated. OpenAI said its researchers and agents did not see Buckmaster and Alpöge’s work before public release and that no specific user data was accessed, but it also said it could not rule out that de-identified data from their product usage had helped improve its models, raising concerns about AI labs, training data, priority, and unpublished mathematical work.

rss · Simon Willison · Sep 8, 23:55

**「Background」** The Navier–Stokes existence and smoothness problem asks whether the equations that model fluid motion always have well-behaved solutions in three dimensions or can develop singularities. It is one of the Clay Mathematics Institute’s seven Millennium Prize Problems, each associated with a $1 million prize, and OpenAI says its claimed result shows finite-time singularity formation for Navier–Stokes dynamics.

**「Impact」** Researchers using hosted AI systems for unpublished mathematical work may need stricter confidentiality and data-use safeguards, because this case raises concrete priority and training-data concerns around AI-assisted discovery.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/navier-stokes-solution/">On the Navier–Stokes Millennium Prize Problem | OpenAI</a></li>

</ul>
</details>

**Tags**: `#AI-assisted mathematics`, `#OpenAI`, `#Navier-Stokes`, `#research`, `#technology industry`

---

<a id="item-tech-news-2"></a>
### [vLLM 0.29.0 makes Model Runner V2 default](https://github.com/vllm-project/vllm/releases/tag/v0.29.0) ⭐️ 8.0/10

vLLM v0.29.0 was released with 594 commits from 277 contributors, including 91 new contributors. The main change is that Model Runner V2 is now the default for all models, with MRV1 still used for a few ROCm models and unsupported features. The release adds memory and inference improvements such as CUDA graph memory profiling for KV cache auto-sizing, batch-sharded sampling to reduce per-step logits memory by 1/TP, speculative decoding enhancements, Mamba prefix caching with reported 9%–25% TTFT improvement, and several Kimi K3 and DeepSeek V4 optimizations. It also expands model support for Hy4-preview, Qwen3.8-Flash-Next, GraniteSWA, GraniteMoeSWA, NemotronH\_Omni\_Reasoning\_V3, Kimi K3 NVFP4 checkpoints, and related multimodal and LoRA paths. Release artifacts include PyPI CUDA 13.0 wheels, ROCm and XPU install options, Docker images for CUDA 13.0, CUDA 12.9, Ubuntu 24.04, ROCm, CPU, and XPU, plus separate prebuilt wheels for CUDA 12.9, CUDA 13.0, CPU, and XPU.

github · khluu · Sep 9, 08:54

**「Background」** vLLM is an open-source library for high-throughput, memory-efficient LLM inference and serving, originally developed at UC Berkeley’s Sky Computing Lab. Its relevance comes from serving-oriented features such as PagedAttention for KV-cache memory management, continuous batching for throughput, and prefix caching for prompt reuse, with support across multiple model architectures and hardware backends.

**「Impact」** Teams serving LLMs with vLLM get a new default execution path and broader model coverage, but should check breaking changes including removed deprecated architectures, the PyAV backend removal, and the deprecation of \`python -m vllm.entrypoints.openai.api\_server\` in favor of \`vllm serve\`.

<details><summary>References</summary>
<ul>
<li><a href="https://zeroentropy.dev/concepts/vllm-serving/">vLLM serving : PagedAttention and continuous batching for LLMs</a></li>
<li><a href="https://github.com/vllm-project/vllm">vllm -project/ vllm : A high-throughput and memory-efficient inference ...</a></li>

</ul>
</details>

**Tags**: `#vLLM`, `#LLM inference`, `#open source`, `#CUDA`, `#model serving`

---