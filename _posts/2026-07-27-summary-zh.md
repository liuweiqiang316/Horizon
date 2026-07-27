---
layout: default
title: "Horizon Summary: 2026-07-27 (ZH)"
date: 2026-07-27
lang: zh
---

> 从 28 条内容中筛选出 5 条重要资讯。

---

1. [月之暗面在 Hugging Face 发布 Kimi-K3 权重](#item-1) ⭐️ 9.0/10
2. [vLLM v0.26.0 带来全面的推理与硬件升级](#item-2) ⭐️ 8.0/10
3. [Bun 的 Rust 重写版本已在 Claude Code 中运行。](#item-3) ⭐️ 8.0/10
4. [Fastjson 1.x 被曝存在无 gadget 远程代码执行漏洞](#item-4) ⭐️ 8.0/10
5. [中芯国际据报测试国产先进 DUV 光刻机](#item-5) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [月之暗面在 Hugging Face 发布 Kimi-K3 权重](https://huggingface.co/moonshotai/Kimi-K3) ⭐️ 9.0/10

月之暗面已在 Hugging Face 发布 Kimi-K3，允许开发者获取模型并进行部署和定制。该模型拥有 2.8 万亿个参数，属于约 3 万亿参数规模的模型。 与只能使用封闭 API 相比，此次发布让机构能更自主地进行微调、管理专有数据并掌控知识产权。它也将实际检验第三方服务商能否以具有商业可行性的价格托管数万亿参数模型。 Kimi-K3 原生采用 MXFP4 量化，并被描述为具备原生视觉能力和 100 万词元的上下文窗口。其许可证规定，如果模型即服务运营商及其关联方在任意连续 12 个月内的合计收入超过 2000 万美元，则在将该软件或其衍生作品用于商业用途前，必须与月之暗面另行签署协议。

hackernews · nateb2022 · 7月27日 06:18 · [社区讨论](https://news.ycombinator.com/item?id=49065752)

**背景**: 开放权重模型会提供训练后的参数，使开发者能够自行托管或调整模型，而不必完全依赖开发者提供的 API。参数数量是显存需求的主要决定因素之一，而量化通过以较低精度存储权重来减少内存占用。社区估算认为，即使采用 MXFP4，Kimi-K3 的权重仍需约 1.5 TB 显存，且这还不包括长上下文和生产级吞吐量所需的额外内存。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.kimi.com/blog/kimi-k3">Kimi K 3 Tech Blog: Open Frontier Intelligence</a></li>
<li><a href="https://huggingface.co/moonshotai/Kimi-K3/blob/main/LICENSE">LICENSE · moonshotai/ Kimi - K 3 at main</a></li>
<li><a href="https://apxml.com/courses/mlops-for-large-models-llmops/chapter-1-foundations-llmops/llm-infrastructure-requirements">Infrastructure Requirements for Large Models</a></li>

</ul>
</details>

**社区讨论**: 讨论者普遍看好模型定制、使用专有数据进行微调以及知识产权自主权，但对自行托管的经济性和可及性提出质疑。有人估算仅权重就需要约 1.5 TB 显存，而要获得实用的上下文容量和吞吐量可能需要 16 块 B200；另有人列出 Fireworks AI 的价格，即每百万未缓存输入词元 3 美元、每百万缓存输入词元 0.30 美元、每百万输出词元 15 美元，同时也有讨论关注许可证的收入门槛限制以及高显存准专业级硬件的缺失。

**标签**: `#large-language-models`, `#open-weight-models`, `#AI-infrastructure`, `#model-licensing`, `#Hugging-Face`

---

<a id="item-2"></a>
## [vLLM v0.26.0 带来全面的推理与硬件升级](https://github.com/vllm-project/vllm/releases/tag/v0.26.0) ⭐️ 8.0/10

vLLM v0.26.0 汇集了 212 名贡献者提交的 411 次代码变更，并为 Inkling 模型家族加入 CUDA 图、Hopper FA4 相对注意力、MTP 推测解码、LoRA 和 ModelOpt NVFP4 量化支持。该版本还带来了跨硬件厂商的 DeepSeek-V4 优化、fp32 生成头、更灵活的注意力后端、扩展的 KV 卸载能力，以及 Rust 前端的多模态改进。 该版本可帮助使用 NVIDIA、AMD 和 XPU 硬件部署大语言模型的团队改善吞吐量、延迟、准确性和部署灵活性。更广泛的模型支持、量化、推测解码、LoRA 与分层存储能力相结合，也让不同生产负载更容易采用优化推理。 对于 DeepSeek-V4，发布说明称专用路由内核带来了 2.94% 的端到端 TPOT 改进，fused_topk_bias 内核速度提升至 1.5 至 2 倍，移除冗余的重复与复制操作又带来了 1.8% 的 TPOT 改进。新的 head_dtype 选项允许 lm_head 使用 fp32 计算，并覆盖 LoRA 路径；同时，每个 KV 缓存组现在可以独立选择注意力后端。

github · khluu · 7月27日 01:06

**背景**: vLLM 是一个用于高效运行和服务大语言模型的推理引擎。KV 缓存保存先前已处理词元的注意力状态，而 KV 卸载会在加速器显存受限时，将部分状态转移到辅助存储。推测解码先通过草稿机制生成候选词元，再进行验证；CUDA 图则通过捕获可重复使用的执行流程来减少反复启动 GPU 任务的开销，而分段 CUDA 图会将这种方式应用于选定的执行部分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.vllm.ai/en/stable/design/cuda_graphs/">CUDA Graphs - vLLM</a></li>
<li><a href="https://github.com/vllm-project/vllm/blob/main/docs/design/cuda_graphs.md">vllm/docs/design/cuda_graphs.md at main · vllm-project/vllm</a></li>

</ul>
</details>

**标签**: `#vLLM`, `#LLM inference`, `#GPU optimization`, `#speculative decoding`, `#quantization`

---

<a id="item-3"></a>
## [Bun 的 Rust 重写版本已在 Claude Code 中运行。](https://lockwood.dev/ai/2026/07/27/how-is-the-bun-rewrite-in-rust-going.html) ⭐️ 8.0/10

Bun 创建者 Jarred Sumner 表示，该运行时的 Rust 重写版本已在 Claude Code 中运行一个多月，整体进展顺利。Bun 1.4 仍需等到承诺的 Node.js 兼容性测试通过后才能发布，暂定于随后一个星期二推出。 将一个重要运行时从 Zig 迁移到 Rust，并在大量使用 LLM 辅助的情况下成功部署，为性能敏感型项目提供了一个值得关注的实践案例。其结果可能影响开发者对大型软件重写中的语言选择、AI 辅助翻译、可维护性和兼容性的判断。 Bun 团队表示，在重写过程中大量使用了 Claude Fable 5 的预发布版本，但在 Claude Code 中完成部署本身并不能证明其已具备完整的 Node.js 兼容性或长期可维护性。Bun 1.4 将等到承诺数量的新增 Node.js 测试通过后才发布，而相关拉取请求据称仍处于已提交但尚未合并的状态。

hackernews · tomlockwood · 7月27日 11:12 · [社区讨论](https://news.ycombinator.com/item?id=49067854)

**背景**: Bun 是一种 JavaScript 运行时，目标是在提供自有高性能工具的同时运行现有的 Node.js 应用和 npm 软件包。它通过兼容层重新实现 Node.js API，并将能够在 Node.js 中运行却无法在 Bun 中运行的软件包视为兼容性缺陷。该项目正在用 Rust 重写大量 Zig 代码，希望在保持性能的同时提高可靠性、可维护性以及贡献者参与的便利程度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://bun.com/blog/bun-in-rust">Rewriting Bun in Rust | Bun Blog</a></li>
<li><a href="https://bun.sh/docs/runtime/nodejs-apis">Node . js compatibility – Runtime | Bun Docs</a></li>
<li><a href="https://www.cosmicjs.com/blog/bun-rust-rewrite-javascript-runtime">Why Bun Is Rewriting in Rust: What It Means for JavaScript Developers</a></li>

</ul>
</details>

**社区讨论**: 社区讨论十分活跃，但观点不一：一些参与者认为，借助 LLM 快速完成重写并在几乎无人察觉的情况下部署到 Claude Code 非常惊人；另一些人则认为，在重大重构之后，提交数量和发布频率并不能有效反映项目进度。质疑者强调，快速翻译代码并不等同于持续开发功能和保证可维护性，还有评论者引用了一个改进原有 Zig 代码的替代项目，认为部分促成重写的问题或许无需更换语言也能解决。

**标签**: `#Bun`, `#Rust`, `#AI-assisted coding`, `#runtime engineering`, `#software rewrites`

---

<a id="item-4"></a>
## [Fastjson 1.x 被曝存在无 gadget 远程代码执行漏洞](https://t.me/zaihuapd/42797) ⭐️ 8.0/10

安全研究人员 Kirill Firsov 披露，Fastjson 1.2.68 至 1.2.83 存在高危远程代码执行漏洞。据称，该漏洞无需启用 autoTypeSupport，也不依赖类路径中的 gadget，并可在 JDK 8、17 和 21 上利用。 Fastjson 是广泛使用的 Java JSON 库，因此处理攻击者可控输入的受影响应用可能面临严重风险。由于 Fastjson 1.x 据称已于 2024 年 10 月停止维护，用户可能需要迁移至 Fastjson2，而不能依赖后续补丁。 该披露尤其值得关注，因为其声称利用过程不需要两个常见前提：启用 AutoType，以及类路径中存在可用的 gadget。不过，现有报告内容并不完整，且未提供 CVE 编号、概念验证、完整缓解配置或官方确认，因此受影响团队在准确判断暴露范围前应进一步核实。

telegram · zaihuapd · 7月27日 10:31

**背景**: Fastjson 用于在 JSON 数据与 Java 对象之间进行转换。其 AutoType 机制可以保留并恢复具体的 Java 类型信息，但允许输入影响实例化类型，历来会带来反序列化安全风险。在 Java 漏洞利用中，gadget 是攻击者在反序列化期间串联起来以触发恶意行为的现有类或代码路径；若漏洞确实不依赖类路径中的 gadget，就意味着少了一项重要的环境限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://alibaba.github.io/fastjson2/autotype_cn.html">FASTJSON 2 Autotype 机 制 介绍 | fastjson 2</a></li>
<li><a href="https://cn-sec.com/archives/3332099.html">聊聊在反序列化漏洞中如何找Gadget利用链 | CN-SEC 中文网</a></li>
<li><a href="https://www.cnblogs.com/johnnyzen/p/17814937.html">[JSON] Fastjson 之版本对比：Fastjson vs Fastjson2 - 千千寰宇 - 博...</a></li>

</ul>
</details>

**标签**: `#Fastjson`, `#Java`, `#RCE`, `#软件供应链安全`, `#漏洞披露`

---

<a id="item-5"></a>
## [中芯国际据报测试国产先进 DUV 光刻机](https://t.me/zaihuapd/42800) ⭐️ 8.0/10

据报道，中芯国际正在试运行上海初创公司宇量昇研发的先进 DUV 光刻机，用于制造 28 纳米芯片，并探索通过多重图形化实现 7 纳米、甚至以较低良率挑战 5 纳米。该消息尚未获得中芯国际或其他权威来源确认。 如果消息得到证实，这次测试将是中国半导体设备供应链国产化的重要一步，并可能降低其受出口管制影响的程度。不过，其商业影响仍取决于设备能否在规模化生产中实现稳定产能、可接受良率和持续可靠运行。 据称，该设备的大部分零部件已实现国产化，但仍有部分依赖进口；业内人士估计，实现稳定量产可能还需一至两年，最快或于 2027 年投入量产。使用 DUV 制造 7 纳米或 5 纳米特征需要多重图形化，这会增加工艺步骤，并提高对准、良率、成本和生产稳定性方面的难度。

telegram · zaihuapd · 7月27日 14:10

**背景**: 光刻是把电路图案转移到硅晶圆上的工艺，也是芯片制造的核心环节之一。DUV 系统通常使用 248 纳米或 193 纳米波长的光，而 EUV 使用短得多的波长，并广泛用于先进制程制造。多重图形化把高密度电路图案拆分到多次曝光和处理步骤中，使 DUV 设备能够制造单次曝光难以分辨的更小特征。

<details><summary>参考链接</summary>
<ul>
<li><a href="http://www.ime.cas.cn/icac/learning/learning_2/202112/t20211221_6324996.html">DUV和EUV光刻机的区别在哪？--科普知识</a></li>
<li><a href="https://zh.wikipedia.org/zh-hans/极紫外光刻">极紫外光刻 - 维基百科，自由的百科全书</a></li>
<li><a href="https://zhuanlan.zhihu.com/p/1960307062815855033">半导体先进工艺：多重图形化技术（LELE、SADP、SAQP）</a></li>

</ul>
</details>

**标签**: `#半导体`, `#DUV光刻机`, `#中芯国际`, `#芯片制造`, `#出口管制`

---