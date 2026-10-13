---
layout: default
title: "Horizon Summary: 2026-10-13 (ZH)"
date: 2026-10-13
lang: zh
---

> 从 38 条内容中筛选出 2 条重要资讯。

---

**科技新闻**
1. [欧洲超市冷柜遭网络攻击](#item-tech-news-1) ⭐️ 8.0/10
2. [Python 3.15 发布](#item-tech-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [欧洲超市冷柜遭网络攻击](https://www.tomshardware.com/tech-industry/cyber-security/unprecedented-cyberattack-cripples-supermarket-fridges-across-europe-as-hackers-activate-automatic-defrosting-delivery-and-store-prices-also-impacted-by-incident) ⭐️ 8.0/10

报道称，黑客攻击了欧洲多地超市的制冷系统，并触发自动除霜，导致冷柜受影响，凸显联网工业与零售控制系统的现实风险。源材料列出路透社、BBC 和《世界报》的相关报道，其中法国超市集团 Intermarché 被称为受害方之一，约 150 家门店遭到针对，配送和门店价格系统也受到事件影响。该事件的公开技术细节有限，但相关链接指向 Claroty Team82 对 Danfoss 制冷控制器漏洞的研究，表明老旧或联网制冷控制器可能成为攻击面。由于制冷中断会直接影响食品保存、门店运营和供应链，该事件不只是传统 IT 入侵，也涉及运营技术安全和设备生命周期管理。

hackernews · Zeekaas · 10月12日 12:16 · [社区讨论](https://news.ycombinator.com/item?id=50055304)

**「背景」** 超市冷柜和冷库常由联网制冷控制器集中监测温度、告警和除霜流程，这类设备属于零售场景中的运营技术系统，而不是传统办公 IT。Claroty Team82 在 2026 年 8 月披露过 Danfoss AK-SM 800A 制冷控制器平台的多个漏洞，称其影响嵌入式 Web 管理界面，Danfoss 已在新版固件中修复。

**「影响」** 受影响的超市需要处理冷链中断、潜在食品损耗以及门店运营系统受扰的问题，同时暴露出使用老旧联网控制器的零售设施面临可被远程滥用的风险。

**「社区讨论」** 评论者主要围绕为什么冷柜控制器会联网、老旧 Danfoss 控制器和 CVE 是否相关、以及低利润零售环境为何难以及时更换设备展开讨论。也有人指出远程诊断、节能和减少工程师上门是联网制冷系统的商业动因，并将此事与 2026 年 8 月美国军事基地冷柜疑似被攻击的讨论相联系，但是否同一漏洞或同一攻击者尚无定论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claroty.com/team82/research/freeze-the-controller-defrost-the-food-uncovering-vulnerabilities-in-danfoss-refrigeration-controllers">Freeze the Controller, Defrost the Food: Uncovering ...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#operational-technology`, `#industrial-control-systems`, `#retail-tech`, `#vulnerabilities`

---

<a id="item-tech-news-2"></a>
### [Python 3.15 发布](https://simonwillison.net/2026/Oct/12/python-3-15/) ⭐️ 8.0/10

Simon Willison 介绍了 Python 3.15 的发布，并将其与开源项目维护中的版本支持策略联系起来：由于他面向所有受支持的 Python 版本构建软件，现在可以告别 Python 3.10，并开始使用 Python 3.11 的特性。文中重点提到 PEP 810 的显式惰性导入，可用 \`lazy import json\` 或 \`lazy from pathlib import Path\` 让模块在符号首次使用时才导入，这直接针对 CLI 插件因重依赖导致启动变慢的问题。Python 3.15 还加入了 PEP 798 的推导式解包语法，例如 \`\[\*L for L in lists\]\`、\`\{\*s for s in sets\}\` 和 \`\{\*\*d for d in dicts\}\`，扩展了 Python 3.5 中 PEP 448 引入的解包能力。标准库方面，原有 \`cProfile\` 被重命名为 \`profiling.tracing\`，并新增名为 Tachyon 的采样分析器 \`profiling.sampling\`，可附加到已有 Python 3.15 进程，生成报告、火焰图、热图以及 Firefox profiler UI 可查看的输出。性能方面，Miguel Grinberg 基于 3.15.0rc3 的测试认为 3.15 相比 3.14 大体没有明显提速，但实验性 JIT 在 Fibonacci 测试中比标准 3.15 解释器快 1.2 倍。

rss · Simon Willison · 10月12日 18:15

**「背景」** Python 的年度版本会带来语言语法、标准库和运行时行为的变化，但开源库通常需要同时兼容多个仍受支持的 Python 版本，因此维护者往往要等旧版本退役后才能使用较新的语法和 API。Python 3.15 的官方“What&\#x27;s New”文档列出了 PEP 810 显式惰性导入以及包含 Tachyon 的新 profiling 包等变化，这些功能分别面向启动开销和运行中程序的性能分析。

**「影响」** 维护跨版本 Python 开源项目的开发者可以在放弃 Python 3.10 后采用更新语言特性，而 Python 3.15 用户则可用标准库惰性导入和采样分析工具减少启动成本并诊断运行中程序。

<details><summary>参考链接</summary>
<ul>
<li>What&#x27;s new in Python 3.15 — Python 3.15.0 documentation</li>

</ul>
</details>

**标签**: `#Python`, `#programming-languages`, `#open-source`, `#software-engineering`

---