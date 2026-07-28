---
layout: default
title: "Horizon Summary: 2026-07-28 (ZH)"
date: 2026-07-28
lang: zh
---

> 从 36 条内容中筛选出 6 条重要资讯。

---

1. [Moonshot AI 发布 Kimi K3 的 2.8 万亿参数权重。](#item-1) ⭐️ 9.0/10
2. [Kimi K3 以 NoPE 和 KDA 取代传统设计。](#item-2) ⭐️ 8.0/10
3. [多针 HIV 疫苗在临床前研究中展现出罕见潜力。](#item-3) ⭐️ 8.0/10
4. [Kimi Linear 提出高效的混合注意力架构。](#item-4) ⭐️ 8.0/10
5. [DeltaNet 演进至 Kimi Delta Attention。](#item-5) ⭐️ 8.0/10
6. [超过半数学术论文如今显现出 LLM 影响。](#item-6) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Moonshot AI 发布 Kimi K3 的 2.8 万亿参数权重。](https://simonwillison.net/2026/Jul/27/kimi-k3/#atom-everything) ⭐️ 9.0/10

2026 年 7 月 27 日，Moonshot AI 在 Hugging Face 上发布了 Kimi K3 的模型权重；该语言模型拥有 2.8 万亿个参数，权重文件大小为 1.56 TB。此次发布采用开放权重许可，并要求达到一定收入规模的模型即服务企业另行签署协议。 发布如此规模模型的权重，使研究人员和基础设施提供商能够更直接地检查、托管并基于前沿级模型构建服务。不过，巨大的存储与计算需求限制了实际自行部署的可行性，而商业条款也使其开放程度低于传统开源软件。 如果被许可方或其关联方经营模型即服务业务，并且连续任意 12 个月的合计收入超过 2000 万美元，则在将该软件或其衍生作品用于商业目的前，必须与 Moonshot AI 另行签署协议。OpenRouter 已经通过七家提供商供应 Kimi K3，其中多数按每百万输入令牌 3 美元、每百万输出令牌 15 美元收费。

rss · Simon Willison · 7月27日 23:39

**背景**: 模型权重是训练后形成的数值参数，它们编码了语言模型的行为。开放权重意味着这些数值可供获取，但不一定同时提供训练数据、完整开发流程，或授予开源软件通常具备的不受限权利。因此，Moonshot 将 Kimi K3 称为“开放权重”而不是“开源”，其商业许可条件进一步体现了这种区别。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://simonwillison.net/2026/Jul/27/kimi-k3/">moonshotai/ Kimi - K 3 | Simon Willison’s Weblog</a></li>
<li><a href="https://www.pbs.org/newshour/science/whats-the-difference-between-closed-open‑source-and-open-weight-ai-a-researcher-explains">What's the difference between closed, open‑source and open-weight AI? A researcher explains | PBS News</a></li>

</ul>
</details>

**标签**: `#large-language-models`, `#open-weights`, `#generative-ai`, `#model-licensing`, `#Kimi-K3`

---

<a id="item-2"></a>
## [Kimi K3 以 NoPE 和 KDA 取代传统设计。](https://sebastianraschka.com/blog/2026/kimi-k3-architecture-notes.html) ⭐️ 8.0/10

Sebastian Raschka 的架构分析指出，Kimi K3 从所有层中移除了 RoPE，并全面采用 NoPE。该模型还主要使用 Kimi Delta Attention（KDA），同时周期性地插入完整注意力层。 这一设计表明，大语言模型即使不使用显式位置嵌入，也可能保持较强的实际性能，而 KDA 有望降低长上下文带来的内存占用和解码成本。这些选择可能影响未来模型在序列推理、全局信息回忆和推理效率之间的权衡方式。 KDA 使用固定大小的循环状态，而不是持续增长的 KV 缓存，但 Kimi K3 仍保留周期性的完整注意力层，以实现精确的全局信息回忆。NoPE 完全移除了显式位置编码，因此模型需要通过因果注意力结构和学习到的注意力模式来推断词元顺序。

hackernews · ModelForge · 7月28日 15:48 · [社区讨论](https://news.ycombinator.com/item?id=49085698)

**背景**: RoPE 即旋转位置嵌入，它将位置信息注入注意力计算，使 Transformer 能够区分词元在序列中的位置。NoPE 不提供这类显式位置信号；相关研究表明，因果 Transformer 仍可学习相对或绝对位置行为，但长度泛化可能依然具有挑战性。KDA 是一种线性注意力机制，旨在用大小受限的循环状态概括此前的上下文，不同于 KV 缓存会随序列长度增长的标准注意力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://vllm.ai/blog/2026-07-27-k3">Kimi K3 Is Here: Efficient Day-0 Support on vLLM | vLLM Blog</a></li>
<li><a href="https://sebastianraschka.com/llm-architecture-gallery/nope/">No Positional Embeddings (NoPE) | Sebastian Raschka, PhD</a></li>
<li><a href="https://arxiv.org/html/2404.12224v1">Length Generalization of Causal Transformers without Position Encoding</a></li>

</ul>
</details>

**社区讨论**: 评论者总体赞赏 Raschka 的详细解析，也认可 Kimi K3 在实际使用中的表现。主要技术疑问是，完全移除位置嵌入是否会让输入变成混乱的“词元汤”，以及仅靠因果注意力能否足够精确地恢复词元顺序。

**标签**: `#large-language-models`, `#model-architecture`, `#attention-mechanisms`, `#positional-embeddings`, `#Kimi-K3`

---

<a id="item-3"></a>
## [多针 HIV 疫苗在临床前研究中展现出罕见潜力。](https://www.lji.org/news-events/news/post/new-hiv-vaccine-shows-unprecedented-success-in-preclinical-study/) ⭐️ 8.0/10

一种新的序贯 HIV 疫苗策略取得了异常可观的临床前结果，它通过一系列不同的注射，逐步引导 B 细胞成熟并产生广谱中和抗体。每次后续免疫都旨在激活合适的 B 细胞，并推动其进入抗体发育的下一阶段。 广谱中和抗体能够阻断许多遗传差异显著的 HIV 毒株，因此，可靠地诱导这类抗体一直是 HIV 疫苗研究的重要目标。这种分阶段策略可能突破传统疫苗设计的局限，但其有效性和安全性仍需在人类试验中得到验证。 这套方案更像是为免疫系统设计的一套课程，而不是常规的重复加强针：不同免疫原先启动罕见的前体 B 细胞，再逐步优化其抗体反应。目前证据仍处于临床前阶段，而相关种系靶向免疫原进入一期临床试验，也不代表这套完整策略已被证明能够预防 HIV 感染。

hackernews · codebyaditya · 7月28日 13:12 · [社区讨论](https://news.ycombinator.com/item?id=49083314)

**背景**: HIV 变异速度很快，会产生大量能够逃避单一毒株特异性抗体的病毒变体。广谱中和抗体能够识别病毒中较为保守的区域，因此可以中和多种毒株，但能够产生这类抗体的 B 细胞谱系十分罕见，而且通常需要经历充分成熟。种系靶向策略使用专门设计的初次免疫原和加强免疫原，先激活合适的初始 B 细胞，再逐步引导其发育。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.scripps.edu/news-and-events/press-room/2026/20260706-schief-nature.html">Scripps Research scientists train the immune system to make antibodies against numerous HIV strains | Scripps Research</a></li>
<li><a href="https://www.nature.com/articles/s41541-025-01168-z">Optimizing human B cell repertoire analyses to interpret clinical data and design sequential HIV vaccines | npj Vaccines</a></li>
<li><a href="https://www.aidsmap.com/news/jun-2024/germline-targeting-future-hiv-vaccine-development">Is germline targeting the future of HIV vaccine development? | aidsmap</a></li>

</ul>
</details>

**社区讨论**: 评论者对把序贯注射设计成免疫系统“课程”的思路印象深刻，但也强调许多 HIV 候选疫苗会在人类试验阶段失败，并提供了原始论文和同行评审材料供进一步核查。另一些人指出，扩大 PrEP 的可及性并加强公共卫生教育已经能够预防传播；还有评论者追问，人体为何不会自然产生大量广谱中和抗体。

**标签**: `#HIV`, `#vaccines`, `#immunology`, `#biomedical-research`, `#clinical-trials`

---

<a id="item-4"></a>
## [Kimi Linear 提出高效的混合注意力架构。](https://arxiv.org/abs/2510.26692) ⭐️ 8.0/10

Moonshot AI 于 2025 年提出 Kimi Linear，通过混合注意力设计，为标准注意力提供一种更具表现力且面向长输入效率优化的替代方案。该项目还开放了 KDA 内核、vLLM 推理支持，以及预训练和指令微调模型检查点。 如果其效率和模型质量能够在更大规模上保持，Kimi Linear 有望降低长上下文 LLM 推理的内存与计算成本，减少对二次复杂度标准注意力的依赖。开放内核、模型检查点和 vLLM 集成，也使研究人员与开发者更容易进行独立测试。 Kimi Linear 采用混合机制，并非替换所有标准注意力运算；已发布的模型之一是 Kimi-Linear-48B-A3B-Instruct。当前结果仍属于早期架构成果，而精确 softmax 注意力在质量和实际速度方面仍可能具有竞争力，因此还需要在更多工作负载和硬件上验证。

hackernews · ronfriedhaber · 7月28日 10:52 · [社区讨论](https://news.ycombinator.com/item?id=49082022)

**背景**: 标准 Transformer 注意力会比较序列中的各个词元，因此计算量和内存需求会随序列长度呈二次增长。线性注意力方法通过重组或近似相关计算改善扩展特性，并可让解码所需内存不再随完整上下文长度持续增长。Kimi Linear 这类混合架构保留部分标准注意力，同时在其他位置使用高效的线性机制，以平衡表现力与性能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://lzwjava.github.io/kimi-linear-hybrid-attention-en">Kimi Linear Hybrid Attention Architecture</a></li>
<li><a href="https://www.transformer101.com/topics/linear-attention">Linear Attention | Transformer 101</a></li>
<li><a href="https://mbrenndoerfer.com/writing/linear-attention-kernel-feature-maps-efficient-transformers">Linear Attention : Breaking the Quadratic Bottleneck with Kernel...</a></li>

</ul>
</details>

**社区讨论**: 讨论者普遍赞赏项目开放 KDA 内核、vLLM 实现和模型检查点，同时争论架构优势能否延续到前沿模型规模，以及非标准注意力会如何影响专用 Transformer 硬件厂商。一名实践者称内部测试结果积极，但表示后续的 Gated DeltaNet 2 似乎表现力更强，并在其测试中效果更好；另有人提到基于 Kimi Linear 的后继工作，不过这些评论不能替代独立验证。

**标签**: `#linear attention`, `#LLM architecture`, `#transformers`, `#efficient inference`, `#open-source AI`

---

<a id="item-5"></a>
## [DeltaNet 演进至 Kimi Delta Attention。](https://blog.doubleword.ai/you-could-have-come-up-with-kimi-delta-attention) ⭐️ 8.0/10

这篇文章从概念和数学角度梳理了 DeltaNet 系列，追踪线性注意力变体直至 Kimi Delta Attention 的演进过程。文章解释了这些机制如何逐步改进用于表示先前上下文的固定大小循环状态。 线性注意力可能成为处理长序列时替代标准 softmax 注意力的方案，因为其循环状态可以避免 KV 缓存随上下文长度持续增长。理解 DeltaNet 及其后续变体，有助于研究人员和大语言模型架构设计者评估新型注意力设计在效率与表达能力之间的权衡。 基础线性注意力把过去的键值信息压缩到由外积累加形成的固定大小矩阵中，而 DeltaNet 使用 delta 规则，根据预测误差修正该状态。Kimi Delta Attention 在 Gated DeltaNet 的基础上引入更细粒度的逐通道遗忘机制，但压缩后的固定大小状态未必能像完整 softmax 注意力那样保留历史信息。

hackernews · AnhTho_FR · 7月28日 16:02 · [社区讨论](https://news.ycombinator.com/item?id=49085909)

**背景**: 在因果 softmax 注意力中，每个新词元的查询都要与此前所有键进行比较，因此位置 l 的单步解码计算量为 O(l)，KV 缓存也会随序列长度增长。线性注意力通过重新组织计算，把此前的键值交互汇总到固定大小的循环状态中，使模型能够像 RNN 一样运行。DeltaNet 不只是累加或覆盖状态，而是加入由误差驱动的 delta 规则更新；Kimi Delta Attention 则进一步细化状态的遗忘和更新方式。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://sustcsonglin.github.io/blog/2024/deltanet-1/">DeltaNet Explained (Part I) | Songlin Yang</a></li>
<li><a href="https://haileyschoelkopf.github.io/blog/2024/linear-attn/">Linear Attention Fundamentals | Hailey Schoelkopf</a></li>
<li><a href="https://arxiv.org/pdf/2510.26692">Kimi Linear: An Expressive, Efficient Attention Architecture</a></li>

</ul>
</details>

**社区讨论**: 评论者对数学表达方式看法不一：有人批评机器学习领域的符号体系缺乏一致性，也有人认为文章预先定义的狄拉克符号非常直观。多位读者强调，研究创意往往只是在他人完成艰难的原创工作之后才显得简单；另有讨论根据行文风格质疑文章是否由大语言模型撰写，还有评论者分享了另一篇可视化教程。

**标签**: `#linear attention`, `#DeltaNet`, `#transformers`, `#LLM architecture`, `#machine learning`

---

<a id="item-6"></a>
## [超过半数学术论文如今显现出 LLM 影响。](https://www.reddit.com/r/MachineLearning/comments/1v93q78/pnas_over_half_of_all_academic_articles_now_show/) ⭐️ 8.0/10

一项发表于 PNAS、分析了 730 万篇论文的研究估计，到 2025 年，显现出 LLM 影响的学术论文比例已达到 51%。研究还发现，这种影响在声望较低和非英语机构中更为明显。 如果这一估计可靠，LLM 辅助写作已经成为学术出版的主流现象，并对科研诚信、使用披露规则、同行评审和编辑政策提出重要问题。不同机构之间的差异还表明，研究人员采用这些工具可能部分是为了克服语言或资源方面的劣势。 报告中的 51% 指显现出推断性语言影响的论文，并不等同于已被证明由 LLM 生成的论文。基于统计或语言标记的检测能够识别语料库层面的变化，但也可能把正常编辑、翻译、学科写作惯例或非英语母语者的表达误判为 AI 辅助。

reddit · r/MachineLearning · /u/Justgototheeffinmoon · 7月28日 16:38

**背景**: LLM 生成文本检测旨在区分机器生成或机器修改的文字与人类写作，通常会分析语言中的统计特征。一些方法对单篇文献进行分类，而语料库层面的方法则估计特征性措辞在大型文献集合中的流行程度如何变化。科学计量研究会对出版数据进行定量分析，但语言证据通常只能表明可能存在影响，而不能直接观察作者是否实际使用了相关工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2310.14724">A Survey on LLM -Generated Text Detection</a></li>
<li><a href="https://openreview.net/pdf?id=YX7QnhxESU">Mapping the Increasing Use of LLMs in Scientific</a></li>
<li><a href="https://cacm.acm.org/research/the-science-of-detecting-llm-generated-text/">The Science of Detecting LLM -Generated Text – Communications of...</a></li>

</ul>
</details>

**标签**: `#large-language-models`, `#academic-publishing`, `#research-integrity`, `#AI-adoption`, `#scientometrics`

---