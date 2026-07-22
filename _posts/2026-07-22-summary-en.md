---
layout: default
title: "Horizon Summary: 2026-07-22 (EN)"
date: 2026-07-22
lang: en
---

> From 38 items, 5 important content pieces were selected

---

1. [Terrence Tao Examines a Claimed Jacobian Conjecture Counterexample](#item-1) ⭐️ 8.0/10
2. [GigaToken Claims Roughly 1,000× Faster Language-Model Tokenization.](#item-2) ⭐️ 8.0/10
3. [Bento Packs a Complete Slide Editor Into One HTML File](#item-3) ⭐️ 8.0/10
4. [LG Will Ban Residential-Proxy SDKs From Smart TV Apps](#item-4) ⭐️ 8.0/10
5. [Four Major AI Coding Agents Expose Sandbox-Escape Flaws.](#item-5) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Terrence Tao Examines a Claimed Jacobian Conjecture Counterexample](https://chatgpt.com/share/6a5fdc7a-d6f8-83e8-bbea-8deb42cfed56) ⭐️ 8.0/10

Terrence Tao shared a ChatGPT conversation in which he used focused, technically sophisticated questions to examine and simplify a claimed counterexample to the Jacobian Conjecture. The transcript is a case study in expert-guided AI reasoning, not an announcement that the conjecture has been disproved. The exchange shows how a leading mathematician can use a large language model as an interactive tool for algebraic exploration while retaining control over assumptions and simplifications. It also illustrates that useful AI-assisted research depends heavily on domain expertise and does not replace independent mathematical verification. A valid counterexample must satisfy the conjecture’s hypothesis—having a nonzero constant Jacobian determinant—while failing to have a polynomial inverse; these properties require exact checking rather than confidence in a chat transcript. The related claimed counterexample is presented as independently checkable through finite symbolic computations, but a claim of this magnitude still requires scrutiny by the mathematical community.

hackernews · gmays · Jul 22, 17:30 · [Discussion](https://news.ycombinator.com/item?id=49010345)

**Background**: The Jacobian Conjecture is a famous unsolved problem about polynomial maps in several variables. It states that a polynomial map from an n-dimensional space to itself with a nonzero constant Jacobian determinant must have a polynomial inverse. Because the statement is universal, one rigorously verified map satisfying the determinant condition but lacking such an inverse would disprove it.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Jacobian_conjecture">Jacobian conjecture - Wikipedia</a></li>
<li><a href="https://github.com/MMVFIRM/alpoge-fable-jacobian-counterexample">GitHub - MMVFIRM/alpoge-fable- jacobian - counterexample : Frozen...</a></li>

</ul>
</details>

**Discussion**: Commenters were impressed by Tao’s short, jargon-rich questions and repeated simplifications, viewing the transcript as evidence that experts can extract substantially more value from language models than nonspecialists. They also noted that the proposed polynomial appears deliberately structured rather than found by blind brute force, while several readers emphasized how inaccessible the underlying mathematics remains and did not treat the transcript itself as verification.

**Tags**: `#mathematics`, `#Jacobian Conjecture`, `#large language models`, `#AI-assisted research`, `#expert prompting`

---

<a id="item-2"></a>
## [GigaToken Claims Roughly 1,000× Faster Language-Model Tokenization.](https://github.com/marcelroed/gigatoken/) ⭐️ 8.0/10

GigaToken is a heavily optimized tokenizer library that claims roughly 1,000× higher throughput than Hugging Face tokenizers and tiktoken, reaching gigabytes-per-second speeds. Its author reports consistent results across modern x86 and ARM processors and nearly all commonly used tokenizers. The project could substantially accelerate workloads that perform tokenization at large scale or independently of model inference. Its effect on end-to-end inference may be limited, however, because community participants note that tokenization often represents less than 0.1% of total inference time. GigaToken replaces regex-heavy pretokenization with SIMD-oriented processing, reduces branching and Python overhead, and aggressively caches mappings from previously seen text segments to encoded tokens. The reported speedup remains a project benchmark claim, and practical use may depend on integration into model-serving and tokenizer ecosystems.

hackernews · syrusakbary · Jul 22, 17:20 · [Discussion](https://news.ycombinator.com/item?id=49010167)

**Background**: Tokenization converts input text into the token identifiers consumed by a language model, while pretokenization first divides text into smaller segments before final encoding. SIMD allows one processor instruction to operate on multiple data elements at once, which can accelerate repetitive text-processing work on supported x86 and ARM CPUs. Caching avoids recomputing encoded tokens when the same pretokenized segment appears again.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/marcelroed/gigatoken">GitHub - marcelroed/gigatoken: Language model tokenization at ...</a></li>
<li><a href="https://github.com/marcelroed/gigatoken/tree/main">GitHub - marcelroed/gigatoken: Language model tokenization at ...</a></li>
<li><a href="https://daily.dev/posts/github---marcelroed-gigatoken-language-model-tokenization-at-gb-s-eobew1umo">GitHub - marcelroed/gigatoken: Language model... - daily.dev</a></li>

</ul>
</details>

**Discussion**: Commenters were impressed by the benchmark results and welcomed the cross-CPU and cross-tokenizer consistency, while also questioning whether the optimization materially improves inference when tokenization is usually a tiny portion of runtime. Others noted that adoption may depend on integration by Hugging Face models or existing serving harnesses, although tokenization-only applications could benefit directly.

**Tags**: `#tokenization`, `#LLM`, `#SIMD`, `#performance-optimization`, `#systems-engineering`

---

<a id="item-3"></a>
## [Bento Packs a Complete Slide Editor Into One HTML File](https://bento.page/slides/) ⭐️ 8.0/10

Bento is a MIT-licensed presentation tool whose editor, viewer, slide data, animations, and offline functionality are packaged into a single shareable HTML file. A default deck is about 560 KB and can be edited, presented, printed, and saved in a browser without installation or a cloud login. Bento demonstrates how local-first web software can combine the portability and user ownership of ordinary files with browser-based editing and live collaboration. Its readable JSON slide model may also make presentations easier for tools such as Claude Code and ChatGPT to inspect and modify. Slide content is stored as a plain JSON block near the top of the file, while the application is compressed into a base64 blob and expanded in the browser through DecompressionStream; the implementation uses reveal.js and other libraries. Collaboration uses an encrypted blind relay that the creator says cannot read document data, while PPTX conversion is performed through external AI tools rather than a built-in native importer.

hackernews · starfallg · Jul 22, 15:19 · [Discussion](https://news.ycombinator.com/item?id=49008211)

**Background**: Local-first software keeps the primary working copy of data under the user's control and is designed to remain useful without a network connection. The approach aims to preserve offline access and long-term ownership while still supporting synchronization or collaboration when connectivity is available.

<details><summary>References</summary>
<ul>
<li><a href="https://www.inkandswitch.com/essay/local-first/">Local-first software: You own your data, in spite of the cloud</a></li>

</ul>
</details>

**Discussion**: Commenters were broadly enthusiastic about self-contained HTML applications and compared Bento favorably with tools such as draw.io, whose saved files still need an online editor. The creator highlighted the transparent JSON-plus-compressed-app layout, while one participant reported that the heavily used collaborative guestbook froze an M1 Mac and suggested that large concurrent sessions may expose performance or rendering limits.

**Tags**: `#local-first`, `#web applications`, `#presentation tools`, `#collaboration`, `#AI-assisted development`

---

<a id="item-4"></a>
## [LG Will Ban Residential-Proxy SDKs From Smart TV Apps](https://krebsonsecurity.com/2026/07/lg-to-ban-residential-proxies-from-smart-tv-apps/) ⭐️ 8.0/10

LG plans to prohibit smart TV apps from embedding residential-proxy SDKs that can enlist customers’ televisions as proxy nodes. The policy responds to reports that such software is widespread in connected-TV app stores and may operate without users clearly understanding the bandwidth-sharing arrangement. Residential proxies let third-party traffic appear to originate from ordinary home connections, making spam, manipulation, scraping, and other abuse harder for online services to identify or block. LG’s decision could protect customers’ privacy and home networks while setting a stronger app-store governance precedent for other smart TV platforms. Spur reported scanning 6,038 LG and Samsung smart TV apps and finding residential-proxy SDKs in 2,058 of them. These SDKs can route paying customers’ traffic through a television owner’s home IP address, so an effective ban will depend on app review, detection, removal, and enforcement rather than policy language alone.

hackernews · DemiGuru · Jul 22, 01:52 · [Discussion](https://news.ycombinator.com/item?id=49000864)

**Background**: A residential proxy network routes internet requests through consumer devices and home IP addresses rather than conventional data-center servers. Software developers may add a proxy SDK to an app to monetize users’ connectivity, turning installed devices into exit nodes for third-party traffic. Because smart TVs are commonly left connected to Wi-Fi and receive less scrutiny than computers or phones, owners may not notice the additional network activity.

<details><summary>References</summary>
<ul>
<li><a href="https://spur.us/blog/smart-tv-apps-residential-proxy-sdks">Nearly Half of LG Smart TV Apps Contain Residential Proxy SDKs</a></li>
<li><a href="https://www.fbi.gov/investigate/cyber/alerts/2026/evading-residential-proxy-networks-protecting-your-devices-from-becoming-a-tool-for-criminals">Evading Residential Proxy Networks: Protecting Your Devices from ... - FBI</a></li>
<li><a href="https://cloud.google.com/blog/topics/threat-intelligence/disrupting-largest-residential-proxy-network">Disrupting the World's Largest Residential Proxy Network | Google Cloud ...</a></li>

</ul>
</details>

**Discussion**: Commenters broadly welcomed action against residential proxies, describing them as major enablers of spam and social-media manipulation, while questioning how an app store could allow so many proxy-enabled apps and whether legal accountability should follow. Others connected the issue to broader frustration with smart TVs, including mandatory accounts, updates, terms-of-service prompts, slow interfaces, and the lack of simple offline displays; one commenter advised keeping the TV disconnected from the network.

**Tags**: `#smart-tv-security`, `#residential-proxies`, `#privacy`, `#malware`, `#app-store-governance`

---

<a id="item-5"></a>
## [Four Major AI Coding Agents Expose Sandbox-Escape Flaws.](https://www.bleepingcomputer.com/news/security/cursor-codex-gemini-cli-antigravity-hit-by-sandbox-escapes/) ⭐️ 8.0/10

Pillar Security disclosed sandbox-escape weaknesses affecting Cursor, OpenAI Codex, Google Gemini CLI, and Antigravity. Attackers can plant indirect prompt injections in repositories that persuade an agent to create trusted workspace files, which host-side development tools may later execute outside the sandbox. The attack bypasses isolation without directly breaking the sandbox, turning the normal interaction between an AI agent and the host toolchain into a path for arbitrary local code execution. It affects developers using autonomous coding tools and shows that sandboxing alone cannot secure repositories, dependencies, or other untrusted project content. Possible trigger points include README files, issues, dependencies, and code diffs, while the resulting artifacts may be configuration files, virtual environments, or command instructions automatically consumed by Python, Git, IDEs, or task runners. Fixes reportedly include Cursor 3.0.0 and Codex CLI v0.95.0, although Google downgraded two Antigravity findings because exploitation requires social engineering that convinces a victim to trust a malicious repository.

telegram · zaihuapd · Jul 22, 08:08

**Background**: An indirect prompt injection occurs when an AI agent reads attacker-controlled content, such as repository text or an issue, and treats embedded instructions as commands to follow. A sandbox is intended to constrain the files, processes, and network resources that an agent can access, but it does not automatically protect the host from artifacts that leave the sandbox through shared workspaces. In this attack chain, trusted host tools become the execution mechanism, so defenses must also govern generated files, workspace trust, privileged services, and automatic tool behavior.

<details><summary>References</summary>
<ul>
<li><a href="https://www.tinyash.com/blog/ai-agent-sandbox-evidence-based-selection-problem/">Agent 能运行不代表边界可信：用一份可追溯数据集挑选 AI 编程沙箱 - 小灰灰的笔记</a></li>

</ul>
</details>

**Tags**: `#AI安全`, `#沙箱逃逸`, `#提示注入`, `#编程代理`, `#供应链安全`

---