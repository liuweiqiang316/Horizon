---
layout: default
title: "Horizon Summary: 2026-10-09 (EN)"
date: 2026-10-09
lang: en
---

> From 37 items, 2 important content pieces were selected

---

**Technology News**
1. [Tsinghua Team Reports Thorium-229 Nuclear Optical Clock](#item-tech-news-1) ⭐️ 8.0/10

**Technology Blog**
1. [Jev Decision Models in a Weekly Roundup](#item-tech-blog-1) ⭐️ 4.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Tsinghua Team Reports Thorium-229 Nuclear Optical Clock](https://www.nature.com/articles/s41586-026-11122-1) ⭐️ 8.0/10

A Tsinghua University research team reportedly developed and stably operated a nuclear optical clock using a self-developed 148 nm continuous-wave vacuum-ultraviolet laser and a thorium-229-doped calcium fluoride crystal. The result was published in Nature, according to the supplied Xinhua-based item. The clock uses an energy-level transition in the thorium-229 nucleus as its timing reference, rather than an electronic transition as in conventional atomic optical clocks. If confirmed as described, the work would mark an important step toward next-generation time and frequency standards for high-precision applications such as satellite navigation and deep-space exploration, though the supplied item provides limited performance metrics or uncertainty data.

telegram · zaihuapd · Oct 8, 05:19

**「Background」** Optical clocks keep time by locking a laser to a sharply defined quantum transition, and nuclear optical clocks would instead use a transition inside an atomic nucleus, which is expected to be less sensitive to some external disturbances. Thorium-229 is the main candidate because it has an unusually low-energy nuclear transition that can be driven with vacuum-ultraviolet light; Nature is a peer-reviewed multidisciplinary science journal where such physics results are commonly reported.

**「Impact」** If confirmed, the result gives precision-metrology researchers a working thorium-229 nuclear-clock platform for pursuing more stable time standards and tests of fundamental physics, though practical use in navigation or deep-space systems remains downstream rather than demonstrated.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Nature_%28journal%29">Nature (journal) - Wikipedia</a></li>
<li><a href="https://particle.news/story/two-teams-build-the-first-working-nuclear-clocks">Particle: Two Teams Build the First Working Nuclear Clocks</a></li>
<li><a href="https://www.nist.gov/news-events/news/2024/09/major-leap-nuclear-clock-paves-way-ultraprecise-timekeeping">Major Leap for Nuclear Clock Paves Way for Ultraprecise... | NIST</a></li>

</ul>
</details>

**Tags**: `#precision timing`, `#atomic clocks`, `#photonics`, `#quantum metrology`, `#research`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Jev Decision Models in a Weekly Roundup](http://www.ruanyifeng.com/blog/2026/10/weekly-issue-414.html) ⭐️ 4.0/10

rss · 阮一峰的网络日志 · Oct 8, 15:04

**「Background」** Ruan Yifeng’s weekly issue is mostly a technology link roundup, but its lead item focuses on TypeSafe AI’s Jev, which the author frames as a surprisingly simple but useful new “decision model.” Unlike chat models that return text, Jev returns floating-point probabilities, making it suited—at least conceptually—to binary judgments, multiple-choice selection, and scoring tasks.

**「Solution」** The author’s central point is that once an AI model emits quantitative judgments instead of prose, many problems that were awkward to automate become computable. He illustrates this with two browser-extension examples: a semantic Ctrl+F that checks each paragraph against a user’s query and ranks passages by relevance probability, and a webpage-quality scorer that applies a rubric ranging from unsupported rhetoric to rigorous, evidence-backed reasoning that addresses counterarguments. In both cases, Jev is treated less like a conversational assistant and more like a reusable classifier or evaluator whose output can be sorted, filtered, or composed into software behavior. Ruan argues that this makes the model immediately useful, while also pointing readers to Simon Willison’s more skeptical view: because Jev returns only a number, it can be even more of a black box than ordinary large language models, which can at least be asked to explain themselves. The concern becomes concrete in hiring, where résumé screening or candidate ranking could be reduced to an opaque score without exposing how the judgment was made. The rest of the issue continues in roundup form, briefly covering claims about Markdown becoming source code, an AI-only home camera concept, an alleged RSA factoring record aided by Claude and GPUs, plus curated articles, tools, resources, images, and quotations.

**「Takeaway」** The issue presents Jev as a reminder that model interfaces matter: changing the output from language to probability can turn AI from a writing partner into infrastructure for automated decisions. But the same abstraction that makes scoring and ranking easy also raises the risk of powerful, unexplained black-box judgments.

**Tags**: `#AI models`, `#decision models`, `#technology roundup`, `#developer tools`, `#Markdown`

---