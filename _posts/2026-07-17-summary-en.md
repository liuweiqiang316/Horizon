---
layout: default
title: "Horizon Summary: 2026-07-17 (EN)"
date: 2026-07-17
lang: en
---

> From 33 items, 3 important content pieces were selected

---

1. [LHS 1140 b Shows Evidence of a Retained Atmosphere.](#item-1) ⭐️ 8.0/10
2. [Kimi K3 Shows the Pelican Benchmark Is Diagnostic, Not Definitive.](#item-2) ⭐️ 8.0/10
3. [Firefox Now Runs Inside Browsers via WebAssembly.](#item-3) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [LHS 1140 b Shows Evidence of a Retained Atmosphere.](https://www.bbc.com/news/articles/cy4kdd1e0ejo) ⭐️ 8.0/10

Astronomers report the strongest evidence yet that LHS 1140 b, a rocky exoplanet in its star’s habitable zone about 48 light-years away, has retained an atmosphere. The observations point to an extended, helium-rich atmosphere, though further characterization is needed. If confirmed, this would be the first atmosphere detected around a rocky planet in a star’s habitable zone, making LHS 1140 b an important target in the search for potentially life-supporting environments. It would also show that such a planet can retain atmospheric material despite orbiting a red dwarf whose activity may strip atmospheres away. The result is evidence for an atmosphere rather than a determination that the planet is habitable or inhabited, and its composition and surface conditions remain uncertain. LHS 1140 b’s classification is important because a thick gaseous envelope on a mini-Neptune would have very different implications from an atmosphere surrounding a predominantly rocky world.

hackernews · neversaydie · Jul 17, 14:06 · [Discussion](https://news.ycombinator.com/item?id=48947560)

**Background**: A star’s habitable zone is the range of orbital distances where temperatures could permit liquid water, provided the planet has suitable atmospheric and surface conditions. Because red dwarfs are cooler and dimmer than the Sun, their habitable zones lie closer to them, potentially exposing planets to activity capable of eroding atmospheres. JWST can investigate transiting exoplanets spectroscopically by measuring how atmospheric chemicals alter starlight passing through or interacting with a planet’s atmosphere.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bbc.com/news/articles/cy4kdd1e0ejo">First atmosphere found around Earth-like planet LHS 1140 b</a></li>
<li><a href="https://www.cfa.harvard.edu/news/first-atmosphere-detected-habitable-zone-rocky-world">First atmosphere detected on a habitable-zone rocky world | Center for...</a></li>
<li><a href="https://science.nasa.gov/exoplanets/habitable-zone/">The Habitable Zone - NASA Science</a></li>

</ul>
</details>

**Discussion**: Commenters were interested but notably skeptical, questioning whether a habitable-zone planet around an active red dwarf could retain an atmosphere and whether “Earth-like” is an appropriate label. Some discussed evidence against a mini-Neptune interpretation, while others moved into speculation about solar gravitational-lens telescopes, interstellar probes, and whether extraterrestrial life exists at all.

**Tags**: `#astronomy`, `#exoplanets`, `#JWST`, `#astrobiology`, `#planetary-atmospheres`

---

<a id="item-2"></a>
## [Kimi K3 Shows the Pelican Benchmark Is Diagnostic, Not Definitive.](https://simonwillison.net/2026/Jul/16/kimi-k3/) ⭐️ 8.0/10

On July 16, 2026, Simon Willison evaluated Kimi K3 by asking it to generate an SVG of a pelican riding a bicycle. He argues that the result is more useful for probing model behavior and quality-cost-speed tradeoffs than for naming an overall winner. Simple generative tests can expose differences in instruction following, coding, visual composition, latency, and inference cost that aggregate benchmark scores may obscure. However, treating one stochastic output as a definitive ranking risks confusing sampling luck or possible training-data familiarity with general model capability. Moonshot AI advertises Kimi K3 as a 2.8-trillion-parameter model with a one-million-token context window. Important caveats include the use of only one sampled pelican per model, possible benchmark contamination, and an unexplained input-token count that commenters suspect may include a hidden system or reasoning prompt.

hackernews · droidjj · Jul 17, 14:21 · [Discussion](https://news.ycombinator.com/item?id=48947717)

**Background**: Kimi is a chatbot and large-language-model family developed by the Chinese company Moonshot AI. The pelican benchmark asks a model to produce SVG code depicting a pelican riding a bicycle, allowing people to inspect both whether the markup works and whether the rendered scene is visually coherent. Because model generation is probabilistic, repeated runs of the same prompt can produce materially different images.

<details><summary>References</summary>
<ul>
<li><a href="https://platform.kimi.ai/docs/guide/kimi-k3-quickstart">Kimi K3 - Kimi API Platform</a></li>
<li><a href="https://platform.kimi.ai/">Kimi API Platform</a></li>
<li><a href="https://huggingface.co/spaces/victor/pelican-benchmark">Pelican Benchmark - a Hugging Face Space by victor</a></li>

</ul>
</details>

**Discussion**: Commenters broadly agreed that the test is better for investigating tradeoffs than declaring a winner, but some questioned whether the frequently published pelican prompt could already be present in training data. They also raised concerns about a possible roughly 85-token hidden prompt, reported that Kimi was about five times cheaper but twice as slow in one comparison, and debated whether architecture and attention matter more than raw parameter count. Several participants called for multiple runs per model—such as eight samples—to reduce selection luck.

**Tags**: `#large-language-models`, `#AI-benchmarks`, `#Kimi-K3`, `#model-evaluation`, `#inference-cost`

---

<a id="item-3"></a>
## [Firefox Now Runs Inside Browsers via WebAssembly.](https://simonwillison.net/2026/Jul/16/firefox-in-webassembly/#atom-everything) ⭐️ 8.0/10

Puter compiled Firefox’s Gecko engine to WebAssembly, enabling a complete Firefox instance to run inside another browser. The demonstration loads websites through network connections tunneled via the Wisp protocol over WebSocket. The project demonstrates that a complex native browser engine can operate inside the WebAssembly sandbox, expanding what can be delivered as a browser-hosted application. It is also a notable example of AI-assisted systems engineering, although its large downloads and server-proxy requirements limit immediate practical deployment. The demo downloads a 233 MB gecko.wasm binary and an 18 MB compressed asset archive, and Firefox/Gecko was selected partly for its strong single-process support. Development reportedly consumed an estimated $25,000 worth of Claude Opus and Fable tokens at list-equivalent pricing, while HTTPS payloads remained encrypted through the proxy but plain HTTP traffic was visible in cleartext.

rss · Simon Willison · Jul 16, 23:34

**Background**: WebAssembly is a compilation target that allows code originating in languages such as C and C++ to execute within a browser sandbox. Emscripten made this port possible by compiling Gecko for that environment, but sandboxed browser code cannot directly open arbitrary network connections. Wisp addresses that restriction by multiplexing TCP or UDP socket traffic over a single WebSocket connection to a proxy server.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/HeyPuter/firefox-wasm">GitHub - HeyPuter/firefox-wasm: 🦊 Firefox in WebAssembly</a></li>
<li><a href="https://github.com/MercuryWorkshop/wisp-protocol">GitHub - MercuryWorkshop/wisp-protocol: Wisp is a low-overhead, easy to implement protocol for proxying multiple TCP/UDP sockets over a single websocket. · GitHub</a></li>
<li><a href="https://simonwillison.net/2026/Jul/16/firefox-in-webassembly/">Firefox in WebAssembly</a></li>

</ul>
</details>

**Tags**: `#WebAssembly`, `#Firefox`, `#browser-engineering`, `#AI-assisted-development`, `#systems-engineering`

---