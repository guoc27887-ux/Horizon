---
layout: default
title: "Horizon Summary: 2026-11-14 (EN)"
date: 2026-11-14
lang: en
---

> From 40 items, 16 important content pieces were selected

---

**Technology News**
1. [FAA orders nationwide ground stop for departing flights](#item-tech-news-1) ⭐️ 8.0/10
2. [Training a ~1T-Parameter MoE on 384 GH200 GPUs with TorchTitan](#item-tech-news-2) ⭐️ 8.0/10
3. [Python early contributor Tim Peters dies at 74](#item-tech-news-3) ⭐️ 8.0/10
4. [Haskell community proposal outlines technical vision for ecosystem](#item-tech-news-4) ⭐️ 7.0/10
5. [AI helps researchers decode Kurt Gödel&\#x27;s notebooks](#item-tech-news-5) ⭐️ 7.0/10
6. [ICML 2027 Adds Two-Stage Review and Author Reviewing Requirements](#item-tech-news-6) ⭐️ 7.0/10
7. [31K-parameter transformer predicts personal blood sugar](#item-tech-news-7) ⭐️ 7.0/10
8. [Frontier models near-perfect on custom materials-science research test](#item-tech-news-8) ⭐️ 7.0/10
9. [Shanghai finds serious flaws in SJTU gene-editing case after child&\#x27;s death](#item-tech-news-9) ⭐️ 7.0/10
10. [Microsoft Outlook, Teams, and Copilot outage lasts over 12 hours](#item-tech-news-10) ⭐️ 7.0/10
11. [DeepSeek opens bundled app-style APIs for search, files, speech, and chat demo](#item-tech-news-11) ⭐️ 7.0/10
12. [OpenAI launches ChatGPT Wallet for agentic payments with major card networks](#item-tech-news-12) ⭐️ 7.0/10

**Financial News**
1. [Jensen Huang affair raises stakes for U.S.-China tech relations](#item-finance-news-1) ⭐️ 8.0/10
2. [Lutnick faces questions as his sons&\#x27; firm cut Nvidia stake while keeping business ties](#item-finance-news-2) ⭐️ 7.0/10
3. [Chicago Fed&\#x27;s Goolsbee says Fed &\#x27;has work to do&\#x27; on inflation after hot PPI report](#item-finance-news-3) ⭐️ 7.0/10
4. [Moonshot AI restructures to prepare for Hong Kong IPO](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [FAA orders nationwide ground stop for departing flights](https://www.nbcnews.com/news/us-news/faa-orders-nationwide-ground-stop-departing-flights-reasons-safety-rcna609247) ⭐️ 8.0/10

The FAA ordered a nationwide ground stop for departing flights on November 13, 2026, citing safety reasons. Reporting cited by commenters pointed to an outage affecting a telecommunications network overseen by L3Harris Technologies that handles radio frequencies air-traffic controllers use to communicate with pilots; it was not immediately clear whether radar feeds were also affected. The New York Times later reported the ground stop had been lifted. The exact cause of the outage remained unclear in the available reporting.

hackernews · zulln · Nov 13, 21:05 · [Discussion](https://news.ycombinator.com/item?id=50489641)

**「Background」** The FAA&\#x27;s air-traffic system depends on a nationwide telecommunications network that carries the radio frequencies controllers use to talk with pilots, so a failure in that layer can force officials to halt departures until they can confirm aircraft can be safely separated. The FAA has used nationwide ground stops only rarely: the last comparable one was in January 2023, when a key FAA computer system malfunctioned, and before that after the September 11, 2001, attacks. In this event, reporting cited by commenters pointed to a telecommunications network overseen by L3Harris Technologies, while the FAA described the problem as a temporary telecommunications outage and said technicians were investigating.

**「Operational impact」** The stop grounded departing flights nationwide for roughly four hours before the FAA lifted it, leaving thousands of travelers facing delays and cancellations as carriers worked through the backlog. Travelers should check airline status before heading to airports, because recovery schedules may continue to shift after the formal stop ends.

**「Community discussion」** Commenters noted how sparse official information was, with one observing that LAX departures appeared halted since mid-morning and other major airports showing widespread delays. One commenter speculated about a connection to the FAA&\#x27;s newly announced nationwide rollout of its SMART AI air-traffic tool, while another found the timing suspicious given a separate Microsoft outage the day before; both remain unverified speculation rather than established causes.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_communication_outage">2026 FAA communication outage - Wikipedia</a></li>
<li><a href="https://www.theguardian.com/us-news/live/2026/nov/13/us-politics-latest-news-updates-democrats-republicans-donald-trump-van-hollen-chuck-schumer?page=with:block-6af789c78f080d8d1c27a4b6">US flight outage live updates: FAA grounds thousands... | The Guardian</a></li>
<li><a href="https://www.aljazeera.com/news/liveblog/2026/11/13/groundling-live">LIVE: FAA issues US ground stop , some international... | Al Jazeera</a></li>
<li><a href="https://www.cnbc.com/2026/11/13/faa-ground-stop.html">FAA lifts ground stop after four hours, but flight ... - CNBC</a></li>
<li><a href="https://www.techrepublic.com/article/news-faa-nationwide-ground-stop-flight-delays-2026/">FAA Grounds US Flights Nationwide, Citing ‘Extraordinary ...</a></li>

</ul>
</details>

**Tags**: `#FAA`, `#air-traffic-control`, `#infrastructure`, `#outage`, `#aviation`

---

<a id="item-tech-news-2"></a>
### [Training a ~1T-Parameter MoE on 384 GH200 GPUs with TorchTitan](https://www.reddit.com/r/MachineLearning/comments/1xvce5h/scaling_to_1t_moe_on_torchtitan_p/) ⭐️ 8.0/10

Engineers working with the TorchTitan and PyTorch maintainers report training a roughly 1-trillion-parameter mixture-of-experts model on 384 NVIDIA GH200 GPUs, the hardware inside the JUPITER supercomputer, reaching about 1,300 tokens per second per GPU. They describe a 14x throughput improvement over their starting point, where an 84-second training step had 68 seconds lost to network waiting on a cluster with about 25 GB/s of InfiniBand bandwidth per GPU. The setup used 384-way FSDP plus 4-way expert parallelism kept within a node, deliberately skipping pipeline parallelism to keep iteration fast. Key optimizations included full activation checkpointing, activation offload to Grace memory, the Muon optimizer, FlexShard expert sharding, GPU-side Newton-Schulz, cost-balanced attention packing, bf16 gradient all-to-all instead of fp32 reduce-scatter, FP8 expert all-gather, and a fix to the PyTorch caching allocator&\#x27;s per-stream memory pools.

reddit · r/MachineLearning · /u/f14-bertolotti · Nov 13, 16:28

**「Background」** TorchTitan is a PyTorch-native platform for large-scale training that uses FSDP2 as its default 1D parallelism, offering improved memory management and slight performance gains over FSDP1. The project is developed openly on GitHub, and in November 2025 AMD released an optimized fork of TorchTitan for AMD GPUs, reflecting its growing role as a shared foundation for distributed LLM training. This report builds on that ecosystem by pushing TorchTitan&\#x27;s FSDP- and expert-parallel stack to roughly one trillion parameters on GH200 hardware.

**「Practical impact for large-scale training」** The result shows that a publicly accessible, Hopper-generation system such as JUPITER can host roughly 1-trillion-parameter MoE training without root access, reaching about 1,300 tokens/s per GPU on 384 GH200 GPUs after a 14x optimization effort. For teams planning large-scale runs, the actionable lessons are concrete: prefer FSDP plus node-local expert parallelism when inter-node bandwidth is the bottleneck, use longer sequences and activation checkpointing to convert idle GPU time into useful compute, shard experts by whole expert so Muon/Newton-Schulz can run locally, keep fp32 accumulation locally while sending bf16 or FP8 over the wire, and watch for allocator fragmentation across CUDA streams that can fake an out-of-memory condition. Some changes, such as group-limited routing for perfectly even expert load, improved throughput but may affect training quality, so they need validation before adoption.

**「Community discussion」** No community comments are available for this item, so there is no discussion to summarize.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/pytorch/torchtitan">GitHub - pytorch / torchtitan : A PyTorch native platform for training...</a></li>
<li><a href="https://arxiv.org/pdf/2410.06511">TorchTitan : One-stop PyTorch native solution for production ready...</a></li>
<li><a href="https://www.eurohpc-ju.europa.eu/jupiter-officially-propels-europe-exascale-era-2025-11-17_en">JUPITER Officially Propels Europe into the Exascale Era</a></li>

</ul>
</details>

**Tags**: `#large language models`, `#mixture of experts`, `#distributed training`, `#PyTorch`, `#GPU performance`

---

<a id="item-tech-news-3"></a>
### [Python early contributor Tim Peters dies at 74](https://x.com/Itsfoss/status/2120957452937998716) ⭐️ 8.0/10

Tim Peters, an early contributor to Python, has died at age 74. Python creator Guido van Rossum announced his death. Peters was the second real user of Python, wrote the Timsort sorting algorithm, authored PEP 20 \(&quot;The Zen of Python&quot;\), and served on the Python Software Foundation board for 13 years.

telegram · zaihuapd · Nov 13, 09:55

**「Why Tim Peters mattered to Python」** Tim Peters was one of Python&\#x27;s earliest and most influential contributors: he wrote the Zen of Python \(PEP 20\), a set of design principles first posted to the Python mailing list in 1999, and created Timsort, the adaptive sorting algorithm used as Python&\#x27;s standard list-sort implementation. He also served on the Python Software Foundation board for 13 years and was described by Guido van Rossum as Python&\#x27;s second real user, making him a foundational figure in the language&\#x27;s early community and technical direction.

**「Impact on the Python community」** Peters&\#x27; death removes one of Python&\#x27;s most influential early technical voices, but his core work remains embedded in the language: Timsort is still the standard sorting algorithm behind Python&\#x27;s list.sort\(\) and sorted\(\), and PEP 20 remains accessible via import this. For developers and maintainers, the practical consequence is continuity rather than disruption—his algorithms and design principles continue to shape how Python code is written and executed, while the community reflects on the loss of a foundational contributor and former Python Software Foundation board member.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Zen_of_Python">Zen of Python - Wikipedia</a></li>
<li><a href="https://discuss.python.org/t/in-memoriam-tim-peters-1952-2026/110028">In Memoriam: Tim Peters 1952–2026 - Core Development...</a></li>
<li><a href="https://dev.to/romdevin/python-pioneer-and-timsort-creator-tim-peters-passes-away-at-74-36hk">Python Pioneer and Timsort Creator Tim Peters Passes Away at 74</a></li>
<li><a href="https://x.com/clcoding/status/2121103764103000486">Python Coding on X: &quot;The Python community has lost one of its ...</a></li>

</ul>
</details>

**Tags**: `#Python`, `#Tim Peters`, `#open source`, `#programming history`, `#Timsort`

---

<a id="item-tech-news-4"></a>
### [Haskell community proposal outlines technical vision for ecosystem](https://discourse.haskell.org/t/a-technical-vision-for-the-haskell-ecosystem/15078) ⭐️ 7.0/10

A community proposal titled “A technical vision for the Haskell ecosystem” was posted on the Haskell Discourse forum, laying out ideas for improving the language’s surrounding tooling and ecosystem. The discussion that followed focused on practical concerns such as debugging support, long-term API stability, and making Haskell usable across more application domains. The item is a proposal and community discussion rather than an announced release or shipped change, so its concrete effects depend on subsequent adoption and implementation.

hackernews · cosmic\_quanta · Nov 13, 14:43 · [Discussion](https://news.ycombinator.com/item?id=50484235)

**「Background」** The proposal comes from the technical leadership committee of the Haskell Foundation, which says it has been bootstrapped and is now fully operational after spending several weeks on its vision and strategy. One stated goal is to shorten GHC&\#x27;s automated check cycle from about six hours to two, though that is an aim rather than a completed optimization. The discussion reflects a longer-running concern in the Haskell community about making the language practical for everyday application development, not just research and compilers.

**「Impact」** For Haskell developers and teams evaluating the language, the proposal could shape priorities around tooling, debugging, and ecosystem stability. The discussion suggests that better live debugging and step-through interactivity are seen as underrated needs, and that broader cross-platform reach—desktop, mobile, and web—remains a key adoption concern compared with ecosystems like JavaScript, Rust, and the JVM. If the vision is adopted, it may influence where contributors and maintainers focus effort in the Haskell toolchain.

**「Community discussion」** Commenters debated why Haskell has not seen wider adoption: ecshafer argued that its terseness and safety features could suit AI-assisted development, while pmkary pointed to Simon Peyton Jones’s “Haskell is Useless” remark and wished Haskell were as universal as JavaScript, Rust, or C\#. Others added concrete experience: georgewsinger described live runtime debugging work in a Haskell VR compositor, time4tea suggested the JVM ecosystem already exemplifies some of the proposal’s goals, and carterschonwald highlighted high-performance Haskell CAD tooling as evidence of the language’s capabilities.

<details><summary>References</summary>
<ul>
<li><a href="https://discourse.haskell.org/t/a-technical-vision-for-the-haskell-ecosystem/15078">A technical vision for the Haskell ecosystem - Haskell Foundation...</a></li>
<li><a href="https://news.ycombinator.com/item?id=50484235">A technical vision for the Haskell ecosystem | Hacker News</a></li>
<li><a href="https://dzen.ru/b/avdWQF0woA1Z8MqS">Haskell Foundation запустила техкомитет: цель — ускорить... | Дзен</a></li>
<li><a href="https://well-typed.com/blog/2026/03/haskell-ecosystem-report-q1-2026/">Haskell ecosystem activities report: December 2025–February 2026</a></li>

</ul>
</details>

**Tags**: `#Haskell`, `#programming languages`, `#developer tooling`, `#open source`, `#ecosystem`

---

<a id="item-tech-news-5"></a>
### [AI helps researchers decode Kurt Gödel&\#x27;s notebooks](https://www.theguardian.com/science/2026/nov/13/kurt-godel-notebooks-ai-helps-unlock-hidden-discoveries-man-who-transformed-maths) ⭐️ 7.0/10

Researchers are reportedly using AI to help unlock Kurt Gödel&\#x27;s notebooks, which are said to contain hundreds of proved theorems. The work concerns Gödel&\#x27;s handwritten notes, including material in Gabelsberger shorthand, and is being framed as a way to reveal previously hidden mathematical discoveries. The report is based on a Guardian account rather than a published, verified catalogue of the theorems, so the scale and significance of what is actually recovered remain uncertain.

hackernews · bookofjoe · Nov 13, 17:30 · [Discussion](https://news.ycombinator.com/item?id=50486748)

**「Why Gödel&\#x27;s notebooks matter」** Kurt Gödel, the Austrian logician whose two incompleteness theorems published in 1931 transformed mathematics, published only a few papers after his seminal results of the 1930s. His private notebooks were written largely in Gabelsberger shorthand, a nearly obsolete German stenographic system, which has made them difficult to read and left their contents largely inaccessible for decades. A research project led by Jan von Plato is now using AI to transcribe and analyze these pages, which are believed to contain hundreds of previously unpublished proved theorems.

**「What it could mean for historians and mathematicians」** If the notebooks can be reliably transcribed, historians and mathematicians may gain access to a large body of Gödel&\#x27;s private mathematical work, including proved results he never published. The immediate practical effect is likely to be improved access to and study of the manuscripts, but claims about hundreds of theorems should be treated as preliminary until the transcriptions and mathematical content are independently reviewed.

**「Community reaction」** Commenters were skeptical that the notebooks will contain major new results: one argued that Gödel was an exceptionally harsh self-reviewer who generally published only “bulletproof” work, so sharp insights are plausible but conclusive new theorems are unlikely. Another questioned the difficulty of reading Gabelsberger shorthand, noting that it was an older German stenography system largely replaced by Deutsche Einheitskurzschrift, while others expressed curiosity about the specific logical themes Gödel pursued.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theguardian.com/science/2026/nov/13/kurt-godel-notebooks-ai-helps-unlock-hidden-discoveries-man-who-transformed-maths">‘Ahead of his time’: AI helps unlock discoveries hidden... | The Guardian</a></li>
<li><a href="https://o-server.main.jp/hacker-news/en/articles/2026/11/14/ai-project-decodes-kurt-g-del-s-private-notebooks-using-gabelsber-50486748.html">AI Project Decodes Kurt Gödel&#x27;s Private Notebooks Using ...</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#mathematics`, `#history of science`, `#Kurt Gödel`, `#handwriting recognition`

---

<a id="item-tech-news-6"></a>
### [ICML 2027 Adds Two-Stage Review and Author Reviewing Requirements](https://www.reddit.com/r/MachineLearning/comments/1xvkxbj/icml_2027_changes_d/) ⭐️ 7.0/10

ICML 2027’s call for papers introduces a two-stage review process in which an area chair decides whether a paper advances to full review, and any proposed first-stage rejection must be confirmed by a senior area chair; authors receive a short justification by Feb. 23. The policy also imposes stricter participation limits: no one may appear on more than 20 submissions, every paper must name a reciprocal reviewer from its author list, reciprocal reviewers may serve on at most six papers, and authors with three or more submissions must join the program committee. Noncompliant papers may be desk rejected. A further rule limits each author to at most one paper with no eligible reciprocal reviewer among its authors, targeting papers whose coauthors—such as undergraduates, interns, or people outside the field—cannot review.

reddit · r/MachineLearning · /u/Gravitist · Nov 13, 21:53

**「Why ICML is changing its review process」** ICML has been facing a growing imbalance between paper submissions and the number of qualified reviewers, which has made reviewer load a persistent problem. ICML 2027&\#x27;s new submission quotas and strengthened reciprocal-reviewing requirement follow a similar approach adopted by ICLR 2027, making this part of a broader move among major ML conferences to tie authorship privileges to reviewing duty.

**「Impact on ICML authors and reviewers」** ICML 2027 authors will need to plan submissions around hard authorship and reviewing constraints: no one may appear on more than 20 submissions, every paper must name a reciprocal reviewer from its author list, authors with three or more submissions must serve on the program committee, and each author can have at most one paper with no eligible reciprocal reviewer. Research groups that rely on coauthors who cannot review—such as undergraduates, interns, or people outside the field—may need to restructure author lists or accept that only one such paper per author is possible. Noncompliant papers risk desk rejection, so authors should check the official ICML 2027 Call for Papers and reciprocal-reviewing policy before submitting.

**「Community reaction」** The submitting Redditor called the package a reasonable fix for years of excessive reviewer load, especially tying authorship volume to reviewing duty, but worried that a quick first-stage area-chair read could miss a good paper even with the senior area chair check. They asked whether the changes will solve the problem or merely push it elsewhere; no other comments were available in the supplied material.

<details><summary>References</summary>
<ul>
<li><a href="https://icml.cc/Conferences/2027/ReciprocalReviewingAndSubmissionQuotas">2027 Reciprocal Reviewing And Submission Quotas - icml.cc</a></li>
<li><a href="https://icml.cc/Conferences/2027/ReciprocalReviewingAndSubmissionQuotas">2027 Reciprocal Reviewing And Submission Quotas - icml.cc</a></li>
<li><a href="https://icml.cc/Conferences/2027/ProgramCommittee">ICML 2027 Program Committee</a></li>

</ul>
</details>

**Tags**: `#machine learning`, `#ICML`, `#peer review`, `#academic publishing`, `#conference policy`

---

<a id="item-tech-news-7"></a>
### [31K-parameter transformer predicts personal blood sugar](https://www.reddit.com/r/MachineLearning/comments/1xvja5n/i_have_trained_a_model_to_predict_my_blood_sugar_p/) ⭐️ 7.0/10

A Reddit user reports training a custom 31,253-parameter encoder-only transformer to predict their own blood sugar up to two hours ahead from continuous glucose monitor \(CGM\) traces plus insulin and carbohydrate inputs. The model was first pretrained on about 19,200 CGM-years of synthetic data—1 million simulated type 1 diabetics at 7 days each—then personalized with LoRA on 80 days of the author&\#x27;s CGM data and tested on 35 days. It uses DILATE/MSE and pinball losses in Kovatchev risk space with learned Kendall-Gal weights, supports variable 3.5–7.0 day context windows, infills missing traces, performs backcasts, and can infer time-of-day from glucose patterns in ≥48-hour contexts. The author says it is competitive with published models but still worse than they are at predicting hypoglycemia in the next ~30 minutes; code is available at github.com/0xdeadf1sh/T1DMAI. These are self-reported results from a single-user experiment without published benchmarks or external validation.

reddit · r/MachineLearning · /u/0xdeadf1sh · Nov 13, 20:48

**「Background」** Continuous glucose monitors \(CGMs\) produce the time-stamped blood-sugar traces used for forecasting, while insulin doses and carbohydrate estimates act as the interventions whose delayed effects a model must learn. The same developer has also published T1DMDROID, a personal Android app that passively reads AiDEX X / LinX CGM data and runs forecasting on-device, and a follow-up post describes a version trained only on synthetic data that was designed for counterfactual reasoning about future insulin and carbohydrate inputs.

**「Why it matters」** For people experimenting with diabetes-related machine learning, the project shows that a very small transformer plus large-scale synthetic pretraining and LoRA personalization can run on a phone and model individual glucose responses to insulin and carbohydrates. Its practical value depends on validation: the author has no downstream benchmark for the simulator&\#x27;s counterfactual reasoning, carbohydrate inputs are estimates, and short-horizon hypoglycemia prediction remains unreliable, so it should be treated as a research prototype and decision-support aid rather than a replacement for clinical judgment or approved medical devices.

<details><summary>References</summary>
<ul>
<li><a href="https://reporank.net/en/repo/0xdeadf1sh-t1dmdroid.html">T 1 DMDROID: Passive Android CGM Reader - Open Source Project...</a></li>
<li><a href="https://github.com/0xdeadf1sh/T1DMDROID">GitHub - 0 xdeadf 1 sh / T 1 DMDROID: A personal Android app for Type...</a></li>
<li><a href="https://theaterfi.re/post/3733950">I have trained a model to predict my blood sugar (Part 2) [P] | TheaterFire</a></li>

</ul>
</details>

**Tags**: `#machine learning`, `#transformers`, `#time series`, `#healthcare AI`, `#synthetic data`

---

<a id="item-tech-news-8"></a>
### [Frontier models near-perfect on custom materials-science research test](https://www.reddit.com/r/MachineLearning/comments/1xvgf6h/four_frontier_models_scored_978100_on_a_7part/) ⭐️ 7.0/10

A graphene and 2D-materials researcher reported that four frontier AI models scored 97.8–100 on a custom seven-part benchmark built to mimic everyday research-group work. The test covered cleaning a synthetic tensile dataset against a lab SOP, writing a CIF density function checked against hidden structures, physics calculations, manuscript critique with planted errors and decoys, calibration questions with false premises and fabricated papers, experimental design, and constrained abstract writing. Using Gemini 4 Carbon, Gemini 4 Hydrogen, Claude Opus 5.5, and Claude Fable 5.2 at “High” reasoning effort, with three fresh runs each, the mean scores were 100.0, 99.7, 99.3, and 98.5, with each run taking 7–24 minutes. The author cautions that the study has one examiner, only three runs per model, and that the test was designed with Claude Opus 5.5’s assistance; the full write-up is on the author’s Substack and the claims have not been independently verified.

reddit · r/MachineLearning · /u/v\_aravind · Nov 13, 18:58

**「Why this benchmark result matters」** The author’s benchmark is a bounded, code-scored test of everyday materials-science tasks, so near-perfect scores across four frontier models suggest that this kind of structured expert work is becoming saturated. The result echoes FrontierScience, a benchmark for expert-level scientific reasoning introduced because many existing science benchmarks rely on multiple-choice knowledge or already published information. The more open question raised by the author is how to evaluate longer, less structured agentic research work, where trajectory and recovery from mistakes may matter as much as the final answer.

**「Why it matters for evaluation」** The author’s conclusion is that bounded, procedure-following research tasks appear saturated for current frontier models, so the more useful evaluation target is long-horizon, open-ended work. They are building a simulated-lab campaign in which an agent receives a budget, instruments, a target spec, planted surprises, and a signed action log over 2–6 hour runs, and they ask how to score trajectory qualities such as recovery from a wrong early assumption separately from final output. A PhD student’s non-measured estimate put the test at 11–16 hours of focused human work with an expected score of 75–90.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2601.21165">[2601.21165] FrontierScience: Evaluating AI&#x27;s Ability to ... Evaluating AI’s ability to perform scientific research tasks FrontierScience Research Leaderboard — November 2026 FrontierScience Research Leaderboard FrontierScience Bench: Evaluating AI Research Capabilities in ... GitHub - medicalsphere/FrontierScience: Implementation of ...</a></li>

</ul>
</details>

**Tags**: `#AI evaluation`, `#benchmarking`, `#materials science`, `#long-horizon agents`, `#frontier models`

---

<a id="item-tech-news-9"></a>
### [Shanghai finds serious flaws in SJTU gene-editing case after child&\#x27;s death](https://mp.weixin.qq.com/s/p0iC3tcI1yr10EBl2NjUvg) ⭐️ 7.0/10

Shanghai authorities have concluded an investigation into a customized gene-editing therapy case at Shanghai Jiao Tong University School of Medicine. The child patient had Snijders Blok-Campeau syndrome; the family contacted a team led by Qiu in 2023, received the customized therapy by injection in March 2025, and died of thrombotic microangiopathy afterward. A paper on the case was published in Nature in February 2026. The investigation found deficiencies in preclinical research, ethics review, and informed consent, and determined that some personnel accepted about 1.06 million yuan from the family. Qiu and Yang were dismissed and disqualified for five years, while involved institutions face rectification requirements and administrative penalties. The findings were reported by Xinhua.

telegram · zaihuapd · Nov 13, 09:24

**「Background」** The case centers on a customized gene-editing therapy for a child with Snijders Blok-Campeau syndrome, a rare developmental disorder. The family contacted the team led by Qiu in 2023, the therapy was injected in March 2025, and the child died of thrombotic microangiopathy; the research was later published in Nature in February 2026. Shanghai Jiao Tong University School of Medicine said on July 26, 2026 that it had formed a special working group to investigate the related paper and the clinical study conducted at its affiliated Xinhua Hospital.

**「Impact」** The sanctions directly remove Qiu and Yang from research and clinical work for five years and impose administrative penalties and required rectification on the involved institutions, signaling that Chinese regulators will treat defective preclinical validation, ethics review, and informed consent in customized gene-editing therapy as grounds for career-ending and institutional discipline. Teams developing personalized gene-editing treatments face a concrete compliance bar: documented preclinical safety data, independent ethics approval, and verifiable informed consent before any patient dosing, especially for single-patient “n-of-1” therapies. The case also shows that payments from patient families to researchers can turn an experimental treatment into a financial-misconduct matter, so institutions may need explicit controls on investigator compensation and family payments in compassionate or investigator-initiated programs.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nbd.com.cn/articles/2026-07-27/4515558.html">nbd.com.cn/articles/2026-07-27/4515558.html</a></li>
<li><a href="https://www.straitstimes.com/asia/east-asia/china-fires-researchers-after-child-dies-in-gene-editing-trial">China fires researchers after child dies in gene - editing trial</a></li>
<li><a href="https://www.chinadaily.com.cn/a/202608/06/WS6a73dfe6a310986e2b46935d.html">Death of girl during gene - editing clinical trial ... - Chinadaily.com.cn</a></li>

</ul>
</details>

**Tags**: `#gene editing`, `#bioethics`, `#clinical trials`, `#regulation`, `#biotechnology`

---

<a id="item-tech-news-10"></a>
### [Microsoft Outlook, Teams, and Copilot outage lasts over 12 hours](https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/) ⭐️ 7.0/10

Microsoft&\#x27;s Outlook, Teams, and Copilot services remained down on November 13 for more than 12 hours, disrupting communications for businesses and governments worldwide. Microsoft attributed the outage to server issues, said it found no evidence of malicious activity, and reported that it had expanded remediation and was seeing signs of recovery. The disruption affected government agencies in Australia, Japan, and the United States, delayed Euronext email operations, and led at least one Taiwanese financial institution to confirm trades by fax. Reuters reported that this was the second Microsoft 365 outage of the year.

telegram · zaihuapd · Nov 13, 12:21

**「Background」** Microsoft 365 is a cloud-hosted productivity suite whose tightly coupled services mean an infrastructure fault can affect email, chat, and AI assistance together. The source notes this was the second Microsoft 365 service disruption of 2026, following an earlier outage that also drew attention to the platform&\#x27;s enterprise reliability.

**「Operational impact」** The outage affected users in more than 70 countries, disrupting email, messaging, and Copilot access for businesses and government agencies. Some government bodies in Australia, Japan, and the United States were affected, Euronext reported email disruption, and a Taiwanese financial institution reportedly used fax to confirm transactions. Organizations relying on Microsoft 365 should treat extended cloud-service outages as a continuity risk and review fallback communication channels. Microsoft said the cause was a server issue with no sign of malicious activity and reported recovery progress after more than 12 hours.

<details><summary>References</summary>
<ul>
<li><a href="https://www.reuters.com/technology/microsoft-365-outlook-down-thousands-us-users-downdetector-shows-2026-11-12/">Microsoft Outlook, Teams outage eases after over a day ...</a></li>
<li><a href="https://www.outlookindia.com/international/microsoft-outage-november-12-2026-outlook-teams-copilot-microsoft-365-down-downdetector-reports-global-service-disruption">Microsoft Outage: Outlook, Teams And Copilot Disrupted ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/2026_Microsoft_outage">2026 Microsoft outage - Wikipedia</a></li>
<li><a href="https://cyprus-mail.com/2026/11/13/global-microsoft-outage-stretches-into-second-day">Global Microsoft outage disrupts Outlook and Teams</a></li>
<li><a href="https://www.breitbart.com/tech/2026/11/13/microsofts-email-meltdown-extends-into-second-day-company-reports-progress-towards-recovery/">Microsoft &#x27;s Email Meltdown Extends into Second Day, Company...</a></li>

</ul>
</details>

**Tags**: `#Microsoft 365`, `#Outage`, `#Cloud Services`, `#Enterprise Software`, `#Reliability`

---

<a id="item-tech-news-11"></a>
### [DeepSeek opens bundled app-style APIs for search, files, speech, and chat demo](https://mp.weixin.qq.com/s/78KBHc4-4N5b2vfL9SkutQ) ⭐️ 7.0/10

DeepSeek announced that its application “family bucket” capabilities are now available through APIs. Developers can enable corresponding parameters in the existing API to obtain conversation abilities including deep-thinking search, file input, link reading, and speech, with the server automatically handling tool calls and context assembly. The V4.1-Flash model supports these features across three API endpoints, while Search, Fetch, OCR, ASR, and TTS can also be called individually. DeepSeek also open-sourced a front-end chat demo, deepseek-ai/chat-demo, which can import historical conversations and lets users run a local deployment resembling the DeepSeek web app; the demo is available at deepseek-ai.github.io/chat-demo. The announcement is brief and does not provide benchmarks, pricing, rate limits, or detailed implementation specifics.

telegram · zaihuapd · Nov 13, 14:27

**「Background」** DeepSeek previously offered its web app features—deep-thinking search, file input, link reading, and voice—mainly through its own chat interface, while its public API exposed model inference rather than those bundled application capabilities. The new release moves those features behind API parameters and standalone endpoints \(Search, Fetch, OCR, ASR, TTS\) on the V4.1-Flash model, with server-side tool calling and context assembly, plus an open-source chat-demo frontend for local deployment.

**「Impact for developers」** Developers can now add DeepSeek&\#x27;s app-style capabilities to existing integrations by enabling parameters on the V4.1-Flash API, rather than building separate search, file, OCR, ASR, and TTS pipelines; Search, Fetch, OCR, ASR, and TTS can also be called individually. Because tool calls and context assembly happen server-side, teams should account for provider-managed orchestration and Flash pricing when migrating workflows. The open-source chat-demo also lets developers self-host a web front end that imports historical conversations.

<details><summary>References</summary>
<ul>
<li><a href="https://extrapolator.ai/2026/11/13/deepseek-flash-api-adds-web-search-file-parsing-and-ocr-tools/">DeepSeek Flash API adds web search, file parsing, and OCR ...</a></li>
<li><a href="https://explainx.ai/blog/deepseek-full-suite-application-apis-web-search-file-url-asr-tts-pricing-2026">DeepSeek App APIs: Search, Files, ASR, TTS From $0.058 ...</a></li>

</ul>
</details>

**Tags**: `#DeepSeek`, `#API`, `#AI Agents`, `#Multimodal AI`, `#Open Source`

---

<a id="item-tech-news-12"></a>
### [OpenAI launches ChatGPT Wallet for agentic payments with major card networks](https://openai.com/index/introducing-chatgpt-wallet/) ⭐️ 7.0/10

OpenAI announced ChatGPT Wallet, a payment feature that lets ChatGPT agents make purchases without handling the user&\#x27;s real card number. It is built with American Express, Mastercard, and Visa, and each purchase requires security verification. Starting today, it is available in the U.S. through dots to ChatGPT Pro subscribers aged 18 and over, and it requires a U.S.-issued card. Users review the item and amount for each purchase, confirm with Face ID or fingerprint, and the payment network issues a token that substitutes for the real card number.

telegram · zaihuapd · Nov 13, 15:43

**「Background」** ChatGPT Wallet is OpenAI&\#x27;s entry into agentic payments, a model in which an AI assistant can complete purchases on a user&\#x27;s behalf without directly handling the underlying card credentials. The launch builds on the existing ChatGPT Pro subscription tier and OpenAI&\#x27;s dots agent framework, and relies on established payment-network tokenization: American Express, Mastercard, and Visa issue a payment token in place of the real card number, while each purchase is approved separately with biometric verification such as Face ID or Touch ID. OpenAI&\#x27;s help documentation notes that Wallet requires a set-up dot, is not available in Chat, Work, or standalone Codex threads, and initially supports eligible US-issued cards for US Pro users.

**「Impact」** For U.S. ChatGPT Pro subscribers, ChatGPT Wallet enables AI agents to complete purchases through existing card networks without exposing the real card number, using per-purchase network tokens and biometric confirmation. Users should expect to review each item and amount before approving, and eligibility currently depends on a U.S.-issued card and the dots rollout. The agentic model also shifts some risk to product selection: because the agent may navigate merchant sites and choose items before asking permission, users may need to watch for wrong quantities, unintended substitutions, or unwanted variants.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/introducing-chatgpt-wallet/">Introducing ChatGPT Wallet - OpenAI</a></li>
<li><a href="https://tech.yahoo.com/ai/chatgpt/articles/openai-introduces-chatgpt-wallet-visa-162102250.html">OpenAI Introduces ChatGPT Wallet With Visa, Mastercard, Amex ...</a></li>
<li><a href="https://help.openai.com/en/articles/20001654-making-purchases-with-chatgpt-wallet">Making purchases with ChatGPT Wallet | OpenAI Help Center</a></li>
<li><a href="https://www.explainx.ai/blog/chatgpt-wallet-dots-agent-payments-pro-us-visa-mastercard-amex-2026">ChatGPT Wallet: Agents Pay With Tokens, Not Your Card ...</a></li>
<li><a href="https://tech.yahoo.com/ai/chatgpt/articles/openai-launches-chatgpt-wallet-ai-190219313.html">OpenAI Launches ChatGPT Wallet for AI Agent Payments</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#ChatGPT`, `#payments`, `#AI agents`, `#fintech`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Jensen Huang affair raises stakes for U.S.-China tech relations](https://www.cnbc.com/2026/11/13/jensen-huang-nvidia-us-china-relations.html) ⭐️ 8.0/10

Congressional scrutiny of former Nvidia CEO Jensen Huang&\#x27;s affair with an alleged Chinese spy is intensifying U.S.-China tensions, with Huang agreeing to testify before Congress by Nov. 26. Analysts cited by CNBC predict a good chance Congress will tighten semiconductor export controls before the end of this year, despite a fragile trade truce ahead of a planned Trump-Xi meeting in Shenzhen from Nov. 18-19.

rss · CNBC Finance · Nov 13, 02:56

**「Background」** The U.S. began restricting Nvidia&\#x27;s advanced chip sales to China in 2022, and the Trump administration eased many Biden-era restrictions in 2025. Huang&\#x27;s resignation and agreed congressional testimony come as Washington and Beijing prepare for a planned Trump-Xi meeting at the APEC summit in Shenzhen on Nov. 18-19, with a fragile trade truce still in place.

**「Impact」** U.S. semiconductor export rules affecting Nvidia and China could tighten, while Beijing may respond by restricting rare earths or chipmaking materials, deepening technology decoupling between the two countries.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theguardian.com/us-news/2026/nov/13/trump-nvidia-stock-jensen-huang-us-china">Trump bought Nvidia stock as he helped chipmaker... | The Guardian</a></li>
<li><a href="https://ru.wikipedia.org/wiki/%D0%A1%D0%B0%D0%BC%D0%BC%D0%B8%D1%82_%D0%90%D0%A2%D0%AD%D0%A1_2026">Саммит АТЭС 2026 — Википедия</a></li>

</ul>
</details>

**Tags**: `#US-China relations`, `#Nvidia`, `#export controls`, `#semiconductors`, `#geopolitics`

---

<a id="item-finance-news-2"></a>
### [Lutnick faces questions as his sons&\#x27; firm cut Nvidia stake while keeping business ties](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reports that Cantor Fitzgerald, now led by Commerce Secretary Howard Lutnick&\#x27;s sons, reported a 49% drop in its Nvidia shares, from 3.5 million at the end of 2024 to 1.78 million by March 2026, while continuing to arrange financing for Nvidia partners and maintaining a $350 price target. The report follows Axios reporting that Lutnick resisted a crackdown on a Singapore company suspected of smuggling Nvidia AI chips to China; there is no evidence of wrongdoing, and Cantor says the filings reflect client-related swap positions rather than large proprietary bets.

rss · CNBC Finance · Nov 13, 23:42

**「Background」** Howard Lutnick led Cantor Fitzgerald before becoming commerce secretary in February 2025, and the firm now is run by his sons, Brandon and Kyle. The Commerce Department oversees the &quot;entity list&quot; of restricted companies, the tool used to curb suspected smuggling of Nvidia&\#x27;s advanced AI chips to China.

**「Why it matters」** The scrutiny touches investors in Nvidia and Cantor Fitzgerald and companies seeking U.S. export licenses, because it raises questions about whether policy decisions on China chip restrictions could be influenced by the commerce secretary&\#x27;s family firm&\#x27;s financial and business relationship with Nvidia.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/12/us/politics/lutnick-nvidia-commerce-china-chips.html">Howard Lutnick Took Softer Line on Nvidia as Calls for Tougher...</a></li>
<li><a href="https://www.cbsnews.com/news/lutnick-nvidia-ai-chips-china/">Lutnick should have prevented the diversion of sensitive Nvidia AI...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#export controls`, `#government ethics`

---

<a id="item-finance-news-3"></a>
### [Chicago Fed&\#x27;s Goolsbee says Fed &\#x27;has work to do&\#x27; on inflation after hot PPI report](https://www.cnbc.com/2026/11/13/chicago-feds-goolsbee-says-central-bank-has-definitely-got-work-to-do-on-inflation.html) ⭐️ 7.0/10

Chicago Fed President Austan Goolsbee said the Federal Reserve &quot;has definitely got work to do&quot; to restore its inflation-fighting credibility after October&\#x27;s producer price index rose 0.3% for the month and 6.5% from a year earlier, the largest annual gain since November 2022. Markets are fully pricing a quarter-point rate increase at the Fed&\#x27;s Dec. 8-9 meeting, with a better-than-10% chance of a half-point move, according to CME Group&\#x27;s FedWatch gauge.

rss · CNBC Finance · Nov 13, 14:22

**「Background」** The producer price index, a proxy for wholesale prices, rose 0.3% in October, slightly less than the 0.4% forecast, but was up 6.5% from a year earlier—the largest annual gain since November 2022. The Fed aims for 2% inflation, and Goolsbee said prices have stayed above that goal for almost six years with recent progress stalling.

**「Why it matters」** If markets are right, the Fed could raise borrowing costs in December, affecting loans, mortgages, and other credit for households and businesses while policymakers try to pull inflation back toward its 2% target.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/13/ppi-inflation-report-october-2026.html">PPI inflation report October 2026</a></li>
<li><a href="https://starman.fund/october-ppi-report-results/">October PPI Report: 0.3% Monthly, 6 . 5 % Annual , Highest Since 2022</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#inflation`, `#monetary policy`, `#producer price index`, `#interest rates`

---

<a id="item-finance-news-4"></a>
### [Moonshot AI restructures to prepare for Hong Kong IPO](https://www.wsj.com/tech/chinas-moonshot-ai-restructures-to-pave-way-for-ipo-49f09abb) ⭐️ 7.0/10

Chinese AI startup Moonshot AI is restructuring its corporate structure to prepare for a planned Hong Kong IPO, according to The Wall Street Journal and people familiar with the matter. Its Cayman Islands holding company will be deactivated, with shares held by early dollar investors transferred to the company&\#x27;s main operating entity in China.

telegram · zaihuapd · Nov 13, 11:29

**「Background」** Moonshot AI, the developer of the Kimi AI assistant, mainly operates in China but was incorporated through a Cayman Islands holding company, a common structure for startups that raise dollars from foreign investors. The restructuring would deactivate that offshore vehicle and move early investors&\#x27; shares into the mainland Chinese operating entity, a step the company is taking to prepare for a planned Hong Kong IPO.

**「Why it matters」** The restructuring could open a path for public-market investors to gain exposure to one of China&\#x27;s prominent AI startups, though the IPO remains planned rather than completed.

<details><summary>References</summary>
<ul>
<li><a href="https://www.wsj.com/tech/chinas-moonshot-ai-restructures-to-pave-way-for-ipo-49f09abb">China’s Moonshot AI Restructures to Pave Way for IPO</a></li>
<li><a href="https://aiweekly.co/alerts/moonshot-ai-unwinds-cayman-vehicle-for-50b-hong-kong-ipo">Moonshot AI Unwinds Cayman Vehicle for $50B Hong Kong IPO</a></li>
<li><a href="https://cn.wsj.com/articles/%E4%B8%AD%E5%9B%BDai%E5%85%AC%E5%8F%B8%E6%9C%88%E4%B9%8B%E6%9A%97%E9%9D%A2%E5%8D%B3%E5%B0%86%E5%AE%8C%E6%88%90%E6%9E%B6%E6%9E%84%E9%87%8D%E7%BB%84-%E4%B8%BAipo%E9%93%BA%E8%B7%AF-718a1b42">中国AI公司月之暗面即将完成架构重组，为IPO铺路 - WSJ</a></li>

</ul>
</details>

**Tags**: `#Moonshot AI`, `#Hong Kong IPO`, `#corporate restructuring`, `#China AI`, `#capital markets`

---