---
layout: default
title: "Horizon Summary: 2026-10-13 (EN)"
date: 2026-10-13
lang: en
---

> From 38 items, 2 important content pieces were selected

---

**Technology News**
1. [Cyberattack defrosts European supermarket fridges](#item-tech-news-1) ⭐️ 8.0/10
2. [Python 3.15 Adds Lazy Imports and Sampling Profiler](#item-tech-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Cyberattack defrosts European supermarket fridges](https://www.tomshardware.com/tech-industry/cyber-security/unprecedented-cyberattack-cripples-supermarket-fridges-across-europe-as-hackers-activate-automatic-defrosting-delivery-and-store-prices-also-impacted-by-incident) ⭐️ 8.0/10

Hackers reportedly disrupted supermarket refrigeration systems across Europe by remotely activating automatic defrosting, affecting French supermarket chains including Intermarché and forcing refrigerator shutdowns. The incident also reportedly affected delivery and store prices, showing that attacks on retail operational technology can spill into everyday business operations and food safety. The source links the case to prior research on Danfoss refrigeration controller vulnerabilities, though the supplied material does not confirm the exact exploit, attacker, or affected controller models. The item highlights the risk of internet-connected industrial and retail control systems, especially older equipment that may remain deployed after end of support.

hackernews · Zeekaas · Oct 12, 12:16 · [Discussion](https://news.ycombinator.com/item?id=50055304)

**「Background」** Supermarket refrigeration is often managed by operational-technology controllers that can be monitored or configured remotely, including functions such as temperature control and defrost cycles. Security researchers at Claroty’s Team82 reported in August 2026 that Danfoss AK-SM 800A refrigeration controllers had multiple vulnerabilities in their embedded web management interface, which Danfoss addressed with updated firmware.

**「Impact」** Affected supermarkets faced refrigeration disruption and related operational issues, with potential spoilage and store-level service consequences where cooling systems had to be shut down.

**「Community discussion」** Commenters focused on why refrigeration controllers are online, citing remote diagnostics, subscription-connected equipment, energy management, and reduced service calls as practical business drivers. Several commenters suspected older Danfoss controllers and referenced earlier reported incidents at US military commissaries, but they treated the links as unconfirmed rather than established attribution.

<details><summary>References</summary>
<ul>
<li><a href="https://claroty.com/team82/research/freeze-the-controller-defrost-the-food-uncovering-vulnerabilities-in-danfoss-refrigeration-controllers">Freeze the Controller, Defrost the Food: Uncovering ...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#operational-technology`, `#industrial-control-systems`, `#retail-tech`, `#vulnerabilities`

---

<a id="item-tech-news-2"></a>
### [Python 3.15 Adds Lazy Imports and Sampling Profiler](https://simonwillison.net/2026/Oct/12/python-3-15/) ⭐️ 8.0/10

Simon Willison highlights the release of Python 3.15 and explains its practical significance for maintainers who support every active Python version: Python 3.10 can now be dropped, making Python 3.11 features available in his projects. The release adds explicit lazy imports from PEP 810, allowing syntax such as \`lazy import json\` and deferring module loading until a symbol is first used, which directly addresses startup delays from heavy optional dependencies in plugin-based tools like his LLM CLI. Python 3.15 also adds unpacking in comprehensions from PEP 798, extending PEP 448-style unpacking with forms such as \`\[\*L for L in lists\]\`, \`\{\*s for s in sets\}\`, and \`\{\*\*d for d in dicts\}\`. The standard library now includes a high-frequency statistical sampling profiler, Tachyon, exposed as \`profiling.sampling\`, while the existing tracing profiler has been renamed from \`cProfile\` to \`profiling.tracing\`. Willison notes that Miguel Grinberg found Python 3.15 performance mostly similar to 3.14 in tests against 3.15.0rc3, except for the experimental JIT, which showed a 1.2x boost over the standard 3.15 interpreter on a Fibonacci benchmark.

rss · Simon Willison · Oct 12, 18:15

**「Background」** Python releases add language and standard-library features through PEPs, while open source maintainers often support only versions that remain within the active support window. Python 3.15’s highlighted changes include explicit lazy imports from PEP 810 and a new profiling package with the Tachyon sampling profiler, which provide context for why dropping Python 3.10 can let projects adopt newer syntax and runtime tooling.

**「Impact」** Python developers and open source maintainers can begin targeting Python 3.11-era features while evaluating Python 3.15’s new lazy import syntax and built-in sampling profiler for startup-time and production-diagnostics improvements.

<details><summary>References</summary>
<ul>
<li>What&#x27;s new in Python 3.15 — Python 3.15.0 documentation</li>

</ul>
</details>

**Tags**: `#Python`, `#programming-languages`, `#open-source`, `#software-engineering`

---