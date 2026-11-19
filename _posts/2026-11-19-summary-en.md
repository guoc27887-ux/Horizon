---
layout: default
title: "Horizon Summary: 2026-11-19 (EN)"
date: 2026-11-19
lang: en
---

> From 44 items, 15 important content pieces were selected

---

**Technology News**
1. [Unauthenticated Nginx HTTP/2 RCE chain can reach host root](#item-tech-news-1) ⭐️ 9.0/10
2. [OpenAI says it is applying its AI models to chip design](#item-tech-news-2) ⭐️ 8.0/10
3. [Google launches Gemini 4 Neon for software engineering and research workflows](#item-tech-news-3) ⭐️ 8.0/10
4. [Microsoft Announces Seven New AI Models at Ignite 2026](#item-tech-news-4) ⭐️ 8.0/10
5. [Google DeepMind makes Genie 4 available to some AI Ultra subscribers](#item-tech-news-5) ⭐️ 8.0/10
6. [Investigative consortium examines Deutsche Bank documents via OpenAleph](#item-tech-news-6) ⭐️ 7.0/10
7. [Quad9 exits France over court-ordered DNS piracy blocking](#item-tech-news-7) ⭐️ 7.0/10
8. [DaisyRose-27B open-weight model draws attention for benchmark gains and training cost](#item-tech-news-8) ⭐️ 7.0/10
9. [Energy-Based Reasoners Claim 385x More Efficient Inference](#item-tech-news-9) ⭐️ 7.0/10
10. [Interactive Voyager 1 Explorer Reaches Down to Single Memory Bits](#item-tech-news-10) ⭐️ 7.0/10
11. [curl maintainer: AI Rust rewrites lag behind real curl fixes](#item-tech-news-11) ⭐️ 7.0/10

**Financial News**
1. [Fed minutes point to more rate hikes and flag AI-related inflation risks](#item-finance-news-1) ⭐️ 8.0/10
2. [Trump, Xi and Putin meet at APEC in Shenzhen with low expectations for breakthroughs](#item-finance-news-2) ⭐️ 7.0/10
3. [Tencent Q3: AI spending surges, WorkBuddy tops domestic daily token usage](#item-finance-news-3) ⭐️ 7.0/10
4. [China and South Korea substantially conclude FTA services and investment follow-up talks](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Unauthenticated Nginx HTTP/2 RCE chain can reach host root](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 9.0/10

Security researcher Xint disclosed NGINX2Root, a chain of five Nginx vulnerabilities plus a Linux kernel flaw that can take an attacker from unauthenticated Nginx access to root on the host. The key issue, CVE-2026-123007, is an HTTP/2 flow-control memory-corruption bug that allows unauthenticated command execution in an Nginx worker. Nginx 1.30.7 and 1.31.9, released on November 18, fix ten CVEs including these issues. Rapid7 has published a proof of concept, but there are currently no reports of exploitation in the wild; operators who cannot upgrade should disable externally exposed HTTP/2.

hackernews · speedping · Nov 18, 15:19 · [Discussion](https://news.ycombinator.com/item?id=50547374)

**「Background」** Nginx is a widely deployed web server and reverse proxy, and HTTP/2 is an optional protocol layer that must be explicitly enabled in its configuration. The newly disclosed issue centers on CVE-2026-123007, a critical integer-underflow/heap-buffer-overflow flaw in Nginx&\#x27;s HTTP/2 flow-control handling: crafted requests can push the flow-control window beyond permitted limits, corrupt worker memory, and potentially allow an unauthenticated attacker to execute code or cause a denial of service. Rapid7 and F5 disclosed the vulnerability together, and proof-of-concept exploit code for CVE-2026-123007 is already publicly available.

**「What operators should do」** Organizations running nginx should inventory internet-facing servers for HTTP/2 exposure and prioritize upgrading to the fixed releases, 1.30.7 or 1.31.9, which were published on November 18, 2026. Where upgrading is not immediately possible, Red Hat&\#x27;s mitigation is to disable HTTP/2 by removing the \`http2\` parameter from \`listen\` directives and, on nginx 1.25 and later, setting \`http2 off;\`. The exposure is narrower than every nginx deployment because HTTP/2 is not enabled by default, but the unauthenticated nature of CVE-2026-123007 and the reported NGINX2Root chain make exposed HTTP/2 endpoints the immediate action item.

**「Community reaction」** Commenters disagreed over practical severity. One warned that the fix had appeared in the open-source repository about a week before disclosure, potentially giving attackers time to weaponize it, while another claimed exploitation requires about 128 GB of HTTP/2 traffic and specific CPU instructions and called it a non-issue. Others focused on mitigation and exposure: HTTP/2 is not enabled by default in Nginx and w3techs data cited in the thread puts adoption at about 12% of servers, still a large absolute number.

<details><summary>References</summary>
<ul>
<li><a href="https://www.rapid7.com/blog/post/ve-cve-2026-123007-critical-nginx-http-2-integer-underflow-leads-to-rce-fixed/">CVE-2026-123007: Critical NGINX HTTP/2 Integer Underflow ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-123007">CVE-2026-123007 - Red Hat Customer Portal</a></li>
<li><a href="https://www.sophos.com/en-us/security-advisories/sophos-sa-20261118-nginx2root">Advisory: NGINX Vulnerabilities - nginx2root (CVE-2026-123007 ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-123007">CVE-2026-123007 - Red Hat Customer Portal</a></li>
<li><a href="https://blog.qualys.com/product-tech/patch-management/2026/11/18/nginx2root-five-nginx-flaws-led-by-cve-2026-123007-how-to-find-mitigate-and-patch-now">NGINX2Root: Five nginx Flaws, Led by CVE-2026-123007. How to ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#nginx`, `#remote-code-execution`, `#http2`, `#vulnerability`

---

<a id="item-tech-news-2"></a>
### [OpenAI says it is applying its AI models to chip design](https://openai.com/index/advancing-chip-design-with-our-models/) ⭐️ 8.0/10

OpenAI announced that it is applying its AI models to chip design, including a chip effort named Jalapeño and work involving RISC-V designs. The announcement was published on OpenAI&\#x27;s site and discussed on Hacker News, but the supplied material does not include the technical details of the designs, performance results, or whether the RISC-V designs will be publicly released. It should therefore be read as a company announcement of an active direction rather than a shipped, independently verified chip or open-source release.

hackernews · vighneshiyer · Nov 18, 17:45 · [Discussion](https://news.ycombinator.com/item?id=50549493)

**「Background」** OpenAI first revealed its Jalapeño inference ASIC at Hot Chips in August 2026, a chip that leaned heavily on AI to achieve a very short design window. In June 2026, The New York Times reported that OpenAI and Broadcom had unveiled the custom AI chip design, noting that building its own chips could reduce OpenAI&\#x27;s dependence on Nvidia and AMD and give it more negotiating leverage. The current announcement extends that effort, describing work on designing a RISC-V core from a specification, improving Jalapeño&\#x27;s compute blocks, optimizing RISC-V cores, and continuing a collaboration with AMD.

**「What it means for chip teams」** For chip design and EDA teams, the immediate consequence is that AI-assisted design is moving from experiments to production workflows: OpenAI says its models optimized circuits used in Jalapeño silicon and improved RISC-V core designs, and it has partnered with Broadcom and Synopsys to apply models to silicon and EDA tooling. Teams evaluating these tools should watch whether OpenAI releases the improved RISC-V designs; the announcement does not clearly say they will be openly shared, so organizations should not assume access. The practical opportunity is using agents to automate repetitive EDA and simulation work, while the open question is whether the resulting design IP will be available outside OpenAI&\#x27;s partners.

**「Community discussion」** On Hacker News, zardo asked whether OpenAI is sharing the RISC-V designs, while jacquesm argued that AI companies are diversifying into other industries and may increasingly compete with their own customers. Other commenters focused on the engineering angle: skyberrys reported good results using agents to generate circuits and automate EDA and simulation workflows, and george\_max speculated about AI eventually helping design more of the hardware stack.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/advancing-chip-design-with-our-models/">Advancing chip design with OpenAI models | OpenAI</a></li>
<li><a href="https://www.tomshardware.com/tech-industry/artificial-intelligence/openai-jalapeno-design-interview-transcript-hardware-vp-richard-ho-explains-how-ai-assisted-design-may-shape-the-future-of-inference-asics">OpenAI Jalapeño design interview transcript... | Tom&#x27;s Hardware</a></li>
<li><a href="https://www.nytimes.com/2026/06/24/technology/openai-broadcom-chip-jalapeno.html">OpenAI and Broadcom Unveil Custom A.I. Chip Design</a></li>
<li><a href="https://openai.com/index/advancing-chip-design-with-our-models/">Advancing chip design with OpenAI models</a></li>
<li><a href="https://www.broadcom.com/company/news/product-releases/64506">OpenAI and Broadcom Unveil LLM-Optimized Intelligence Processor</a></li>
<li><a href="https://news.synopsys.com/2026-09-30-OpenAI-and-Synopsys-Announce-GPT-Synopsys-Frontier-Intelligence-to-Revolutionize-Chip-Design">OpenAI and Synopsys Announce GPT-Synopsys: Frontier ...</a></li>

</ul>
</details>

**Tags**: `#AI`, `#chip design`, `#hardware`, `#OpenAI`, `#RISC-V`

---

<a id="item-tech-news-3"></a>
### [Google launches Gemini 4 Neon for software engineering and research workflows](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/) ⭐️ 8.0/10

Google has released Gemini 4 Neon, a model aimed at fast end-to-end execution in complex software engineering, knowledge work, and scientific research workflows. It is available to developers, enterprises, and Google AI Pro/Ultra subscribers, with pricing of $3 per million input tokens \($0.15 for cached input\), $15 per million output tokens, and a 1 million-token context window. Google says it tops Artificial Analysis&\#x27; coding agent index at 58.6, ranks third overall on the xhigh tier of the intelligence index at 61, scores 65.2% on Terminal-Bench 4.1, and costs 32% less per task than Carbon at the default high setting. These benchmark figures come from the announcement and have not been independently verified here.

hackernews · yigitdemirag · Nov 18, 21:34 · [Discussion](https://news.ycombinator.com/item?id=50552424)

**「Background」** Gemini 4 Neon is Google&\#x27;s newest addition to the Gemini 4 model family, positioned as a fast, frontier-level model for complex software engineering, knowledge work, and research workflows. It succeeds or complements Gemini 4 Carbon, which Google had positioned as its flagship &\#x27;long horizon&\#x27; model; Neon now tops some agentic coding benchmarks while Carbon retains an edge on research-scale reasoning evaluations like CritPt. The model is available to developers, enterprises, and Google AI Pro/Ultra subscribers, with a 1 million token context window and pricing of $3 per million input tokens \($0.15 cached\) and $15 per million output tokens.

**「Impact」** Developers and researchers can now use Gemini 4 Neon for fast end-to-end execution in complex software engineering, knowledge work, and science workflows, with Google publishing a developer guide and API documentation covering capabilities, API conventions, migration steps, and a quickstart. Its benchmark results—\#1 on the Artificial Analysis Coding Agent Index \(58.6\), 65.2% on Terminal-Bench 4.1, and 46.2% on FrontierCode 2.0 at its default high setting—suggest it is a strong option for coding-agent and research-scale tasks, though community observers note it scores lower than Carbon on some research-reasoning evals like CritPt, so teams should match the model to the task rather than assume it replaces Carbon across all workloads. Pricing and availability details \(per the source\) should be confirmed against Google&\#x27;s official documentation before committing production workloads.

**「Community reaction」** Commenters debated Google&\#x27;s model naming and positioning: stillpointlab said the proliferation of names like Neon, Carbon, Opus, and Haiku makes it hard to map models to use cases, while declanjackson noted that Neon scores higher overall than Carbon but Carbon remains positioned as the &\#x27;long horizon&\#x27; model, with stronger results on research-scale reasoning evals such as CritPt. Separately, seizethecheese reported that Neon is being served at about 127 tokens per second via OpenRouter, faster than Carbon at about 46 tokens per second, and questioned why the apparent flagship model is also the faster one; impulser\_ argued from personal use that Gemini models still feel less generally capable than Anthropic&\#x27;s Opus 5.5 despite comparable benchmarks.

<details><summary>References</summary>
<ul>
<li><a href="https://www.neowin.net/news/google-launches-gemini-4-neon-claims-its-three-times-faster-than-carbon/">Google launches Gemini 4 Neon , claims it&#x27;s three times... - Neowin</a></li>
<li><a href="https://artificialanalysis.ai/models/gemini-4-neon">Gemini 4 Neon Models - Intelligence, Performance &amp; Price Comparison</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-neon/">Introducing Gemini 4 Neon</a></li>
<li><a href="https://deepmind.google/blog/introducing-gemini-4-neon/">Introducing Gemini 4 Neon - deepmind.google</a></li>
<li><a href="https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/guides/gemini-4-neon">Developer&#x27;s guide to Gemini 4 Neon | Gemini Enterprise Agent ...</a></li>
<li><a href="https://aistudio.google.com/docs/models/gemini-4-neon">Gemini 4 Neon - Gemini API | Google AI Studio</a></li>

</ul>
</details>

**Tags**: `#AI`, `#Google`, `#Gemini`, `#LLMs`, `#model releases`

---

<a id="item-tech-news-4"></a>
### [Microsoft Announces Seven New AI Models at Ignite 2026](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 8.0/10

Microsoft announced seven new AI models at its Ignite 2026 conference, described as offering scalable price-performance. The lineup includes MAI Code 2, a coding model that early community testers report is competitive with leading alternatives such as Anthropic&\#x27;s Opus and OpenAI&\#x27;s Sol. The announcement is significant for AI-assisted software engineering, though performance comparisons remain largely promotional and independently unverified.

hackernews · gmays · Nov 18, 16:08 · [Discussion](https://news.ycombinator.com/item?id=50548021)

**「Background」** Microsoft&\#x27;s MAI model family is its in-house line of AI models, and the new Ignite 2026 release extends it with seven models spanning coding, cybersecurity, image generation, transcription, and general work tasks. The headline coding model, MAI Code 2, is positioned as a flagship agentic coding model that Microsoft says reaches 98% of the coding quality of GPT-6.1 Sol at about 40% of the price, while MAI Cyber 2 Flash is claimed to beat GPT-6 Astra&\#x27;s quality on the CyberGym-E2E benchmark at less than 2% of the cost per task. These claims place Microsoft directly against OpenAI and Anthropic in the market for high-performance coding and enterprise AI models, with the added argument that its models could reduce reliance on external AI providers.

**「Impact」** For developers and enterprises evaluating coding assistants, Microsoft&\#x27;s release of MAI Code 2 and MAI Code 2 Flash adds a lower-cost option for everyday coding tasks, with Microsoft claiming leading performance at a fraction of the cost of competing models. Early hands-on feedback is cautiously positive: one commenter who tested MAI Code 2 said it has been quite good for their usual work and roughly on par with Anthropic&\#x27;s Opus or OpenAI&\#x27;s Sol, though that is individual experience rather than an independent benchmark. Public benchmark comparisons still favor Claude Opus 5.5 over GPT-6.2 Sol for agentic tasks \(84.1 vs. 71.7\), so teams should validate MAI Code 2 against their own workflows and cost targets before switching. The practical consequence is increased pricing and capability pressure on incumbent coding-model providers, and a concrete action for buyers is to pilot MAI Code 2 on representative tasks and compare quality, latency, and total cost against their current model.

**「Community Reaction」** Reactions are mixed. One tester reported MAI Code 2 has been &\#x27;quite good&\#x27; for their usual work and roughly on par with Opus or Sol, while another argued Microsoft should open-source some models to gain market share, warning it risks becoming &\#x27;Windows Phone OS all over again.&\#x27; Others were more skeptical, with one AI engineering practitioner calling the keynote &\#x27;shallow and opportunistic&\#x27; and seeing no reason to adopt Microsoft&\#x27;s stack, and another expressing broader frustration about AI-driven changes to software work.

<details><summary>References</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world-class models at scalable price-performance ...</a></li>
<li><a href="https://windowsforum.com/news/microsoft-ignite-2026-mai-code-2-models-agent-365-governance-and-enterprise-ai-stack.453003/">Microsoft Ignite 2026: MAI Code 2 Models, Agent 365 ...</a></li>
<li><a href="https://www.zeebiz.com/technology/news-microsoft-mai-code-2-ai-models-openai-anthropic-405704">Microsoft unveils MAI Code 2 AI models with focus on coding ...</a></li>
<li><a href="https://benchlm.ai/compare/claude-opus-5-5-vs-gpt-6-2-sol">Claude Opus 5.5 vs GPT-6. 2 Sol : Benchmarks &amp; Cost</a></li>
<li><a href="https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/">MAI Code 2 and Code 2 Flash: Everyday coding at... | Microsoft AI</a></li>

</ul>
</details>

**Tags**: `#Microsoft`, `#AI models`, `#coding assistants`, `#Ignite 2026`, `#LLMs`

---

<a id="item-tech-news-5"></a>
### [Google DeepMind makes Genie 4 available to some AI Ultra subscribers](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/) ⭐️ 8.0/10

Google DeepMind announced that Genie 4, its AI world model, is now available through Project Genie. Access is limited to “Eligible Google AI Ultra subscribers,” according to the announcement. The supplied source does not include technical benchmarks, pricing, regional availability, or detailed capability measurements, so the practical scope of the release remains unclear. Community reaction focused heavily on how confusing the eligibility and subscription path appears to be.

hackernews · leumon · Nov 18, 18:49 · [Discussion](https://news.ycombinator.com/item?id=50550415)

**「Background」** Google DeepMind&\#x27;s Genie line is a series of AI &quot;world models&quot; that generate interactive, navigable environments rather than static images or video. The current announcement follows an earlier research-preview stage: TechCrunch reported on October 27, 2026 that Genie 4 added audio, more realistic worlds, and real-time steering, with Gemini acting as a planning &quot;director&quot; that checks frames while Genie generates visuals. It is now being rolled out through Project Genie, starting with eligible Google AI Ultra subscribers.

**「Practical impact」** For now, access is limited to eligible Google AI Ultra subscribers, so most developers and players cannot test Genie 4 directly. The near-term consequence is that creators and studios can evaluate its real-time, steerable worlds and generated audio only through that subscription tier, while broader game-engine use remains speculative. If you are interested, check whether your Google account and region qualify for the Ultra tier before assuming availability.

**「Community reaction」** Commenters disagreed about what matters most in the release. kingrolo reported that a workspace account could not get Google AI Ultra and that a personal account’s Ultra page appeared to mention Genie 3 instead, leaving it unclear whether UK availability or incomplete page updates were responsible. alecst argued that discussion was too focused on pricing and capability while ignoring potentially serious negative consequences, while vchiriac and giancarlostoro saw more promise, with the latter suggesting world models could eventually influence game-engine-like applications.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/google-deepmind/genie-4-now-available-project-genie/">Project Genie update featuring Genie 4</a></li>
<li><a href="https://techcrunch.com/2026/10/27/googles-genie-4-world-model-adds-audio-more-realistic-worlds-and-real-time-steering/">Google ’s Genie 4 world model adds audio, more... | TechCrunch</a></li>
<li><a href="https://www.youtube.com/watch?v=nBFOUmCmK1g">Genie 4 : Google&#x27;s AI Builds Worlds You Can Walk Into - YouTube</a></li>
<li><a href="https://techcrunch.com/2026/10/27/googles-genie-4-world-model-adds-audio-more-realistic-worlds-and-real-time-steering/">Google’s Genie 4 world model adds audio, more... | TechCrunch</a></li>

</ul>
</details>

**Tags**: `#AI`, `#Google DeepMind`, `#world models`, `#generative AI`, `#game engines`

---

<a id="item-tech-news-6"></a>
### [Investigative consortium examines Deutsche Bank documents via OpenAleph](https://www.inside-db.com/) ⭐️ 7.0/10

An investigative journalism consortium has published a large-scale examination of Deutsche Bank documents. The project used OpenAleph, a document-analysis platform maintained by DARC and built on Elasticsearch and the FollowTheMoney schema, to process roughly 15 million documents, most of which were Outlook mailbox exports. The consortium says its reporters will continue evaluating the material and will not publish the raw data online. The reporting has drawn substantial discussion on Hacker News about both the findings and the underlying technology.

hackernews · gyre007 · Nov 18, 15:38 · [Discussion](https://news.ycombinator.com/item?id=50547620)

**「Background」** The investigation centers on a leak of more than 15 million files covering Deutsche Bank&\#x27;s activities from the early 2010s onward, including allegations that the bank missed money-laundering and sanctions warning signs while business interests sometimes outweighed compliance. To make the material workable for roughly 230 journalists and 50 news organizations, the consortium used OpenAleph, a document-analysis platform maintained by DARC and built on Elasticsearch with the FollowTheMoney schema, which was developed specifically for investigative journalism.

**「Why it matters」** For journalists and data engineers, the project is a concrete example of using OpenAleph, Elasticsearch, and the FollowTheMoney schema to analyze millions of documents at scale for investigative reporting. For readers, the consortium&\#x27;s decision not to publish raw data means the public will rely on the consortium&\#x27;s selected reporting rather than independently examining the underlying documents.

**「Community discussion」** A reporter involved in the project, ltrg, explained that the roughly 15 million documents were shared with consortium partners through OpenAleph, maintained by DARC and based on Elasticsearch and the FollowTheMoney schema. Another commenter, mlmonkey, criticized the decision not to publish the raw data, arguing that selective omission can mislead the public even without outright lies. Others focused on presentation and context: gwbas1c said the site needs a higher-level summary of the key points, while eunos argued that tax minimization is a long-standing practice in Germany, citing the example of Taxfix.

<details><summary>References</summary>
<ul>
<li><a href="https://www.lemonde.fr/en/les-decodeurs/article/2026/11/17/inside-deutsche-bank-an-investigation-by-230-journalists-and-50-news-orgs-into-15-million-files_6782703_8.html">&#x27;Inside Deutsche Bank&#x27;: An investigation by 230 journalists ...</a></li>
<li><a href="https://www.himalmag.com/inside-deutsche-bank-leak-investigation/">Inside Deutsche Bank: Leak of 15 million files from Deutsche ...</a></li>
<li><a href="https://www.linkedin.com/pulse/inside-deutsche-bank-making-15-million-files-searchable-nrflf">Inside Deutsche Bank: Making 15 million files ... - LinkedIn</a></li>

</ul>
</details>

**Tags**: `#investigative journalism`, `#data engineering`, `#elasticsearch`, `#open source`, `#finance`

---

<a id="item-tech-news-7"></a>
### [Quad9 exits France over court-ordered DNS piracy blocking](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

Quad9, a public DNS resolver, has withdrawn from France because of court-ordered DNS blocking used to enforce anti-piracy measures. The move has prompted debate over whether DNS resolvers are an appropriate enforcement point for copyright claims, and whether responsibility lies with courts applying the law or with lawmakers who wrote it. The discussion is based on commentary and links to statements from Quad9 and Cloudflare rather than a newly shipped technical capability.

hackernews · ritzaco · Nov 18, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50545958)

**「Background」** Quad9 is a public DNS resolver that translates domain names into IP addresses for users, and it has previously been drawn into French piracy enforcement. A December 2024 report described a French piracy blocking order with global reach and Quad9 vowing to fight it, and an October 2026 report said Quad9 would withdraw from France by November 24, 2026 to avoid having to censor DNS while continuing its court fight. The current article argues that DNS resolvers are the wrong enforcement point for piracy, a debate sharpened by Quad9&\#x27;s withdrawal and by Cloudflare&\#x27;s related commentary.

**「Impact on French users and DNS operators」** From November 24, 2026, Quad9 will stop serving users in France rather than comply with a beIN Sports blocking order, so French users who rely on it for public DNS resolution will need to switch to another resolver. The case also puts other public DNS operators in a difficult position: Cloudflare characterized the withdrawal as &quot;a canary in the coal mine&quot; and warned that mandating DNS-level blocking is dangerous, suggesting other resolvers may face similar court orders or exit decisions. Organizations in France that depend on Quad9 for security filtering or privacy-focused resolution should plan a migration and review how DNS blocking mandates could affect their chosen resolvers.

**「Community reaction」** Commenters disagreed over where blame belongs: skrebbel argued that it matters whether French judges misread the law or correctly applied a bad law, while trentnix viewed non-prosecutorial anti-piracy measures as a potential route to suppressing disfavored speech. Others focused on market alternatives, with bemtevi arguing that cheap, DRM-free paid downloads would reduce piracy, and AppalachianEng claiming that large AI companies have already consumed much intellectual property, making individual piracy enforcement less coherent.

<details><summary>References</summary>
<ul>
<li>&quot;Quad9 is retracting from Franc…&quot; - Das Federversum - Marcel Waldvogel</li>
<li>French Piracy Blocking Order Goes Global, DNS Service Quad9 Vows to Fight - Reddit</li>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad9’s withdrawal from France: A canary in the coal mine</a></li>
<li><a href="https://techstackups.com/articles/quad9-leaves-france-dns-blocking/">Quad9 Is Leaving France: Why DNS Resolvers Are the Wrong ...</a></li>
<li><a href="https://daily.dev/posts/quad9-quits-france-and-cloudflare-is-calling-it-a-canary-wfqsqz2nz">Quad9 quits France, and Cloudflare is calling it a canary</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet-policy`, `#censorship`, `#piracy`, `#infrastructure`

---

<a id="item-tech-news-8"></a>
### [DaisyRose-27B open-weight model draws attention for benchmark gains and training cost](https://www.radixark.com/blog/daisyrose-27b) ⭐️ 7.0/10

RadixArk&\#x27;s DaisyRose-27B is being discussed as a new open-weight 27B model, with a Hugging Face release listed under RadixArk/DaisyRose-27B. The discussion highlights reported benchmark-focused training and a stated training cost of 18 days on 144 H200 GPUs. Community reactions focus on whether the gains are balanced across unrelated benchmarks, the lack of an immediately available GGUF build, and the hardware requirements for training a Qwen-based model.

hackernews · de\_sty · Nov 18, 19:39 · [Discussion](https://news.ycombinator.com/item?id=50551046)

**「Background」** DaisyRose-27B is a post-trained derivative of Qwen3.8-27B, an existing open-weight base model. RadixArk says it used its Miles reinforcement-learning framework in fully asynchronous mode and trained the model for 18 days on 144 H200 GPUs, raising Terminal-Bench 4.1 pass@1 from 5.6% to 12.0% and reporting gains on six other benchmarks. The HN discussion compares it with other Qwen-based fine-tunes such as Sabi-noema and asks whether benchmark-targeted training sacrifices broader capability.

**「Practical impact」** For practitioners, DaisyRose-27B is available as an open-weight 27B model on Hugging Face, but its immediate usefulness depends on local deployment support: one commenter noted there was no GGUF download yet and said they would wait for a quantized build before testing. The reported cost of 18 days on 144 H200 GPUs also signals that reproducing this post-training effort is expensive, while the discussion suggests buyers and users should check whether benchmark gains come with regressions on tasks outside the training evaluation set.

**「Community discussion」** Commenters raised two main concerns: jacquesm asked for before-and-after results on benchmarks not used in training to reveal capability tradeoffs, while woah argued that heavy reliance on evaluation datasets casts doubt on near-term claims that AI will become self-improving. xlayn said they would wait for a GGUF build before testing, and mips\_avatar asked about the RL topology, specifically whether training and rollout used separate dedicated H200 nodes.

<details><summary>References</summary>
<ul>
<li><a href="https://www.radixark.com/blog/daisyrose-27b">DaisyRose-27B: Pushing the Frontier of Post-Training Efficiency</a></li>
<li><a href="https://www.aigpu.cloud/en/blog/radixark-daisyrose-27b-rl-post-training">RadixArk&#x27;s DaisyRose-27B Doubles Agent Benchmark Scores with ...</a></li>
<li><a href="https://news.lavx.hu/article/radixark-releases-daisyrose-27b-built-on-qwen3-8-27b">RadixArk Releases DaisyRose-27B, Built on Qwen3.8-27B</a></li>
<li><a href="https://www.radixark.com/blog/daisyrose-27b">DaisyRose - 27 B : Pushing the Frontier of Post-Training... | RadixArk Blog</a></li>
<li><a href="https://huggingface.co/Qwen">Org profile for Qwen on Hugging Face, the AI community building the...</a></li>

</ul>
</details>

**Tags**: `#open-source-models`, `#large-language-models`, `#reinforcement-learning`, `#benchmarks`, `#model-training`

---

<a id="item-tech-news-9"></a>
### [Energy-Based Reasoners Claim 385x More Efficient Inference](https://energy-based-reasoners.github.io/) ⭐️ 7.0/10

A project page for Energy-Based Reasoners is circulating on Hacker News with a claim of 385x more efficient inference. The supplied evidence is promotional and does not include enough technical detail to verify the efficiency figure, model scope, benchmarks, or availability. Commenters describe the approach as promising for narrow logic-puzzle-style tasks, such as Sudoku, but question whether it scales beyond those settings.

hackernews · frenchmajesty · Nov 18, 09:29 · [Discussion](https://news.ycombinator.com/item?id=50543989)

**「Background」** Energy-Based Reasoners \(EBRs\) are a proposed alternative to recurrent reasoning models: instead of relying on a conventional looped update rule, they learn an energy function over latent reasoning states and treat each refinement step as gradient descent on that energy, with the gradient guiding both state updates and a stopping signal. The project page and arXiv abstract describe this formulation, and the accompanying discussion cites a benchmark claim that EBRs reach 99.9% accuracy on Sudoku-Extreme with 5 samples while using 345 times less inference compute than the next-best model, Looped Flows, which scores 99.3% under the same sample count. The broader context is renewed interest in energy-based models for reasoning, including Logical Intelligence&\#x27;s recent Kona 1.0 release, which has been described as the first commercial energy-based reasoning model and is associated with Yann LeCun as founding chair of its technical research board.

**「Why it matters」** If independently validated, a 385x inference-efficiency improvement could make certain reasoning workloads much cheaper to run, but the current evidence does not establish that benefit for general AI workloads. Practitioners should treat the claim as unverified until benchmarks, training details, and comparisons with conventional LLM inference are published.

**「Community reaction」** Commenters are interested but cautious. One user recommended Logical Intelligence, chaired in part by Yann LeCun, for context on energy-based models, while another who says they spent a year training EBMs argued that they are impressive validators but hard to train and niche-specific, claiming that at least one Sudoku solver does not scale. Others asked for a clearer definition of what “energy” means in the paper.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.08977">[2611.08977] Energy-Based Reasoners: Your Recurrent Reasoner ...</a></li>
<li><a href="https://energy-based-reasoners.github.io/">Energy-Based Reasoners: Your Recurrent Reasoner Should Be an ...</a></li>
<li><a href="https://daily.dev/posts/energy-based-reasoners-385x-more-efficient-inference-dnzpii9nt">Energy-Based Reasoners: 385x more efficient inference</a></li>
<li><a href="https://paperlens.io/idea/kona-1/">Kona 1: Energy - Based Reasoning | PaperLens</a></li>

</ul>
</details>

**Tags**: `#energy-based models`, `#inference efficiency`, `#AI reasoning`, `#machine learning`, `#LLMs`

---

<a id="item-tech-news-10"></a>
### [Interactive Voyager 1 Explorer Reaches Down to Single Memory Bits](https://rshekhar.com/voyager/) ⭐️ 7.0/10

A new interactive website by Raj Shekhar lets users explore Voyager 1&\#x27;s hardware and status, released as the spacecraft reached one light-day from Earth. Visitors can view the live positions of both Voyager probes, inspect a nuclear battery&\#x27;s 24 plutonium spheres, descend into the data computer to individual memory chips and even a single bit of the command computer&\#x27;s memory, examine the Golden Record&\#x27;s cover instructions, review how Voyager 1 was repaired by radio commands, and see which Earth dish is currently communicating with the probes. A four-minute companion film is also available on YouTube.

hackernews · raj-shekhar · Nov 18, 16:18 · [Discussion](https://news.ycombinator.com/item?id=50548161)

**「Why this milestone matters」** Voyager 1 is NASA&\#x27;s long-running deep-space probe, launched in 1977, that flew by Jupiter, Saturn, and Saturn&\#x27;s moon Titan and later became the first spacecraft to enter interstellar space in 2012. It is now the most distant human-made object from Earth, and it was projected to reach a distance of one light-day from Earth on November 18, 2026 — the milestone the interactive site marks. That context explains why the site&\#x27;s hardware-level tour, from its plutonium-powered battery to individual memory chips, is framed around a spacecraft still operating nearly 50 years after launch.

**「Why it matters」** The site makes spacecraft engineering accessible at an unusually fine granularity, letting students and space enthusiasts understand 1970s computing and power systems interactively rather than through static diagrams. It also serves as a live tracking tool, showing real-time communication status with the most distant human-made objects.

**「Community reaction」** Commenters praised the project and shared related resources, including a Golden Record tribute site and an audio-to-image decoder. One user asked for deeper technical detail on the exact physical failure mechanism behind a known memory chip fault, while another questioned how much of the site was AI-generated versus manually researched and whether it was verified against authoritative sources.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Voyager_1">Voyager 1 - Wikipedia</a></li>
<li><a href="https://onelightday-voyager1.space/">One Light Day · Voyager 1</a></li>
<li><a href="https://www.aljazeera.com/news/2026/11/18/nasas-voyager-1-hits-record-one-light-day-distance-50-years-after-launch">NASA’s Voyager 1 hits record one light - day distance, 50... | Al Jazeera</a></li>

</ul>
</details>

**Tags**: `#spacecraft`, `#hardware`, `#interactive visualization`, `#Voyager`, `#engineering history`

---

<a id="item-tech-news-11"></a>
### [curl maintainer: AI Rust rewrites lag behind real curl fixes](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) ⭐️ 7.0/10

curl maintainer Daniel Stenberg said that while AI agents converted 185,000 lines of curl&\#x27;s C code into 340,000 lines of Rust over a little more than three weeks, the actual curl project merged over 300 commits in the same period. He counted a little over 200 bug fixes in that window, plus a few vulnerability fixes, and noted that another month would add roughly 200 more fixes and possibly more vulnerability fixes. His point is that these Rust rewrites are snapshots that do not automatically receive the fixes and security patches that continue to land in upstream curl, and he asked whether the clones can keep up.

rss · Simon Willison · Nov 18, 15:58

**「Background」** curl is a widely used open-source command-line tool and library for transferring data over network protocols, maintained for decades in C by Daniel Stenberg. The discussion follows recent AI-agent-generated Rust rewrites of curl, which prompted Stenberg to compare those snapshots with the ongoing maintenance work in the canonical project.

**「Why this matters for users of such rewrites」** For anyone evaluating or depending on an AI-generated Rust rewrite of curl, Stenberg&\#x27;s figures are a concrete compatibility and security concern: a rewrite produced in a few weeks will not contain the roughly 200 bug fixes and vulnerability patches merged upstream during that same period, and the gap can keep growing as upstream development continues. Teams considering such a rewrite would need a plan to track and port upstream curl fixes, rather than treating the generated code as a drop-in equivalent.

<details><summary>References</summary>
<ul>
<li><a href="https://daniel.haxx.se/blog/2026/11/17/actual-curl-rewrites-in-rust/">Actual curl rewrites in rust - daniel.haxx.se</a></li>
<li><a href="https://letsdatascience.com/news/curl-maintainer-daniel-stenberg-answers-ai-built-rust-rewrit-53834580">Curl maintainer Daniel Stenberg answers AI-built Rust ...</a></li>

</ul>
</details>

**Tags**: `#curl`, `#rust`, `#ai-assisted-development`, `#open-source`, `#security`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed minutes point to more rate hikes and flag AI-related inflation risks](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 8.0/10

The Federal Reserve&\#x27;s October meeting minutes show that almost all officials thought further rate increases would likely be needed to return inflation to the Fed&\#x27;s 2% goal, even though the committee voted 10-2 to hold its benchmark rate at 3.75%-4%. Officials also flagged AI-related demand as a material inflation risk, and markets are currently pricing a quarter-point hike at the December 8-9 meeting with some chance of a larger half-point move.

rss · CNBC Finance · Nov 18, 19:41

**「Background」** The Federal Open Market Committee is the Fed panel that sets the federal funds rate, the benchmark borrowing rate used to influence inflation and hiring. At its October meeting, the committee voted 10-2 to keep that rate in a 3.75%-4% range, with Governor Lisa Cook and Cleveland Fed President Beth Hammack dissenting in favor of a quarter-point increase. The minutes said almost all participants saw further increases as likely under their baseline outlooks, while officials waited for more information to help return inflation to the Fed&\#x27;s 2% goal.

**「Why it matters」** If the Fed raises rates further, borrowing costs for mortgages, car loans, credit cards, and business loans would likely stay higher, while investors would face a tighter monetary-policy path into 2027.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html">Fed minutes October 2026 : Officials expect more rate hikes , worry...</a></li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#interest rates`, `#inflation`, `#artificial intelligence`, `#monetary policy`

---

<a id="item-finance-news-2"></a>
### [Trump, Xi and Putin meet at APEC in Shenzhen with low expectations for breakthroughs](https://www.cnbc.com/2026/11/18/apec-trump-xi-putin-shenzhen.html) ⭐️ 7.0/10

At this week&\#x27;s APEC summit in Shenzhen, U.S. President Donald Trump, Chinese President Xi Jinping and Russian President Vladimir Putin are set to hold the first-ever three-way leaders&\#x27; meeting, while Trump and Xi are expected to discuss implementing the U.S.-China trade truce. The U.S. and China agreed in September to lower tariffs on $30 billion of each other&\#x27;s goods, but no effective date was set, and expectations for major breakthroughs are low.

rss · CNBC Finance · Nov 18, 06:04

**「Background」** The 33rd APEC leaders&\#x27; meeting is being held in Shenzhen on November 18–19, and the U.S.–China trade truce reached after their 2025 meeting in South Korea was extended to January 2027. The two sides agreed in September to lower tariffs on $30 billion of each other&\#x27;s goods, but without an effective date, and China has said it will only increase U.S. agricultural purchases if those cuts take effect.

**「Why it matters」** Businesses and governments across Asia are watching for signals on U.S.-China tariff implementation and AI technology restrictions, since tighter U.S. controls and possible Chinese countermeasures could affect companies that rely on access to American AI technology and cross-border trade.

<details><summary>References</summary>
<ul>
<li><a href="https://sputnikglobe.com/20261117/putin-lands-in-shenzhen-for-apec-summit--and-historic-trilateral-meeting-with-trump--xi-1125082115.html">Putin Lands In Shenzhen for APEC Summit — and Historic Trilateral ...</a></li>
<li><a href="https://www.aa.com.tr/en/asia-pacific/explainer-trade-technology-and-possible-putin-talks-what-awaits-trump-in-asia/4124280">Anadolu Ajansı: EXPLAINER – Trade , technology and possible Putin...</a></li>
<li><a href="https://www.caixinglobal.com/2026-10-01/in-depth-whats-in-the-us-china-tariff-truce-and-whats-left-unsettled-102490269.html">In Depth: What’ s in the China - U . S . Tariff Truce , and... - Caixin Global</a></li>

</ul>
</details>

**Tags**: `#APEC summit`, `#US-China trade`, `#geopolitics`, `#AI technology restrictions`, `#global energy prices`

---

<a id="item-finance-news-3"></a>
### [Tencent Q3: AI spending surges, WorkBuddy tops domestic daily token usage](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

Tencent reported Q3 2026 revenue of RMB 207.3 billion, up 8% year over year and below market expectations, with net profit attributable to shareholders of RMB 63.6 billion, up 0.8%. Quarterly capital expenditure reached RMB 81.433 billion, far above the estimated RMB 55.4 billion, driving free cash flow to negative RMB 69.1 billion; the company also said WorkBuddy has the highest daily token usage among domestic large language model products, consuming over 100 trillion tokens per day.

telegram · zaihuapd · Nov 18, 09:20

**「Background」** Tencent&\#x27;s capital spending has been climbing as it invests in AI infrastructure; in the third quarter of 2026 it reached RMB 81.43 billion, well above the market estimate of RMB 55.4 billion, while quarterly free cash flow was negative RMB 69.1 billion. The company also reported Q3 revenue of RMB 207.34 billion, below the market estimate of RMB 210.53 billion.

**「Impact」** Investors in Tencent and Chinese AI/tech stocks face higher near-term spending pressure, as the AI-driven capex surge pushed quarterly free cash flow negative.

<details><summary>References</summary>
<ul>
<li>腾讯控股第三季度资本支出814.3亿元，市场预估554亿元 - 网易</li>
<li>腾讯控股第三季度营收2073.4亿元人民币 - 网易</li>

</ul>
</details>

**Tags**: `#Tencent`, `#quarterly earnings`, `#AI capex`, `#free cash flow`, `#Chinese tech`

---

<a id="item-finance-news-4"></a>
### [China and South Korea substantially conclude FTA services and investment follow-up talks](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

China and South Korea announced on November 18 the substantial conclusion of follow-up negotiations on services and investment under their free trade agreement. China committed to grant South Korea most-favored-nation treatment in film and gaming and to expand opening in tourism, legal, construction, and financial services.

telegram · zaihuapd · Nov 18, 10:02

**「Background」** The China–South Korea free trade agreement already covers goods trade; these follow-up talks, which began in March 2018, address services and investment. Earlier rounds had moved slowly, with the tenth round reported as making no substantive progress.

**「Impact」** South Korean film, gaming, tourism, legal, construction, and financial-services firms could gain broader access to China&\#x27;s market, while audiovisual co-production is set to expand from movies to TV dramas, animation, variety shows, and documentaries; some technical details still need to be settled at the working level.

<details><summary>References</summary>
<ul>
<li><a href="https://cn.yna.co.kr/view/MYH20140321012000881">韩 中 自 贸 协 定 第十轮 谈 判 未取得 实 质 进展 | 韩 联社</a></li>

</ul>
</details>

**Tags**: `#China-South Korea FTA`, `#trade policy`, `#services and investment`, `#market opening`, `#audiovisual co-production`

---