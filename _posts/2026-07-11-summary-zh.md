---
layout: default
title: "Horizon Summary: 2026-07-11 (ZH)"
date: 2026-07-11
lang: zh
---

> 从 28 条内容中筛选出 6 条重要资讯。

---

1. [vLLM 0.25.0 全面升级大模型推理核心](#item-1) ⭐️ 9.0/10
2. [SGLang v0.5.15 加速生产级大模型推理](#item-2) ⭐️ 8.0/10
3. [相对论效应支配重元素的化学键。](#item-3) ⭐️ 8.0/10
4. [据报道，Apple 起诉 OpenAI 窃取商业秘密。](#item-4) ⭐️ 8.0/10
5. [人形机器人首次远程手术活猪](#item-5) ⭐️ 8.0/10
6. [U-Boot 六个漏洞可引发启动前固件攻击](#item-6) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [vLLM 0.25.0 全面升级大模型推理核心](https://github.com/vllm-project/vllm/releases/tag/v0.25.0) ⭐️ 9.0/10

vLLM 0.25.0 将 Model Runner V2 设为所有稠密模型的默认执行路径，移除旧版 PagedAttention 实现，并使 Transformers 建模后端达到原生 vLLM 的性能水平。该版本包含来自 232 名贡献者的 558 次提交，其中 64 人为首次贡献者，同时新增了模型支持、推测解码能力和多项执行优化。 将新版运行器标准化并淘汰旧代码，有助于简化 vLLM 架构，同时改善使用 GPU 部署大模型的团队所关注的性能与可维护性。更快的 Transformers 后端还让更多模型能够沿用熟悉的 Transformers 实现，而不必必然牺牲原生 vLLM 的服务性能。 Model Runner V2 现已支持 EVS、实时嵌入、Mamba 混合模型的前缀缓存、多模态前缀双向注意力，以及兼容完整 CUDA 图的动态推测解码。其他新增内容包括面向异构词表的通用推测解码、Transformers 后端的 FP8 MoE 支持、统一的流式解析引擎，以及 LLaVA-OneVision-2、Unlimited OCR 和 MOSS-Transcribe-Diarize 等模型。

github · khluu · 7月11日 20:06

**背景**: vLLM 是一个面向高吞吐量和高显存效率大模型推理的开源引擎。Model Runner V2 通过模块化模型逻辑、GPU 原生输入准备、持久批处理和异步调度重构执行核心，以降低 CPU 开销。PagedAttention 是 vLLM 早期用于分块管理注意力键值缓存显存的机制；由于 V1 和 Model Runner V2 后端现已成为标准路径，0.25.0 删除了这一旧版实现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://vllm.ai/blog/2026-03-24-mrv2">Model Runner V2: A Modular and Faster Core for vLLM | vLLM Blog</a></li>
<li><a href="https://docs.vllm.ai/en/v0.22.1/design/model_runner_v2/">Model Runner V2 Design Document - vLLM</a></li>
<li><a href="https://learnopencv.com/vllm-deploy-llms-at-scale-paged-attention/">vLLM : Deploying LLMs at Scale Like OpenAI</a></li>

</ul>
</details>

**标签**: `#vLLM`, `#LLM inference`, `#GPU optimization`, `#CUDA`, `#open source`

---

<a id="item-2"></a>
## [SGLang v0.5.15 加速生产级大模型推理](https://github.com/sgl-project/sglang/releases/tag/v0.5.15) ⭐️ 8.0/10

SGLang v0.5.15 为 NVIDIA Blackwell 引入了面向生产环境调优的 GLM-5.2 NVFP4 推理，在批大小为 1 时，使用 8 张 B300 可达到每用户每秒 500 个以上词元，使用 4 张 GB300 可达到 450 个词元。该版本还将 Spec V2 和可中断 CUDA Graph 设为默认方案，并新增模型支持以及针对长上下文解码、DeepSeek-V4、线性注意力和路由 MoE 的优化。 该版本能够提高服务吞吐量，并降低延迟敏感型或长上下文大模型工作负载的计算成本，尤其有利于在 Blackwell GPU 上部署服务的运营方。调度与计算图优化现已进入默认生产路径，用户不再需要手动启用这些性能功能。 Spec V2 通过可纳入 CUDA Graph 的 DSA 草稿扩展调度、移除设备与主机之间的双向同步，并融合元数据操作，实现了 11% 的端到端吞吐量提升。IndexShare MTP 可将长上下文草稿步骤的成本最多降低至原来的约二分之一，TopK V2 支持运行时 k 值最高达到 2048，而索引器前置操作融合可使批大小为 1 时的解码速度提高约 8%。

github · Fridge003 · 7月10日 22:58

**背景**: SGLang 是一个大模型推理服务框架，负责运行模型推理，并通过运行时优化改善吞吐量和延迟。推测解码会先生成多个候选词元，再对其进行验证；Spec V2 还让调度与 GPU 计算重叠，以减少运行时开销。NVFP4 是 NVIDIA Blackwell 硬件原生支持的 4 位数值格式，在模型和服务栈得到适当优化后，可实现成本更低、吞吐量更高的推理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.sglang.io/docs/advanced_features/speculative_decoding">Speculative Decoding - SGLang Documentation</a></li>
<li><a href="https://huggingface.co/melcheikh/gemma-4-31B-it-qat-NVFP4-Blackwell">melcheikh/gemma-4-31B-it-qat- NVFP 4 - Blackwell · Hugging Face</a></li>
<li><a href="https://newreleases.io/project/github/sgl-project/sglang/release/v0.5.15">sgl-project/ sglang v0.5.15 on GitHub</a></li>

</ul>
</details>

**标签**: `#LLM-serving`, `#SGLang`, `#inference-optimization`, `#speculative-decoding`, `#NVIDIA-Blackwell`

---

<a id="item-3"></a>
## [相对论效应支配重元素的化学键。](https://www.brown.edu/news/2026-07-09/chemical-bonds-relativity) ⭐️ 8.0/10

新研究表明，相对论性自旋—轨道相互作用直接支配涉及重元素的化学键性质。这种耦合打破了传统上对 σ 键与 π 键的严格区分。 这一结果更精确地说明了相对论如何塑造化学键，并可能改进重元素化合物的量子化学模型。这类模型有助于理解和设计性质依赖重原子的材料。 在重原子中，电子运动速度可能高到必须考虑相对论效应，因此电子的自旋与轨道运动不能再被视为完全独立。相对论影响重元素化学这一总体认识早已确立；此次研究的进展在于直接刻画自旋—轨道耦合如何决定化学键的性质。

hackernews · hhs · 7月10日 22:30 · [社区讨论](https://news.ycombinator.com/item?id=48866134)

**背景**: 相对论量子化学把量子化学与相对论力学结合起来，用于描述原子和分子，尤其是含有重元素的体系。重原子核会使部分电子达到相当高的运动速度，从而改变轨道的收缩、扩张和能级分裂。自旋—轨道耦合把电子的内禀自旋与轨道运动联系起来，而 σ 键和 π 键通常用于描述键轴周围不同的电子密度空间分布。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.brown.edu/news/2026-07-09/chemical-bonds-relativity">Einstein’s relativity rules chemical bonds in heavy elements, new research shows | Brown University</a></li>
<li><a href="https://www.sciencedirect.com/science/article/abs/pii/S0010854522005951">Relativistic effects on the chemical bonding properties of the heavier elements and their compounds - ScienceDirect</a></li>
<li><a href="https://www.degruyterbrill.com/document/doi/10.1515/cti-2023-0043/html?lang=en">Relativistic effects on the chemistry of heavier elements: why not given proper importance in chemistry education at the undergraduate and postgraduate level?</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍赞叹相对论在化学中的直接作用，并提到汞在室温下呈液态、黄金具有特殊颜色等常见例子。也有人质疑这一发现是否真正全新，因为重原子中的相对论效应早已为人所知；此次工作的主要区别似乎在于更明确地证明自旋—轨道耦合如何决定化学键性质。

**标签**: `#quantum-chemistry`, `#relativity`, `#chemical-bonding`, `#materials-science`, `#fundamental-physics`

---

<a id="item-4"></a>
## [据报道，Apple 起诉 OpenAI 窃取商业秘密。](https://9to5mac.com/2026/07/10/apple-sues-openai-trade-secret-theft/) ⭐️ 8.0/10

据报道，Apple 已起诉 OpenAI 及数名前 Apple 员工，指控他们转移机密硬件信息并隐瞒招聘活动。所提供报道的日期为 2026 年 7 月 10 日，因此无法根据现有材料独立核实这些说法。 如果指控得到证实，OpenAI 及相关前员工可能面临严重法律后果，其据称开展的硬件业务及与 Apple 供应商的关系也可能受到干扰。此案还可能影响科技公司管理员工离职、人才招聘和商业敏感信息访问权限的方式。 根据讨论中引用的指控，部分被招募者据称被告知不要立即披露他们将入职 OpenAI，一些离职员工还被指通过电子邮件把机密材料发送给自己。Apple 还据称主张 OpenAI 在接触 Apple 供应商时使用了机密硬件信息，但现有材料未提供起诉书、法院回应或独立搜索结果以供核实。

hackernews · stock_toaster · 7月10日 20:47 · [社区讨论](https://news.ycombinator.com/item?id=48865019)

**背景**: 商业秘密是企业通过限制访问和保密要求加以保护、并具有商业价值的信息。当员工跳槽至竞争对手并被指带走或使用受保护的技术信息时，可能引发商业秘密纠纷。在这起据报道的案件中，争议材料涉及 Apple 硬件以及 OpenAI 对前 Apple 员工的招聘。

**社区讨论**: 评论者普遍认为这些指控十分严重，重点关注据称隐瞒招聘活动、员工把机密文件发送给自己，以及接触 Apple 供应商等行为。多人预测 OpenAI 的硬件计划可能遭受严重后果，或进一步担忧客户数据与知识产权风险，但这些判断带有推测性，部分评论的措辞也明显偏激。

**标签**: `#OpenAI`, `#Apple`, `#trade-secrets`, `#AI-industry`, `#technology-law`

---

<a id="item-5"></a>
## [人形机器人首次远程手术活猪](https://arstechnica.com/ai/2026/07/humanoid-robots-controlled-by-surgeons-did-world-first-operation-on-live-pigs/) ⭐️ 8.0/10

外科医生远程操控宇树 G1 人形机器人，为活猪完成了两例微创胆囊切除术，据称这是通用人形机器人首次实施活体动物手术。该临床前研究已发表于《自然》。 这项试验表明，紧凑且成本相对较低的通用机器人未来可能把远程手术扩展到农村、战场、太空任务及其他资源受限环境。它也探索了专用手术系统之外的替代方案，而后者的价格通常可达数十万至数百万美元。 G1 高约 1.5 米、重约 27 公斤，基础款起价为 1.35 万美元，配备灵巧手的版本据称约为 6.7 万美元。现有证据仅来自两例由外科医生遥操作的活猪手术，因此尚不能证明其具备自主手术能力、人体应用安全性或临床可用性。

telegram · zaihuapd · 7月11日 02:29

**背景**: 远程手术让外科医生在控制端操作位于另一地点的机器人器械，动作指令通过通信链路传输。微创胆囊切除术通常通过腹部小切口置入摄像设备和器械，以分离并取出胆囊。与达芬奇等专用手术系统不同，G1 是通用人形机器人，本次研究将其改造用于操控手术工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.aibangbots.com/a/8383">宇树 G1 系列人形机器人全解析｜家用 / 科研 / 竞赛 / 工业全覆盖</a></li>
<li><a href="https://m.fx361.com/news/2022/0516/11747954.html">单臂机器人系统辅助胆囊切除术同传统三孔和单孔腹腔镜胆囊切除术的动物实验对照研究_参考网</a></li>
<li><a href="https://www.thepaper.cn/newsDetail_forward_22289645">5G超远程手术机器人引爆互联网后的下一步_澎湃号·媒体_澎湃新闻-The Paper</a></li>

</ul>
</details>

**标签**: `#人形机器人`, `#远程手术`, `#医疗机器人`, `#机器人学`, `#临床前研究`

---

<a id="item-6"></a>
## [U-Boot 六个漏洞可引发启动前固件攻击](https://www.bleepingcomputer.com/news/security/new-u-boot-flaws-could-enable-stealthy-firmware-attacks/) ⭐️ 8.0/10

Binarly 披露了 U-Boot 的 FIT 签名验证代码中的六个漏洞，其中两个可导致任意代码执行，另外四个可造成设备崩溃。这些漏洞最早可追溯至 U-Boot 2013.07，影响超过 50 个稳定版本以及众多下游厂商分支。 由于漏洞利用发生在固件验证阶段，恶意代码可在操作系统和安全软件启动前运行，进而篡改启动流程或植入持久性固件恶意软件。支持远程固件更新的 BMC 等设备可能在攻击者无需物理接触的情况下受到威胁。 U-Boot 维护者已经接受 Binarly 提交的补丁，但用户只有在硬件厂商将补丁集成进各自固件更新后才能获得修复。停止支持的老旧产品可能长期甚至永久暴露，而现有信息尚未表明这些漏洞已遭到大规模实际利用。

telegram · zaihuapd · 7月11日 08:32

**背景**: U-Boot 是广泛用于嵌入式系统和管理硬件的引导程序，负责初始化设备并加载操作系统。FIT 即扁平化镜像树，可封装内核、设备树和根文件系统等组件，而签名验证用于确保设备只加载可信镜像。BMC 是用于服务器管理的专用控制器，可提供远程开机、重装操作系统和挂载 ISO 镜像等功能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/zhaojh329/U-boot-1/blob/master/第6章-U-boot启动内核之一uImage.md">U - boot -1/第6章- U - boot 启动内核之一uImage.md at master...</a></li>
<li><a href="https://www.link-nemo.com/u/1510311/post/1798288">从路由器到服务器：潜伏 13 年的 U - Boot 漏 洞 曝光，威胁数百万设备</a></li>
<li><a href="https://huluic.cn/article/b1b7d3b1c5c6e80561.html">huluic.cn/article/b1b7d3b1c5c6e80561.html</a></li>

</ul>
</details>

**标签**: `#U-Boot`, `#固件安全`, `#安全启动`, `#任意代码执行`, `#供应链安全`

---