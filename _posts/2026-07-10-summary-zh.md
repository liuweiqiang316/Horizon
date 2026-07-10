---
layout: default
title: "Horizon Summary: 2026-07-10 (ZH)"
date: 2026-07-10
lang: zh
---

> 从 37 条内容中筛选出 3 条重要资讯。

---

1. [QuadRF 可隔墙显示 Wi-Fi 并发现发射射频信号的无人机。](#item-1) ⭐️ 8.0/10
2. [据称，GPT-5.6 Sol Ultra 证明了循环双覆盖猜想。](#item-2) ⭐️ 8.0/10
3. [OpenAI 与 Google 曾服务被列名中企的海外关联实体](#item-3) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [QuadRF 可隔墙显示 Wi-Fi 并发现发射射频信号的无人机。](https://www.jeffgeerling.com/blog/2026/quadrf-can-spot-drones-and-see-wifi-through-my-wall/) ⭐️ 8.0/10

QuadRF 是一套开源空间射频感知系统，可实时绘制无线发射源的位置，让用户隔墙定位 Wi-Fi 信号源，并发现正在发射信号的无人机。其射频相机软件能以最高每秒 30 帧扫描支持的频谱，并在空间图上显示信号方向。 该系统让定向射频分析更易用于定位恶意接入点、隐藏式无线设备、干扰源和无人机。其开源设计以及对 GNU Radio 的兼容性，也可能使其成为 SDR 研究人员、安全从业者和硬件实验者的实用工具。 QuadRF 目前可视化 4.9 GHz 至 6.0 GHz 的信号，以颜色区分频率，并依赖正确的摄像头对齐校准和无线电增益设置。它检测和定位的是射频发射，而不是直接隔墙拍摄物体；能否发现无人机取决于无人机是否在支持的频段内发射信号。

hackernews · speckx · 7月10日 15:59 · [社区讨论](https://news.ycombinator.com/item?id=48861717)

**背景**: 软件定义无线电（SDR）把调谐和信号处理等功能从固定无线电硬件转移到软件中。空间射频感知结合定向天线或多个天线通道的测量结果，估算发射源所在方向或位置，再将信息显示为地图或热力图。无人机通常使用无线电链路进行控制或传输视频，因此这些发射信号可能暴露正在通信的无人机；不过，射频探测不同于雷达，也不一定能发现不发射信号的无人机。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.crowdsupply.com/scale-rf/quadrf">QuadRF | Crowd Supply</a></li>
<li><a href="https://hackaday.com/2026/06/20/seeing-the-world-in-radio-waves-with-the-quadrf/">Seeing The World In Radio Waves With The QuadRF | Hackaday</a></li>
<li><a href="https://scalerf.com/updates/">QuadRF Updates</a></li>

</ul>
</details>

**社区讨论**: 讨论整体较为兴奋，读者提出了智能眼镜可视化、隐藏设备排查、无人机防御和声源定位等潜在应用。项目创建者说明，演示中的对齐校准和增益设置指导并不完善，并表示正根据反馈改进开源界面；另有评论指出，若要实现更通用的探测，还需要覆盖更多常用射频频段。

**标签**: `#radio-frequency sensing`, `#software-defined radio`, `#drone detection`, `#wireless security`, `#open source`

---

<a id="item-2"></a>
## [据称，GPT-5.6 Sol Ultra 证明了循环双覆盖猜想。](https://cdn.openai.com/pdf/04d1d1e4-bc75-476a-97cf-49055cd98d31/cdc_proof.pdf) ⭐️ 8.0/10

一份据称由 GPT-5.6 Sol Ultra 生成的 PDF 给出了长期未决的循环双覆盖猜想的简洁证明。现有材料尚未表明该论证已通过独立图论专家或形式化证明系统的验证。 如果证明正确，它将解决图论中的一个重要开放问题，并成为前沿语言模型参与数学研究的突出案例。其更广泛的意义取决于严格验证，以及模型是否提出了真正新颖的推理，而不是存在缺陷或模仿既有思路的论证。 该猜想认为，每个无桥图都存在一组环，使每条边恰好被覆盖两次。由于据称的证明异常简洁且主张非同寻常，在将其视为定理之前，需要专家逐行审查，最好还应在证明助手中完成形式化验证。

hackernews · scrlk · 7月10日 18:29 · [社区讨论](https://news.ycombinator.com/item?id=48863490)

**背景**: 在图论中，图由顶点及连接顶点的边组成，而环是一条除起点外不重复顶点的闭合路径。桥是指删除后会使图不再连通的边。循环双覆盖猜想询问每个无桥图是否都存在一组环，使所有边合计恰好出现两次；一份表面上逻辑严密的书面证明并不会自动成立，仍需核查其中的每一步推导。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.emergentmind.com/topics/cycle-double-cover-cdc-conjecture">Cycle Double Cover Conjecture</a></li>
<li><a href="https://www.sfu.ca/~mohar/Problems/CYCLECOV.HTM">cyclecov</a></li>
<li><a href="https://math.duke.edu/mathplus/2023/automated-theorem-proving-and-proof-verification">Automated theorem proving and proof verification</a></li>

</ul>
</details>

**社区讨论**: 评论者对这是一份据称成立的证明而非仅仅一个反例感到兴奋，也有人欢迎公开提示词，并追问前沿模型尝试开放问题时的总体成功率。质疑者强调，可能只有极少数专家具备验证该论证的能力，担心标题热度超过实际审查进度，并认为简短巧妙的证明未必代表模型具备自主构建理论的能力。

**标签**: `#artificial-intelligence`, `#automated-theorem-proving`, `#graph-theory`, `#mathematics`, `#LLMs`

---

<a id="item-3"></a>
## [OpenAI 与 Google 曾服务被列名中企的海外关联实体](https://www.ft.com/content/5d6aafa1-5d47-4585-aa95-6ec06a6cd20f) ⭐️ 8.0/10

OpenAI 与 Google 确认，曾向阿里巴巴、百度和腾讯的新加坡关联实体提供先进 AI 服务，而这些公司的母公司均被列入美国国防部的 1260H 名单。相关服务在现行规则下属于合法行为，但 OpenAI 上月发现疑似模型蒸馏活动后，暂停了阿里巴巴关联用户的 API 访问权限，并向美国政府报告。 这些案例暴露了实体名单限制与企业通过海外关联实体获取服务之间的制度缺口，可能推动华盛顿将出口管制扩大至前沿模型及其 API。此类政策变化将影响美国 AI 服务商、中国科技企业以及跨国云服务的合规做法。 被列入 1260H 名单本身并不会自动触发对普通商业交易或技术出口的全面禁令，因此上述服务仍可合法提供。Anthropic 采取了更严格的企业政策，禁止中国公司及其海外实体访问该公司的前沿模型。

telegram · zaihuapd · 7月10日 09:59

**背景**: 美国《2021 财年国防授权法》第 1260H 条要求国防部识别其认定的中国军事企业，并向国会提交相关名单。被列名会带来采购限制、声誉风险和合规影响，但并不等同于全面制裁或出口禁令。模型蒸馏可以利用高性能模型通过 API 生成的输出训练另一个模型，从而降低人工标注成本，并可能转移原模型的部分能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://sanctionsnews.bakermckenzie.com/us-government-updates-1260h-list-of-chinese-military-companies/">US Government Updates 1260H List of Chinese Military Companies - Global Sanctions and Export Controls Blog</a></li>
<li><a href="https://www.lexology.com/library/detail.aspx?g=c48bdc31-325f-4653-b9c9-aec4e00afcab">美国国防部更新 1260H“中国涉军企业” 清单的法律影响与应对建议 - Lexology</a></li>
<li><a href="https://www.tmtpost.com/7892989.html">Anthropic装糊涂，全球 AI 圈看笑了-钛媒体官方网站</a></li>

</ul>
</details>

**标签**: `#AI出口管制`, `#OpenAI`, `#Google`, `#中美科技竞争`, `#模型蒸馏`

---