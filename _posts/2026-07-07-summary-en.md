---
layout: default
title: "Horizon Summary: 2026-07-07 (EN)"
date: 2026-07-07
lang: en
---

> From 38 items, 8 important content pieces were selected

---

1. [Januscape exposes KVM guest-to-host escape.](#item-1) ⭐️ 9.0/10
2. [Chat Control proposals threaten encryption.](#item-2) ⭐️ 8.0/10
3. [Chat Control advances in EU Parliament.](#item-3) ⭐️ 8.0/10
4. [Tencent releases Hy3 open-weight LLM.](#item-4) ⭐️ 8.0/10
5. [MIRA brings multiplayer world models to Rocket League.](#item-5) ⭐️ 8.0/10
6. [China plans a national AI compute network.](#item-6) ⭐️ 8.0/10
7. [Anthropic releases Claude Sonnet 5.](#item-7) ⭐️ 8.0/10
8. [China weighs curbs on top AI model exports.](#item-8) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Januscape exposes KVM guest-to-host escape.](https://github.com/V4bel/Januscape) ⭐️ 9.0/10

Security researcher Hyunwoo Kim disclosed Januscape, tracked as CVE-2026-53359, a KVM/x86 vulnerability that can let a guest VM escape to the host or trigger a host kernel panic. The flaw is described as a shadow MMU use-after-free bug affecting both Intel and AMD platforms across Linux kernels from 2010 to June 2026. KVM is a core virtualization layer for Linux servers and cloud infrastructure, so a guest-to-host escape directly threatens the isolation boundary used in multi-tenant environments. Public proof-of-concept code raises the urgency for cloud operators, Linux distributors, and anyone running untrusted VMs on KVM. The bug corrupts KVM shadow-page state in the host kernel through operations initiated inside the guest, and the published PoC can trigger a host kernel panic. The report also says the flaw was used as a Google kvmCTF 0-day and may enable local privilege escalation to root on distributions such as RHEL.

telegram · zaihuapd · Jul 7, 10:14

**Background**: KVM, or Kernel-based Virtual Machine, is the Linux kernel’s built-in virtualization technology and is commonly used to run virtual machines on x86 servers. The KVM shadow MMU maintains shadow page tables that mirror or mediate guest page-table state so the host can safely and efficiently translate guest memory accesses. A use-after-free bug occurs when code continues using memory after it has been freed, which can lead to memory corruption, crashes, or privilege-boundary violations. Google’s kvmCTF is a vulnerability-reward program focused on VM-reachable KVM bugs and on hardening the virtualization boundary.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/V4bel/Januscape">GitHub - V4bel/Januscape</a></li>
<li><a href="https://docs.kernel.org/virt/kvm/x86/mmu.html">The x86 kvm shadow mmu — The Linux Kernel documentation</a></li>
<li><a href="https://security.googleblog.com/2024/06/virtual-escape-real-reward-introducing.html">Virtual Escape; Real Reward: Introducing Google’s kvmCTF</a></li>

</ul>
</details>

**Tags**: `#KVM`, `#virtualization`, `#security`, `#Linux kernel`, `#VM escape`

---

<a id="item-2"></a>
## [Chat Control proposals threaten encryption.](https://fightchatcontrol.eu/chat-control-overview) ⭐️ 8.0/10

Fight Chat Control published an explainer comparing “Chat Control 1.0,” the EU’s temporary voluntary scanning framework, with “Chat Control 2.0,” a proposed permanent regulation that would make detection and reporting of child sexual abuse material mandatory for platforms. The overview highlights that the newer proposal could require scanning private communications, including services using end-to-end encryption. The proposal matters because it sits at the center of a major policy fight over whether governments can mandate large-scale content scanning without undermining encrypted messaging. If adopted, it could affect messaging providers, cloud services, app developers, and ordinary users whose private communications may become subject to automated inspection. Chat Control 1.0 is described as a temporary derogation from the ePrivacy Directive that allowed, but did not require, providers to scan private messages and did not apply to end-to-end encrypted services. Chat Control 2.0, by contrast, is described as a proposed permanent CSAM regulation that could require providers to scan communications and bypass or weaken end-to-end encryption, potentially through client-side scanning before messages are encrypted.

hackernews · gasull · Jul 7, 14:23 · [Discussion](https://news.ycombinator.com/item?id=48818311)

**Background**: End-to-end encryption means that only the sender and intended recipient should be able to read a message, while the service provider should not have access to its contents. Client-side scanning is a proposed workaround in which a user’s device checks text, images, videos, or files before they are encrypted or sent. Critics argue that this changes the trust model of encrypted messaging because the device becomes a monitoring point, even if the network transmission remains encrypted. The EU debate is framed around detecting CSAM, but opponents warn that a general scanning mandate could expand beyond that purpose.

<details><summary>References</summary>
<ul>
<li><a href="https://fightchatcontrol.eu/chat-control-overview">Chat Control 1.0 vs 2.0 - Fight Chat Control</a></li>
<li><a href="https://www.internetsociety.org/resources/doc/2020/fact-sheet-client-side-scanning/">Fact Sheet: Client-Side Scanning - Internet Society UK Government Pushes for Mass Scanning of Encrypted Messages EU Chat Control: What Client-Side Scanning Actually Means for ... Client-Side Scanning: The New Front in the Encryption Debate Why Adding Client-Side Scanning Breaks End-To-End Encryption Bugs in our pockets: the risks of client-side scanning</a></li>
<li><a href="https://www.patrick-breyer.de/en/posts/chat-control/">Chat Control: The EU's CSAM scanner proposal</a></li>

</ul>
</details>

**Discussion**: The discussion is largely skeptical of the proposals, with commenters saying that combating child sexual abuse is important but does not justify broad surveillance powers over everyone’s private messages. Several commenters focus on the technical conflict with end-to-end encryption, debating whether implementation would require privileged decryption, client-side scanning, or an Apple-style on-device scanner. Others raise democratic and civil-liberties concerns, arguing that the measure contradicts privacy promises and could normalize a surveillance state.

**Tags**: `#privacy`, `#encryption`, `#EU regulation`, `#surveillance`, `#tech policy`

---

<a id="item-3"></a>
## [Chat Control advances in EU Parliament.](https://www.heise.de/en/news/Showdown-in-Strasbourg-The-unexpected-return-of-Chat-Control-1-0-11356680.html) ⭐️ 8.0/10

The European Parliament has advanced the controversial “Chat Control” proposal through an initial procedural round, reviving debate over scanning private communications. The move raises renewed concerns about client-side scanning, end-to-end encryption, and privacy safeguards across EU digital services. If adopted, the proposal could affect messaging platforms, cloud services, and users who rely on encrypted communications in the EU. The debate sits at the center of a broader conflict between child-safety enforcement goals and the security guarantees of private digital communication. The core technical concern is client-side scanning, where content can be checked on a user’s device before it is encrypted and sent. Community commenters also emphasized a procedural issue: because the file is reportedly in a second-reading stage, amendments or renewed rejection may require an absolute majority of 361 MEPs, while the opposing side may need only a simple majority of those present.

hackernews · miroljub · Jul 7, 15:16 · [Discussion](https://news.ycombinator.com/item?id=48819008)

**Background**: “Chat Control” is the informal name often used for the EU’s proposed regulation to prevent and combat child sexual abuse online. Client-side scanning refers to systems that inspect message text, images, videos, or files on the sender’s device before delivery, often by comparing them with known patterns or databases. Critics argue that adding such scanning to encrypted apps weakens end-to-end encryption because private content is examined before encryption can protect it. An encryption backdoor generally means special access for third parties, such as authorities, to encrypted communications, which security advocates warn can create systemic risks.

<details><summary>References</summary>
<ul>
<li><a href="https://www.eff.org/deeplinks/2025/09/chat-control-back-menu-eu-it-still-must-be-stopped-0">Chat Control Is Back on the Menu in the EU. It Still Must Be Stopped | Electronic Frontier Foundation</a></li>
<li><a href="https://www.internetsociety.org/resources/doc/2020/fact-sheet-client-side-scanning/">Fact Sheet: Client-Side Scanning - Internet Society</a></li>
<li><a href="https://www.internetsociety.org/blog/2025/05/what-is-an-encryption-backdoor/">What Is an Encryption Backdoor? - Internet Society</a></li>

</ul>
</details>

**Discussion**: The discussion is largely critical of the proposal and its legislative handling, with commenters arguing that unpopular surveillance measures are being reintroduced until they pass. Some participants focused on parliamentary procedure and turnout before the summer break, while others shared voting records and expressed concern about democratic legitimacy and encryption security.

**Tags**: `#privacy`, `#encryption`, `#EU-policy`, `#surveillance`, `#digital-rights`

---

<a id="item-4"></a>
## [Tencent releases Hy3 open-weight LLM.](https://simonwillison.net/2026/Jul/6/hy3/#atom-everything) ⭐️ 8.0/10

Tencent released Hy3, an Apache 2.0-licensed Mixture-of-Experts language model with 295B total parameters, 21B active parameters, 3.8B MTP layer parameters, and a 256K context length. The model follows the Hy3 Preview from late April and is temporarily available for free on OpenRouter until July 21. Hy3 adds another major Chinese open-weight model to the competitive LLM landscape, with permissive licensing that can matter for commercial and research adoption. Its large MoE scale, long context window, and claimed competitiveness with flagship open-source models make it relevant for developers evaluating alternatives to existing open models. The full Hy3 model is listed as 598GB on Hugging Face, while the FP8 quantized version is about 300GB, so local deployment still requires substantial storage and hardware. Tencent says post-training was scaled using higher-quality data after feedback from more than 50 products, but the announcement does not provide independent benchmark validation in the supplied content.

rss · Simon Willison · Jul 6, 23:57

**Background**: A Mixture-of-Experts model uses conditional computation, where only part of the model is activated for a given token or request, which is why Hy3 can have 295B total parameters but only 21B active parameters. This approach is widely used to increase model capacity without making every inference step as expensive as a dense model of the same total size. MTP, or multi-token prediction, refers to model components that learn to anticipate more than one future token, and it can be used in some systems to improve generation efficiency. FP8 quantization stores model values in an 8-bit floating-point format, reducing memory use and potentially improving inference efficiency compared with higher-precision formats.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/blog/moe">Mixture of Experts Explained - Hugging Face</a></li>
<li><a href="https://sebastianraschka.com/llm-architecture-gallery/mtp/">Multi-Token Prediction (MTP) | Sebastian Raschka, PhD</a></li>
<li><a href="https://arxiv.org/abs/2310.18313">[2310.18313] FP8-LM: Training FP8 Large Language Models LLMs and quantization: FP8, FP4, and INT8 explained Images FP8 Quantization for LLM models — AMD Quark 0.12 documentation Floating-Point 8: An Introduction to Efficient, Lower ... GitHub - sii-research/Metis Accelerating large language models with NVFP4 quantization</a></li>

</ul>
</details>

**Tags**: `#AI`, `#LLM`, `#open-source-models`, `#Tencent`, `#machine-learning`

---

<a id="item-5"></a>
## [MIRA brings multiplayer world models to Rocket League.](https://www.reddit.com/r/MachineLearning/comments/1upofuw/mira_multiplayer_interactive_world_models_trained/) ⭐️ 8.0/10

General Intuition, Kyutai, and Epic Games released MIRA, a 5B-parameter interactive multiplayer world model trained on 10,000 hours of synthetic Rocket League gameplay. The release includes a playable online demo, a technical report, an open GitHub repository, and a 1,000-hour four-player gameplay dataset. MIRA is notable because it models a fast, multi-agent game where up to four players' actions jointly affect the generated future, rather than simulating only a single player's viewpoint. This makes it relevant to generative simulation, game AI, and broader research on interactive world models that can respond in real time to human or agent input. According to the release and repository, MIRA generates gameplay frame by frame from all four players' action streams and can run a full 2v2 match at 20 FPS on a single NVIDIA B200 GPU. The technical report says the authors studied scaling from 500M to 5B parameters and from 100 to 10,000 hours of training data, including emergent capabilities and failure modes.

reddit · r/MachineLearning · /u/MasterScrat · Jul 7, 07:59

**Background**: A world model is a machine-learning system that learns an internal representation of an environment and predicts how that environment changes over time in response to actions. In games, this means the model can generate what happens next after players press controls, rather than merely replaying recorded footage. Rocket League is a useful testbed because it has continuous motion, physics-like interactions, and multiple players whose actions interact quickly. The B200 reference indicates that this real-time demo depends on high-end NVIDIA Blackwell-class AI hardware.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/mira-wm/mira">GitHub - mira-wm/mira: Code for MIRA: Multiplayer Interactive World Models with Representation Autoencoders · GitHub</a></li>
<li><a href="https://mira-wm.com/paper">MIRA Multiplayer Interactive World Models with Representation Autoencoders</a></li>
<li><a href="https://www.nvidia.com/en-us/data-center/dgx-b200/">DGX B200: The Foundation for Your AI Factory | NVIDIA</a></li>

</ul>
</details>

**Tags**: `#world-models`, `#generative-ai`, `#game-ai`, `#machine-learning`, `#datasets`

---

<a id="item-6"></a>
## [China plans a national AI compute network.](https://t.me/zaihuapd/42399) ⭐️ 8.0/10

China is reportedly planning to invest about 2 trillion yuan, or roughly $295 billion, over five years to build a nationwide network of interconnected data centers. The plan would have major facilities operated by state-owned telecom companies and would prioritize domestic AI chips and technologies from suppliers such as Huawei. If implemented at this scale, the project could substantially expand access to high-performance AI compute for Chinese companies and public-sector users. It would also reinforce China’s push to reduce reliance on U.S. chipmakers such as Nvidia and AMD amid intensifying semiconductor competition. The report says at least 80% of the chips and technologies used in the project would come from domestic suppliers. It also describes telecom operators such as China Telecom and China Unicom selling token-based compute packages, effectively packaging AI compute in a way similar to mobile data plans.

telegram · zaihuapd · Jul 7, 04:45

**Background**: A nationwide integrated compute network is intended to connect distributed computing resources so that users can access them more efficiently across regions. In China’s policy context, compute power is increasingly treated as digital infrastructure for AI, big data, government services, and industrial applications. The cited “six networks” infrastructure agenda refers to broader efforts to build modern infrastructure networks, including compute networks, power grids, logistics networks, and related systems. Token-based AI plans refer to billing or packaging compute consumption around AI model tokens, which are the units processed when models read or generate text.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.sina.com.cn/tech/roll/2026-04-22/doc-inhvixke5665671.shtml">算力政策讨论实录：全国一体化算力网到底是张什么网？|一体化|财经_新...</a></li>
<li><a href="https://www.gov.cn/lianbo/202605/content_7070126.htm">统筹建设、动态推进“六张网”__中国政府网</a></li>
<li><a href="https://zhuanlan.zhihu.com/p/2040566606816863290">Token套餐全面上线！三大运营商入局，AI时代"流量包"来了</a></li>

</ul>
</details>

**Tags**: `#AI infrastructure`, `#China tech policy`, `#data centers`, `#semiconductors`, `#cloud computing`

---

<a id="item-7"></a>
## [Anthropic releases Claude Sonnet 5.](https://t.me/zaihuapd/42404) ⭐️ 8.0/10

Anthropic released Claude Sonnet 5, describing it as the most capable Sonnet model so far for agentic workflows, coding, tool use, and knowledge work. The announcement says it is stronger than Sonnet 4.6, approaches Opus 4.8 performance, is available immediately across all plans, and becomes the default model for Free and Pro users. If the claimed improvements hold up, Claude Sonnet 5 could make browser-based, terminal-based, and coding-agent workflows more practical for everyday users and developers. Its lower positioning versus higher-end models also matters because agentic tasks can consume many input and output tokens, making price a key adoption factor. The post says Claude Sonnet 5 can plan, use tools such as a browser and terminal, and run autonomously, but it does not provide benchmark tables or detailed safety limitations. It also mentions a limited-time Claude Platform price through August 31, 2026 of $2 per million input tokens, while the provided content is truncated before the full output-token price is shown.

telegram · zaihuapd · Jul 7, 09:02

**Background**: Agentic workflows are AI-driven processes in which agents reason, plan, take actions, and use tools with limited human intervention. In LLM products, tool use can include calling a browser, executing terminal commands, or interacting with external systems to complete multi-step tasks. Token pricing is the common billing model for LLM APIs, with separate charges often applied to input tokens and output tokens, so long prompts, tool calls, and autonomous loops can materially affect cost.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ibm.com/think/topics/agentic-workflows">What are agentic workflows? - IBM</a></li>
<li><a href="https://knightli.com/en/2026/04/25/llm-token-pricing-principles/">Why LLM APIs Charge by Tokens: A Clear Guide to Input, Output ...</a></li>
<li><a href="https://github.com/bradAGI/awesome-cli-coding-agents">bradAGI/awesome-cli-coding-agents - GitHub</a></li>

</ul>
</details>

**Tags**: `#AI`, `#LLM`, `#Anthropic`, `#Claude`, `#AI Agents`

---

<a id="item-8"></a>
## [China weighs curbs on top AI model exports.](https://www.reuters.com/world/beijing-is-looking-curbing-overseas-access-chinas-top-ai-models-sources-say-2026-07-07/) ⭐️ 8.0/10

Reuters reported on July 7 that China’s Ministry of Commerce has recently convened Alibaba, ByteDance, Zhipu AI, and others to discuss restricting overseas access to China’s most advanced domestic AI models, including unreleased models. The discussions also reportedly include possible limits on foreign investment in Chinese AI startups. If adopted, the measures could turn frontier AI model access into a formal export-control issue and affect foreign developers, companies, and investors that rely on Chinese AI systems. It would also signal that China is treating advanced AI capabilities as strategically sensitive technology in a broader geopolitical competition over AI. The reported restrictions are still under discussion, and Reuters said it is unclear whether they will be implemented or whether they would apply only to future model releases. The meetings reportedly also discussed treating leakage or theft of core AI technology as a national-security legal offense.

telegram · zaihuapd · Jul 7, 11:42

**Background**: Top AI models are large systems that can generate text, write code, reason through tasks, and power applications through online access such as APIs. The report names Zhipu AI, whose GLM-4.7 documentation describes it as a high-intelligence model series strengthened for agentic coding, long-horizon task planning, and tool collaboration. Export controls are government restrictions on transferring sensitive goods, software, services, or technology across borders, often justified by national-security concerns.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.bigmodel.cn/cn/guide/models/text/glm-4.7">GLM-4.7 - 智谱AI开放文档</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#export controls`, `#China`, `#geopolitics`, `#AI industry`

---