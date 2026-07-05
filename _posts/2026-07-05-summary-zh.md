---
layout: default
title: "Horizon Summary: 2026-07-05 (ZH)"
date: 2026-07-05
lang: zh
---

> 从 30 条内容中筛选出 2 条重要资讯。

---

1. [欧盟理事会快速推进聊天监控 1.0](#item-1) ⭐️ 8.0/10
2. [F-Droid 谴责 Google 的安卓开发者验证。](#item-2) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [欧盟理事会快速推进聊天监控 1.0](https://www.heise.de/en/news/Chat-Control-1-0-EU-Council-forces-messenger-scans-via-fast-track-11353659.html) ⭐️ 8.0/10

据报道，欧盟理事会正在快速推进聊天监控 1.0，该措施将允许 Facebook 等消息服务提供商扫描聊天内容以查找有害内容，此前相关临时法律依据已经到期。此举恢复的是一套有争议的扫描制度，而不是针对端到端加密通信工具的范围更广的聊天监控 2.0 提案。 这很重要，因为它会影响数百万欧盟用户对通信隐私的预期，并可能使平台级消息扫描成为一种常态化监管工具。即使它没有直接要求削弱端到端加密，它仍然处在围绕加密、儿童安全执法和数字通信公民自由的更广泛政策争议之中。 讨论中提出的一个关键区别是，聊天监控 1.0 涉及服务提供商自愿或被允许进行扫描，而争议更大的聊天监控 2.0 通常与可能向 Signal 等加密服务施压的提案相关。技术读者需要注意，如果客户端扫描被用于加密通信，它意味着在加密前或解密后检查内容，批评者认为这会破坏端到端加密的保密模型。

hackernews · stavros · 7月5日 11:44 · [社区讨论](https://news.ycombinator.com/item?id=48793393)

**背景**: “聊天监控”是欧盟围绕在数字通信中发现和打击儿童性虐待材料相关举措的通称。范围更广的《儿童性虐待条例》提案由欧盟内务委员 Ylva Johansson 于 2022 年 5 月 11 日提出。客户端扫描是指在消息发送前，对文本、图片、视频或文件进行检查，以判断其是否与有害内容数据库匹配或相似。争议来自于扫描私人消息可能与隐私权发生冲突，而在加密系统中，这也可能削弱用户对端到端加密所期待的实际保护。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Chat_Control">Chat Control - Wikipedia</a></li>
<li><a href="https://www.internetsociety.org/resources/doc/2020/fact-sheet-client-side-scanning/">Fact Sheet: Client-Side Scanning - Internet Society</a></li>
<li><a href="https://edri.org/our-work/chat-control-what-is-actually-going-on/">Chat Control: What is actually going on? - European Digital Rights (EDRi)</a></li>

</ul>
</details>

**社区讨论**: 社区讨论总体上担忧但带有区分：一位主要评论者强调，这次涉及的是聊天监控 1.0，而不是更危险、面向端到端加密通信工具的聊天监控 2.0。其他评论者表达了对欧盟机构的不信任、对类似提案不断回归的挫败感，并推测更严格的身份和年龄验证制度可能会推动用户转向去中心化替代方案。

**标签**: `#privacy`, `#encryption`, `#EU regulation`, `#messaging`, `#surveillance`

---

<a id="item-2"></a>
## [F-Droid 谴责 Google 的安卓开发者验证。](https://f-droid.org/2026/07/01/adv-malware.html) ⭐️ 8.0/10

F-Droid 发布博客文章，将 Google 的安卓开发者验证（ADV）称为实质上的恶意软件，认为它可以阻止未获 Google 集中批准的开发者所发布的应用运行。根据该消息，相关机制将于 9 月 30 日先在巴西、印尼、新加坡和泰国启用，并计划在 2027 年及以后扩大到全球。 如果该机制如批评者所说那样运作，ADV 可能会显著改变安卓侧载和替代应用分发方式，使 Google 验证成为认证安卓设备上安装应用的关口。这将影响独立开发者、F-Droid 用户、开源应用仓库，以及关注用户控制权和软件自由的数字权利组织。 Google 自己的开发者验证页面将这一变化描述为一层额外安全保护，用于阻止反复作恶，并称从 2026 年 9 月起，部分地区的认证安卓设备将要求应用由已验证开发者注册后才能安装。F-Droid 的反对点在于，该验证器通过 Play Protect 作为系统级服务分发，而 Google 对开发者批准的控制可能被用于排除合法但不受欢迎的软件，例如广告拦截器。

telegram · zaihuapd · 7月5日 00:41

**背景**: 安卓长期以来允许用户从 Google Play 之外安装应用，这种做法通常被称为侧载。F-Droid 是一个面向安卓的替代应用仓库，专注于自由和开源软件，并将自己定位为优先保障用户自由的分发生态。Google Play Protect 是 Google 的安卓安全系统，用于扫描应用并识别潜在有害应用。新的开发者验证计划则为在部分地区认证安卓设备上安装应用的开发者增加了身份验证和注册要求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.android.com/developer-verification">Android developer verification | Android Developers</a></li>
<li><a href="https://developers.google.com/android/play-protect/client-protections">On-device protections | Play Protect | Google for Developers</a></li>
<li><a href="https://f-droid.org/">F-Droid - Free and Open Source Android App Repository</a></li>

</ul>
</details>

**标签**: `#android`, `#f-droid`, `#app-distribution`, `#digital-rights`, `#google`

---