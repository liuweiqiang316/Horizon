---
layout: default
title: "Horizon Summary: 2026-07-26 (ZH)"
date: 2026-07-26
lang: zh
---

> 从 32 条内容中筛选出 4 条重要资讯。

---

1. [欧盟提议采用浏览器级隐私偏好设置](#item-1) ⭐️ 8.0/10
2. [GrapheneOS 详解锁定设备的数据提取防护](#item-2) ⭐️ 8.0/10
3. [Ruff v0.16.0 大幅扩充默认代码检查规则。](#item-3) ⭐️ 8.0/10
4. [SpaceX 据称拒接 Falcon 9 远期订单](#item-4) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [欧盟提议采用浏览器级隐私偏好设置](https://killthecookiebanner.eu/) ⭐️ 8.0/10

欧盟委员会提议允许用户在浏览器中集中设置隐私偏好，由网站自动接收并遵守这些选择。这种方式可能取代大量重复且具有误导性的 Cookie 同意横幅，但目前仍是提案，尚未成为正式实施的标准。 浏览器级机制可以降低用户反复操作的负担，并提高同意选择的一致性，同时促使网站、广告商和同意管理服务商调整其合规系统。这也体现了隐私保护向机器可读信号转变的趋势，用户不必再在每个网站上重复作出相同选择。 该提案需要明确浏览器可以传递哪些偏好、网站应如何遵守这些信号，以及用户能否针对单个网站覆盖默认设置。登录等功能所必需的 Cookie 可能仍可使用，而可选的跟踪行为仍将是同意机制需要处理的核心问题。

hackernews · rapnie · 7月26日 11:53 · [社区讨论](https://news.ycombinator.com/item?id=49057175)

**背景**: Cookie 是网站通过浏览器保存的小型数据，可用于维持登录状态、记录偏好、进行分析和跟踪。现代浏览器能够阻止 Cookie，但全面拦截可能导致部分服务无法正常运行，也可能迫使用户反复恢复设置。Global Privacy Control 是一种现有的浏览器信号，用于跨网站传达特定隐私选择，展示了如何以机器可读形式表达用户偏好。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://commission.europa.eu/cookies-policy_en">Cookies policy - European Commission</a></li>
<li><a href="https://globalprivacycontrol.org/">Global Privacy Control — Take Control Of Your Privacy</a></li>
<li><a href="https://www.theverge.com/news/823788/europe-cookie-prompt-browser-changes-proposal">Europe’s cookie nightmare is crumbling | The Verge</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍欢迎这项提案，认为它将显著改善浏览体验，但也指出用户很少通过横幅作出真正知情的同意，更直接的解决办法往往是停止不必要的监视。讨论还呼吁提供按网站覆盖默认设置的能力，并将该提案与加州预计于 2027 年实施的浏览器级隐私要求进行比较，同时敦促欧盟尽快将设想转化为具有约束力的措施。

**标签**: `#web-privacy`, `#EU-regulation`, `#cookies`, `#browser-standards`, `#consent-management`

---

<a id="item-2"></a>
## [GrapheneOS 详解锁定设备的数据提取防护](https://discuss.grapheneos.org/d/40700-grapheneos-protections-against-data-extraction-from-locked-devices) ⭐️ 8.0/10

GrapheneOS 发布了一份技术概述，说明其如何抵御从已锁定 Android 设备中进行取证式数据提取。其防护措施包括 18 小时自动重启功能，可将闲置设备恢复到更安全的首次解锁前状态。 让手机恢复到首次解锁前状态，可以从内存中清除磁盘加密密钥，并减少取证工具能够获取的数据。这对记者、机密消息源、过境旅客以及设备可能在锁定状态下被扣押的其他高风险用户尤其重要。 首次解锁前状态比手机解锁后再锁屏更安全，因为在首次解锁后状态中，加密密钥可能仍然驻留于内存。自动重启无法弥补弱凭据的缺陷，因此 PIN 或密码的熵仍是抵御离线猜测攻击的重要因素。

hackernews · Cider9986 · 7月26日 05:57 · [社区讨论](https://news.ycombinator.com/item?id=49055169)

**背景**: 现代 Android 设备采用的加密状态通常分为首次解锁前和首次解锁后。首次解锁前是指设备启动后、用户尚未输入凭据的状态，此时受保护的用户数据仍处于加密状态，正常访问所需的密钥也尚未加载。设备首次解锁后，即使屏幕再次锁定，部分密钥仍可能留在内存中，因而取证工具可能提取到更多信息。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GrapheneOS">GrapheneOS - Wikipedia</a></li>
<li><a href="https://blogs.dsu.edu/digforce/2023/08/23/bfu-and-afu-lock-states/">BFU and AFU Lock States – Blog | DigForCE Lab</a></li>
<li><a href="https://discuss.grapheneos.org/d/40700-grapheneos-protections-against-data-extraction-from-locked-devices?ref=upstract.com">GrapheneOS protections against data extraction from locked...</a></li>

</ul>
</details>

**社区讨论**: 评论者总体认可这些防护措施，并强调 18 小时自动重启对记者很有价值，同时也讨论了凭据熵，指出 Android 图案锁提供的熵相对较低。一名参与者认为 GrapheneOS 仍缺少完整的备份与恢复系统，使用户无法方便地在过境前清空手机并在之后恢复应用数据；另一些人则将这些防护与 Apple 的安全功能进行了比较。

**标签**: `#GrapheneOS`, `#mobile-security`, `#Android`, `#digital-forensics`, `#data-privacy`

---

<a id="item-3"></a>
## [Ruff v0.16.0 大幅扩充默认代码检查规则。](https://simonwillison.net/2026/Jul/25/ruff/#atom-everything) ⭐️ 8.0/10

Astral 于 2026 年 7 月 23 日发布 Ruff v0.16.0，将默认启用的代码检查规则从 59 条增加到 413 条。扩充后的默认规则无需配置即可发现更多问题，包括语法错误和会立即导致运行时错误的代码。 更严格的默认规则可以显著增强 Python 项目的缺陷检测能力，但也可能导致安装未锁定 Ruff 版本的 CI 流水线突然失败。团队可能需要锁定 Ruff 版本、更新配置，或修复新报告的违规问题后再采用该版本。 Ruff 目前共有 968 条规则，而上次在 v0.1.0 调整默认规则时共有 708 条；在 sqlite-utils 中运行自动修复和不安全修复后，共发现 1,618 个错误，修复了 1,538 个，剩余 80 个。剩余问题包括未指定时区的日期时间调用、宽泛捕获 Exception，以及无效的属性访问；使用 --unsafe-fixes 时应配合完善的测试覆盖和代码审查。

rss · Simon Willison · 7月25日 22:44

**背景**: Ruff 是一种 Python 代码检查工具，用于分析源代码中可能存在的错误和规则违规，其规则均以 Rust 重新实现为内置功能。默认规则集决定了项目没有明确选择规则时会执行哪些检查。部分检查针对的不只是代码风格问题：在 global 声明之前使用相应名称属于 Python 语法错误，而在 __init__ 中使用 yield 会使初始化方法返回生成器并导致运行时错误。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.astral.sh/ruff/rules/">Rules | Ruff</a></li>
<li><a href="https://docs.astral.sh/ruff/rules/load-before-global-declaration/">load - before - global - declaration (PLE0118) | Ruff</a></li>
<li><a href="https://docs.astral.sh/ruff/rules/yield-in-init/">yield - in - init (PLE0100) | Ruff</a></li>

</ul>
</details>

**标签**: `#Python`, `#Ruff`, `#linting`, `#CI/CD`, `#developer-tools`

---

<a id="item-4"></a>
## [SpaceX 据称拒接 Falcon 9 远期订单](https://www.bloomberg.com/news/articles/2026-07-23/spacex-is-turning-away-falcon-customers-in-major-bet-on-starship) ⭐️ 8.0/10

据报道，SpaceX 已停止接受 2028 年之后的 Falcon 9 专属发射请求，也不再接受其拼单发射项目的远期预订。该公司据称还在缩减部分 Falcon 系列非重复使用部件的生产，以将运力转向 Starship。 Falcon 9 是全球商业发射运力的重要来源，因此在 Starship 投入商业运营前收紧其远期供应，可能使卫星运营商面临发射运力缺口。这一决定还意味着 SpaceX 将包括扩展 Starlink 在内的增长计划集中押注于一款规模更大、但仍在开发中的运载系统。 SpaceX 仍可能为美国国防部和 NASA 保留 Falcon 9 任务；如果 Starship 无法在 2028 年底前接替现有运力，商业客户将承受最大的风险。Bloomberg 指出，这项据报道的计划仍可能改变，尤其是在 Starship 开发再次受挫的情况下。

telegram · zaihuapd · 7月26日 12:42

**背景**: Falcon 9 是 SpaceX 研制的部分可重复使用两级中型运载火箭，推动了商业卫星以及 Starlink 等大型星座发射成本的下降。其拼单任务允许多个客户共享一次发射，而不必各自购买整枚火箭的运力。Starship 由星舰飞船和 Super Heavy 助推器组成，目标是成为可将超过 100 吨载荷送入轨道的完全可重复使用系统，但目前尚未开始商业运营。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-07-23/spacex-is-turning-away-falcon-customers-in-major-bet-on-starship">SpaceX Is Turning Away Falcon Customers in Major Bet... - Bloomberg</a></li>
<li><a href="https://www.spacex.com/vehicles/starship">SpaceX - Starship</a></li>
<li><a href="https://en.wikipedia.org/wiki/Falcon_9">Falcon 9 - Wikipedia</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#Starship`, `#Falcon 9`, `#商业航天`, `#卫星发射`

---