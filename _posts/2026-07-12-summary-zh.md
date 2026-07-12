---
layout: default
title: "Horizon Summary: 2026-07-12 (ZH)"
date: 2026-07-12
lang: zh
---

> 从 29 条内容中筛选出 2 条重要资讯。

---

1. [Grok Build 会向 xAI 发送代码库和 Git 历史。](#item-1) ⭐️ 8.0/10
2. [中国批准首款侵入式脑机接口医疗器械。](#item-2) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Grok Build 会向 xAI 发送代码库和 Git 历史。](https://gist.github.com/cereblab/dc9a40bc26120f4540e4e09b75ffb547) ⭐️ 8.0/10

一项针对 Grok Build CLI 0.2.93 版本的网络流量分析称，该工具会把所有受跟踪文件以及代码库的 Git 历史上传给 xAI，无论智能体是否实际读取过这些文件。据称，工具实际读取的文件也会被纳入模型请求并上传至 Google Cloud Storage，其中可能包括 .env 等含有密钥的文件。 这种行为可能暴露专有源代码、已删除或历史版本中的内容、凭据及其他敏感数据，其范围可能超出用户对一次编程请求的合理预期。对于允许专有 AI 智能体在内部代码库中运行的企业，这会带来显著的合规、隐私和供应链风险。 据报告，代码库级传输采用 Git bundle，因此上传内容可能包含提交历史，而不只是当前工作目录中的文件。相关结论来自独立网络流量分析，而非所提供的官方文档；现有材料也未说明 xAI 的数据保留期限或上传数据之后会被如何使用。

hackernews · jhoho · 7月12日 01:09 · [社区讨论](https://news.ycombinator.com/item?id=48877371)

**背景**: Grok Build 是 xAI 推出的终端编程智能体，目前官方宣传其由 Grok 4.5 驱动。与简单的代码补全不同，编程智能体可以检查文件、修改代码、执行命令，并与远程模型服务通信。沙箱可以限制此类进程能够访问的文件和网络目的地，从而降低代码库数据、环境变量或凭据离开本机的风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://x.ai/cli">Grok Build | SpaceXAI</a></li>
<li><a href="https://docs.x.ai/build/overview">Grok Build | SpaceXAI Docs</a></li>
<li><a href="https://getbeam.dev/blog/docker-sandbox-ai-agents.html">Docker Sandboxes for AI Agents : Secure Execution Without...</a></li>

</ul>
</details>

**社区讨论**: 多数评论者认为上传整个代码库的做法令人担忧，并倾向于使用开源运行器，或通过只读 Git 元数据、隐藏敏感目录、隔离网络及代理白名单实施严格沙箱。少数人认为，智能体拥有广泛的工作区访问权可能符合预期，并可能有助于后端处理；另一些人则强调，专有运行器可能随更新改变数据收集行为，而用户无法审计其实现。

**标签**: `#AI coding agents`, `#privacy`, `#network security`, `#source code security`, `#sandboxing`

---

<a id="item-2"></a>
## [中国批准首款侵入式脑机接口医疗器械。](https://t.me/zaihuapd/42515) ⭐️ 8.0/10

2026 年 3 月 13 日，中国国家药品监督管理局批准博睿康医疗科技（上海）有限公司的植入式脑机接口手部运动功能代偿系统上市。据报道，这是全球首个获准上市的侵入式脑机接口医疗器械。 此次批准推动侵入式脑机接口从试验研究走向受监管的临床应用，有望为颈段脊髓损伤患者提供恢复实用抓握能力的新途径。这也是神经康复、神经工程及中国医疗器械产业的重要里程碑。 该系统通过微创手术将电极置于硬脑膜外，利用无线供能和通信技术解码使用者的运动意图，再驱动气动手套辅助完成抓握。其适用对象为 18 至 60 岁、因颈段脊髓损伤导致四肢瘫痪的患者，但现有报道未披露临床试验规模、不良事件、设备耐久性或长期疗效数据。

telegram · zaihuapd · 7月12日 14:39

**背景**: 脑机接口记录脑活动，并将特定信号模式转换为控制外部设备的指令。与通过头皮采集信号的非侵入式系统不同，侵入式系统需要通过手术植入电极；硬脑膜外植入意味着电极位于硬脑膜之外，而非直接进入脑组织。该产品并不修复受损的脊髓，而是通过解码运动意图并控制气动手套，以机械辅助方式代偿手部运动功能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.thepaper.cn/newsDetail_forward_32760792">全球首个植入式脑机接口三类医疗器械获批上市，可助瘫痪患者完成抓握_...</a></li>
<li><a href="https://zh.wikipedia.org/zh-hans/脑机接口">脑机接口 - 维基百科，自由的百科全书</a></li>
<li><a href="https://baike.baidu.com/item/植入式脑机接口手部运动功能代偿系统/67478989">植入式脑机接口手部运动功能代偿系统_百度百科</a></li>

</ul>
</details>

**标签**: `#脑机接口`, `#神经康复`, `#医疗器械`, `#神经工程`, `#临床应用`

---