---
layout: default
title: "Horizon Summary: 2026-07-25 (EN)"
date: 2026-07-25
lang: en
---

> From 24 items, 4 important content pieces were selected

---

1. [vLLM v0.26.0 Expands Model Support and Cross-Vendor Inference Optimization](#item-1) ⭐️ 8.0/10
2. [SGLang v0.5.16 adds DSpark and optimized Inkling support.](#item-2) ⭐️ 8.0/10
3. [Android Could Soon Restrict On-Device ADB Access.](#item-3) ⭐️ 8.0/10
4. [Anthropic introduces Claude Opus 5.](#item-4) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [vLLM v0.26.0 Expands Model Support and Cross-Vendor Inference Optimization](https://github.com/vllm-project/vllm/releases/tag/v0.26.0) ⭐️ 8.0/10

vLLM v0.26.0 was released with 411 commits from 212 contributors, including 61 first-time contributors. It adds a full support stack for the Inkling model family, cross-platform DeepSeek-V4 optimizations, expanded speculative decoding and quantization features, and fp32 generation heads for improved accuracy. The release gives model-serving teams broader hardware and model choices while targeting lower latency, higher throughput, reduced memory use, and better numerical accuracy. Its optimizations span NVIDIA, AMD ROCm, and XPU paths, reflecting growing demand for portable LLM inference rather than dependence on a single accelerator vendor. DeepSeek-V4 gains include a specialized routing kernel reporting a 2.94% end-to-end TPOT improvement, a 1.5–2× faster fused_topk_bias kernel, and repeat/copy removal yielding another 1.8% end-to-end TPOT improvement. The release also permits attention backends to be selected per KV-cache group, adds tiered KV offloading and object-store support, and extends the Rust frontend with video, audio, and a native vllm-bench port.

github · khluu · Jul 25, 10:38

**Background**: vLLM is an LLM inference and serving engine designed to execute trained models efficiently on accelerator hardware. Speculative decoding reduces latency by drafting multiple tokens and then verifying them, while quantization uses lower-precision numerical formats to reduce model memory requirements and potentially improve inference speed. NVIDIA ModelOpt supports formats including NVFP4, and Hopper is NVIDIA’s GPU architecture used by products such as the H100.

<details><summary>References</summary>
<ul>
<li><a href="https://newreleases.io/project/github/vllm-project/vllm/release/v0.26.0">vllm -project/ vllm v0.26.0 on GitHub</a></li>
<li><a href="https://docs.vllm.ai/projects/speculators/en/latest/user_guide/algorithms/mtp/">MTP - Speculators Docs</a></li>
<li><a href="https://huggingface.co/docs/diffusers/quantization/modelopt">NVIDIA ModelOpt · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#vLLM`, `#LLM inference`, `#GPU optimization`, `#speculative decoding`, `#model serving`

---

<a id="item-2"></a>
## [SGLang v0.5.16 adds DSpark and optimized Inkling support.](https://github.com/sgl-project/sglang/releases/tag/v0.5.16) ⭐️ 8.0/10

SGLang v0.5.16 incorporates 574 merged pull requests from 169 contributors, led by the new DSpark confidence-driven speculative decoding algorithm and optimized support for the 975-billion-parameter multimodal Inkling MoE model. The release reports 383.7 tokens/s for DeepSeek-V4-Pro on B300 TP8 and up to 71,700 input tokens/s for Inkling on Blackwell. Adaptive verification can make speculative decoding more efficient by avoiding a fixed draft length, while Inkling support demonstrates SGLang's ability to serve extremely large multimodal models across NVIDIA and AMD accelerators. These improvements are relevant to operators seeking higher throughput and lower memory use in large-scale LLM inference. DSpark uses semi-autoregressive block drafting and selects each verification-window size from draft confidence; it is enabled with `--speculative-algorithm DSPARK` and `SGLANG_RAGGED_VERIFY_MODE=compact`. The reported benchmarks are hardware- and workload-specific, and the release also removes QServe and FBGEMM FP8 paths while requiring FlashInfer for NVFP4 GEMM.

github · Qiaolin-Yu · Jul 25, 00:13

**Background**: Speculative decoding accelerates generation by having a draft process propose multiple tokens that a larger target model verifies together, but fixed verification lengths can waste computation as load changes. DSpark instead schedules variable-length verification according to confidence and system load. Inkling is a multimodal mixture-of-experts model that combines sliding-window and full attention with Mamba2 linear attention, while its NVFP4 experts target efficient execution on NVIDIA Blackwell hardware.

<details><summary>References</summary>
<ul>
<li><a href="https://www.lmsys.org/blog/2026-07-06-dspark-sglang">DSpark in SGLang: Speculative Decoding with Confidence-Driven ...</a></li>
<li><a href="https://developer.nvidia.com/blog/delivering-massive-performance-leaps-for-mixture-of-experts-inference-on-nvidia-blackwell/">Delivering Massive Performance Leaps for Mixture of Experts ...</a></li>
<li><a href="https://www.emergentmind.com/topics/linear-attention-mamba-lam">Linear Attention Mamba (LAM) Overview</a></li>

</ul>
</details>

**Tags**: `#LLM-inference`, `#speculative-decoding`, `#SGLang`, `#multimodal-models`, `#GPU-optimization`

---

<a id="item-3"></a>
## [Android Could Soon Restrict On-Device ADB Access.](https://kitsumed.github.io/blog/posts/android-may-soon-restrict-on-device-adb/) ⭐️ 8.0/10

Google is considering restrictions on accessing ADB directly from an Android device, although the proposal appears preliminary and no final platform policy has been announced. The discussion also includes limiting ADB connections to selected network interfaces or IP addresses. On-device ADB supports developer workflows, automation, sideloading, and advanced user control, so restricting it could make Android less flexible for developers and power users. Critics question whether the security benefit justifies the loss of autonomy because the cited attack surface generally requires developer settings and remote ADB to have already been enabled. The possible change concerns on-device or remote ADB access rather than an announced removal of ADB as a whole. Because the proposal is not final, its precise scope, enforcement mechanism, Android version, and availability of developer exceptions remain uncertain.

hackernews · shscs911 · Jul 25, 06:57 · [Discussion](https://news.ycombinator.com/item?id=49045159)

**Background**: Android Debug Bridge, or ADB, is a command-line tool for communicating with Android devices and emulators. Its client-server architecture lets developers issue commands from a client or script, while device debugging normally requires the user to enable developer options and authorize access. Beyond debugging, advanced users also rely on ADB for installing applications, automation, and device-management tasks.

<details><summary>References</summary>
<ul>
<li><a href="https://developer.android.com/tools/adb">Android Debug Bridge (adb) | Android Studio | Android Developers</a></li>

</ul>
</details>

**Discussion**: Commenters were largely skeptical, arguing that the attack scenario affects very few users because it requires developer settings and remote ADB to be enabled. Some supported narrower controls based on interfaces or IP addresses, while others viewed the proposal as part of a broader trend toward tighter sideloading restrictions and greater Google control over Android.

**Tags**: `#Android`, `#ADB`, `#mobile-security`, `#developer-tools`, `#platform-openness`

---

<a id="item-4"></a>
## [Anthropic introduces Claude Opus 5.](https://simonwillison.net/2026/Jul/24/introducing-claude-opus-5/#atom-everything) ⭐️ 8.0/10

Anthropic has introduced Claude Opus 5, describing it as a thoughtful, proactive model that approaches Claude Fable 5 intelligence at half the price while matching Opus 4.8 pricing. It was leading the Artificial Analysis leaderboard at the time of the post. If independent testing confirms these claims, Opus 5 could offer near-frontier capabilities at materially lower cost, influencing model selection and the economics of agentic AI applications. Its proactive problem-solving may be especially useful for complex coding, computer-use, and multi-step workflows. Opus 5 offers a fast mode with identical capabilities and higher output speed at twice the base price; OpenRouter lists that mode at $10 per million input tokens and $50 per million output tokens. Anthropic says the model can find cybersecurity vulnerabilities nearly as well as Mythos 5 but remains substantially weaker at exploiting them, and the post's performance assessment is still based mainly on vendor claims and preliminary impressions.

rss · Simon Willison · Jul 24, 23:48

**Background**: Artificial Analysis compares AI models across independent measures including quality, price, output speed, and latency, so leading its leaderboard indicates strong aggregate benchmark performance rather than superiority in every use case. A proactive or agentic model goes beyond returning a single prompt response by planning, taking actions, and refining its approach across multiple steps. Anthropic illustrated this behavior with a task in which Opus 5 could not directly view a machine-part drawing, so it created a computer-vision pipeline to extract the geometry before rebuilding the part in FreeCAD.

<details><summary>References</summary>
<ul>
<li><a href="https://artificialanalysis.ai/">AI Model & API Providers Analysis | Artificial Analysis</a></li>
<li><a href="https://openrouter.ai/anthropic/claude-opus-5-fast">Claude Opus 5 ( Fast ) - API Pricing & Providers | OpenRouter</a></li>
<li><a href="https://www.tiledb.com/blog/what-is-agentic-ai">What is agentic AI: A comprehensive 2026 guide</a></li>

</ul>
</details>

**Tags**: `#AI models`, `#Anthropic`, `#Claude`, `#LLM benchmarks`, `#AI pricing`

---