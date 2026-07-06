---
layout: default
title: "Horizon Summary: 2026-07-06 (EN)"
date: 2026-07-06
lang: en
---

> From 33 items, 1 important content pieces were selected

---

1. [Tencent open-sources Hunyuan Hy3 preview.](#item-1) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Tencent open-sources Hunyuan Hy3 preview.](https://t.me/zaihuapd/42385) ⭐️ 8.0/10

Tencent officially released and open-sourced Hunyuan Hy3 preview, a Mixture-of-Experts language model with 295B total parameters, 21B active parameters, and support for a 256K context window. The model is positioned for complex reasoning, agent applications, and coding tasks. The release adds another large open MoE model to the rapidly competitive LLM ecosystem, especially from a major Chinese technology company. Its long-context and agent-oriented focus could affect developers building document-heavy, coding, and workflow-automation products on open models. Tencent says Hy3 preview is the first model trained on its rebuilt infrastructure and that deep coordination between the model architecture and inference framework improved serving performance. In Tencent’s CodeBuddy product, first-token latency reportedly fell by 54%, but the provided material does not include full benchmark tables or a paper.

telegram · zaihuapd · Jul 6, 10:09

**Background**: A Mixture-of-Experts model uses multiple specialized sub-networks, often called experts, and a routing or gating mechanism chooses which experts handle a given input. This design can allow a model to have a very large total parameter count while activating only part of the model for each token, which can improve efficiency compared with dense models of similar total size. Context length refers to the maximum number of tokens a model can process in one request, including input and generated output, so a 256K context window is aimed at long documents, extended conversations, and large codebases.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tencent.com/zh-cn/articles/2202320.html">腾讯混元Hy3 preview发布：主打实用，Agent能力大幅提升 - Tencent 腾讯</a></li>
<li><a href="https://github.com/Tencent-Hunyuan/Hy3-preview">Tencent-Hunyuan/Hy3-preview - GitHub</a></li>
<li><a href="https://huggingface.co/blog/zh/moe">混合专家模型（MoE）详解</a></li>

</ul>
</details>

**Tags**: `#AI模型`, `#开源`, `#MoE`, `#大语言模型`, `#腾讯混元`

---