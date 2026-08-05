---
layout: default
title: "Horizon Summary: 2026-08-05 (EN)"
date: 2026-08-05
lang: en
---

> From 40 items, 2 important content pieces were selected

---

**Technology News**
1. [China Issues Mandatory L3/L4 Automated-Driving Safety Standard](#item-tech-news-1) ⭐️ 8.0/10
2. [ChainDrop Reportedly Infects More Than 1,300 npm Packages](#item-tech-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [China Issues Mandatory L3/L4 Automated-Driving Safety Standard](https://wap.miit.gov.cn/jgsj/zbys/qcgy/art/2026/art_a1d2072374884287b67048a77560014e.html) ⭐️ 8.0/10

China has approved GB 44721—2026, its first mandatory national safety standard for Level 3 conditional and Level 4 highly automated driving systems, with implementation planned for July 1, 2027. Developed by the Ministry of Industry and Information Technology, it applies to M-category passenger vehicles and N-category goods vehicles equipped with L3 or L4 systems, but excludes automated parking systems. The standard upgrades a 2024 voluntary standard into mandatory requirements covering manufacturers’ full-lifecycle safety assurance, dynamic-driving capabilities, human-machine interaction and user disclosure, and multidimensional inspection and testing. It requires automated-driving systems to achieve a safety level at least equivalent to that of a qualified, attentive human driver, potentially affecting vehicle development, compliance, and testing across the industry.

telegram · zaihuapd · Aug 4, 13:06

**「Background」** L3 conditional automation performs the driving task within specified operating conditions but may require a human to take over, while L4 high automation can handle fallback itself within its defined operating domain. In Chinese vehicle classifications, M-category vehicles carry passengers and N-category vehicles carry goods; the new standard covers both categories but excludes automated parking systems.

**「Impact」** Automakers offering L3/L4 passenger or freight vehicles in China will need to align system design, lifecycle safety processes, human-machine interaction, user disclosures, and testing with mandatory GB 44721—2026 from July 1, 2027; automated parking systems are excluded.

<details><summary>References</summary>
<ul>
<li><a href="http://news.cnfol.com/guoneicaijing/20260805/32326183.shtml">news.cnfol.com/guoneicaijing/20260805/32326183.shtml</a></li>
<li><a href="https://www.autohome.com.cn/news/202608/1316205.html">autohome.com.cn/news/202608/1316205.html</a></li>

</ul>
</details>

**Tags**: `#自动驾驶`, `#汽车安全标准`, `#智能网联汽车`, `#技术监管`

---

<a id="item-tech-news-2"></a>
### [ChainDrop Reportedly Infects More Than 1,300 npm Packages](https://www.bleepingcomputer.com/news/security/massive-chaindrop-npm-supply-chain-attack-infects-hundreds-of-packages/) ⭐️ 8.0/10

A report says the self-propagating ChainDrop worm has compromised more than 1,300 npm packages with a combined 2 billion monthly downloads, including the popular Keyv and Cacheable caching tools. The campaign reportedly began after attackers compromised a Keyv maintainer’s GitHub account and spread to packages associated with organizations including Deliveroo, Qlik, and ServiceTitan; malicious releases were published through normal GitHub Actions workflows and carried legitimate provenance attestations. During npm installation, a setup.mjs loader and Math\_Symbol.js stealer allegedly execute automatically, collect GitHub, npm, AWS, and Kubernetes credentials, and use maintainer access to infect additional packages. Security firms advise anyone who installed an affected version to treat the environment as compromised, rebuild it, rotate all tokens, inspect logs, and check for the npm-cache\[.\]com indicator. The incident was supplied as a Telegram summary of a BleepingComputer report, so its stated scale, technical details, and claim that the attack remains active require confirmation from the original report or official advisories.

telegram · zaihuapd · Aug 5, 03:04

**「Background」** npm packages can define lifecycle scripts that execute automatically during installation, so malicious code inserted into a dependency may run without an application explicitly invoking it. A self-propagating supply-chain worm can use stolen maintainer credentials or publishing automation to release compromised versions of additional packages, potentially preserving the appearance of a legitimate release process.

**「Impact」** Teams that installed affected npm releases should treat their environments and GitHub, npm, AWS, and Kubernetes credentials as potentially compromised, rebuild systems, rotate tokens, inspect logs, and pin dependencies to verified clean versions.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/massive-chaindrop-npm-supply-chain-attack-infects-hundreds-of-packages/">Massive ChainDrop npm supply-chain attack infects hundreds of packages</a></li>
<li><a href="https://www.stepsecurity.io/blog/chaindrop-npm-worm">ChainDrop npm Worm: Bun-loaded CI/CD credential harvester with Ethereum dead-drop C2 - StepSecurity</a></li>

</ul>
</details>

**Tags**: `#npm`, `#软件供应链安全`, `#开源安全`, `#凭证窃取`, `#GitHub Actions`

---