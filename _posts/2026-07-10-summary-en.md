---
layout: default
title: "Horizon Summary: 2026-07-10 (EN)"
date: 2026-07-10
lang: en
---

> From 37 items, 3 important content pieces were selected

---

1. [QuadRF visualizes Wi-Fi through walls and spots RF-emitting drones.](#item-1) ⭐️ 8.0/10
2. [GPT-5.6 Sol Ultra reportedly proves the Cycle Double Cover Conjecture.](#item-2) ⭐️ 8.0/10
3. [OpenAI and Google Served Overseas Affiliates of Listed Chinese Firms](#item-3) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [QuadRF visualizes Wi-Fi through walls and spots RF-emitting drones.](https://www.jeffgeerling.com/blog/2026/quadrf-can-spot-drones-and-see-wifi-through-my-wall/) ⭐️ 8.0/10

QuadRF is an open-source spatial RF sensing system that maps wireless emitters in real time, allowing users to locate Wi-Fi sources through walls and spot transmitting drones. Its RF-camera software can scan the supported spectrum at up to 30 frames per second and display signal directions on a spatial plot. The system makes directional RF analysis more accessible for locating rogue access points, hidden wireless devices, interference sources, and drones. Its open-source design and GNU Radio compatibility could also make it useful to SDR researchers, security practitioners, and hardware experimenters. QuadRF currently visualizes signals from 4.9 GHz to 6.0 GHz, color-codes frequencies, and depends on correct camera alignment calibration and radio-gain settings. It detects and localizes RF emissions rather than literally imaging objects through walls, and its ability to spot a drone depends on the aircraft transmitting within the supported band.

hackernews · speckx · Jul 10, 15:59 · [Discussion](https://news.ycombinator.com/item?id=48861717)

**Background**: Software-defined radio, or SDR, shifts functions such as tuning and signal processing from fixed radio hardware into software. Spatial RF sensing combines measurements from directional or multiple antenna channels to estimate where a transmitter is located and then presents that information as a map or heat map. Drones commonly use radio links for control or video, so those emissions can reveal a transmitting aircraft, although RF detection is distinct from radar and does not necessarily identify a silent drone.

<details><summary>References</summary>
<ul>
<li><a href="https://www.crowdsupply.com/scale-rf/quadrf">QuadRF | Crowd Supply</a></li>
<li><a href="https://hackaday.com/2026/06/20/seeing-the-world-in-radio-waves-with-the-quadrf/">Seeing The World In Radio Waves With The QuadRF | Hackaday</a></li>
<li><a href="https://scalerf.com/updates/">QuadRF Updates</a></li>

</ul>
</details>

**Discussion**: Discussion was broadly enthusiastic, with readers proposing applications ranging from smart-glasses visualization and hidden-device searches to drone defense and sound-source localization. The creator clarified that calibration and gain guidance in the demonstration was imperfect and said the open-source interface was being improved based on feedback, while some commenters cautioned indirectly that broader RF-band coverage would be needed for more general-purpose detection.

**Tags**: `#radio-frequency sensing`, `#software-defined radio`, `#drone detection`, `#wireless security`, `#open source`

---

<a id="item-2"></a>
## [GPT-5.6 Sol Ultra reportedly proves the Cycle Double Cover Conjecture.](https://cdn.openai.com/pdf/04d1d1e4-bc75-476a-97cf-49055cd98d31/cdc_proof.pdf) ⭐️ 8.0/10

A PDF attributed to GPT-5.6 Sol Ultra reportedly presents a concise proof of the long-standing Cycle Double Cover Conjecture. The supplied material does not establish that independent graph theorists or a formal proof system have validated the argument. If correct, the proof would resolve a major open problem in graph theory and provide a striking example of a frontier language model contributing to mathematical research. Its broader significance depends on rigorous verification and on whether the model produced genuinely new reasoning rather than a flawed or derivative argument. The conjecture says that every bridgeless graph has a collection of cycles covering each edge exactly twice. Because the reported proof is unusually concise and the claim is extraordinary, line-by-line expert review—and ideally formalization in a proof assistant—is needed before it should be treated as a theorem.

hackernews · scrlk · Jul 10, 18:29 · [Discussion](https://news.ycombinator.com/item?id=48863490)

**Background**: In graph theory, a graph consists of vertices connected by edges, while a cycle is a closed path that does not repeat vertices except at its starting point. A bridge is an edge whose removal disconnects the graph. The Cycle Double Cover Conjecture asks whether every graph without such a bridge admits cycles that collectively use every edge exactly twice; a logical-looking written proof is not automatically reliable until each inference has been checked.

<details><summary>References</summary>
<ul>
<li><a href="https://www.emergentmind.com/topics/cycle-double-cover-cdc-conjecture">Cycle Double Cover Conjecture</a></li>
<li><a href="https://www.sfu.ca/~mohar/Problems/CYCLECOV.HTM">cyclecov</a></li>
<li><a href="https://math.duke.edu/mathplus/2023/automated-theorem-proving-and-proof-verification">Automated theorem proving and proof verification</a></li>

</ul>
</details>

**Discussion**: Commenters were excited that the result is a purported proof rather than merely a counterexample, and some welcomed the release of the prompt while asking about frontier models' overall solve rates. Skeptics emphasized that very few specialists may be qualified to validate the argument, warned that the headline could outrun scrutiny, and questioned whether a short clever proof demonstrates autonomous theory-building.

**Tags**: `#artificial-intelligence`, `#automated-theorem-proving`, `#graph-theory`, `#mathematics`, `#LLMs`

---

<a id="item-3"></a>
## [OpenAI and Google Served Overseas Affiliates of Listed Chinese Firms](https://www.ft.com/content/5d6aafa1-5d47-4585-aa95-6ec06a6cd20f) ⭐️ 8.0/10

OpenAI and Google confirmed that they had provided advanced AI services to Singapore affiliates of Alibaba, Baidu, and Tencent, whose parent companies appear on the U.S. Department of Defense’s Section 1260H list. The access was legal under current rules, but OpenAI suspended API access for Alibaba-linked users last month after detecting suspected model distillation and reported the activity to the U.S. government. The cases expose a gap between entity-based restrictions and access through overseas affiliates, potentially strengthening calls in Washington for controls covering frontier models and APIs. Any expansion could affect U.S. AI providers, Chinese technology groups, and multinational cloud-service compliance practices. Placement on the Section 1260H list does not itself impose a comprehensive ban on ordinary commercial transactions or technology exports, which helps explain why the services remained lawful. Anthropic applies a stricter company policy by barring Chinese companies and their overseas entities from accessing its frontier models.

telegram · zaihuapd · Jul 10, 09:59

**Background**: Section 1260H of the U.S. National Defense Authorization Act for Fiscal Year 2021 requires the Defense Department to identify entities it considers Chinese military companies and report the list to Congress. The designation carries procurement, reputational, and compliance consequences, but it is not equivalent to a blanket sanctions or export-control prohibition. Model distillation can involve using outputs from a capable model’s API as training data for another model, reducing the need for costly human labeling and potentially transferring aspects of the original model’s capabilities.

<details><summary>References</summary>
<ul>
<li><a href="https://sanctionsnews.bakermckenzie.com/us-government-updates-1260h-list-of-chinese-military-companies/">US Government Updates 1260H List of Chinese Military Companies - Global Sanctions and Export Controls Blog</a></li>
<li><a href="https://www.lexology.com/library/detail.aspx?g=c48bdc31-325f-4653-b9c9-aec4e00afcab">美国国防部更新 1260H“中国涉军企业” 清单的法律影响与应对建议 - Lexology</a></li>
<li><a href="https://www.tmtpost.com/7892989.html">Anthropic装糊涂，全球 AI 圈看笑了-钛媒体官方网站</a></li>

</ul>
</details>

**Tags**: `#AI出口管制`, `#OpenAI`, `#Google`, `#中美科技竞争`, `#模型蒸馏`

---