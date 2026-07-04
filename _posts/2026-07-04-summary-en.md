---
layout: default
title: "Horizon Summary: 2026-07-04 (EN)"
date: 2026-07-04
lang: en
---

> From 47 items, 3 important content pieces were selected

---

1. [Pegasus infected a European Parliament member.](#item-1) ⭐️ 8.0/10
2. [Wordgard rethinks browser rich-text editing.](#item-2) ⭐️ 8.0/10
3. [CDD claims logit-only recovery of finetuning data.](#item-3) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Pegasus infected a European Parliament member.](https://citizenlab.ca/research/member-of-committee-investigating-spyware-hacked-with-pegasus/) ⭐️ 8.0/10

Citizen Lab reported that European Parliament member Stelios Kouloglou, who was involved in investigating spyware abuse, had his iPhone infected with Pegasus on or around October 21, 2022, and again on March 6 and 7, 2023. The finding came after Kouloglou contacted Citizen Lab in May 2026 and researchers performed forensic analysis of artifacts from his device. The case raises serious concerns that spyware may have been used against a lawmaker scrutinizing the spyware industry itself, potentially compromising democratic oversight and sensitive parliamentary work. It also adds to wider European concerns about state-linked surveillance tools being used against politicians, journalists, activists, and other public-interest targets. Citizen Lab said it had high confidence in the infection findings and noted that the first infection overlapped with a previously identified Pegasus campaign targeting Russian- and Belarusian-speaking exiled journalists and activists in Europe. Pegasus infections can be especially difficult for targets to prevent because the spyware has used zero-click exploit chains that do not require the victim to tap a link or open a file.

hackernews · ledoge · Jul 3, 20:38 · [Discussion](https://news.ycombinator.com/item?id=48779683)

**Background**: Pegasus is spyware developed by Israel’s NSO Group and sold to government customers, officially for purposes such as fighting crime and terrorism. Public investigations by groups including Citizen Lab and Amnesty International have repeatedly found Pegasus used against journalists, lawyers, dissidents, politicians, and human-rights activists. Once installed on a phone, Pegasus has generally been reported to access messages, calls, location data, app data, microphones, and cameras, making a compromise of a personal or work phone highly sensitive.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Pegasus_(spyware)">Pegasus (spyware)</a></li>
<li><a href="https://surfshark.com/blog/pegasus-spyware">What is Pegasus spyware? How to detect and remove it - Surfshark</a></li>

</ul>
</details>

**Discussion**: Commenters focused on attribution and political context, with several pointing to prior Pegasus controversies in Greece, Poland, Italy, and other European countries. Some argued that the incident may be better understood as a member-state surveillance scandal rather than a direct attack on the European Parliament, while others questioned why confidential personal medical information and government documents may have coexisted on the same device.

**Tags**: `#cybersecurity`, `#spyware`, `#Pegasus`, `#government-surveillance`, `#European-Union`

---

<a id="item-2"></a>
## [Wordgard rethinks browser rich-text editing.](https://wordgard.net/) ⭐️ 8.0/10

Wordgard, a new in-browser rich-text editor system from ProseMirror creator Marijn Haverbeke, has been introduced at wordgard.net. It aims to provide tools for building semantic content editors while reworking parts of the architecture familiar from ProseMirror. Rich-text editing remains one of the hardest areas of web development, and ProseMirror has been highly influential among teams building structured editors. A new editor from the same author could shape how future web editors handle document modeling, typing, collaboration, and application-specific content rules. Wordgard is described as a semantic rich-text editor system rather than a free-form HTML editor, meaning applications control exactly what content structures are supported. Community discussion notes that it shares concepts with ProseMirror but does not appear to offer a simple upgrade path, so migration may require substantial work.

hackernews · indy · Jul 3, 08:50 · [Discussion](https://news.ycombinator.com/item?id=48772573)

**Background**: ProseMirror is a toolkit for building WYSIWYG-style rich-text editors on the web, especially for applications that need documents more structured and constrained than plain HTML. Wordgard appears to target a similar problem space: helping developers build custom browser-based editors where the document model is controlled by the application. This matters because browser editing primitives have long been difficult to use reliably for complex products such as publishing tools, note apps, and collaborative document systems.

<details><summary>References</summary>
<ul>
<li><a href="https://wordgard.net/">Wordgard</a></li>
<li><a href="https://prosemirror.net/">ProseMirror</a></li>
<li><a href="https://code.haverbeke.berlin/wordgard/wordgard">wordgard / wordgard : The Wordgard rich text editor</a></li>

</ul>
</details>

**Discussion**: The Hacker News discussion is broadly intrigued and positive, with several commenters praising the technical direction and the design. Key concerns include the lack of a clear migration path from ProseMirror, the difficulty of statically typing document JSON, and the broader frustration that robust rich-text editing still lacks a simple web-standard solution.

**Tags**: `#rich-text-editing`, `#web-development`, `#prosemirror`, `#collaborative-editing`, `#developer-tools`

---

<a id="item-3"></a>
## [CDD claims logit-only recovery of finetuning data.](https://www.reddit.com/r/MachineLearning/comments/1umn2dk/contrastive_decoding_diffing_cdd_recovering/) ⭐️ 8.0/10

The post introduces Contrastive Decoding Diffing, a proposed method that contrasts base-model and finetuned-model logits to recover verbatim finetuning content without access to weights, activations, or a probe corpus. The authors report a 4+/5 verbatim recovery score on 19 of 20 organism-by-model pairs across four model families from 1B to 32B parameters on the SDF benchmark. If validated, CDD would make finetuning-data extraction possible under a much weaker grey-box access model than prior white-box activation-based approaches. That would raise practical privacy and security concerns for model providers exposing token probabilities or logits through APIs, especially when models are narrowly finetuned on confidential or synthetic datasets. CDD is presented as an output-level analog of Activation Difference Lens: instead of computing activation differences inside the model, it decodes using differences between base and finetuned logits. The post also reports an accidental finding where the fictional scientist name “Dr. Elena Rodriguez” appeared across unrelated finetuning domains because Claude Sonnet 3.6 allegedly overused that persona when generating synthetic training data.

reddit · r/MachineLearning · /u/CebulkaZapiekana · Jul 3, 19:01

**Background**: Fine-tuning adapts a pretrained language model to a narrower task or dataset, and recent work discussed under Activation Difference Lens studies how those changes can leave detectable traces in internal activations. Contrastive decoding is a generation strategy that compares token scores from two models or distributions and chooses tokens based on their difference rather than a single model’s raw preference. Logits are the unnormalized token scores produced before probabilities are computed, so logit access can reveal more about a model’s next-token preferences than plain text outputs alone.

<details><summary>References</summary>
<ul>
<li><a href="https://www.emergentmind.com/topics/contrastive-decoding">Contrastive Decoding in Language Models</a></li>
<li><a href="https://learnmechinterp.com/topics/finetuning-traces/">Finetuning Traces in Activations | Learn Mechanistic Interpretability</a></li>

</ul>
</details>

**Tags**: `#LLM security`, `#data extraction`, `#model privacy`, `#contrastive decoding`, `#machine learning research`

---