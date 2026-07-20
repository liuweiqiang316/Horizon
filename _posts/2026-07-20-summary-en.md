---
layout: default
title: "Horizon Summary: 2026-07-20 (EN)"
date: 2026-07-20
lang: en
---

> From 36 items, 4 important content pieces were selected

---

1. [A Hacker Reportedly Wiped Romania’s Land Registry.](#item-1) ⭐️ 8.0/10
2. [AI-Writing Estimates on arXiv Hit Detector Limits.](#item-2) ⭐️ 8.0/10
3. [Fastjson 1.x Reportedly Has a Gadget-Free Critical RCE](#item-3) ⭐️ 8.0/10
4. [Zhipu Completes a Gigawatt-Scale Data Center Using Chinese Chips](#item-4) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [A Hacker Reportedly Wiped Romania’s Land Registry.](https://news.risky.biz/risky-bulletin-hacker-wipes-romanias-entire-land-registry-database/) ⭐️ 8.0/10

A hacker reportedly erased Romania’s land registry systems and connected backups, prompting the responsible agency to restore its website and rebuild its network from scratch. Officials may still be able to recover the records from an offline copy, but the integrity and completeness of that recovery have not yet been publicly confirmed. Land registry records underpin proof of property ownership, so permanent loss or corruption could disrupt sales, mortgages, inheritance, taxation, and legal disputes. The incident also highlights how backup isolation and tested recovery procedures are essential for government systems that support critical public functions. Restoring the public website does not by itself demonstrate that the underlying registry data is intact, and the alleged deletion of all backups remains unverified. Commenters also cited an agency announcement about migrating applications to Romania’s Government Cloud under the coordination of the Special Telecommunications Service, with inspections expected to assess the applications and data afterward.

hackernews · speckx · Jul 20, 13:28 · [Discussion](https://news.ycombinator.com/item?id=48978605)

**Background**: An offline backup is separated from the production network and therefore may remain unreachable when an attacker compromises online systems and connected backup infrastructure. This separation can prevent malware or ransomware from deleting every recoverable copy, although organizations must still test restoration and verify the recovered data. For a land registry, recovery must preserve not only records but also their accuracy and consistency because they are used to establish property rights.

<details><summary>References</summary>
<ul>
<li><a href="https://www.backblaze.com/blog/disaster-recovery-101-backup-vs-replication/">Disaster Recovery 101: The Difference Between Cloud Replication...</a></li>

</ul>
</details>

**Discussion**: Commenters were cautiously relieved that an offline copy might prevent a lasting loss of ownership records, while emphasizing that recovery claims still need verification. Other discussion blamed weak passwords and possibly missing 2FA, alleged corruption in government IT contracting, and debated a security firm’s claimed identification of an Algerian suspect and the relevance of extradition arrangements; these claims remain speculative or unverified.

**Tags**: `#cybersecurity`, `#critical-infrastructure`, `#data-recovery`, `#government-IT`, `#ransomware`

---

<a id="item-2"></a>
## [AI-Writing Estimates on arXiv Hit Detector Limits.](https://unslop.run/blog/measuring-ai-writing-on-arxiv) ⭐️ 8.0/10

An analysis scored the full text of 12,750 arXiv papers from 2021 through January 2026, finding that 39% were flagged as machine-written in January 2026, with computer science peaking at 65%. The author also examined detector error and cautioned that these flags cannot be treated as reliable estimates of actual AI use. The results suggest a sharp rise in AI-assisted scientific writing, but they also show why detector outputs could mislead publishers, reviewers, and researchers. If false positives vary by discipline, writing style, or time period, apparent growth rates may reflect measurement drift as well as changing author behavior. The detector was deliberately tuned to reduce false positives and produced a pre-ChatGPT flag rate of about 0.4%; mathematics reportedly remained near 0.7% while computer science rose much more sharply. Nevertheless, community tests found scores of 27%, 40%, and 74% on human-written documents from 2011, 2012, and 2015, illustrating that a low aggregate baseline does not eliminate severe errors on individual papers.

hackernews · dopamine_daddy · Jul 20, 16:36 · [Discussion](https://news.ycombinator.com/item?id=48981206)

**Background**: AI-writing detectors infer likely authorship from statistical properties of text rather than directly observing how a document was produced. Some methods use signals such as perplexity and burstiness, while others use supervised classifiers, but their performance can deteriorate under domain shift, new generators, or paraphrasing. False positives are especially important in low-prevalence settings because even a seemingly small error rate can substantially distort the estimated share of AI-written papers.

<details><summary>References</summary>
<ul>
<li><a href="https://sebastianraschka.com/blog/2023/detect-ai.html">What Are the Different Approaches for Detecting Content Generated by LLMs Such As ChatGPT? And How Do They Work and Differ?</a></li>
<li><a href="https://www.emergentmind.com/topics/ai-text-detectors">AI Text Detectors: Methods & Challenges</a></li>
<li><a href="https://lawlibguides.sandiego.edu/c.php?g=1443311&p=10721367">The Problems with AI Detectors: False Positives and False Negatives - Generative AI Detection Tools - Guides at University of San Diego Legal Research Center</a></li>

</ul>
</details>

**Discussion**: Discussion was strongly skeptical of text-only detection: one commenter reported high machine-writing scores for several pre-LLM academic works, while another argued that identical text cannot be classified differently based on whether a human or model produced it. Others focused on incentives, warning that organizations may reward the volume and superficial polish generated by tools such as Claude Code without being able to measure underlying quality.

**Tags**: `#AI detection`, `#arXiv`, `#scientific publishing`, `#measurement reliability`, `#generative AI`

---

<a id="item-3"></a>
## [Fastjson 1.x Reportedly Has a Gadget-Free Critical RCE](https://x.com/k_firsov/status/2078872293745570032) ⭐️ 8.0/10

Security researcher Kirill Firsov reported a critical remote code execution vulnerability affecting Fastjson 1.2.68 through 1.2.83. The researcher claims exploitation does not require autoTypeSupport or a classpath gadget and works on JDK 8, 17, and 21. Fastjson is a widely deployed Java JSON library, so a gadget-independent RCE could expose applications even when operators believe existing AutoType restrictions have reduced their risk. The report is especially urgent because Fastjson 1.x reportedly stopped receiving maintenance in October 2024, leaving migration to Fastjson2 or another maintained parser as the longer-term response. The immediate recommendations are to enable SafeMode through startup parameters or configuration and to migrate to Fastjson2. However, the disclosure currently lacks a CVE, public technical analysis, proof of concept, or official vendor confirmation, so the exact attack conditions, affected scope, and effectiveness of the proposed mitigations remain independently unverified.

telegram · zaihuapd · Jul 20, 14:32

**Background**: Fastjson's AutoType mechanism can use type information embedded in JSON to select a Java class during deserialization, which has historically created security risks when processing untrusted input. A classpath gadget is existing code in an application's dependencies that an attacker chains together to reach a dangerous operation such as command execution. Fastjson 1.2.68 and later support SafeMode, which the project's documentation says completely disables AutoType.

<details><summary>References</summary>
<ul>
<li><a href="https://alibaba.github.io/fastjson2/autotype_cn.html">FASTJSON 2 Autotype 机 制 介绍 | fastjson 2</a></li>
<li><a href="https://github.com/alibaba/fastjson/wiki/fastjson_safemode">fastjson_safemode · alibaba/fastjson Wiki</a></li>
<li><a href="https://www.cnblogs.com/leyilea/p/18426099">Java反序列化利用链篇 | CC1链_全网最菜的分析思路【本系列文章的分析...</a></li>

</ul>
</details>

**Tags**: `#Fastjson`, `#远程代码执行`, `#Java安全`, `#供应链安全`, `#漏洞披露`

---

<a id="item-4"></a>
## [Zhipu Completes a Gigawatt-Scale Data Center Using Chinese Chips](https://www.bloomberg.com/news/articles/2026-07-20/z-ai-completes-giant-data-center-with-chinese-chips-to-train-ai) ⭐️ 8.0/10

Zhipu reportedly completed a 1-gigawatt data center equipped entirely with Chinese-made chips and has begun partial operations. The facility will support development of its frontier GLM models. If confirmed at the reported scale, the project would mark a major advance in China's effort to build large AI training infrastructure without relying on foreign accelerators. It could also demonstrate whether domestic chips can be integrated into clusters large enough for frontier-model development. Zhipu reportedly already operates several computing clusters containing more than 10,000 chips each, but the report does not identify the chip models or disclose performance, efficiency, networking, utilization, or the capacity currently online. The 1-gigawatt figure describes power scale rather than compute performance, and only part of the facility is reportedly operating.

telegram · zaihuapd · Jul 20, 15:43

**Background**: GLM is Zhipu's self-developed model architecture and the foundation of its large-model platform. Training frontier models requires large clusters of accelerators working together to process enormous datasets, making chip availability, interconnects, power delivery, and cooling important constraints. A gigawatt is one billion watts, so a facility at this power scale represents unusually large infrastructure, although its actual AI capability depends on the installed and operational hardware.

<details><summary>References</summary>
<ul>
<li><a href="https://immersivetranslate.com/blog/zhipu_glm_immersive_translate_new_model/">沉浸式翻译接入 智 谱 GLM ...</a></li>
<li><a href="https://h5.ifeng.com/c/vivoArticle/v0025LUUQpbAyR2FaFkag4ZHmf8NF1aeAqjIdqyeCvjPTnI__?isNews=1&showComments=0">英伟达为何值5万亿美元？ 答案或藏在 AI 数 据 中 心 里</a></li>

</ul>
</details>

**Tags**: `#AI基础设施`, `#国产芯片`, `#数据中心`, `#智谱AI`, `#大模型训练`

---