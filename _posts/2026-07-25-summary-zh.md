---
layout: default
title: "Horizon Summary: 2026-07-25 (ZH)"
date: 2026-07-25
lang: zh
---

> 从 24 条内容中筛选出 4 条重要资讯。

---

1. [vLLM v0.26.0 扩展模型支持与跨厂商推理优化](#item-1) ⭐️ 8.0/10
2. [SGLang v0.5.16 增加了 DSpark 和优化的 Inkling 支持。](#item-2) ⭐️ 8.0/10
3. [Android 可能很快限制设备端 ADB 访问。](#item-3) ⭐️ 8.0/10
4. [Anthropic 发布 Claude Opus 5。](#item-4) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [vLLM v0.26.0 扩展模型支持与跨厂商推理优化](https://github.com/vllm-project/vllm/releases/tag/v0.26.0) ⭐️ 8.0/10

vLLM v0.26.0 正式发布，包含来自 212 名贡献者的 411 次提交，其中 61 人是首次贡献。该版本为 Inkling 模型家族增加完整支持，并带来跨平台 DeepSeek-V4 优化、更多推测解码与量化功能，以及用于提高准确性的 fp32 生成头。 该版本为模型服务团队提供了更广泛的硬件和模型选择，同时着重降低延迟、提高吞吐量、减少内存占用并改善数值准确性。其优化覆盖 NVIDIA、AMD ROCm 和 XPU 路径，反映出业界对可移植 LLM 推理的需求日益增长，而不是依赖单一加速器厂商。 DeepSeek-V4 的改进包括端到端 TPOT 提升 2.94% 的专用路由内核、速度提高 1.5 至 2 倍的 fused_topk_bias 内核，以及通过移除冗余重复与复制操作带来的额外 1.8% 端到端 TPOT 提升。该版本还允许为每个 KV 缓存组选择注意力后端，增加分层 KV 卸载和对象存储支持，并为 Rust 前端加入视频、音频以及原生 vllm-bench 移植。

github · khluu · 7月25日 10:38

**背景**: vLLM 是一个 LLM 推理与服务引擎，旨在让训练完成的模型能够在加速器硬件上高效运行。推测解码会先草拟多个词元再进行验证，以降低生成延迟；量化则使用低精度数值格式来减少模型内存需求，并可能提升推理速度。NVIDIA ModelOpt 支持包括 NVFP4 在内的格式，而 Hopper 是 NVIDIA 的 GPU 架构，用于 H100 等产品。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://newreleases.io/project/github/vllm-project/vllm/release/v0.26.0">vllm -project/ vllm v0.26.0 on GitHub</a></li>
<li><a href="https://docs.vllm.ai/projects/speculators/en/latest/user_guide/algorithms/mtp/">MTP - Speculators Docs</a></li>
<li><a href="https://huggingface.co/docs/diffusers/quantization/modelopt">NVIDIA ModelOpt · Hugging Face</a></li>

</ul>
</details>

**标签**: `#vLLM`, `#LLM inference`, `#GPU optimization`, `#speculative decoding`, `#model serving`

---

<a id="item-2"></a>
## [SGLang v0.5.16 增加了 DSpark 和优化的 Inkling 支持。](https://github.com/sgl-project/sglang/releases/tag/v0.5.16) ⭐️ 8.0/10

SGLang v0.5.16 合并了来自 169 位贡献者的 574 个拉取请求，主要新增 DSpark 置信度驱动的推测解码算法，并优化了对 9750 亿参数多模态 Inkling MoE 模型的支持。该版本报告称，DeepSeek-V4-Pro 在 B300 TP8 上达到每秒 383.7 个词元，而 Inkling 在 Blackwell 上的输入吞吐最高达到每秒 7.17 万个词元。 自适应验证无需采用固定草稿长度，因此可能提高推测解码效率；对 Inkling 的支持则展示了 SGLang 在 NVIDIA 和 AMD 加速器上部署超大规模多模态模型的能力。这些改进对希望在大规模 LLM 推理中提升吞吐并降低内存占用的运营者具有重要意义。 DSpark 采用半自回归分块草拟，并根据草稿置信度确定每个验证窗口的大小；启用时需要设置 `--speculative-algorithm DSPARK` 和 `SGLANG_RAGGED_VERIFY_MODE=compact`。所报告的基准结果依赖特定硬件与工作负载；该版本还移除了 QServe 和 FBGEMM FP8 路径，并要求使用 FlashInfer 执行 NVFP4 GEMM。

github · Qiaolin-Yu · 7月25日 00:13

**背景**: 推测解码通过草稿过程一次提出多个词元，再由更大的目标模型统一验证，从而加速生成，但固定验证长度可能在负载变化时浪费计算。DSpark 改为根据置信度和系统负载安排可变长度验证。Inkling 是一种多模态混合专家模型，结合了滑动窗口注意力、全注意力和 Mamba2 线性注意力，其 NVFP4 专家则面向 NVIDIA Blackwell 硬件上的高效执行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.lmsys.org/blog/2026-07-06-dspark-sglang">DSpark in SGLang: Speculative Decoding with Confidence-Driven ...</a></li>
<li><a href="https://developer.nvidia.com/blog/delivering-massive-performance-leaps-for-mixture-of-experts-inference-on-nvidia-blackwell/">Delivering Massive Performance Leaps for Mixture of Experts ...</a></li>
<li><a href="https://www.emergentmind.com/topics/linear-attention-mamba-lam">Linear Attention Mamba (LAM) Overview</a></li>

</ul>
</details>

**标签**: `#LLM-inference`, `#speculative-decoding`, `#SGLang`, `#multimodal-models`, `#GPU-optimization`

---

<a id="item-3"></a>
## [Android 可能很快限制设备端 ADB 访问。](https://kitsumed.github.io/blog/posts/android-may-soon-restrict-on-device-adb/) ⭐️ 8.0/10

Google 正在考虑限制直接从 Android 设备内部访问 ADB，但该提案似乎仍处于初步阶段，尚未公布最终的平台政策。相关讨论还涉及将 ADB 连接限制在指定的网络接口或 IP 地址上。 设备端 ADB 支持开发流程、自动化、侧载以及高级用户控制，因此限制它可能降低 Android 对开发者和高级用户的灵活性。批评者认为，相关攻击面通常要求用户已经启用开发者设置和远程 ADB，因此有限的安全收益未必足以抵消用户自主权的损失。 这项潜在变更针对的是设备端或远程 ADB 访问，并不代表 Google 已宣布全面移除 ADB。由于提案尚未定案，其具体范围、执行机制、适用的 Android 版本以及是否提供开发者例外仍不明确。

hackernews · shscs911 · 7月25日 06:57 · [社区讨论](https://news.ycombinator.com/item?id=49045159)

**背景**: Android 调试桥（ADB）是一种用于与 Android 设备和模拟器通信的命令行工具。它采用客户端与服务器架构，允许开发者通过客户端或脚本执行命令，而设备调试通常需要用户启用开发者选项并授权访问。除了调试之外，高级用户也会利用 ADB 安装应用、执行自动化和完成设备管理任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.android.com/tools/adb">Android Debug Bridge (adb) | Android Studio | Android Developers</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍持怀疑态度，认为该攻击场景要求用户启用开发者设置和远程 ADB，因此只会影响极少数用户。一些人支持基于网络接口或 IP 地址的更精细限制，另一些人则将该提案视为 Android 收紧侧载并扩大 Google 平台控制权这一趋势的一部分。

**标签**: `#Android`, `#ADB`, `#mobile-security`, `#developer-tools`, `#platform-openness`

---

<a id="item-4"></a>
## [Anthropic 发布 Claude Opus 5。](https://simonwillison.net/2026/Jul/24/introducing-claude-opus-5/#atom-everything) ⭐️ 8.0/10

Anthropic 发布了 Claude Opus 5，并称其是一款善于审慎思考、能够主动解决问题的模型，以一半的价格接近 Claude Fable 5 的智能水平，同时维持与 Opus 4.8 相同的定价。文章发布时，该模型位居 Artificial Analysis 排行榜榜首。 如果这些说法得到独立测试证实，Opus 5 可能以显著更低的成本提供接近前沿的能力，从而影响模型选择以及智能体式 AI 应用的经济性。其主动解决问题的特点可能尤其适合复杂编程、计算机操作和多步骤工作流。 Opus 5 提供能力相同但输出速度更高的快速模式，其价格是基础模式的两倍；OpenRouter 将该模式的价格列为每百万输入词元 10 美元、每百万输出词元 50 美元。Anthropic 称该模型发现网络安全漏洞的能力接近 Mythos 5，但利用漏洞的能力明显较弱；目前的性能判断仍主要来自厂商说法和初步印象。

rss · Simon Willison · 7月24日 23:48

**背景**: Artificial Analysis 使用质量、价格、输出速度和延迟等独立指标比较 AI 模型，因此位居其排行榜首位代表综合基准表现强劲，并不意味着在每一种使用场景中都最优秀。主动式或智能体式模型不只是对单个提示作出回答，还会规划任务、采取行动，并在多个步骤中调整方法。Anthropic 举例称，在一项无法直接查看机械零件图纸的任务中，Opus 5 自行编写了计算机视觉处理流程，从原始像素中提取几何信息，随后在 FreeCAD 中重建零件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://artificialanalysis.ai/">AI Model & API Providers Analysis | Artificial Analysis</a></li>
<li><a href="https://openrouter.ai/anthropic/claude-opus-5-fast">Claude Opus 5 ( Fast ) - API Pricing & Providers | OpenRouter</a></li>
<li><a href="https://www.tiledb.com/blog/what-is-agentic-ai">What is agentic AI: A comprehensive 2026 guide</a></li>

</ul>
</details>

**标签**: `#AI models`, `#Anthropic`, `#Claude`, `#LLM benchmarks`, `#AI pricing`

---