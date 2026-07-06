---
layout: default
title: "Horizon Summary: 2026-07-06 (ZH)"
date: 2026-07-06
lang: zh
---

> 从 33 条内容中筛选出 1 条重要资讯。

---

1. [腾讯开源混元 Hy3 preview。](#item-1) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [腾讯开源混元 Hy3 preview。](https://t.me/zaihuapd/42385) ⭐️ 8.0/10

腾讯正式发布并开源了混元 Hy3 preview，这是一款混合专家语言模型，拥有 295B 总参数、21B 激活参数，并支持 256K 上下文长度。该模型主要面向复杂推理、智能体应用和代码开发任务。 这次发布为竞争激烈的大语言模型生态增加了一个来自中国大型科技公司的开源 MoE 模型。其长上下文和面向智能体的定位，可能影响开发者基于开源模型构建长文档处理、代码开发和流程自动化产品。 腾讯称 Hy3 preview 是其架构重建后训练的首个模型，并表示模型架构与推理框架的深度协同提升了服务性能。在腾讯 CodeBuddy 产品中，首个 token 延迟据称降低了 54%，但现有材料没有提供完整基准测试表或论文。

telegram · zaihuapd · 7月6日 10:09

**背景**: 混合专家模型会使用多个专门的子网络，通常称为“专家”，并通过路由或门控机制决定某个输入由哪些专家处理。这种设计可以让模型拥有很大的总参数规模，但每个 token 只激活其中一部分参数，因此相较同等总规模的稠密模型可能更高效。上下文长度指模型在一次请求中能够处理的最大 token 数量，包括输入和生成输出，因此 256K 上下文窗口主要面向长文档、长对话和大型代码库场景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tencent.com/zh-cn/articles/2202320.html">腾讯混元Hy3 preview发布：主打实用，Agent能力大幅提升 - Tencent 腾讯</a></li>
<li><a href="https://github.com/Tencent-Hunyuan/Hy3-preview">Tencent-Hunyuan/Hy3-preview - GitHub</a></li>
<li><a href="https://huggingface.co/blog/zh/moe">混合专家模型（MoE）详解</a></li>

</ul>
</details>

**标签**: `#AI模型`, `#开源`, `#MoE`, `#大语言模型`, `#腾讯混元`

---