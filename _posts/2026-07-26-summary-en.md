---
layout: default
title: "Horizon Summary: 2026-07-26 (EN)"
date: 2026-07-26
lang: en
---

> From 32 items, 4 important content pieces were selected

---

1. [EU Proposes Browser-Level Privacy Preferences](#item-1) ⭐️ 8.0/10
2. [GrapheneOS Details Defenses Against Locked-Device Data Extraction](#item-2) ⭐️ 8.0/10
3. [Ruff v0.16.0 Dramatically Expands Default Linting.](#item-3) ⭐️ 8.0/10
4. [SpaceX Reportedly Turns Away Long-Term Falcon 9 Orders](#item-4) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [EU Proposes Browser-Level Privacy Preferences](https://killthecookiebanner.eu/) ⭐️ 8.0/10

The European Commission has proposed allowing people to set privacy preferences centrally in their browsers, with websites automatically receiving and respecting those choices. The approach could replace many repetitive and misleading cookie-consent banners, but it remains a proposal rather than an enacted standard. A browser-level mechanism could make consent more consistent and less burdensome for users while forcing websites, advertisers, and consent-management providers to adapt their compliance systems. It also reflects a broader shift toward machine-readable privacy signals instead of asking people to make the same choice on every website. The proposal would need rules defining which preferences browsers can transmit, how websites must honor them, and whether users can override defaults for individual sites. Functionally necessary cookies may still be used to provide features such as logins, while optional tracking would remain the central consent issue.

hackernews · rapnie · Jul 26, 11:53 · [Discussion](https://news.ycombinator.com/item?id=49057175)

**Background**: Cookies are small pieces of data that websites store through a browser for purposes including login state, preferences, analytics, and tracking. Modern browsers can block cookies, but blanket blocking may disrupt services and require users to restore preferences repeatedly. Global Privacy Control is an existing example of a browser-transmitted signal designed to communicate certain privacy choices across websites, illustrating how preferences can be expressed in a machine-readable form.

<details><summary>References</summary>
<ul>
<li><a href="https://commission.europa.eu/cookies-policy_en">Cookies policy - European Commission</a></li>
<li><a href="https://globalprivacycontrol.org/">Global Privacy Control — Take Control Of Your Privacy</a></li>
<li><a href="https://www.theverge.com/news/823788/europe-cookie-prompt-browser-changes-proposal">Europe’s cookie nightmare is crumbling | The Verge</a></li>

</ul>
</details>

**Discussion**: Commenters broadly welcomed the proposal as a major usability improvement but argued that banners rarely produce genuinely informed consent and that the better solution is often to stop unnecessary surveillance. They also called for per-site overrides, contrasted the proposal with California's browser-level privacy requirements expected in 2027, and cautioned that the EU should turn the idea into binding action.

**Tags**: `#web-privacy`, `#EU-regulation`, `#cookies`, `#browser-standards`, `#consent-management`

---

<a id="item-2"></a>
## [GrapheneOS Details Defenses Against Locked-Device Data Extraction](https://discuss.grapheneos.org/d/40700-grapheneos-protections-against-data-extraction-from-locked-devices) ⭐️ 8.0/10

GrapheneOS published a technical overview of how it resists forensic data extraction from locked Android devices. Its protections include an 18-hour auto-reboot feature that returns an idle device to the more secure Before First Unlock state. Returning a phone to Before First Unlock removes disk-encryption keys from memory and reduces the data available to forensic tools. This is particularly relevant to journalists, confidential sources, border travelers, and other high-risk users whose devices may be seized while locked. Before First Unlock is stronger than merely locking a phone after it has already been unlocked, because encryption keys may remain loaded during the After First Unlock state. Auto-reboot does not compensate for a weak credential, so PIN or password entropy remains an important part of resisting offline guessing.

hackernews · Cider9986 · Jul 26, 05:57 · [Discussion](https://news.ycombinator.com/item?id=49055169)

**Background**: Modern Android devices use encryption states commonly described as Before First Unlock and After First Unlock. Before First Unlock is the state after boot but before the user enters a credential, when protected user data remains encrypted and the required keys are not loaded for normal access. After the first unlock, some keys may remain in memory even when the screen is locked, potentially allowing forensic tools to recover more information.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GrapheneOS">GrapheneOS - Wikipedia</a></li>
<li><a href="https://blogs.dsu.edu/digforce/2023/08/23/bfu-and-afu-lock-states/">BFU and AFU Lock States – Blog | DigForCE Lab</a></li>
<li><a href="https://discuss.grapheneos.org/d/40700-grapheneos-protections-against-data-extraction-from-locked-devices?ref=upstract.com">GrapheneOS protections against data extraction from locked...</a></li>

</ul>
</details>

**Discussion**: Commenters generally welcomed the protections and highlighted the 18-hour auto-reboot as useful for journalists, while also debating credential entropy and noting that Android pattern locks offer relatively little entropy. One participant argued that GrapheneOS still needs a complete backup-and-restore system so users can wipe phones before border crossings and restore app data afterward; others compared these protections with Apple security features.

**Tags**: `#GrapheneOS`, `#mobile-security`, `#Android`, `#digital-forensics`, `#data-privacy`

---

<a id="item-3"></a>
## [Ruff v0.16.0 Dramatically Expands Default Linting.](https://simonwillison.net/2026/Jul/25/ruff/#atom-everything) ⭐️ 8.0/10

Released by Astral on July 23, 2026, Ruff v0.16.0 increases its default lint rules from 59 to 413. The expanded defaults detect more problems without configuration, including syntax errors and code that would cause immediate runtime errors. The stricter defaults can materially improve defect detection across Python projects, but they can also abruptly break CI pipelines that install an unpinned Ruff version. Teams may need to pin Ruff, update configurations, or remediate newly reported violations before adopting the release. Ruff now contains 968 rules overall, up from 708 when its defaults last changed in v0.1.0; in sqlite-utils, running automatic and unsafe fixes found 1,618 errors, fixed 1,538, and left 80. The remaining findings included timezone-naive datetime use, broad Exception handling, and useless attribute access, while the use of --unsafe-fixes warrants comprehensive test coverage and review.

rss · Simon Willison · Jul 25, 22:44

**Background**: Ruff is a Python linting tool that analyzes source code for likely errors and rule violations, with its rules reimplemented in Rust as first-party functionality. A default rule set determines which checks run when a project has not explicitly selected rules. Some checks identify more than stylistic issues: loading a name before its global declaration is a Python syntax error, while using yield inside __init__ makes the initializer return a generator and leads to a runtime error.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.astral.sh/ruff/rules/">Rules | Ruff</a></li>
<li><a href="https://docs.astral.sh/ruff/rules/load-before-global-declaration/">load - before - global - declaration (PLE0118) | Ruff</a></li>
<li><a href="https://docs.astral.sh/ruff/rules/yield-in-init/">yield - in - init (PLE0100) | Ruff</a></li>

</ul>
</details>

**Tags**: `#Python`, `#Ruff`, `#linting`, `#CI/CD`, `#developer-tools`

---

<a id="item-4"></a>
## [SpaceX Reportedly Turns Away Long-Term Falcon 9 Orders](https://www.bloomberg.com/news/articles/2026-07-23/spacex-is-turning-away-falcon-customers-in-major-bet-on-starship) ⭐️ 8.0/10

SpaceX has reportedly stopped accepting dedicated Falcon 9 launch requests beyond 2028 and future bookings for its rideshare program. It is also said to be reducing production of some expendable Falcon components as it shifts capacity toward Starship. Falcon 9 is a major source of global commercial launch capacity, so retiring future availability before Starship enters commercial service could leave satellite operators with a launch shortfall. The decision would also concentrate SpaceX’s growth plans—including Starlink expansion—on a much larger but still developing vehicle. SpaceX may continue reserving Falcon 9 missions for the US Department of Defense and NASA, while commercial customers face the greatest exposure if Starship cannot take over by the end of 2028. Bloomberg notes that the reported plan could still change, particularly if Starship encounters further development setbacks.

telegram · zaihuapd · Jul 26, 12:42

**Background**: Falcon 9 is SpaceX’s partially reusable, two-stage medium-lift rocket and has helped reduce launch costs for commercial satellites and large constellations such as Starlink. Its rideshare missions let multiple customers share one launch rather than purchasing an entire rocket. Starship combines the Starship spacecraft with the Super Heavy booster and is designed as a fully reusable system capable of carrying more than 100 metric tonnes to orbit, but it has not yet begun commercial operations.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-07-23/spacex-is-turning-away-falcon-customers-in-major-bet-on-starship">SpaceX Is Turning Away Falcon Customers in Major Bet... - Bloomberg</a></li>
<li><a href="https://www.spacex.com/vehicles/starship">SpaceX - Starship</a></li>
<li><a href="https://en.wikipedia.org/wiki/Falcon_9">Falcon 9 - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#Starship`, `#Falcon 9`, `#商业航天`, `#卫星发射`

---