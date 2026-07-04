---
layout: default
title: "Horizon Summary: 2026-07-04 (ZH)"
date: 2026-07-04
lang: zh
---

> 从 47 条内容中筛选出 3 条重要资讯。

---

1. [Pegasus 感染了一名欧洲议会议员。](#item-1) ⭐️ 8.0/10
2. [Wordgard 重新思考浏览器富文本编辑。](#item-2) ⭐️ 8.0/10
3. [CDD 声称仅凭 logit 恢复微调数据。](#item-3) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Pegasus 感染了一名欧洲议会议员。](https://citizenlab.ca/research/member-of-committee-investigating-spyware-hacked-with-pegasus/) ⭐️ 8.0/10

Citizen Lab 报告称，参与调查间谍软件滥用的欧洲议会议员 Stelios Kouloglou 的 iPhone 曾在 2022 年 10 月 21 日前后以及 2023 年 3 月 6 日和 7 日再次感染 Pegasus。该发现是在 Kouloglou 于 2026 年 5 月联系 Citizen Lab 后，研究人员对其设备取证痕迹进行分析得出的。 此案令人严重担忧，因为间谍软件可能被用于针对正在审查间谍软件行业本身的议员，从而可能破坏民主监督和敏感的议会工作。它也加剧了欧洲范围内对国家相关监控工具被用于针对政治人物、记者、活动人士和其他公共利益目标的担忧。 Citizen Lab 表示，其对感染结论具有高度信心，并指出第一次感染与此前发现的一起 Pegasus 行动存在时间重叠，该行动针对欧洲境内讲俄语和白俄罗斯语的流亡记者及活动人士。Pegasus 感染尤其难以由目标自行防范，因为该间谍软件曾使用无需受害者点击链接或打开文件的零点击漏洞利用链。

hackernews · ledoge · 7月3日 20:38 · [社区讨论](https://news.ycombinator.com/item?id=48779683)

**背景**: Pegasus 是以色列 NSO Group 开发的间谍软件，并出售给政府客户，官方用途包括打击犯罪和恐怖主义。Citizen Lab 和 Amnesty International 等组织的公开调查多次发现，Pegasus 被用于针对记者、律师、异见人士、政治人物和人权活动人士。一旦安装到手机上，Pegasus 通常被认为能够访问消息、通话、位置数据、应用数据、麦克风和摄像头，因此个人或工作手机被入侵会造成高度敏感的风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Pegasus_(spyware)">Pegasus (spyware)</a></li>
<li><a href="https://surfshark.com/blog/pegasus-spyware">What is Pegasus spyware? How to detect and remove it - Surfshark</a></li>

</ul>
</details>

**社区讨论**: 评论者主要关注归因和政治背景，数人提到希腊、波兰、意大利以及其他欧洲国家此前围绕 Pegasus 的争议。一些人认为，此事更应被理解为成员国层面的监控丑闻，而不是对欧洲议会的直接攻击；另一些人则质疑为何个人敏感医疗信息和政府机密文件可能同时存在于同一台设备上。

**标签**: `#cybersecurity`, `#spyware`, `#Pegasus`, `#government-surveillance`, `#European-Union`

---

<a id="item-2"></a>
## [Wordgard 重新思考浏览器富文本编辑。](https://wordgard.net/) ⭐️ 8.0/10

ProseMirror 的创建者 Marijn Haverbeke 推出了新的浏览器内富文本编辑器系统 Wordgard，网址为 wordgard.net。它旨在为构建语义化内容编辑器提供工具，同时重新设计 ProseMirror 使用者熟悉的部分架构。 富文本编辑仍然是 Web 开发中最困难的领域之一，而 ProseMirror 已经深刻影响了许多构建结构化编辑器的团队。同一作者推出的新编辑器可能会影响未来 Web 编辑器处理文档建模、类型、协作和应用专用内容规则的方式。 Wordgard 被描述为语义化富文本编辑器系统，而不是自由形式的 HTML 编辑器，这意味着应用可以精确控制支持哪些内容结构。社区讨论指出，它与 ProseMirror 共享一些概念，但似乎没有简单的升级路径，因此迁移可能需要大量工作。

hackernews · indy · 7月3日 08:50 · [社区讨论](https://news.ycombinator.com/item?id=48772573)

**背景**: ProseMirror 是一个用于在 Web 上构建所见即所得式富文本编辑器的工具包，尤其适合需要比普通 HTML 更结构化、更受约束的文档的应用。Wordgard 看起来面向相似的问题领域：帮助开发者构建由应用控制文档模型的自定义浏览器编辑器。这一点很重要，因为浏览器中的编辑基础能力长期以来很难可靠地支撑发布工具、笔记应用和协作文档系统等复杂产品。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wordgard.net/">Wordgard</a></li>
<li><a href="https://prosemirror.net/">ProseMirror</a></li>
<li><a href="https://code.haverbeke.berlin/wordgard/wordgard">wordgard / wordgard : The Wordgard rich text editor</a></li>

</ul>
</details>

**社区讨论**: Hacker News 讨论整体上表现出好奇和积极态度，多位评论者称赞其技术方向和设计。主要担忧包括缺少从 ProseMirror 迁移的清晰路径、文档 JSON 难以进行静态类型建模，以及人们对稳健富文本编辑至今仍缺少简单 Web 标准方案的不满。

**标签**: `#rich-text-editing`, `#web-development`, `#prosemirror`, `#collaborative-editing`, `#developer-tools`

---

<a id="item-3"></a>
## [CDD 声称仅凭 logit 恢复微调数据。](https://www.reddit.com/r/MachineLearning/comments/1umn2dk/contrastive_decoding_diffing_cdd_recovering/) ⭐️ 8.0/10

这篇帖子介绍了 Contrastive Decoding Diffing，这是一种通过对比基础模型和微调模型的 logit 来逐字恢复微调内容的方法，不需要访问权重、激活值或探测语料库。作者称，在 SDF 基准上，该方法覆盖四个模型家族、参数规模从 1B 到 32B，并在 20 个“生物体×模型”组合中的 19 个取得了 4+/5 的逐字恢复分数。 如果这一结果得到验证，CDD 将使微调数据提取在比既有白盒激活方法弱得多的灰盒访问条件下成为可能。这会给通过 API 暴露词元概率或 logit 的模型提供方带来实际的隐私和安全风险，尤其是在模型针对机密数据集或合成数据集进行窄域微调时。 CDD 被描述为 Activation Difference Lens 的输出层对应方法：它不计算模型内部的激活差异，而是利用基础模型与微调模型之间的 logit 差异进行解码。帖子还提到一个意外发现：虚构科学家姓名“Dr. Elena Rodriguez”出现在多个语义无关的微调领域中，原因据称是 Claude Sonnet 3.6 在生成合成训练数据时偏好使用这一人设。

reddit · r/MachineLearning · /u/CebulkaZapiekana · 7月3日 19:01

**背景**: 微调是指把一个预训练语言模型进一步适配到更窄的任务或数据集上，而 Activation Difference Lens 相关工作研究的是这种适配如何在模型内部激活中留下可检测痕迹。对比解码是一种生成策略，它比较两个模型或两个分布的词元分数，并根据差异而不是单个模型的原始偏好来选择词元。logit 是计算概率之前的未归一化词元分数，因此访问 logit 通常比只看到文本输出更能揭示模型的下一个词元偏好。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.emergentmind.com/topics/contrastive-decoding">Contrastive Decoding in Language Models</a></li>
<li><a href="https://learnmechinterp.com/topics/finetuning-traces/">Finetuning Traces in Activations | Learn Mechanistic Interpretability</a></li>

</ul>
</details>

**标签**: `#LLM security`, `#data extraction`, `#model privacy`, `#contrastive decoding`, `#machine learning research`

---