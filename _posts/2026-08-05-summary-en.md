---
layout: default
title: "Horizon Summary: 2026-08-05 (EN)"
date: 2026-08-05
lang: en
---

> From 32 items, 3 important content pieces were selected

---

**Technology News**
1. [Google Reshuffles DeepMind as Dean and Ghemawat Depart](#item-tech-news-1) ⭐️ 8.0/10
2. [Reported ChainDrop Worm Compromises Over 1,300 npm Packages](#item-tech-news-2) ⭐️ 8.0/10
3. [FFmpeg 9.0 Adds Animated WebP and New GPU Filters](#item-tech-news-3) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Google Reshuffles DeepMind as Dean and Ghemawat Depart](https://blog.google/company-news/inside-google/message-ceo/next-chapter-ai-momentum/) ⭐️ 8.0/10

Google is reportedly moving Demis Hassabis from CEO of Google DeepMind to chair as part of a broader AI leadership reshuffle. Jeff Dean is leaving after 27 years at Google, alongside Google Senior Fellow Sanjay Ghemawat. Dean and Ghemawat plan to launch an independent public benefit corporation focused on accelerating discoveries in machine learning, science, and engineering. The departures remove two foundational engineers from Google while changing how one of the industry’s most influential AI organizations is led.

hackernews · colesantiago · Aug 5, 16:05 · [Discussion](https://news.ycombinator.com/item?id=49184755)

**「Background」** Google DeepMind is Google’s central AI research organization, and Demis Hassabis led it as CEO before this restructuring; he is also a Nobel Prize laureate. Jeff Dean and Sanjay Ghemawat are veteran Google engineers, with Ghemawat particularly known for co-creating foundational distributed-systems infrastructure.

**「Impact」** Google DeepMind faces a simultaneous leadership and expertise transition as Demis Hassabis leaves day-to-day management and longtime Google engineers Jeff Dean and Sanjay Ghemawat depart to build Discovery Loop.

**「Community reaction」** Commenters largely considered Dean and Ghemawat’s departure more consequential than Hassabis’s role change, describing it as the end of an era and raising concerns about retaining senior engineers. Broader claims about a sustained talent exodus and its effects on Google’s AI competitiveness remained speculative.

<details><summary>References</summary>
<ul>
<li><a href="https://www.solidot.org/story?sid=85019">奇客Solidot | Google DeepMind CEO Demis Hassabis 卸任</a></li>
<li><a href="https://aiwiki.ai/wiki/sanjay_ghemawat">Sanjay Ghemawat | AI Wiki</a></li>
<li><a href="https://the-decoder.com/google-deepmind-loses-both-its-ceo-and-chief-scientist-as-demis-hassabis-and-jeff-dean-step-down-simultaneously/">Google Deepmind loses both its CEO and chief scientist as Demis ...</a></li>
<li><a href="https://www.axios.com/2026/08/05/google-deepmind-demis-hassabis-ai">Google DeepMind CEO Demis Hassabis is stepping aside</a></li>

</ul>
</details>

**Tags**: `#Google DeepMind`, `#AI leadership`, `#Jeff Dean`, `#machine learning`, `#technology industry`

---

<a id="item-tech-news-2"></a>
### [Reported ChainDrop Worm Compromises Over 1,300 npm Packages](https://www.bleepingcomputer.com/news/security/massive-chaindrop-npm-supply-chain-attack-infects-hundreds-of-packages/) ⭐️ 8.0/10

A Telegram summary of a BleepingComputer report says the self-propagating ChainDrop worm compromised more than 1,300 npm packages with a combined two billion monthly downloads, including the popular Keyv and Cacheable caching tools. The reported attack began with a compromised Keyv maintainer GitHub account and spread to packages associated with organizations including Deliveroo, Qlik, and ServiceTitan, using normal GitHub Actions publishing workflows and carrying legitimate provenance attestations. Malicious setup.mjs and Math\_Symbol.js files allegedly execute during npm install, steal GitHub, npm, AWS, and Kubernetes credentials, and use maintainer access to infect additional packages. The report advises treating systems that installed affected versions as compromised, rebuilding environments, rotating all tokens, reviewing logs, and checking for the npm-cache\[.\]com domain. The claimed scope and assertion that the campaign remains active require confirmation from official npm notices or primary security research.

telegram · zaihuapd · Aug 5, 03:04

**「Background」** npm packages can define lifecycle scripts that run automatically during installation; in this case, poisoned packages used a preinstall entry to execute the setup.mjs payload dropper, which then invoked the Math\_Symbol.js credential-stealing script. This is a software supply-chain attack because compromising a maintainer account and its normal publishing workflow can distribute malicious releases—and even produce legitimate provenance records—through channels developers ordinarily trust.

**「Impact」** Developers and CI environments that installed affected releases should treat their systems as compromised, rebuild them, rotate GitHub, npm, AWS, and Kubernetes credentials, and review access logs.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/massive-chaindrop-npm-supply-chain-attack-infects-hundreds-of-packages/">Massive ChainDrop npm supply-chain attack infects hundreds of packages</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/massive-chaindrop-npm-supply-chain-attack-infects-hundreds-of-packages/">Massive ChainDrop npm supply- chain attack infects hundreds of...</a></li>
<li><a href="https://www.techradar.com/pro/security/new-chaindrop-worm-poisons-over-1-300-npm-packages-keyv-and-cacheable-among-those-hit">New ChainDrop worm poisons over 1,300 npm packages , Keyv and...</a></li>

</ul>
</details>

**Tags**: `#npm`, `#软件供应链安全`, `#凭证窃取`, `#开源生态`, `#恶意软件`

---

<a id="item-tech-news-3"></a>
### [FFmpeg 9.0 Adds Animated WebP and New GPU Filters](https://news.ycombinator.com/item?id=49166202) ⭐️ 8.0/10

FFmpeg 9.0 has been released with an animated WebP decoder and demuxer, a Playdate video encoder and muxer, and HE-AAC 960 decoding for DAB+. GPU-related additions include the v360\_vulkan and transpose\_cuda filters, alongside an AMF frame-rate conversion filter. The release also introduces an ONNX Runtime backend for deep-neural-network processing. Through Anthropic’s Claude for Open Source Program, the FFmpeg team received six months of free Claude Max access and reportedly used Claude to help identify missing backports, although some community members raised concerns about security-review procedures for AI-assisted development. The supplied secondary summary does not provide detailed compatibility changes or broader release-note caveats.

telegram · zaihuapd · Aug 5, 10:32

**「Background」** FFmpeg is an open-source suite of command-line tools and libraries for decoding, encoding, filtering, and packaging multimedia, and it underpins many media applications and services. A backport applies a change from a newer development branch to an older or release branch, commonly to carry over bug fixes or security patches without importing all newer code.

**「Upgrade impact」** Applications that embed FFmpeg libraries will need compatibility testing and likely rebuilding or code changes because FFmpeg 9.0 raises the major version of all seven libraries and breaks ABI compatibility across them.

<details><summary>References</summary>
<ul>
<li><a href="https://jbkempf.com/blog/2026/ffmpeg-9.0/">FFmpeg 9.0 — Jean-Baptiste Kempf</a></li>

</ul>
</details>

**Tags**: `#FFmpeg`, `#multimedia-codecs`, `#GPU-acceleration`, `#AI-assisted-development`, `#open-source`

---