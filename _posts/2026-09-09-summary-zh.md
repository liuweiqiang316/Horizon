---
layout: default
title: "Horizon Summary: 2026-09-09 (ZH)"
date: 2026-09-09
lang: zh
---

> 从 36 条内容中筛选出 2 条重要资讯。

---

**科技新闻**
1. [OpenAI 声称解决纳维–斯托克斯难题](#item-tech-news-1) ⭐️ 9.0/10
2. [vLLM 发布 v0.29.0](#item-tech-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenAI 声称解决纳维–斯托克斯难题](https://simonwillison.net/2026/Sep/8/on-navier-stokes/) ⭐️ 9.0/10

Simon Willison 转载并评论了 OpenAI 的说法：OpenAI 使用一个未发布模型提出了纳维–斯托克斯存在性与光滑性问题的解决方案；该问题是 2000 年 5 月 24 日以来设有 100 万美元奖金的七个千禧年大奖难题之一。OpenAI 称其在 9 月 1 日听到两个千禧年难题已被解决的传闻后启动评估，代理在 9 月 5 日、首批代理启动约 88 小时后得到该问题的解决方案，并又通过 GPT‑6 Astra 用 17 小时完成 Lean 形式化与验证。OpenAI 表示，所有尝试的问题合计发送 490 万条消息、使用约 3000 亿个输出 token，其中纳维–斯托克斯问题使用 270 万条消息和约 1300 亿个输出 token；Willison 估算若按 GPT‑6 Astra 公开 API 价格，3000 亿输出 token 将约合 1500 万美元。事件同时受到争议影响：NYU 数学教授 Tristan Buckmaster 称自己与现任 Anthropic 员工 Levent Alpöge 已用 Claude 和 Codex（主要是 GPT‑5.6 Sol）合作近一年，并在 8 月 15 日取得突破，而 OpenAI 后来承认其工作是在相关传闻后开始。OpenAI 否认研究人员和代理在公开发布前看过 Buckmaster 与 Alpöge 的工作，称未访问特定用户数据，但也表示不能排除来自其产品使用的去标识化数据曾帮助改进模型；Willison 因此将焦点放在 AI 实验室如何使用用户数据改进模型，以及未发表数学成果是否会被“传闻”触发的高成本 LLM 搜索抢先追赶。

rss · Simon Willison · 9月8日 23:55

**「背景」** Navier–Stokes 方程用于描述流体运动，其“存在性与光滑性”问题关注三维流体方程的解是否总是存在并保持光滑，或是否可能在有限时间内形成奇点。该问题是克雷数学研究所 2000 年公布的七个“千禧年大奖难题”之一，每题悬赏 100 万美元；OpenAI 对此称其内部系统给出的结果显示流体动力学可能在有限时间内产生奇点。

**「影响」** 如果该证明经独立审查和正式认可成立，它将使受影响的数学与 AI 研究群体面对一个由未发布模型解决千禧难题的先例，并迫使使用商业 AI 工具开展前沿研究的人重新评估训练数据、优先权和成果归属风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/navier-stokes-solution/">On the Navier–Stokes Millennium Prize Problem | OpenAI</a></li>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_existence_and_smoothness">Navier–Stokes existence and smoothness - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Millennium_Prize_Problems">Millennium Prize Problems - Wikipedia</a></li>

</ul>
</details>

**标签**: `#AI-assisted mathematics`, `#OpenAI`, `#Navier-Stokes`, `#research`, `#technology industry`

---

<a id="item-tech-news-2"></a>
### [vLLM 发布 v0.29.0](https://github.com/vllm-project/vllm/releases/tag/v0.29.0) ⭐️ 8.0/10

vLLM v0.29.0 发布，包含来自 277 名贡献者的 594 次提交，其中 91 名为新贡献者，并将 Model Runner V2 设为所有模型的默认运行器。该版本扩展了 MRV2 的能力，包括用于 KV cache 自动定容的 CUDA graph 内存分析、按批次分片采样以将每步 logits 内存降低到 1/TP、prompt embeds、\`extract\_hidden\_states\` speculation、spec decode 下的 padded FULL cudagraph dispatch，以及 EAGLE/MTP draft prefill 前跳过 DP 同步；少数 ROCm 模型和 MRV2 尚不支持的功能仍使用 MRV1。新模型支持包括 Hy4-preview、Qwen3.8-Flash-Next、GraniteSWA、GraniteMoeSWA、NemotronH\_Omni\_Reasoning\_V3、Kimi K3 NVFP4 checkpoint，以及 DeepSeek-backbone embedding、FP8 ModernBERT 等相关能力。性能和推理改进覆盖 Kimi-K3、DeepSeek V4、speculative decoding、RL weight sync、Mamba prefix caching 和多模态路径，例如 K3 latent tail 的 fused MXFP4 top-k finalization 宣称约 5% 端到端延迟改进，K3 Mamba metadata 准备内核提升 6.6–7.6 倍，\`eh\_proj\` 相关 GEMM 内核提升 12.9–25.2%。该版本同时改变默认项并引入破坏性变更，包括默认启用 FlashInfer all-reduce、prefix-cache \`NONE\_HASH\` 默认确定性、加入 \`--max-num-queued-reqs\` 和 \`--max-num-queued-tokens\`，移除 10 个已弃用模型架构、移除 PyAV 视频解码后端，并弃用 \`python -m vllm.entrypoints.openai.api\_server\` 入口而推荐 \`vllm serve\`。

github · khluu · 9月9日 08:54

**「背景」** vLLM 是一个用于大语言模型推理和服务的开源框架，核心目标是在多用户请求下提高吞吐量并降低显存占用。它常被用于生产化模型服务，依赖 PagedAttention、连续批处理和前缀缓存等机制来管理 KV 缓存、复用提示词计算，并支持 NVIDIA、AMD、CPU 等不同硬件环境。

**「影响」** 使用 vLLM 部署 LLM 的团队可获得更广的模型覆盖和多项 CUDA/推理优化，但升级前需要检查被移除架构、入口命令、视频解码后端、环境变量以及少数 ROCm/MRV2 兼容性限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://zeroentropy.dev/concepts/vllm-serving/">vLLM serving : PagedAttention and continuous batching for LLMs</a></li>
<li><a href="https://dev.co/ai/frameworks/vllm">vLLM : Open - Source LLM Inference &amp; Serving Engine | DEV.co</a></li>

</ul>
</details>

**标签**: `#vLLM`, `#LLM inference`, `#open source`, `#CUDA`, `#model serving`

---