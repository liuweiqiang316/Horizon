---
layout: default
title: "Horizon Summary: 2026-07-07 (ZH)"
date: 2026-07-07
lang: zh
---

> 从 38 条内容中筛选出 8 条重要资讯。

---

1. [Januscape 暴露 KVM 虚拟机逃逸漏洞。](#item-1) ⭐️ 9.0/10
2. [聊天监控提案威胁加密通信。](#item-2) ⭐️ 8.0/10
3. [Chat Control 在 EU 议会推进。](#item-3) ⭐️ 8.0/10
4. [腾讯发布 Hy3 开放权重模型。](#item-4) ⭐️ 8.0/10
5. [MIRA 将多人世界模型带入 Rocket League。](#item-5) ⭐️ 8.0/10
6. [中国拟建设全国 AI 算力网络。](#item-6) ⭐️ 8.0/10
7. [Anthropic 发布 Claude Sonnet 5。](#item-7) ⭐️ 8.0/10
8. [中国考虑限制顶尖 AI 模型出口。](#item-8) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Januscape 暴露 KVM 虚拟机逃逸漏洞。](https://github.com/V4bel/Januscape) ⭐️ 9.0/10

安全研究员 Hyunwoo Kim 公开了 Januscape，即 CVE-2026-53359，这是一个 KVM/x86 漏洞，可让客户虚拟机逃逸到宿主机，或触发宿主机内核崩溃。该漏洞被描述为影子 MMU 中的释放后使用缺陷，影响 2010 年至 2026 年 6 月期间的多个 Linux 内核，并同时涉及 Intel 与 AMD 平台。 KVM 是 Linux 服务器和云基础设施的重要虚拟化层，因此客户机到宿主机的逃逸会直接威胁多租户环境依赖的隔离边界。公开的概念验证代码提高了云服务运营者、Linux 发行版维护者以及在 KVM 上运行不受信任虚拟机的用户的修复紧迫性。 该漏洞可通过客户机内部发起的操作破坏宿主机内核中的 KVM 影子页状态，已发布的概念验证代码能够触发宿主机内核崩溃。报告还称，该漏洞曾作为 Google kvmCTF 的 0-day 使用，并且在 RHEL 等发行版中可能允许本地普通用户提权至 root。

telegram · zaihuapd · 7月7日 10:14

**背景**: KVM，即基于内核的虚拟机，是 Linux 内核内置的虚拟化技术，常用于在 x86 服务器上运行虚拟机。KVM 影子 MMU 维护影子页表，用来镜像或调解客户机页表状态，使宿主机能够安全且高效地转换客户机内存访问。释放后使用漏洞是指代码在内存被释放后仍继续使用该内存，可能导致内存破坏、系统崩溃或权限边界被突破。Google 的 kvmCTF 是一个面向可由虚拟机触达的 KVM 漏洞的奖励项目，目标是强化虚拟化隔离边界。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/V4bel/Januscape">GitHub - V4bel/Januscape</a></li>
<li><a href="https://docs.kernel.org/virt/kvm/x86/mmu.html">The x86 kvm shadow mmu — The Linux Kernel documentation</a></li>
<li><a href="https://security.googleblog.com/2024/06/virtual-escape-real-reward-introducing.html">Virtual Escape; Real Reward: Introducing Google’s kvmCTF</a></li>

</ul>
</details>

**标签**: `#KVM`, `#virtualization`, `#security`, `#Linux kernel`, `#VM escape`

---

<a id="item-2"></a>
## [聊天监控提案威胁加密通信。](https://fightchatcontrol.eu/chat-control-overview) ⭐️ 8.0/10

Fight Chat Control 发布了一篇解释文章，对比了“聊天监控 1.0”和“聊天监控 2.0”，前者是欧盟临时性的自愿扫描框架，后者是拟议中的永久性法规，要求平台强制检测并报告儿童性虐待材料。该概述强调，较新的提案可能要求扫描私人通信，包括使用端到端加密的服务。 该提案之所以重要，是因为它处在一场重大政策争议的核心：政府能否在不破坏加密通信的情况下强制实施大规模内容扫描。如果获得通过，它可能影响消息平台、云服务、应用开发者以及普通用户，因为他们的私人通信可能被自动检查。 聊天监控 1.0 被描述为对《电子隐私指令》的临时例外，允许但不强制服务提供商扫描私人消息，并且不适用于端到端加密服务。相比之下，聊天监控 2.0 被描述为拟议中的永久性儿童性虐待材料法规，可能要求服务提供商扫描通信，并绕过或削弱端到端加密，可能的方式是在消息加密前进行客户端扫描。

hackernews · gasull · 7月7日 14:23 · [社区讨论](https://news.ycombinator.com/item?id=48818311)

**背景**: 端到端加密意味着只有发送者和预期接收者应当能够读取消息，服务提供商不应接触消息内容。客户端扫描是一种拟议的变通方案，即在文本、图片、视频或文件被加密或发送之前，由用户设备先进行检查。批评者认为，这会改变加密通信的信任模型，因为即使网络传输仍然加密，用户设备也会变成监控点。欧盟的这场争论以检测儿童性虐待材料为理由，但反对者警告说，普遍扫描义务可能会扩展到其他用途。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://fightchatcontrol.eu/chat-control-overview">Chat Control 1.0 vs 2.0 - Fight Chat Control</a></li>
<li><a href="https://www.internetsociety.org/resources/doc/2020/fact-sheet-client-side-scanning/">Fact Sheet: Client-Side Scanning - Internet Society UK Government Pushes for Mass Scanning of Encrypted Messages EU Chat Control: What Client-Side Scanning Actually Means for ... Client-Side Scanning: The New Front in the Encryption Debate Why Adding Client-Side Scanning Breaks End-To-End Encryption Bugs in our pockets: the risks of client-side scanning</a></li>
<li><a href="https://www.patrick-breyer.de/en/posts/chat-control/">Chat Control: The EU's CSAM scanner proposal</a></li>

</ul>
</details>

**社区讨论**: 讨论总体上对这些提案持怀疑态度，评论者认为打击儿童性虐待非常重要，但这并不能成为对所有人私人消息实施广泛监控的理由。多名评论者关注它与端到端加密之间的技术冲突，讨论实施方式是否需要特权解密、客户端扫描，或类似 Apple 的设备端扫描器。也有人提出民主和公民自由方面的担忧，认为该措施与保护隐私的承诺相矛盾，并可能使监控国家常态化。

**标签**: `#privacy`, `#encryption`, `#EU regulation`, `#surveillance`, `#tech policy`

---

<a id="item-3"></a>
## [Chat Control 在 EU 议会推进。](https://www.heise.de/en/news/Showdown-in-Strasbourg-The-unexpected-return-of-Chat-Control-1-0-11356680.html) ⭐️ 8.0/10

欧洲议会已在首轮程序中推进有争议的“Chat Control”提案，使围绕私人通信扫描的争论再次升温。此举重新引发了对客户端扫描、端到端加密以及 EU 数字服务隐私保障的担忧。 如果该提案最终通过，它可能影响 EU 内依赖加密通信的消息平台、云服务和用户。这场争论处在儿童安全执法目标与私人数字通信安全保障之间更广泛冲突的核心位置。 核心技术担忧是客户端扫描，也就是内容在用户设备上被加密和发送之前就可能被检查。社区评论者还强调了一个程序性问题：据称该议案处于二读阶段，因此修正案或再次否决可能需要 361 名欧洲议会议员的绝对多数，而支持推进的一方可能只需出席议员的简单多数。

hackernews · miroljub · 7月7日 15:16 · [社区讨论](https://news.ycombinator.com/item?id=48819008)

**背景**: “Chat Control”通常是 EU 拟议的打击线上儿童性虐待法规的非正式名称。客户端扫描是指在消息送达前，在发送者设备上检查文本、图片、视频或文件的系统，通常会将内容与已知模式或数据库进行比对。批评者认为，把这类扫描加入加密应用会削弱端到端加密，因为私人内容会在加密发挥保护作用之前被检查。加密后门通常指为第三方，例如执法机关，提供访问加密通信内容的特殊通道，安全倡导者警告这会带来系统性风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.eff.org/deeplinks/2025/09/chat-control-back-menu-eu-it-still-must-be-stopped-0">Chat Control Is Back on the Menu in the EU. It Still Must Be Stopped | Electronic Frontier Foundation</a></li>
<li><a href="https://www.internetsociety.org/resources/doc/2020/fact-sheet-client-side-scanning/">Fact Sheet: Client-Side Scanning - Internet Society</a></li>
<li><a href="https://www.internetsociety.org/blog/2025/05/what-is-an-encryption-backdoor/">What Is an Encryption Backdoor? - Internet Society</a></li>

</ul>
</details>

**社区讨论**: 讨论整体上对该提案及其立法处理方式持批评态度，评论者认为不受欢迎的监控措施正被反复重新包装并推动，直到通过为止。一些参与者关注暑期休会前的议会程序和出席率，另一些人分享投票记录，并表达了对民主正当性和加密安全的担忧。

**标签**: `#privacy`, `#encryption`, `#EU-policy`, `#surveillance`, `#digital-rights`

---

<a id="item-4"></a>
## [腾讯发布 Hy3 开放权重模型。](https://simonwillison.net/2026/Jul/6/hy3/#atom-everything) ⭐️ 8.0/10

腾讯发布了 Hy3，这是一款采用 Apache 2.0 许可的 Mixture-of-Experts 语言模型，拥有 2950 亿总参数、210 亿激活参数、38 亿 MTP 层参数，以及 256K 上下文长度。该模型是在 4 月下旬 Hy3 Preview 之后推出的，并可在 OpenRouter 免费临时使用至 7 月 21 日。 Hy3 为竞争激烈的大语言模型领域增加了又一个来自中国的重量级开放权重模型，其宽松许可对商业和研究采用都可能很重要。它的大规模 MoE 架构、长上下文窗口，以及与旗舰级开源模型竞争的官方说法，使其对正在评估现有开放模型替代方案的开发者具有参考价值。 完整的 Hy3 模型在 Hugging Face 上标注为 598GB，而 FP8 量化版本约为 300GB，因此本地部署仍然需要相当高的存储和硬件条件。腾讯称，在收集 50 多个产品的反馈后，使用更高质量数据扩大了后训练规模，但所提供内容中没有给出独立基准验证。

rss · Simon Willison · 7月6日 23:57

**背景**: Mixture-of-Experts 模型使用条件计算，也就是针对某个 token 或请求只激活模型的一部分，因此 Hy3 可以拥有 2950 亿总参数，但每次只激活 210 亿参数。这种方法常用于提高模型容量，同时避免让每一步推理都承担同等规模稠密模型的全部计算成本。MTP，即多 token 预测，指模型组件学习预测不止一个未来 token，在一些系统中可用于提升生成效率。FP8 量化使用 8 位浮点格式存储模型数值，相比更高精度格式可以减少内存占用，并可能提升推理效率。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/moe">Mixture of Experts Explained - Hugging Face</a></li>
<li><a href="https://sebastianraschka.com/llm-architecture-gallery/mtp/">Multi-Token Prediction (MTP) | Sebastian Raschka, PhD</a></li>
<li><a href="https://arxiv.org/abs/2310.18313">[2310.18313] FP8-LM: Training FP8 Large Language Models LLMs and quantization: FP8, FP4, and INT8 explained Images FP8 Quantization for LLM models — AMD Quark 0.12 documentation Floating-Point 8: An Introduction to Efficient, Lower ... GitHub - sii-research/Metis Accelerating large language models with NVFP4 quantization</a></li>

</ul>
</details>

**标签**: `#AI`, `#LLM`, `#open-source-models`, `#Tencent`, `#machine-learning`

---

<a id="item-5"></a>
## [MIRA 将多人世界模型带入 Rocket League。](https://www.reddit.com/r/MachineLearning/comments/1upofuw/mira_multiplayer_interactive_world_models_trained/) ⭐️ 8.0/10

General Intuition、Kyutai 和 Epic Games 发布了 MIRA，这是一个拥有 50 亿参数的交互式多人世界模型，使用 1 万小时的合成 Rocket League 游戏数据训练。此次发布包括可在线游玩的演示、技术报告、开源 GitHub 仓库，以及 1000 小时的四人游戏数据集。 MIRA 的重要之处在于，它建模的是一个高速、多智能体游戏环境，最多四名玩家的动作会共同影响生成的后续画面，而不是只模拟单个玩家的视角。这使它对生成式仿真、游戏 AI，以及能够实时响应人类或智能体输入的交互式世界模型研究都具有参考价值。 根据发布内容和仓库说明，MIRA 会根据四名玩家的动作流逐帧生成游戏画面，并能在单张 NVIDIA B200 GPU 上以 20 FPS 运行完整的 2v2 对局。技术报告称，作者研究了模型规模从 5 亿到 50 亿参数、训练数据从 100 小时到 1 万小时的扩展效果，包括涌现能力和典型失败模式。

reddit · r/MachineLearning · /u/MasterScrat · 7月7日 07:59

**背景**: 世界模型是一种机器学习系统，它学习环境的内部表示，并预测环境会如何随动作而随时间变化。在游戏中，这意味着模型可以根据玩家按下的控制输入生成接下来发生的事情，而不仅仅是回放录制视频。Rocket League 是一个有代表性的测试环境，因为它包含连续运动、类似物理的交互，以及多名玩家之间快速相互影响的动作。B200 的提法表明，这个实时演示依赖高端 NVIDIA Blackwell 级 AI 硬件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/mira-wm/mira">GitHub - mira-wm/mira: Code for MIRA: Multiplayer Interactive World Models with Representation Autoencoders · GitHub</a></li>
<li><a href="https://mira-wm.com/paper">MIRA Multiplayer Interactive World Models with Representation Autoencoders</a></li>
<li><a href="https://www.nvidia.com/en-us/data-center/dgx-b200/">DGX B200: The Foundation for Your AI Factory | NVIDIA</a></li>

</ul>
</details>

**标签**: `#world-models`, `#generative-ai`, `#game-ai`, `#machine-learning`, `#datasets`

---

<a id="item-6"></a>
## [中国拟建设全国 AI 算力网络。](https://t.me/zaihuapd/42399) ⭐️ 8.0/10

据报道，中国计划在未来五年投入约 2 万亿元人民币，约合 2950 亿美元，用于建设全国互联的数据中心网络。该计划将由国有电信企业运营主要设施，并优先采用华为等本土供应商的 AI 芯片和技术。 如果按这一规模推进，该项目可能显著扩大中国企业和公共部门获得高性能 AI 算力的能力。它也将强化中国在半导体竞争加剧背景下降低对 Nvidia、AMD 等美国芯片厂商依赖的努力。 报道称，该项目所采用的芯片和技术中至少八成将来自本土供应商。报道还提到，中国电信、中国联通等运营商已推出按 token 计费的算力套餐，类似把 AI 算力像移动数据流量一样打包销售。

telegram · zaihuapd · 7月7日 04:45

**背景**: 全国一体化算力网络的目标，是把分散在不同地区的算力资源连接起来，让用户能更高效地跨区域调用。根据中国相关政策语境，算力正日益被视为支撑 AI、大数据、政务服务和产业应用的数字基础设施。报道提到的“六张网”基础设施议程，指的是建设现代化基础设施网络的更广泛安排，其中包括算力网、电网、物流网等。按 token 计费的 AI 套餐，是围绕 AI 模型处理文本时使用的 token 单位来计量或打包算力消耗。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.sina.com.cn/tech/roll/2026-04-22/doc-inhvixke5665671.shtml">算力政策讨论实录：全国一体化算力网到底是张什么网？|一体化|财经_新...</a></li>
<li><a href="https://www.gov.cn/lianbo/202605/content_7070126.htm">统筹建设、动态推进“六张网”__中国政府网</a></li>
<li><a href="https://zhuanlan.zhihu.com/p/2040566606816863290">Token套餐全面上线！三大运营商入局，AI时代"流量包"来了</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#China tech policy`, `#data centers`, `#semiconductors`, `#cloud computing`

---

<a id="item-7"></a>
## [Anthropic 发布 Claude Sonnet 5。](https://t.me/zaihuapd/42404) ⭐️ 8.0/10

Anthropic 发布了 Claude Sonnet 5，并称其是迄今最适合代理式工作流、编码、工具使用和知识工作的 Sonnet 模型。公告称它强于 Sonnet 4.6，性能接近 Opus 4.8，即日起面向所有套餐开放，并成为免费版和专业版用户的默认模型。 如果这些能力提升在实际使用中成立，Claude Sonnet 5 可能让基于浏览器、终端和编码代理的工作流更适合普通用户和开发者日常使用。它相对高端模型价格更低也很重要，因为代理式任务往往会消耗大量输入和输出词元，成本会直接影响采用率。 该消息称 Claude Sonnet 5 能够规划任务、使用浏览器和终端等工具，并可自主运行，但没有提供基准测试表或详细的安全限制说明。内容还提到 Claude Platform 在 2026 年 8 月 31 日前的限时价格为每百万输入词元 2 美元，但给出的文本在完整输出词元价格出现前被截断了。

telegram · zaihuapd · 7月7日 09:02

**背景**: 代理式工作流是由人工智能驱动的流程，其中代理会进行推理、规划、采取行动，并在较少人工干预的情况下使用工具。在大语言模型产品中，工具使用可以包括调用浏览器、执行终端命令，或与外部系统交互来完成多步骤任务。词元计价是大语言模型接口常见的收费方式，输入词元和输出词元通常分开计费，因此长提示、工具调用和自主循环都会显著影响成本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ibm.com/think/topics/agentic-workflows">What are agentic workflows? - IBM</a></li>
<li><a href="https://knightli.com/en/2026/04/25/llm-token-pricing-principles/">Why LLM APIs Charge by Tokens: A Clear Guide to Input, Output ...</a></li>
<li><a href="https://github.com/bradAGI/awesome-cli-coding-agents">bradAGI/awesome-cli-coding-agents - GitHub</a></li>

</ul>
</details>

**标签**: `#AI`, `#LLM`, `#Anthropic`, `#Claude`, `#AI Agents`

---

<a id="item-8"></a>
## [中国考虑限制顶尖 AI 模型出口。](https://www.reuters.com/world/beijing-is-looking-curbing-overseas-access-chinas-top-ai-models-sources-say-2026-07-07/) ⭐️ 8.0/10

路透社 7 月 7 日报道称，中国商务部近期召集阿里巴巴、字节跳动、智谱 AI 等企业开会，讨论限制最先进国产 AI 模型向海外提供访问，包括尚未发布的模型。相关讨论还据称包括限制境外资本投资中国 AI 初创企业的可能性。 如果相关措施落地，前沿 AI 模型访问可能被正式纳入出口管制范畴，并影响依赖中国 AI 系统的海外开发者、企业和投资者。这也表明，在围绕 AI 的全球竞争中，中国可能正把先进 AI 能力视为具有战略敏感性的技术。 据报道，相关限制仍处于讨论阶段，目前尚不清楚最终是否会实施，也不确定是否只适用于未来发布的新模型。会议还据称讨论了将 AI 核心技术泄露或窃取纳入国家安全法律罪名的问题。

telegram · zaihuapd · 7月7日 11:42

**背景**: 顶尖 AI 模型通常是能够生成文本、编写代码、进行推理并通过 API 等在线方式为应用提供能力的大型系统。报道中提到的智谱 AI，其 GLM-4.7 文档将该系列描述为面向智能体编程、长程任务规划和工具协同强化的高智能模型。出口管制是政府对敏感商品、软件、服务或技术跨境转移设置的限制，通常以国家安全风险作为理由。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.bigmodel.cn/cn/guide/models/text/glm-4.7">GLM-4.7 - 智谱AI开放文档</a></li>

</ul>
</details>

**标签**: `#AI policy`, `#export controls`, `#China`, `#geopolitics`, `#AI industry`

---