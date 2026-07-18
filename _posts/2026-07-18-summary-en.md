---
layout: default
title: "Horizon Summary: 2026-07-18 (EN)"
date: 2026-07-18
lang: en
---

> From 33 items, 5 important content pieces were selected

---

1. [GPT-5.6 reportedly closes a decades-old convex optimization gap.](#item-1) ⭐️ 8.0/10
2. [Windows Update silently installs LG monitor software.](#item-2) ⭐️ 8.0/10
3. [SpaceX Discusses Multibillion-Dollar AI Computing Deal With Pentagon](#item-3) ⭐️ 8.0/10
4. [TSMC Targets A14 Production in 2028.](#item-4) ⭐️ 8.0/10
5. [US Weighs FINRA-Like Watchdog for Leading AI Models](#item-5) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [GPT-5.6 reportedly closes a decades-old convex optimization gap.](https://old.reddit.com/r/math/comments/1uxj3cy/after_openais_cdc_proof_announcement_gpt56_used_a/) ⭐️ 8.0/10

An advanced GPT system reportedly generated a proof closing a roughly 30-year oracle-complexity gap for deterministic, derivative-free minimization of convex Lipschitz functions. The associated paper studies optimization over a d-dimensional Euclidean ball using only exact function-value queries. If the proof withstands expert review, it would be a genuine, though specialized, mathematical contribution and evidence that language models can assist with unresolved theoretical research. It may also shift how mathematicians and theoretical computer scientists select problems, verify proofs, and train junior researchers. The result concerns deterministic query complexity when an algorithm can observe exact function values but not derivatives, rather than a general solution to convex optimization. The supplied material does not include the proof, independent validation, or a clear account of the model workflow, and commenters also disputed whether the run used “Sol Pro” rather than “Ultra.”

hackernews · mbustamanter · Jul 18, 13:00 · [Discussion](https://news.ycombinator.com/item?id=48957779)

**Background**: A convex function has a shape that makes every local minimum a global minimum, while Lipschitz continuity limits how rapidly its value can change. Derivative-free optimization must locate an approximate minimum through function evaluations rather than gradients. Oracle complexity counts how many such queries an algorithm needs, and a complexity gap exists when the best known upper and lower bounds do not match.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/html/2607.13335v1">Closing the Oracle-Complexity Gap in Derivative-Free Convex ...</a></li>
<li><a href="https://arxiv.org/pdf/1407.5144v1">Lower Bounds on the Oracle Complexity of Nonsmooth Convex ...</a></li>

</ul>
</details>

**Discussion**: The discussion was impressed but cautious: a knowledgeable commenter characterized the result as narrower than OpenAI’s cyclic double cover work, yet still a real contribution. Participants debated whether AI will eliminate “low-” and “medium-hanging” research problems that traditionally train junior mathematicians, while others questioned the model’s multi-agent workflow and suggested using LLMs to examine difficult, human-opaque proofs.

**Tags**: `#convex-optimization`, `#AI-for-mathematics`, `#theoretical-computer-science`, `#automated-theorem-proving`, `#large-language-models`

---

<a id="item-2"></a>
## [Windows Update silently installs LG monitor software.](https://videocardz.com/newz/lg-monitors-silently-install-software-through-windows-update-without-user-consent) ⭐️ 8.0/10

Connecting a compatible LG monitor can prompt Windows Update to install LG’s Monitor App Installer automatically, without an explicit approval step. The installed software can run persistently and promote additional products such as McAfee software. The behavior expands a routine hardware-detection process into a channel for installing network-enabled vendor applications, creating user-consent, privacy, and software-supply-chain concerns. It also raises questions about Microsoft’s responsibility for reviewing and limiting applications distributed through trusted Windows device-installation mechanisms. The monitor itself does not directly execute an installer; Windows identifies the hardware and retrieves an associated application through its device-metadata and update infrastructure. Users can disable automatic manufacturer-app downloads through Group Policy, or through Device Installation Settings on Windows editions without gpedit.msc, although doing so may also block useful companion apps.

hackernews · baranul · Jul 18, 10:21 · [Discussion](https://news.ycombinator.com/item?id=48956688)

**Background**: Windows Update routinely downloads and installs recommended drivers for connected hardware, including displays, audio devices, and network adapters. Windows can also associate device metadata with manufacturer-provided companion applications, allowing software to arrive when matching hardware is detected. Because users generally trust this automated path, insufficiently reviewed vendor packages can create security and supply-chain risks beyond those of an ordinary optional download.

<details><summary>References</summary>
<ul>
<li><a href="https://learn.microsoft.com/en-in/answers/questions/5906642/how-to-check-if-drivers-are-up-to-date">How to check if drivers are up to date - Microsoft Q&A</a></li>
<li><a href="https://cybersecuritynews.com/windows-update-installs-lg-monitor-app-pushes-mcafee-ads/">Windows Update Silently Installs LG Monitor App That Pushes...</a></li>
<li><a href="https://learn.microsoft.com/en-us/windows-hardware/drivers/driversecurity/driver-security-checklist">Driver security checklist - Windows drivers | Microsoft Learn</a></li>

</ul>
</details>

**Discussion**: Commenters were broadly alarmed that connecting hardware could trigger installation of persistent, internet-capable third-party software, with some describing the behavior as malware-like. Several argued that Microsoft bears primary responsibility because Windows—not the monitor—initiates the installation, while others shared Group Policy and Device Installation Settings mitigations and called for a more granular driver-consent model.

**Tags**: `#Windows Update`, `#device security`, `#privacy`, `#bloatware`, `#supply chain`

---

<a id="item-3"></a>
## [SpaceX Discusses Multibillion-Dollar AI Computing Deal With Pentagon](https://www.wsj.com/tech/ai/spacex-in-talks-to-provide-computing-power-for-pentagons-ai-push-15e752e4) ⭐️ 8.0/10

SpaceX is negotiating with the U.S. Department of Defense to provide data-center computing capacity for classified and operational AI applications. The potential contract could be worth billions of dollars, but the talks remain ongoing and could still collapse. A deal would extend SpaceX beyond its space and satellite businesses into defense AI infrastructure while deepening its relationship with the Pentagon. It could also reshape competition among major providers seeking to supply cloud computing and AI technology to U.S. national-security agencies. The Pentagon has reportedly approved technologies from SpaceX, Amazon, Google, Microsoft, and Oracle for use in classified environments. SpaceX has also recently reached related computing-supply agreements with Anthropic and Google, although the prospective Pentagon deal's architecture, capacity, schedule, and security requirements were not disclosed.

telegram · zaihuapd · Jul 18, 01:44

**Background**: Cloud computing lets organizations obtain computing and data-center resources without operating every system locally. For the Pentagon, classified cloud environments must support sensitive national-security and military workloads while meeting stricter access and information-protection requirements. The department is accelerating its acquisition of this capacity as it expands the use of AI models in national-security functions and routine operations.

**Tags**: `#SpaceX`, `#国防科技`, `#AI基础设施`, `#云计算`, `#五角大楼`

---

<a id="item-4"></a>
## [TSMC Targets A14 Production in 2028.](https://t.me/zaihuapd/42643) ⭐️ 8.0/10

TSMC announced that its next-generation A14 process is scheduled to enter production in 2028, following the planned late-2026 launch of A16. Compared with N2, A14 is projected to deliver up to 15% higher performance at the same power, up to 30% lower power at the same speed, and more than 20% higher logic density. If these targets are achieved, A14 could extend TSMC's manufacturing advantage for performance- and power-sensitive chips, including high-performance computing and AI products. The roadmap also gives chip designers an early view of the process options expected after N2 and A16. A14 is described as a 1.4-nanometer-class process based on TSMC's second-generation GAAFET nanosheet transistors and its NanoFlex Pro design-technology co-optimization approach. The performance, power, and density figures are currently roadmap projections for a process planned for 2028, rather than results from mass-produced chips.

telegram · zaihuapd · Jul 18, 05:00

**Background**: A semiconductor process node is a generation of manufacturing technology used to build transistors and interconnects on a chip; names such as N2, A16, and A14 distinguish successive generations rather than directly specifying every physical feature. TSMC's N2 introduces nanosheet transistors, a form of gate-all-around transistor intended to improve control of current as devices shrink. A14 is positioned as a later generation that further improves performance, power efficiency, and logic density.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cls.cn/detail/2014112">台积电A14制程细节亮相：速度提升15%，2028年量产！</a></li>
<li><a href="https://baike.baidu.com/item/A14/65752676">A14_百度百科</a></li>

</ul>
</details>

**Tags**: `#台积电`, `#半导体制造`, `#A14制程`, `#芯片技术`, `#制程路线图`

---

<a id="item-5"></a>
## [US Weighs FINRA-Like Watchdog for Leading AI Models](https://www.bloomberg.com/news/articles/2026-07-17/us-considers-creating-finra-like-watchdog-to-vet-top-ai-models) ⭐️ 8.0/10

The Trump administration is discussing an industry-participating, independent body that would review the safety of leading AI models and report to the SEC. Treasury Secretary Scott Bessent is leading development of the proposal, which is under review by White House Chief of Staff Susie Wiles. If adopted, the framework could reshape how frontier models are evaluated and released in the United States while giving the financial and technology industries a larger role in setting safety standards. It could also establish a new division of responsibility between government oversight and industry self-regulation, particularly around cybersecurity risks. The proposal has not yet been reviewed by President Donald Trump, remains under discussion, and may change. It follows objections from Anthropic and OpenAI to government demands affecting recent model releases and aligns broadly with Demis Hassabis's call for an industry-funded independent regulator.

telegram · zaihuapd · Jul 18, 05:45

**Background**: FINRA is an independent, nongovernmental self-regulatory organization for the US securities industry, operating under SEC oversight. A FINRA-like AI body would therefore use industry participation and specialized rulemaking or review while remaining accountable to a federal regulator. In this proposal, that model would be adapted to safety reviews of leading AI systems rather than oversight of securities firms and professionals.

<details><summary>References</summary>
<ul>
<li><a href="https://www.mg21.com/finra.html">美国金融业监管局：Financial Industry Regulatory Authority(FINRA) | 美股之家 - 港股美股开户投资百科全书</a></li>

</ul>
</details>

**Tags**: `#AI监管`, `#前沿模型`, `#模型安全`, `#美国政策`, `#网络安全`

---