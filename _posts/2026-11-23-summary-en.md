---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 28 items, 4 important content pieces were selected

---

**Technology News**
1. [OpenAI Links Language-Model Perplexity to Intelligence](#item-tech-news-1) ⭐️ 8.0/10
2. [O&\#x27;Reilly Essay Asks What Silicon Valley Should Optimize For](#item-tech-news-2) ⭐️ 7.0/10

**Technology Blog**
1. [When in Doubt, Flail About](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [US tech stocks plunge; Asian markets roll out stabilization measures](#item-finance-news-1) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenAI Links Language-Model Perplexity to Intelligence](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 8.0/10

OpenAI published an article examining how language-model perplexity relates to intelligence, using prediction loss as a lens for model capability. The piece prompted active technical discussion about whether perplexity can serve as a simple, meaningful benchmark alongside more complex evaluations. Commenters highlighted that lower perplexity generally means better next-token prediction, and noted reported examples such as GPT-5 apparently having higher perplexity than GPT-4.5. Microsoft’s Mustafa Suleyman also publicly shared that MAI-2 Base was evaluated on OpenAI’s held-out set with a log-perplexity of 0.819.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「What perplexity measures」** Perplexity is a language-model evaluation metric derived from next-token prediction loss: lower values mean the model is less “surprised” by held-out text, with 1 as the best case and vocabulary size as the worst case. It is distinct from the similarly named AI search company Perplexity, and the OpenAI piece uses it to connect pre-training prediction accuracy to broader model capability. The discussion is notable because reinforcement-learning and reasoning-focused models have shifted attention toward task benchmarks, while this article argues prediction loss remains a meaningful capability signal.

**「Potential shift toward perplexity as a shared capability benchmark」** For AI practitioners, the article could encourage wider use of pre-training perplexity or log-loss on a common held-out set as a simple, comparable measure of model capability, alongside task-specific benchmarks. The discussion suggests this matters because evaluation suites have become increasingly complex, and a prediction-loss metric is easier to reason about. A concrete example from the supplied discussion is Microsoft reporting MAI-2 Base on OpenAI&\#x27;s evaluation set with a log-perplexity of 0.819, attributed to Mustafa Suleyman. However, the source content is unavailable, so the exact scope of OpenAI&\#x27;s claims and any recommended actions cannot be verified from the supplied material.

**「Community discussion」** On Hacker News, hazrmard explained that perplexity measures a model’s surprise when predicting the next token, ranging from 1 in the best case to vocabulary size in the worst case. jrflo said the clear trend was surprising given the increased use of reinforcement learning, and d\_burfoot argued that prediction or compression rate naturally captures a model’s ability to extract world models from raw data.

<details><summary>References</summary>
<ul>
<li>Perplexity AI, better than Google and ChatGPT. What is it and how to use it? | by Thomas Latterner | Medium</li>
<li><a href="https://openai.com/">OpenAI | Research &amp; Deployment</a></li>

</ul>
</details>

**Tags**: `#artificial intelligence`, `#language models`, `#machine learning`, `#evaluation metrics`, `#OpenAI`

---

<a id="item-tech-news-2"></a>
### [O&\#x27;Reilly Essay Asks What Silicon Valley Should Optimize For](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

O&\#x27;Reilly published an essay examining how Silicon Valley&\#x27;s technology industry has changed and arguing that technology and market mechanisms should be redesigned around human flourishing rather than profit alone. The essay frames mechanism design as &quot;reverse game theory&quot;: instead of only analyzing the rules of the current economic game, it asks what game society ought to be playing. The piece is reflective commentary rather than a product release, technical breakthrough, or industry announcement.

hackernews · greenyouse · Nov 22, 19:20 · [Discussion](https://news.ycombinator.com/item?id=50602947)

**「Background」** The essay builds on Tim O&\#x27;Reilly&\#x27;s Oct. 16, 2026 Johns Hopkins lecture, which traces Silicon Valley&\#x27;s shift from customer-centered value creation toward extraction driven by shareholder capitalism, monopoly ambitions, and hype. Its central concept is mechanism design, described as reverse game theory: rather than accepting the rules of the current market, designers should ask what game society ought to be playing and align technology with human flourishing.

**「Why it matters」** The essay&\#x27;s practical implication is a challenge to founders, investors, and policymakers to treat incentive structures—such as shareholder-value maximization and venture funding dynamics—as designable systems rather than natural forces. It does not announce a specific policy, product, or measurable outcome, so its immediate effect is to contribute an argument to ongoing debate about technology&\#x27;s societal goals.

**「Community response」** Commenters largely engaged with the essay&\#x27;s premise rather than disputing the article itself. Animats argued that the market is a human-built machine whose mechanism designers should be held accountable, while michalsustr highlighted the essay&\#x27;s closing call to optimize collectively for human flourishing. CoolestBeans added a more material explanation, contending that the zero-interest-rate policy era let companies grow to &quot;grotesque proportions&quot; and encouraged upstarts to pursue new markets rather than compete in existing ones, and that today&\#x27;s higher rates and AI spending are pressuring tech companies. Smath raised a narrower question about Milton Friedman&\#x27;s shareholder-profit doctrine, asking whether it is more defensible if interpreted over the long term.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oreilly.com/radar/what-happened-to-silicon-valley/">What Happened to Silicon Valley ? – O’Reilly</a></li>
<li><a href="https://news.lavx.hu/article/tim-o-reilly-traces-silicon-valley-s-shift-from-value-creation-to-extraction">Tim O&#x27;Reilly Traces Silicon Valley&#x27;s Shift From Value ...</a></li>

</ul>
</details>

**Tags**: `#Silicon Valley`, `#technology industry`, `#mechanism design`, `#AI`, `#society`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [When in Doubt, Flail About](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 7.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「背景」** Sean Goedecke argues that when engineers face unclear situations—no clear guidance, no obvious next step—the instinct to wait for full understanding is usually wrong. The challenge is that acting without understanding can look reckless and damage your reputation, yet waiting often means staying useless longer.

**「方案」** His proposed method is deliberate “flailing”: try many different interventions, pay close attention to feedback, and ruthlessly drop whatever is not getting positive responses. Trying many things matters because most plans will be bad; with ten attempts, one may work, whereas a single plan creates overcommitment. Feedback should come both from experienced colleagues and from reality itself, such as whether latency drops or user metrics improve. He identifies three common forms. Product flailing applies when a feature lacks product-market fit: at GitHub Models, many experiments failed, but allowing AI inference from a GitHub Actions token stuck and became the seed of “Continuous AI.” Engineering flailing applies to systems too tangled, optimized, large, or unknown to map fully first; he prefers speculative changes, dropping failures immediately and investigating only apparent improvements, with AI agents useful for generating several candidate refactors. Organizational flailing applies when problems are human rather than technical—teams not communicating or a leader unsure why morale is poor. There, engineers might automate manual work, take over tasks, or propose long-term plans, but must be especially quick to abandon failing actions or they may become the target of frustration.

**「启示」** Goedecke’s core point is that under uncertainty, broad low-cost experimentation with fast feedback is often a better path to understanding than prolonged analysis. The discomfort of feeling like you are flailing is normal and can even be treated as a signal that you are doing the right kind of exploratory work.

**Tags**: `#engineering judgment`, `#decision making`, `#organizational dynamics`, `#product development`, `#feedback loops`

---

## Financial News

<a id="item-finance-news-1"></a>
### [US tech stocks plunge; Asian markets roll out stabilization measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 8.0/10

U.S. AI-related technology stocks sold off sharply on Friday, with the Nasdaq falling 5.28% in one day and the Philadelphia Semiconductor Index dropping nearly 11%. In response, mainland China, South Korea, and Taiwan announced market-stabilization steps, including lower margin requirements, expanded buyback flexibility, tighter monitoring of short selling, and a temporary ban on short selling below the previous close in Taiwan.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** The Nasdaq is a U.S. stock index heavily weighted toward technology companies, while the Philadelphia Semiconductor Index tracks chipmakers; both are often used as barometers for AI-related market sentiment. The measures announced in mainland China, South Korea, and Taiwan are market-stabilization tools—such as margin requirements, buyback limits, and short-selling restrictions—typically used to curb panic selling after sharp declines.

**「Impact」** Investors in technology and semiconductor stocks, as well as traders using margin, short-selling, or derivatives in Asian markets, may face changed trading rules and tighter risk controls starting Nov. 23-24.

**Tags**: `#stock market selloff`, `#technology stocks`, `#semiconductors`, `#Asia market regulation`, `#short selling restrictions`

---