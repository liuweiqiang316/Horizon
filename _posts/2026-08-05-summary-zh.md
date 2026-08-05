---
layout: default
title: "Horizon Summary: 2026-08-05 (ZH)"
date: 2026-08-05
lang: zh
---

> 从 40 条内容中筛选出 2 条重要资讯。

---

**科技新闻**
1. [中国发布首部 L3/L4 自动驾驶强制性国标](#item-tech-news-1) ⭐️ 8.0/10
2. [报道称 ChainDrop 污染逾 1300 个 npm 包](#item-tech-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [中国发布首部 L3/L4 自动驾驶强制性国标](https://wap.miit.gov.cn/jgsj/zbys/qcgy/art/2026/art_a1d2072374884287b67048a77560014e.html) ⭐️ 8.0/10

工业和信息化部组织制定的强制性国家标准《智能网联汽车 自动驾驶系统安全要求》（GB 44721—2026）已获批发布，拟于 2027 年 7 月 1 日起实施。这是中国首部针对 L3 级有条件自动驾驶和 L4 级高度自动驾驶系统的强制性国家标准，适用于搭载相关系统的 M 类载客车辆和 N 类载货车辆，但不适用于自动泊车系统。该标准由 2024 年推荐性国标系统升级而来，从企业全生命周期安全保障、系统动态驾驶能力、人机交互与用户告知、多维度检验检测四方面建立强制要求。标准要求自动驾驶系统的安全水平至少达到合格且专注驾驶人的水平，将成为相关车企开展系统研发、测试与合规工作的统一安全基准。

telegram · zaihuapd · 8月4日 13:06

**「标准背景」** L3 指有条件自动驾驶，L4 指高度自动驾驶，两者均只在规定的设计运行条件下执行驾驶任务；其中 L3 在系统提出接管请求时仍需要后备用户响应。该标准由 2024 年的推荐性国家标准升级而来，并将适用范围明确为 M 类载客车辆和 N 类载货车辆，但不涵盖自动泊车系统。

**「影响」** 面向中国市场开发搭载 L3/L4 系统的载客和载货车辆的企业，需在拟定的 2027 年 7 月 1 日实施日前，使全生命周期安全、动态驾驶能力、人机交互、用户告知及检验检测满足强制要求；自动泊车系统不在适用范围内。

**标签**: `#自动驾驶`, `#汽车安全标准`, `#智能网联汽车`, `#技术监管`

---

<a id="item-tech-news-2"></a>
### [报道称 ChainDrop 污染逾 1300 个 npm 包](https://www.bleepingcomputer.com/news/security/massive-chaindrop-npm-supply-chain-attack-infects-hundreds-of-packages/) ⭐️ 8.0/10

Telegram 转述 BleepingComputer 报道称，自传播蠕虫 ChainDrop 已污染超过 1300 个 npm 包，涉及 Keyv、Cacheable 等缓存工具，相关包合计月下载量据称达 20 亿次。攻击据称始于 Keyv 维护者的 GitHub 账户失陷，随后扩散到与 Deliveroo、Qlik、ServiceTitan 等机构有关的包，并通过正常 GitHub Actions 流程发布带有合法来源证明的恶意版本。中毒包会在 npm install 时运行 setup.mjs 投放器和 Math\_Symbol.js 窃密脚本，盗取 GitHub、npm、AWS、Kubernetes 等凭证，并利用维护者权限继续感染其他包。安全公司建议安装过受影响版本的用户将系统视为已失陷，重建环境、轮换全部令牌并检查日志，同时将 npm-cache\[.\]com 作为失陷指标；不过事件规模、具体技术细节及仍在扩散的说法目前仅来自二手转述，仍需原始报道或官方通告核实。

telegram · zaihuapd · 8月5日 03:04

**「背景」** npm 软件供应链攻击通常通过劫持维护者账号或发布令牌，把恶意代码作为正常版本推送到软件包仓库，并借助依赖关系触达下游项目。npm 包可配置在安装期间自动执行的脚本，而 GitHub Actions 等可信发布流程及其来源证明只能确认发布路径，无法保证被发布的代码本身安全。

**「影响」** 安装过受影响版本（包括经传递依赖引入）的开发者和组织应将本地及 CI/CD 环境视为可能失陷，固定到已知安全版本、重建环境并轮换 GitHub、npm、AWS 和 Kubernetes 等凭证；仅使用“^”版本范围不足以避免解析到恶意最新版。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.stepsecurity.io/blog/chaindrop-npm-worm">ChainDrop npm Worm: Bun-loaded CI/CD credential harvester with Ethereum dead-drop C2 - StepSecurity</a></li>

</ul>
</details>

**标签**: `#npm`, `#软件供应链安全`, `#开源安全`, `#凭证窃取`, `#GitHub Actions`

---