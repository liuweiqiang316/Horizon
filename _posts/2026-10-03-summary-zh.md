---
layout: default
title: "Horizon Summary: 2026-10-03 (ZH)"
date: 2026-10-03
lang: zh
---

> 从 23 条内容中筛选出 1 条重要资讯。

---

**科技新闻**
1. [Aleph Alpha 发布 Kolibri 开放权重模型](#item-tech-news-1) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Aleph Alpha 发布 Kolibri 开放权重模型](https://aleph-alpha.com/en/blog/kolibri-has-landed-a-sovereign-open-weight-model/) ⭐️ 8.0/10

Aleph Alpha 宣布 Kolibri，这是一个主打“主权”的开放权重大语言模型，并提供技术报告和一篇补充文章。随附材料据称讨论了模型训练、数据集构建以及面向现代 agentic LLM 的实现细节，使外部研究者和工程团队更容易审视其方法。社区讨论中特别提到，Kolibri 使用 abstention data 和 Merlin-Arthur protocol 训练，以便在答案不在上下文中时倾向回答“我不知道”，从而尝试限制幻觉。现有材料显示这是一次透明度较高的模型发布，但未提供足以证明其构成范式突破的独立基准结论。

hackernews · bastitx · 10月3日 09:36 · [社区讨论](https://news.ycombinator.com/item?id=49942706)

**「背景」** “开放权重”通常指模型参数可供下载和自行部署，但不一定等同于完整开源训练代码或训练数据；“主权 AI”强调由特定国家或地区可控地开发、部署和治理模型。Kolibri 的技术报告称其为英语—德语 Mixture-of-Experts Transformer，总参数为 78.1B、每个 token 激活 3.46B，并以 Apache 2.0 许可证发布权重。

**「影响」** 对希望评估非美国、非中国开放权重模型的 AI 开发者而言，Kolibri 提供了可试用的模型权重和较详细的训练说明。

**「社区讨论」** 评论者普遍关注其开放程度，有人称技术报告像“如何制作现代 agentic LLM”的教程，并赞赏其公开数据集制作细节；也有用户临时托管了 Kolibri-1 供他人无需 GPU 试用。讨论中同时出现对“主权”表述的质疑，认为若公司将与加拿大 Cohere 合并，应在相关叙事中更明确说明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aleph-alpha.com/downloads/tech-report.pdf">Kolibri : A Sovereign European Model on the Pareto Frontier</a></li>

</ul>
</details>

**标签**: `#open-weight-models`, `#large-language-models`, `#AI-safety`, `#model-training`, `#open-source-ai`

---