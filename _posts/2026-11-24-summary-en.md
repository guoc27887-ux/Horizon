---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 38 items, 3 important content pieces were selected

---

**Technology News**
1. [Nvidia Board Reinstates Jensen Huang as CEO Two Weeks After Ouster](#item-tech-news-1) ⭐️ 9.0/10
2. [Singapore won&\#x27;t be a conduit for evading US chip curbs, PM Wong says](#item-tech-news-2) ⭐️ 7.0/10

**Technology Blog**
1. [vLLM Day-0 Support for ERNIE 5.5 Flash Preview via Plugin](#item-tech-blog-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Nvidia Board Reinstates Jensen Huang as CEO Two Weeks After Ouster](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 9.0/10

Nvidia&\#x27;s board has unanimously reinstated Jensen Huang as CEO, reversing his removal less than two weeks after it occurred. In its statement, the board said it received input from senior levels of the US government and, based on that input, is confident that Huang&\#x27;s reinstatement poses no national security risk. Huang returns to lead the dominant supplier of AI chips at a time when US-China semiconductor export controls remain a contentious policy area. The available statement addresses the national-security question but does not detail the circumstances that prompted the original ouster.

hackernews · jaz · Nov 23, 14:00 · [Discussion](https://news.ycombinator.com/item?id=50611576)

**「Background」** Jensen Huang had been removed as Nvidia&\#x27;s CEO by its own board less than two weeks earlier, an abrupt ouster that quickly became entangled with national-security concerns in Washington. In reinstating him, the board said it had received input from senior levels of the US government indicating that his return posed no national security risk, and separate reporting says President Trump spoke &quot;directly&quot; to the board before the reversal. Lawmakers from both parties have criticized the reinstatement, citing continued national-security concerns.

**「Impact」** For Nvidia&\#x27;s customers and the broader AI hardware market, the decision restores leadership continuity at the dominant AI-chip supplier and removes near-term uncertainty about the company&\#x27;s direction. At the same time, the board&\#x27;s full reversal within two weeks, and its explicit citation of US government input, is likely to draw scrutiny from corporate-governance experts and policymakers focused on US-China chip export rules.

**「Community discussion」** Commenters flagged the board&\#x27;s citation of US government input as the operative part of the statement: icyfox argued that Delaware&\#x27;s Caremark standard, which sets a high bar for director liability, combined with a claimed Justice Department decision not to prosecute, likely shields the board, while expressing surprise at the unanimous two-week reversal. x313 cautioned against assuming Nvidia committed a crime, citing officials&\#x27; reported uncertainty about the espionage allegations, and others compared the episode to the 2023 OpenAI board fight as evidence that formal board authority can yield to outside pressure, with apexalpha calling the US stance hypocritical given pressure on ASML and Japanese chipmakers to join China sanctions.

<details><summary>References</summary>
<ul>
<li>Statement From NVIDIA Board of Directors</li>
<li>Nvidia reinstates Jensen Huang after Trump speaks &#x27;directly&#x27; to board</li>
<li>Trump praises Jensen Huang&#x27;s return as Nvidia CEO</li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Jensen Huang`, `#corporate governance`, `#semiconductors`, `#US-China tech policy`

---

<a id="item-tech-news-2"></a>
### [Singapore won&\#x27;t be a conduit for evading US chip curbs, PM Wong says](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

Singapore Prime Minister Lawrence Wong said Singapore will not allow itself to be used as a conduit for companies evading US chip export controls, and that authorities are investigating Megaspeed&\#x27;s purchases of Nvidia chips. His statement came a day after the US Commerce Department placed Megaspeed and six other Southeast Asian companies on its trade blacklist, with the Federal Register citing a &quot;significant risk&quot; that they could divert advanced computing products to unauthorized users; the listing also covers related entities in Malaysia and Thailand. Reuters reported that Alibaba&\#x27;s Singapore subsidiary, Apex Enterprise Solutions, is also on the list, and Alibaba said it has never diverted controlled advanced computing chips.

telegram · zaihuapd · Nov 24, 05:03

**「US blacklist of Megaspeed and partners」** The day before Wong&\#x27;s remarks, the US Commerce Department added Singapore-based Megaspeed — described in press reports as the company at the center of an alleged Nvidia-related spying scandal — and six other Southeast Asian companies to its trade blacklist, citing a &quot;significant risk&quot; that advanced computing products could be diverted to unauthorized users; the listing also covers related entities in Malaysia and Thailand. Among those named is Apex Enterprise Solutions, Alibaba&\#x27;s Singapore subsidiary, which the company says has never diverted chips subject to US export restrictions and will take legal steps to defend itself. The action fits within US export controls that keep advanced AI chips such as Nvidia&\#x27;s away from China and other unauthorized destinations, putting Southeast Asian intermediaries under growing scrutiny.

**「Impact」** The blacklist restricts US-origin advanced computing products, including Nvidia chips, from being shipped to Megaspeed, Apex Enterprise Solutions, and the other listed firms and their Malaysian and Thai affiliates without US authorization. Singapore&\#x27;s investigation into Megaspeed&\#x27;s Nvidia purchases signals tighter enforcement scrutiny of chip transactions routed through the city-state.

<details><summary>References</summary>
<ul>
<li><a href="https://www.aljazeera.com/economy/2026/11/24/us-adds-megaspeed-firm-at-centre-of-nvidia-scandal-to-export-control-list">US adds Megaspeed to trade blacklist after Nvidia spy... | Al Jazeera</a></li>
<li><a href="https://uz.kursiv.media/en/2026-11-24/us-blacklist-megaspeed-alice-huang/">US blacklists Megaspeed , once led by China spy suspect Alice Huang</a></li>

</ul>
</details>

**Tags**: `#semiconductors`, `#export-controls`, `#nvidia`, `#singapore`, `#us-china-tech`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [vLLM Day-0 Support for ERNIE 5.5 Flash Preview via Plugin](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 7.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** ERNIE 5.5 Flash Preview is a 280B-parameter sparse mixture-of-experts model \(14B activated per token, 1M-token context\) that the Baidu ERNIE and vLLM teams wanted servable on release day. Supporting a brand-new architecture normally means maintaining a fork or waiting for model-specific Docker images and nightly wheels, so the teams instead delivered support as a standalone vLLM plugin.

**「Solution」** ERNIE 5.5 Flash was designed around inference cost: 43 layers \(37 Heavily Compressed Attention, 6 MLA-DSA sparse attention\), 512 top-10 routed experts computing in a 2048-dim latent space, and a MultiMax output head. Because naive op-by-op implementations of these structures create many intermediate tensors, the authors built dedicated fused kernels—folding fixed mixing matrices into weights at load time, merging all router GEMMs into one, and computing the ~200K-logit piecewise activation in a single pass—reporting 1.55×–6.53× per-kernel speedups, though these figures are self-reported without benchmark methodology. FlashIndexer plugs a small head router \(distilled on ~1B tokens with the backbone frozen\) plus threshold pre-filtering into the DSA indexer, making sparse-index cost independent of context length for a claimed 1.4× speedup at 1M context. W4A8 quantization-aware training matches inference granularity, scales, and rounding exactly, so MXFP4 expert weights deploy without calibration; a 3-layer DSpark draft model, trained across mid-training, post-training, and on-policy distillation, drafts up to 7 tokens per step with a mean acceptance length above 4.0. Deployment needs only the official vllm==0.32.0 wheel plus the vLLM-ERNIE plugin, which registers model architectures as lazy-imported module paths through vllm.general\_plugins, so other models in the same environment are unaffected.

**「Takeaway」** The authors&\#x27; broader point is that co-designing a model for inference—fused kernels, quantization-aware training, and a bundled draft model shipped with the weights—combined with vLLM&\#x27;s entrypoint plugin mechanism, delivers day-0 high-performance serving without forking the inference engine.

**Tags**: `#vllm`, `#inference-optimization`, `#mixture-of-experts`, `#kernel-fusion`, `#speculative-decoding`

---