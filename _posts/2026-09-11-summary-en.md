---
layout: default
title: "Horizon Summary: 2026-09-11 (EN)"
date: 2026-09-11
lang: en
---

> From 38 items, 5 important content pieces were selected

---

**Technology News**
1. [TryNix Runs Nix Packages in the Browser](#item-tech-news-1) ⭐️ 8.0/10
2. [GPT-Live-1 Comes to OpenAI API](#item-tech-news-2) ⭐️ 8.0/10
3. [GitLab Patches Critical File-Read Vulnerability](#item-tech-news-3) ⭐️ 8.0/10
4. [OpenAI Launches Agents API Public Beta](#item-tech-news-4) ⭐️ 8.0/10

**Technology Blog**
1. [A Technology Weekly on PRs, AI, and Verification](#item-tech-blog-1) ⭐️ 4.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [TryNix Runs Nix Packages in the Browser](https://simonwillison.net/2026/Sep/10/trynix/) ⭐️ 8.0/10

TryNix provides an x86\_64 Linux virtual machine that runs entirely in the browser using WebAssembly and qemu-wasm. The VM can boot any Nix package from the past 13 years, with environments addressed by URL, such as a link that loads an interactive shell with Python 3.6.2 from 2017. Simon Willison highlighted Farid Zakaria’s description of the project as his “magnum opus” of Nix work. Zakaria is also building workflows on top of it, including trynix-preview, a GitHub Action that comments on pull requests with a link to boot the PR’s build in the browser without servers.

rss · Simon Willison · Sep 10, 23:44

**「Background」** Nix is a package manager and build system known for reproducible, version-addressed software environments, while nixpkgs is its large package collection. TryNix combines qemu-wasm, a WebAssembly port of QEMU, with the nixpkgs-multiverse index so a browser tab can boot a Linux VM containing packages that nixpkgs shipped across many historical versions.

**「Impact」** Nix users and maintainers can use TryNix to share reproducible, browser-launchable package environments and potentially review pull request builds interactively.

<details><summary>References</summary>
<ul>
<li><a href="https://fzakaria.com/2026/09/04/any-nix-package-live-in-your-browser">Any Nix package, live in your browser | Farid Zakaria’s Blog</a></li>
<li><a href="https://trynix.dev/">trynix — boot anything nixpkgs ever shipped, in your browser</a></li>

</ul>
</details>

**Tags**: `#Nix`, `#WebAssembly`, `#Virtual Machines`, `#Software Testing`, `#Reproducible Builds`

---

<a id="item-tech-news-2"></a>
### [GPT-Live-1 Comes to OpenAI API](https://openai.com/index/introducing-gpt-live-1-in-the-api/) ⭐️ 8.0/10

OpenAI launched GPT-Live-1 in its API on September 10, 2026, according to the source item. The model is designed for low-latency, full-duplex voice interaction, meaning it can listen and speak at the same time while supporting natural interruptions, background-noise handling, long conversations, and phone-based voice agents. OpenAI says GPT-Live-1 improves by 30 percentage points over GPT-Realtime-2.1 on Full Duplex Bench. The API voice frontend is priced at $0.05 per minute, and the system can delegate complex reasoning and tool calls to backend models.

telegram · zaihuapd · Sep 11, 03:09

**「Background」** Full-duplex voice models are designed to listen and speak at the same time, which enables more natural turn-taking than systems that wait for one side to finish before responding. OpenAI’s prior GPT-Realtime line already targeted low-latency speech interaction, and GPT-Live-1 is presented as a newer API option focused on interruption handling, telephony-style use cases, and backend delegation for reasoning or tool use.

**「Impact」** Developers building real-time voice agents can use GPT-Live-1 for more natural phone and conversational applications, with a stated frontend cost of $0.05 per minute.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/introducing-gpt-live-1-in-the-api/">Build more natural voice experiences with GPT‑Live‑1 in the API | OpenAI</a></li>

</ul>
</details>

**Tags**: `#OpenAI API`, `#实时语音 AI`, `#语音代理`, `#大语言模型`, `#AI 工具调用`

---

<a id="item-tech-news-3"></a>
### [GitLab Patches Critical File-Read Vulnerability](https://docs.gitlab.com/releases/patches/patch-release-gitlab-19-3-2-released/) ⭐️ 8.0/10

GitLab released emergency patches 19.3.2, 19.2.6, and 19.1.8 on September 10 to fix CVE-2026-85706, which GitLab rated CVSS 10.0. Under specific conditions, an unauthenticated user could exploit path-constraint and authentication flaws in the repository commits API to read arbitrary files from a GitLab server. Affected versions include 18.7 through versions before 19.1.8, 19.2 versions before 19.2.6, and 19.3 versions before 19.3.2. GitLab said GitLab.com has already been fixed and GitLab Dedicated users do not need to take action, while the issue was reported by researcher s3ntago through HackerOne. The company has not disclosed the exact prerequisites, and the source says there is no public reproducible PoC or evidence of in-the-wild exploitation so far.

telegram · zaihuapd · Sep 11, 11:05

**「Background」** GitLab Community Edition \(CE\) and Enterprise Edition \(EE\) are distributed for organizations to run and manage on their own infrastructure, while GitLab.com is operated by GitLab as a hosted service. GitLab uses patch releases such as 19.3.2, 19.2.6, and 19.1.8 to deliver security fixes for supported release branches.【tool-1-1】

**「Impact」** Administrators of self-managed GitLab instances in the affected version ranges should upgrade immediately to the corresponding fixed release to prevent possible unauthenticated server file reads.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.gitlab.com/releases/patches/patch-release-gitlab-19-3-2-released/">GitLab Critical Patch Release : 19 . 3 . 2 , 19 . 2 . 6 , 19 . 1 . 8 | GitLab Docs</a></li>

</ul>
</details>

**Tags**: `#GitLab`, `#网络安全`, `#漏洞修复`, `#自建实例`

---

<a id="item-tech-news-4"></a>
### [OpenAI Launches Agents API Public Beta](https://openai.com/index/introducing-the-agents-api/) ⭐️ 8.0/10

OpenAI launched the public beta of its Agents API on September 10, 2026, according to the supplied source. The API lets developers create production-grade cloud agents through a single API call and run them in an OpenAI-hosted sandbox, their own infrastructure, or partner environments. It is based on the open-source Codex harness and supports long-session context compression, tool search, parallel tool calls, and collaboration between sub-agents. During the public beta, OpenAI is not charging an additional platform fee, with users paying only for the tokens and tools used by their agents.

telegram · zaihuapd · Sep 11, 11:12

**「Background」** AI agents are applications that use a model together with tools, memory or session state, and orchestration logic to carry out multi-step tasks with limited human intervention. OpenAI’s Codex harness is the infrastructure layer associated with its coding agent, and reports describe the Agents API as exposing that kind of hosted harness so developers do not have to build common agent plumbing such as session management and tool orchestration themselves.

**「Impact」** Developers building agentic applications can test managed production-oriented agent deployment without extra beta fees, while still incurring token and tool usage costs.

<details><summary>References</summary>
<ul>
<li><a href="https://www.marktechpost.com/2026/09/10/openai-launches-the-agents-api-in-public-beta-putting-the-codex-harness-behind-one-api-call/">OpenAI Launches the Agents API in Public Beta, Putting the Codex Harness Behind One API Call - MarkTechPost</a></li>
<li><a href="https://byteiota.com/openai-agents-api-public-beta-build-without-the-boilerplate/">OpenAI Agents API Public Beta: Build Without the Boilerplate | byteiota</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#Agents API`, `#AI智能体`, `#Codex`, `#API平台`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [A Technology Weekly on PRs, AI, and Verification](http://www.ruanyifeng.com/blog/2026/09/weekly-issue-412.html) ⭐️ 4.0/10

rss · 阮一峰的网络日志 · Sep 11, 00:11

**「Background」** This issue of Ruanyifeng’s technology weekly is a broad link roundup rather than a deep technical analysis, spanning open-source collaboration, AI, formal verification, developer tools, and assorted resources. Its main argument is that Laravel’s reported decision to accept only pull requests instead of issues reflects a practical response to overloaded maintainers, but it also raises questions about whether AI makes contribution easier without merely replacing low-quality issues with low-quality PRs.

**「Solution」** The author argues that a PR carries more actionable information than an issue and requires enough effort to deter bots and casual abuse; with AI generating patches from natural-language descriptions, he considers the submission barrier nearly equivalent to filing an issue. The article does not, however, develop the corresponding risks around review burden, long-term maintainability, or AI-generated changes that solve only the immediate symptom. Its centerpiece is a report that Anthropic’s Claude spent 11 days translating Andrew Wiles’s 129-page proof of Fermat’s Last Theorem into Lean, first producing more than 30,000 auxiliary theorems, using over 29,000 of them, consuming billions of tokens, and resulting in roughly 13 million lines of code; the author presents this as evidence that AI could help formalize and check proofs that humans struggle to verify, without explaining the trust boundaries or engineering process in depth. The remaining selections cover Tesla’s investor-owned Cybercab model, a camera-equipped Dyson toothbrush, an AI navigation cane, RSA-512 factoring, JavaScript recursion, open-model trends, and tools such as Caddy’s WAF plugin, vet, Krep, and Inbucket, alongside advice to keep products simple, separable from their core technology, and defined by one distinctive feature.

**「Takeaway」** The issue is most useful as a discovery map for technology trends and provocative claims, especially the changing relationship between AI and open-source or mathematical work. Its central proposals are suggestive, but readers seeking transferable technical understanding will need to follow the linked sources and examine their evidence, constraints, and maintenance costs.

**Tags**: `#technology-news`, `#open-source`, `#AI`, `#formal-verification`, `#developer-tools`

---