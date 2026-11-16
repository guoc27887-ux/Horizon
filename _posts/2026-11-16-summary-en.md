---
layout: default
title: "Horizon Summary: 2026-11-16 (EN)"
date: 2026-11-16
lang: en
---

> From 36 items, 10 important content pieces were selected

---

**Technology News**
1. [Sebastian Raschka Explains Positional Embeddings in Modern LLMs](#item-tech-news-1) ⭐️ 8.0/10
2. [Meta FAIR and NYU study finds vision-encoder pretraining optional but vision-only parameters essential](#item-tech-news-2) ⭐️ 8.0/10
3. [Meituan open-sources LongCat-2.5, claiming training without NVIDIA GPUs](#item-tech-news-3) ⭐️ 8.0/10
4. [MacBook Pro OLED PWM flicker draws scrutiny](#item-tech-news-4) ⭐️ 7.0/10
5. [Microsoft 365 outage linked to delayed chlorine alert at German hotel](#item-tech-news-5) ⭐️ 7.0/10
6. [Open-source cudaMemcpy tuner boosts pageable transfers 5x on B300](#item-tech-news-6) ⭐️ 7.0/10
7. [Report links Rubio and Anthropic to pressure campaign around Jensen Huang&\#x27;s exit](#item-tech-news-7) ⭐️ 7.0/10

**Financial News**
1. [US, China and Russia leaders to hold first trilateral meeting at Shenzhen APEC summit](#item-finance-news-1) ⭐️ 9.0/10
2. [Lutnick faces questions over Nvidia ties as his sons&\#x27; firm cut its Nvidia stake](#item-finance-news-2) ⭐️ 7.0/10
3. [FT reports Jensen Huang discussing possible return as Nvidia CEO](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Sebastian Raschka Explains Positional Embeddings in Modern LLMs](https://magazine.sebastianraschka.com/p/understanding-positional-embeddings) ⭐️ 8.0/10

Sebastian Raschka published an article explaining how positional embeddings work in modern large language models. The piece focuses on the practical mechanics of the technique, which lets transformer models distinguish token order despite attention being order-agnostic. It prompted a technically substantive Hacker News discussion, including a comment arguing that a deeper treatment should cover positional embeddings as group representations and their learnable parameterization.

hackernews · vismit2000 · Nov 15, 12:14 · [Discussion](https://news.ycombinator.com/item?id=50506376)

**「Why positional embeddings matter」** Transformers process tokens in parallel rather than sequentially, so the architecture needs an explicit signal that tells the model where each token sits in a sequence. Positional embeddings provide that signal, and variants such as rotary embeddings have become common in modern LLMs. Sebastian Raschka&\#x27;s article focuses on how these mechanisms are implemented, while a commenter argues that a fuller understanding comes from viewing positional embeddings as group representations that can be derived and parameterized mathematically.

**「Practical impact」** For engineers and researchers working with transformer models, the article provides a practical map of how positional-embedding choices affect sequence-order handling and long-context behavior. The accompanying references indicate that RoPE is used by Llama, Mistral, Qwen, and many frontier models, while ALiBi penalizes attention between distant tokens and YaRN extends RoPE beyond its training range without retraining. The practical consequence is that model builders and fine-tuners need to understand these schemes when comparing architectures, adjusting context length, or reasoning about compatibility with existing checkpoints.

<details><summary>References</summary>
<ul>
<li><a href="https://www.institutepm.com/knowledge-hub/rope-alibi-yarn-explained">RoPE , ALiBi , and YaRN Explained: How Modern LLMs Handle Long...</a></li>

</ul>
</details>

**Tags**: `#LLMs`, `#positional embeddings`, `#transformers`, `#machine learning`, `#deep learning`

---

<a id="item-tech-news-2"></a>
### [Meta FAIR and NYU study finds vision-encoder pretraining optional but vision-only parameters essential](https://www.reddit.com/r/MachineLearning/comments/1xx1k2o/meta_fair_nyu_unbundling_multimodal_vision/) ⭐️ 8.0/10

Researchers from Meta FAIR and NYU trained more than 200 multimodal LLMs from scratch under a shared compute budget to separate three design choices usually bundled into a vision encoder: separate pretraining, vision-only parameters, and placement before the LLM. They found that separate encoder pretraining is optional—encoders pretrained with contrastive, self-supervised, and captioning objectives at best tied a from-scratch encoder at matched compute, and even 6.5x longer MetaCLIP pretraining raised ImageNet linear-probe accuracy from 80.4% to 84.4% without improving VQA. Vision-only parameters, however, are required: encoder-free models trailed at every backbone size from 0.6B to 6.4B and needed roughly 3x the compute to catch up, while giving the LLM the encoder&\#x27;s parameters improved text performance but not VQA. Placement before the LLM was also optional—an &quot;in-fusion&quot; design adding zero-initialized vision-only weights to the LLM&\#x27;s first 8 layers matched the encoder from 1.7B to 6.4B with about 13% lower time to first token, and at 1.7B reached 45.0 VQA versus the encoder&\#x27;s 44.4. The work is presented by one of the authors on r/MachineLearning, with the paper on alphaXiv and a blog/FAQ page.

reddit · r/MachineLearning · /u/trungh98 · Nov 15, 17:38

**「Why this study matters」** Multimodal LLMs typically attach a separately pretrained vision encoder to a language model, but recent releases have moved in different directions—some dropping the encoder, some training it from scratch, and some reintroducing one—making it hard to tell which design choices actually matter. The study&\#x27;s contribution is to unbundle a standard encoder into three separable choices: separate vision pretraining, dedicated vision-only parameters, and placement before the LLM, then test each under a shared compute budget.

**「Practical implications for multimodal model design」** For teams designing or training multimodal LLMs, the study suggests that compute spent on separately pretraining a vision encoder may be unnecessary under a matched budget, while preserving dedicated vision-only parameters is important: encoder-free models trailed from 0.6B to 6.4B and needed about 3x the compute to catch up. The reported in-fusion alternative—zero-initialized vision-only weights in the LLM&\#x27;s first 8 layers—was on par with an encoder from 1.7B to 6.4B and reduced time to first token by about 13%, so architecture and parameter allocation may matter more than encoder pretraining for VQA performance. These conclusions are based on the paper&\#x27;s controlled setup using Qwen3-style 1.7B/4B configurations, 0.4B vision parameters, 16 VQA benchmarks at 448 px, and 12 language benchmarks, so teams should validate against their own data, scale, and objectives before dropping encoder pretraining.

**「Community discussion」** No community comments were available on the Reddit thread at the time of collection. The post itself is authored by a self-identified paper author \(/u/trungh98\) who invited questions, so any discussion would be author-led Q&amp;A rather than independent community debate.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Vision_%28Marvel_Comics%29">Vision (Marvel Comics ) - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#multimodal models`, `#vision encoders`, `#machine learning research`, `#model architecture`, `#Meta FAIR`

---

<a id="item-tech-news-3"></a>
### [Meituan open-sources LongCat-2.5, claiming training without NVIDIA GPUs](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team has open-sourced the weights of LongCat-2.5, a 1.6-trillion-parameter model designed for agents that autonomously handle long, multi-step tasks, especially coding. The weights were released about a week after the model&\#x27;s official launch, under the MIT license for commercial use. The model activates roughly 48 billion parameters per token, accepts text, image, and video input, and scores 88.4 on Terminal Bench v2.1, slightly below Claude Opus 5&\#x27;s 89.1. Meituan says training used Chinese Huawei Ascend accelerators throughout and no NVIDIA GPUs, but this is an official claim rather than an independently verified result.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** LongCat-2.5 is a native multimodal mixture-of-experts model with 1.6 trillion total parameters, about 48 billion activated per token, and a 1 million-token context window, designed for long-horizon agentic tasks such as coding. Meituan&\#x27;s LongCat team released the weights under an MIT license after an initial model launch, making the system available for commercial use and inspection. The claim that it was trained on Huawei Ascend accelerators rather than NVIDIA GPUs matters because NVIDIA hardware has been the dominant platform for training very large AI models, so a 1.6T-parameter model trained without it would be a notable datapoint for China&\#x27;s domestic AI-chip ecosystem.

**「Practical impact for developers and AI teams」** Developers and organizations can now access MIT-licensed LongCat-2.5 weights for commercial use, enabling agentic coding applications with text, image, and video input and roughly 48 billion activated parameters per token. Its reported Terminal Bench v2.1 score of 88.4—just below Claude Opus 5&\#x27;s 89.1—suggests near-frontier coding-agent capability, though the claim that training used no NVIDIA GPUs is an official Meituan statement rather than an independently verified result. Teams evaluating it should also note that a separate listing advertises a LongCat-2.5-Preview in OpenCode with 1 million-token context and free access, but no published end date.

<details><summary>References</summary>
<ul>
<li><a href="https://www.longcatai.org/models/longcat-2-5">LongCat - 2 . 5 | 1 . 6 T Native Multimodal Model for Agentic Tasks</a></li>
<li><a href="https://huggingface.co/meituan-longcat/LongCat-2.5">meituan - longcat / LongCat - 2 . 5 · Hugging Face</a></li>
<li><a href="https://presentofai.com/e/39988">Meituan releases 1.6T-parameter LongCat 2 . 5 on Chinese chips</a></li>
<li><a href="https://www.orcarouter.ai/ru/blog/longcat-2-5-preview-free-opencode">LongCat - 2 . 5 -Preview бесплатно на OpenCode: 1M токенов, без...</a></li>

</ul>
</details>

**Tags**: `#AI models`, `#open source`, `#LLM training`, `#Chinese semiconductors`, `#agentic coding`

---

<a id="item-tech-news-4"></a>
### [MacBook Pro OLED PWM flicker draws scrutiny](https://macanorak.com/the-macbook-pros-oled-pwm-problem-when-a-better-display-becomes-worse-to-use/) ⭐️ 7.0/10

A MacAnorak article examines pulse-width modulation \(PWM\) flicker in the new MacBook Pro&\#x27;s OLED display, arguing that a display technology intended to improve image quality can be worse to use for flicker-sensitive people. The piece reports measurements of the display&\#x27;s PWM behavior, including a 240 Hz claim, and notes that the tandem OLED design&\#x27;s dimming behavior is more complicated than a single simple flicker rate. The article has prompted technical discussion about whether the effective flicker frequency is higher than the measured figure and about how PWM sensitivity affects users.

hackernews · MacAnorak · Nov 15, 13:15 · [Discussion](https://news.ycombinator.com/item?id=50506719)

**「Background」** The MacBook Pro&\#x27;s new display is Apple&\#x27;s first OLED MacBook panel, described as a tandem OLED design in which two OLED emission layers are stacked to raise brightness and efficiency. PWM \(pulse-width modulation\) flicker is a display dimming technique in which brightness is controlled by rapidly switching the backlight or pixels on and off; some users report eye strain or headaches from low-frequency flicker, while others do not notice it. The current discussion follows testing of the new MacBook Pro&\#x27;s PWM behavior, with commenters debating whether the measured 240 Hz figure reflects the panel&\#x27;s actual worst-case flicker frequency.

**「Practical impact」** For users who are sensitive to display flicker, the reported low PWM frequency on the new MacBook Pro&\#x27;s OLED panel could make a nominally better screen harder to use for long sessions, with symptoms such as eye strain, headaches, fatigue, migraines, or blurred vision. Buyers with a history of flicker sensitivity may want to test the display in person before upgrading, and current owners who experience discomfort may need to limit use, adjust brightness, or fall back to an external display. The community debate over whether the effective frequency is 240 Hz, 480 Hz, or 960 Hz also means affected users should not assume a single published number settles how the panel will feel to them.

**「Community discussion」** Commenter legitronics questioned the testers&\#x27; 240 Hz conclusion, suggesting the two OLED layers may pulse at 480 Hz out of phase, producing an effective rate closer to 960 Hz at most usable brightness levels. Others, including achr2, expressed surprise at the low PWM frequency and cited research on human flicker perception, while Velocifyer and Telaneo argued that more research is needed into flicker sensitivity and related display factors such as CRI and motion blur.

<details><summary>References</summary>
<ul>
<li><a href="https://www.techradar.com/computing/macbooks/whats-the-tech-inside-the-touchscreen-macbook-pros-proled-xdr-screen-heres-why-the-tandem-oled-panel-is-important">What&#x27;s the tech inside the touchscreen MacBook Pro &#x27;s &#x27;PROLED XDR....</a></li>
<li><a href="https://forums.macrumors.com/threads/pwm-confirmed-2024-ipp-oled-keep-those-2018-12-9-ipps-face-with-symbols-on-mouth.2426261/page-6">PWM Confirmed - 2024 IPP - OLED - Keep... | MacRumors Forums</a></li>
<li><a href="https://circadianshield.com/blog/pwm-flicker-headaches">PWM Sensitivity Headaches : Symptoms, 2-Min Test &amp; Fixes</a></li>
<li><a href="https://grokipedia.com/page/Screen_dimming_apps_for_AMOLED_devices">Screen dimming apps for AMOLED devices — Grokipedia</a></li>

</ul>
</details>

**Tags**: `#hardware`, `#displays`, `#OLED`, `#MacBook Pro`, `#PWM flicker`

---

<a id="item-tech-news-5"></a>
### [Microsoft 365 outage linked to delayed chlorine alert at German hotel](https://www1.wdr.de/nrw/rheinland/rhein-erft-kreis/technischer-defekt-chlor-phantasialand-100.html) ⭐️ 7.0/10

A defective pool-water dosing system at a German hotel, combined with a Microsoft 365 email outage that reportedly disrupted monitoring alerts, was followed by chlorine gas exposure affecting 15 guests. Reports cited by community discussion describe 13 guests initially complaining of airway irritation, with two more affected later; four were taken to hospital, one with a medium injury, and the rest were discharged. The incident is being discussed as a dual failure: the dosing system dispensed too much chlorine, while the email-based alerting path failed during the Microsoft 365 outage. The full technical and responsibility details are not established from the supplied source content.

hackernews · DeepLogin · Nov 15, 18:36 · [Discussion](https://news.ycombinator.com/item?id=50509411)

**「Background」** The incident occurred at a hotel associated with Phantasialand in Germany&\#x27;s Rhein-Erft district, where a pool chlorination system malfunctioned and dispensed too much chlorine. According to WDR, a Microsoft outage on Friday, November 14, 2026, prevented the park from receiving the automated email warning about the excessive chlorine level, so the fault went unnoticed until guests were exposed. Closed-loop chlorination systems are commonly used to keep pool disinfectant within safe limits, but, as one operator commented, they can fail in a way that under-measures chlorine and causes over-dosing, which is why commercial installations are expected to have independent monitoring and human oversight rather than relying on a single alerting channel.

**「Operational impact」** The immediate consequence was that 15 hotel guests were exposed to chlorine gas and developed airway irritation; 4 were taken to hospital, with one described as having a medium injury and the rest discharged. For operators of safety-critical facilities, the actionable concern is that a defective pool dosing system combined with a monitoring alert path that depended on Microsoft 365 email left no reliable backup channel or independent human check, so alarms could be delayed or lost during a cloud outage. The practical lesson is to treat cloud email as non-safety-critical: use redundant, independent alerting paths, local alarms, and fail-safe dosing controls, and verify responsibility and compliance requirements rather than assuming a single vendor notification will protect guests.

**「Community discussion」** Commenters largely argued that the hotel&\#x27;s design—not Microsoft—was the core problem: N19PEDL2 called it “100% fault of the hotel” for relying on email without backup, and discordance said anything capable of causing such harm needs redundant architecture. Amluto, describing experience with closed-loop chlorination systems, warned that such systems can fail by measuring low or zero chlorine and overdispensing, requiring human oversight or an independent sensor design. Havoc cautioned that the German article sounds less dramatic than the Hacker News title and described the event as two distinct failures.

<details><summary>References</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50509411">Microsoft 365 outage leads to chlorine gas poisoning of 15 hotel ...</a></li>
<li><a href="https://www1.wdr.de/nrw/rheinland/rhein-erft-kreis/technischer-defekt-chlor-phantasialand-100.html">Chlor: Phantasialand bekam wegen Outlook nichts mit</a></li>
<li><a href="https://www.microsoft.com/en-us">Microsoft – AI, Cloud, Productivity, Computing, Gaming &amp; Apps</a></li>

</ul>
</details>

**Tags**: `#incident-response`, `#cloud-outage`, `#safety-critical-systems`, `#microsoft-365`, `#operational-resilience`

---

<a id="item-tech-news-6"></a>
### [Open-source cudaMemcpy tuner boosts pageable transfers 5x on B300](https://www.reddit.com/r/MachineLearning/comments/1xx2n25/making_cudamemcpy_5x_faster_on_a_b300_p/) ⭐️ 7.0/10

A developer released an open-source cudaMemcpy tuner that speeds up pageable host-to-device transfers about 5x on an NVIDIA B300. In the posted benchmark, copying a 1 GB PyTorch tensor from CPU to GPU rose from 10.2 GB/s to 51.5 GB/s when the benchmark was run under \`cmt tune\`. The tool and a detailed write-up are available on GitHub and the author&\#x27;s blog.

reddit · r/MachineLearning · /u/makneeee · Nov 15, 18:20

**「Why pageable transfers are slow」** CUDA&\#x27;s cudaMemcpy moves data between host memory and GPU memory, and pageable host memory is the default for ordinary allocations such as a PyTorch CPU tensor. Pageable transfers take a slower staging path than pinned \(page-locked\) memory, so host-to-device bandwidth can be far below the hardware&\#x27;s potential. The B300 is NVIDIA&\#x27;s Blackwell-generation GPU, and the reported 10.2 GB/s baseline for a 1 GB PyTorch copy illustrates that gap.

**「Why it matters」** For workloads that must use pageable host memory rather than pinned memory, this can cut CPU-to-GPU transfer time for large tensors by roughly 80%, directly reducing data-loading stalls in PyTorch-style pipelines. Engineers can try it by running their existing benchmark or application under \`cmt tune\`, while checking that the tuned transfer path preserves correctness for their workload.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Nvidia">Nvidia - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#CUDA`, `#GPU memory transfers`, `#PyTorch`, `#performance tuning`, `#open source`

---

<a id="item-tech-news-7"></a>
### [Report links Rubio and Anthropic to pressure campaign around Jensen Huang&\#x27;s exit](https://www.washingtonpost.com/technology/2026/11/13/behind-jensen-huangs-spy-scandal-shadow-war-trumps-ear-china/) ⭐️ 7.0/10

A Washington Post report says Nvidia founder Jensen Huang&\#x27;s departure followed a coordinated pressure campaign after he used his personal relationship with President Trump to loosen US chip-export restrictions on China and publicly called China hawks a disgrace and unpatriotic. According to the report, Senator Marco Rubio used CIA intelligence to write a hard-line memo to pressure the president. The report also describes suspicion—unconfirmed by reporters or Anthropic—that Anthropic executives supplied the initial tip that led New York Times reporters to Singapore company Megaspeed, connected to a woman linked to Huang. Anthropic had been lobbying the White House for strict chip-export controls, including firmware-level locks or tracking to stop unapproved open-source models, while Huang opposed tracking and backdoor features in chips. With Huang out of the way, House China committee leadership is pushing to add three strict provisions to the year-end defense bill: further limits on high-end AI chip exports, mandatory anti-smuggling tracking technology in chips, and restrictions on China&\#x27;s access to chipmaking equipment.

telegram · zaihuapd · Nov 15, 08:08

**「Background」** The dispute centers on US export controls for advanced AI chips to China, a policy area where Nvidia has pushed for broader sales while Anthropic has lobbied for tighter restrictions and hardware-level controls. The source says Huang had persuaded Trump to relax China chip-export rules and publicly criticized China hawks, while Anthropic favored firmware locks or tracking mechanisms to prevent unapproved use. The report also points to a New York Times podcast in which investigative reporters said an anonymous tech-industry contact first directed them toward Megaspeed, the Singapore company linked to the woman in the Huang affair; the reporters and Anthropic have not responded to the claim that Anthropic supplied the tip.

**「Concrete impact」** The immediate consequence is that opponents of loosened Nvidia chip sales to China now have a stronger political opening: the House Select Committee on China and allied lawmakers are pushing to attach three provisions to the year-end defense bill—tighter export limits on advanced AI chips, mandatory anti-smuggling tracking technology inside chips, and restrictions on China&\#x27;s access to chipmaking equipment. If enacted, these measures would directly affect Nvidia&\#x27;s China business and could force compliance with built-in tracking or firmware controls that Huang had opposed. For companies and developers, the practical concern is that US-China AI chip access may become more restricted and more instrumented, while the allegations against Anthropic remain unconfirmed and should not be treated as established fact.

**Tags**: `#AI policy`, `#semiconductors`, `#Nvidia`, `#Anthropic`, `#US-China tech relations`

---

## Financial News

<a id="item-finance-news-1"></a>
### [US, China and Russia leaders to hold first trilateral meeting at Shenzhen APEC summit](https://apnews.com/article/trump-xi-putin-summit-china-5fe92253ef38100bae913834a9b74d72) ⭐️ 9.0/10

China&\#x27;s Foreign Ministry says the leaders of the United States, China and Russia plan to hold their first dedicated trilateral meeting on Nov. 19 on the sidelines of the APEC summit in Shenzhen. The meeting is arranged outside APEC&\#x27;s formal agenda, and the announcement covers the planned meeting rather than any agreed outcomes.

telegram · zaihuapd · Nov 16, 01:38

**「Background」** APEC is an annual forum for regional economic cooperation, and leaders often use its sidelines for separate bilateral or ad hoc meetings that are not part of the official agenda. The planned Nov. 19 meeting in Shenzhen would be the first time the US, Chinese, and Russian leaders hold a dedicated three-way meeting, according to China&\#x27;s Foreign Ministry and media reports.

**「Why it matters」** A first three-way meeting among the US, China and Russia could shape expectations for global trade, security and diplomatic coordination, though no policy results have been announced yet.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bbc.com/zhongwen/articles/cwe85djzkkv5o/simp">APEC ... - BBC News 中 文</a></li>

</ul>
</details>

**Tags**: `#geopolitics`, `#US-China-Russia`, `#APEC`, `#diplomacy`, `#global-policy`

---

<a id="item-finance-news-2"></a>
### [Lutnick faces questions over Nvidia ties as his sons&\#x27; firm cut its Nvidia stake](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reports that Cantor Fitzgerald, now led by Commerce Secretary Howard Lutnick&\#x27;s sons, reported a 49% drop in its Nvidia shares, from 3.5 million at the end of 2024 to 1.78 million by March 2026, while continuing to do business with Nvidia. The report comes as Lutnick faces scrutiny over intelligence warnings about Nvidia CEO Jensen Huang and resistance to cracking down on a company suspected of smuggling Nvidia chips to China; no proof of wrongdoing has been reported.

rss · CNBC Finance · Nov 15, 19:58

**「Background」** Howard Lutnick left Wall Street to become commerce secretary in February 2025, while Cantor Fitzgerald, the firm he formerly ran and now led by his sons Brandon and Kyle, reported Nvidia as its second-largest stock position behind Strategy. The Commerce Department oversees the entity list, the U.S. restricted-party list used to curb exports such as suspected Nvidia chip smuggling to China, and President Trump authorized new restrictions on those companies on Nov. 5. The scrutiny follows Nvidia CEO Jensen Huang&\#x27;s resignation on Thursday and Axios reports that Lutnick received classified warnings about Huang and resisted a crackdown on Megaspeed.

**「Why it matters」** The episode could affect confidence in U.S. export-control decisions involving Nvidia and China, and puts Cantor Fitzgerald&\#x27;s Nvidia-related financing and trading relationships under closer ethical and regulatory scrutiny.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/15/bessent-nvidia-ceo-lutnick-megaspeed.html">Bessent calls for ‘dramatic shakeup’ at Nvidia , urges outside CEO</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#export controls`, `#government ethics`

---

<a id="item-finance-news-3"></a>
### [FT reports Jensen Huang discussing possible return as Nvidia CEO](https://www.ft.com/content/0f30a230-4d66-481b-a4fd-3a4ed0c45855) ⭐️ 7.0/10

The Financial Times reports that Jensen Huang is considering returning as Nvidia CEO and has discussed the idea with close allies, after resigning last Thursday over the disclosure of two extramarital affairs. The FT also reports that Nvidia&\#x27;s board has approached Arm CEO Rene Haas as a potential successor.

telegram · zaihuapd · Nov 16, 01:06

**「Background」** Jensen Huang had been Nvidia&\#x27;s founder-CEO before resigning last Thursday after reports of two extramarital affairs, one involving a woman suspected of being a Chinese spy, which raised concerns about US AI-chip export policy. The Financial Times separately reports that Nvidia&\#x27;s board has approached Arm CEO Rene Haas as a possible successor.

**「Why it matters」** Nvidia&\#x27;s leadership is central to the AI chip industry, so the reported board discussions over Huang&\#x27;s possible return or a successor such as Rene Haas could affect investor confidence and the company&\#x27;s strategic direction.

<details><summary>References</summary>
<ul>
<li><a href="https://www.ft.com/content/2a64f698-46dd-4178-a3f4-4c5f4c0a0926?syn-25a6b1a6=1">Arm boss Rene Haas approached in Nvidia CEO search</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#CEO succession`, `#corporate governance`, `#AI chips`, `#US-China policy`

---