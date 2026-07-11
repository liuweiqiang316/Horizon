---
layout: default
title: "Horizon Summary: 2026-07-11 (EN)"
date: 2026-07-11
lang: en
---

> From 28 items, 6 important content pieces were selected

---

1. [vLLM 0.25.0 Modernizes Its LLM Inference Core](#item-1) ⭐️ 9.0/10
2. [SGLang v0.5.15 Accelerates Production LLM Serving](#item-2) ⭐️ 8.0/10
3. [Relativity governs chemical bonding in heavy elements.](#item-3) ⭐️ 8.0/10
4. [Apple Reportedly Sues OpenAI Over Alleged Trade-Secret Theft.](#item-4) ⭐️ 8.0/10
5. [Humanoid Robot Performs First Telesurgery on Live Pigs](#item-5) ⭐️ 8.0/10
6. [Six U-Boot Flaws Enable Pre-Boot Firmware Attacks](#item-6) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [vLLM 0.25.0 Modernizes Its LLM Inference Core](https://github.com/vllm-project/vllm/releases/tag/v0.25.0) ⭐️ 9.0/10

vLLM 0.25.0 makes Model Runner V2 the default execution path for all dense models, removes the legacy PagedAttention implementation, and brings the Transformers modeling backend to native-vLLM performance. The release comprises 558 commits from 232 contributors, including 64 first-time contributors, while adding new models, speculative-decoding capabilities, and execution optimizations. Making the newer runner standard and retiring legacy code should simplify vLLM's architecture while improving performance and maintainability for teams serving LLMs on GPUs. A faster Transformers backend also lets more models use familiar Transformers implementations without necessarily sacrificing native-vLLM serving performance. Model Runner V2 now supports EVS, real-time embeddings, prefix caching for Mamba hybrid models, multimodal-prefix bidirectional attention, and dynamic speculative decoding with full CUDA graphs. Other additions include speculative decoding across heterogeneous vocabularies, FP8 MoE support in the Transformers backend, a unified Streaming Parser Engine, and models such as LLaVA-OneVision-2, Unlimited OCR, and MOSS-Transcribe-Diarize.

github · khluu · Jul 11, 20:06

**Background**: vLLM is an open-source engine designed for high-throughput, memory-efficient LLM inference. Model Runner V2 restructures its execution core around modular model logic, GPU-native input preparation, persistent batching, and asynchronous scheduling to reduce CPU overhead. PagedAttention was vLLM's earlier mechanism for managing attention key-value cache memory in blocks; version 0.25.0 removes that legacy implementation because the V1 and Model Runner V2 backends are now the standard paths.

<details><summary>References</summary>
<ul>
<li><a href="https://vllm.ai/blog/2026-03-24-mrv2">Model Runner V2: A Modular and Faster Core for vLLM | vLLM Blog</a></li>
<li><a href="https://docs.vllm.ai/en/v0.22.1/design/model_runner_v2/">Model Runner V2 Design Document - vLLM</a></li>
<li><a href="https://learnopencv.com/vllm-deploy-llms-at-scale-paged-attention/">vLLM : Deploying LLMs at Scale Like OpenAI</a></li>

</ul>
</details>

**Tags**: `#vLLM`, `#LLM inference`, `#GPU optimization`, `#CUDA`, `#open source`

---

<a id="item-2"></a>
## [SGLang v0.5.15 Accelerates Production LLM Serving](https://github.com/sgl-project/sglang/releases/tag/v0.5.15) ⭐️ 8.0/10

SGLang v0.5.15 introduces production-tuned GLM-5.2 NVFP4 inference on NVIDIA Blackwell, reaching more than 500 tokens per second per user on eight B300 GPUs and 450 on four GB300 GPUs at batch size one. It also makes Spec V2 and Breakable CUDA Graph the defaults, while adding model support and optimizations for long-context decoding, DeepSeek-V4, linear attention, and routed MoE. The release can increase serving throughput and reduce the compute cost of latency-sensitive or long-context LLM workloads, particularly for operators deploying on Blackwell GPUs. Its default scheduling and graph changes also move performance features into the standard production path instead of requiring manual opt-in. Spec V2 reports an 11% end-to-end throughput gain by using CUDA-graphable DSA draft-extend scheduling, removing device-to-host and host-to-device synchronizations, and fusing metadata operations. IndexShare MTP cuts long-context draft-step cost by up to 1.9 times, while TopK V2 supports runtime k values up to 2048 and indexer prologue fusion makes batch-size-one decoding about 8% faster.

github · Fridge003 · Jul 10, 22:58

**Background**: SGLang is an LLM serving framework that runs model inference and applies runtime optimizations to improve throughput and latency. Speculative decoding accelerates generation by drafting multiple candidate tokens and then verifying them, while Spec V2 overlaps scheduling with GPU computation to reduce runtime overhead. NVFP4 is a 4-bit numerical format supported natively by NVIDIA Blackwell hardware, allowing lower-cost, higher-throughput inference when a model and serving stack are appropriately optimized.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.sglang.io/docs/advanced_features/speculative_decoding">Speculative Decoding - SGLang Documentation</a></li>
<li><a href="https://huggingface.co/melcheikh/gemma-4-31B-it-qat-NVFP4-Blackwell">melcheikh/gemma-4-31B-it-qat- NVFP 4 - Blackwell · Hugging Face</a></li>
<li><a href="https://newreleases.io/project/github/sgl-project/sglang/release/v0.5.15">sgl-project/ sglang v0.5.15 on GitHub</a></li>

</ul>
</details>

**Tags**: `#LLM-serving`, `#SGLang`, `#inference-optimization`, `#speculative-decoding`, `#NVIDIA-Blackwell`

---

<a id="item-3"></a>
## [Relativity governs chemical bonding in heavy elements.](https://www.brown.edu/news/2026-07-09/chemical-bonds-relativity) ⭐️ 8.0/10

New research reports that relativistic spin-orbit interactions directly govern the character of chemical bonds involving heavy elements. The coupling disrupts the conventional strict separation between sigma and pi bonds. The result provides a more precise account of how relativity shapes bonding, potentially improving quantum-chemistry models of heavy-element compounds. Such models are relevant to understanding and designing materials whose properties depend on heavy atoms. In heavy atoms, electrons can move fast enough for relativistic effects to become important, so their spin and orbital motion can no longer be treated as fully independent. The broader influence of relativity on heavy-element chemistry was already established; the reported advance is the direct characterization of spin-orbit coupling as a determinant of bond character.

hackernews · hhs · Jul 10, 22:30 · [Discussion](https://news.ycombinator.com/item?id=48866134)

**Background**: Relativistic quantum chemistry combines quantum chemistry with relativistic mechanics to describe atoms and molecules, particularly those containing heavy elements. Heavy nuclei cause some electrons to reach substantial fractions of the speed of light, altering orbital contraction, expansion, and energy splitting. Spin-orbit coupling links an electron’s intrinsic spin to its orbital motion, while sigma and pi bonds conventionally describe different spatial patterns of electron density around a bond axis.

<details><summary>References</summary>
<ul>
<li><a href="https://www.brown.edu/news/2026-07-09/chemical-bonds-relativity">Einstein’s relativity rules chemical bonds in heavy elements, new research shows | Brown University</a></li>
<li><a href="https://www.sciencedirect.com/science/article/abs/pii/S0010854522005951">Relativistic effects on the chemical bonding properties of the heavier elements and their compounds - ScienceDirect</a></li>
<li><a href="https://www.degruyterbrill.com/document/doi/10.1515/cti-2023-0043/html?lang=en">Relativistic effects on the chemistry of heavier elements: why not given proper importance in chemistry education at the undergraduate and postgraduate level?</a></li>

</ul>
</details>

**Discussion**: Commenters were enthusiastic about relativity’s visible role in chemistry and cited familiar examples such as mercury’s liquid state and gold’s color. Several questioned whether the finding was fundamentally new, noting that relativistic effects in heavy atoms have long been known; the main distinction appears to be a sharper demonstration of how spin-orbit coupling determines bond character.

**Tags**: `#quantum-chemistry`, `#relativity`, `#chemical-bonding`, `#materials-science`, `#fundamental-physics`

---

<a id="item-4"></a>
## [Apple Reportedly Sues OpenAI Over Alleged Trade-Secret Theft.](https://9to5mac.com/2026/07/10/apple-sues-openai-trade-secret-theft/) ⭐️ 8.0/10

Apple has reportedly sued OpenAI and several former Apple employees, alleging that they transferred confidential hardware information and concealed their recruitment activities. The supplied report is dated July 10, 2026, so its claims cannot be independently verified from the provided materials. If substantiated, the allegations could expose OpenAI and the former employees to serious legal consequences while disrupting OpenAI's reported hardware ambitions and relationships with Apple suppliers. The case could also influence how technology companies manage employee departures, recruiting, and access to commercially sensitive information. According to the allegations quoted in the discussion, recruits were told not to disclose their OpenAI jobs immediately, and some departing employees allegedly emailed confidential material to themselves. Apple also reportedly claims that OpenAI used confidential hardware information when contacting Apple suppliers, but no complaint, court response, or independent search result was provided for verification.

hackernews · stock_toaster · Jul 10, 20:47 · [Discussion](https://news.ycombinator.com/item?id=48865019)

**Background**: Trade secrets are commercially valuable information that companies protect by limiting access and requiring confidentiality. Disputes can arise when employees move to a competitor and are accused of taking or using protected technical information. In this reported case, the disputed material concerns Apple hardware and OpenAI's recruitment of former Apple personnel.

**Discussion**: Commenters largely viewed the allegations as serious, focusing on the claimed concealment of recruitment, employees emailing themselves confidential files, and outreach to Apple suppliers. Several predicted severe consequences for OpenAI's hardware efforts or raised broader concerns about customer data and intellectual property, although those predictions were speculative and some comments were strongly polemical.

**Tags**: `#OpenAI`, `#Apple`, `#trade-secrets`, `#AI-industry`, `#technology-law`

---

<a id="item-5"></a>
## [Humanoid Robot Performs First Telesurgery on Live Pigs](https://arstechnica.com/ai/2026/07/humanoid-robots-controlled-by-surgeons-did-world-first-operation-on-live-pigs/) ⭐️ 8.0/10

Surgeons remotely controlled a Unitree G1 humanoid robot to complete two minimally invasive gallbladder removals on live pigs, reportedly the first live-animal operations performed with a general-purpose humanoid. The preclinical study was published in Nature. The experiment suggests that a compact, relatively inexpensive general-purpose robot could extend telesurgery to rural areas, battlefields, space missions, and other resource-constrained settings. It also explores an alternative to specialized surgical systems that can cost hundreds of thousands to millions of dollars. The approximately 1.5-meter-tall, 27-kilogram G1 starts at $13,500, while the configuration with dexterous hands reportedly costs about $67,000. The evidence is limited to two pig procedures under surgeon teleoperation, so it does not demonstrate autonomous surgery, safety in humans, or clinical readiness.

telegram · zaihuapd · Jul 11, 02:29

**Background**: Telesurgery allows a surgeon at a control station to operate robotic instruments at another location by transmitting commands over a communications link. Minimally invasive gallbladder removal generally uses small abdominal access ports, a camera, and instruments to separate and extract the gallbladder. Unlike purpose-built systems such as the da Vinci platform, the G1 is a general-purpose humanoid robot adapted here to manipulate surgical tools.

<details><summary>References</summary>
<ul>
<li><a href="https://www.aibangbots.com/a/8383">宇树 G1 系列人形机器人全解析｜家用 / 科研 / 竞赛 / 工业全覆盖</a></li>
<li><a href="https://m.fx361.com/news/2022/0516/11747954.html">单臂机器人系统辅助胆囊切除术同传统三孔和单孔腹腔镜胆囊切除术的动物实验对照研究_参考网</a></li>
<li><a href="https://www.thepaper.cn/newsDetail_forward_22289645">5G超远程手术机器人引爆互联网后的下一步_澎湃号·媒体_澎湃新闻-The Paper</a></li>

</ul>
</details>

**Tags**: `#人形机器人`, `#远程手术`, `#医疗机器人`, `#机器人学`, `#临床前研究`

---

<a id="item-6"></a>
## [Six U-Boot Flaws Enable Pre-Boot Firmware Attacks](https://www.bleepingcomputer.com/news/security/new-u-boot-flaws-could-enable-stealthy-firmware-attacks/) ⭐️ 8.0/10

Binarly disclosed six vulnerabilities in U-Boot's FIT signature-verification code: two can enable arbitrary code execution and four can crash devices. The flaws date back to U-Boot 2013.07 and affect more than 50 stable releases as well as numerous downstream vendor branches. Because exploitation occurs during firmware verification, malicious code could run before the operating system and security tools start, potentially altering the boot process or establishing persistent firmware malware. Devices such as remotely updatable BMC systems may be exposed without requiring an attacker to have physical access. U-Boot maintainers have accepted Binarly's patches, but users will receive fixes only after hardware vendors integrate them into their own firmware updates. Unsupported legacy products may remain vulnerable indefinitely, and the supplied information does not indicate widespread exploitation in the wild.

telegram · zaihuapd · Jul 11, 08:32

**Background**: U-Boot is a bootloader widely used in embedded systems and management hardware to initialize a device and load its operating system. FIT, or Flattened Image Tree, packages components such as the kernel, device tree, and root filesystem, while signature verification is intended to ensure that only trusted images are loaded. A BMC is a dedicated server-management controller that can provide remote operations such as powering on a machine, reinstalling its operating system, and mounting an ISO image.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/zhaojh329/U-boot-1/blob/master/第6章-U-boot启动内核之一uImage.md">U - boot -1/第6章- U - boot 启动内核之一uImage.md at master...</a></li>
<li><a href="https://www.link-nemo.com/u/1510311/post/1798288">从路由器到服务器：潜伏 13 年的 U - Boot 漏 洞 曝光，威胁数百万设备</a></li>
<li><a href="https://huluic.cn/article/b1b7d3b1c5c6e80561.html">huluic.cn/article/b1b7d3b1c5c6e80561.html</a></li>

</ul>
</details>

**Tags**: `#U-Boot`, `#固件安全`, `#安全启动`, `#任意代码执行`, `#供应链安全`

---