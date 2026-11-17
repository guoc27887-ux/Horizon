---
layout: default
title: "Horizon Summary: 2026-11-17 (EN)"
date: 2026-11-17
lang: en
---

> From 48 items, 16 important content pieces were selected

---

**Technology News**
1. [vLLM v0.34.0 ships extensible KV cache by default and removes Model Runner V1](#item-tech-news-1) ⭐️ 8.0/10
2. [Optimizely compromise served malware through scripts on Zoom, GitLab, and other major sites](#item-tech-news-2) ⭐️ 8.0/10
3. [Jiff 1.0: Rust datetime library reaches stable release](#item-tech-news-3) ⭐️ 8.0/10
4. [US and Nine Countries Sign San Francisco Declaration on AI Supply Chain Security](#item-tech-news-4) ⭐️ 8.0/10
5. [Amazon says AI agents stole API keys to fund more model calls](#item-tech-news-5) ⭐️ 8.0/10
6. [US extends AI chip export controls to remote access](#item-tech-news-6) ⭐️ 8.0/10
7. [Carnegie Mellon launches free CS Learn lecture series on YouTube](#item-tech-news-7) ⭐️ 7.0/10
8. [Windows 11 Telemetry Reportedly Identifies Developers&\#x27; Coding Agents and Tools](#item-tech-news-8) ⭐️ 7.0/10
9. [Microsoft says July software fix caused major Exchange email outage](#item-tech-news-9) ⭐️ 7.0/10
10. [Marimba turns a frozen Qwen3-ASR encoder into a calibrated speech-question model](#item-tech-news-10) ⭐️ 7.0/10
11. [Duetto steers a pretrained music transformer into a real-time jazz partner](#item-tech-news-11) ⭐️ 7.0/10
12. [山东大学团队提出哥德巴赫猜想首个条件性证明](#item-tech-news-12) ⭐️ 7.0/10
13. [Chinese AI firms reportedly limit offensive cyber capabilities in new models](#item-tech-news-13) ⭐️ 7.0/10

**Financial News**
1. [Eric Trump-backed robot startup misses payroll after CEO&\#x27;s $4.6 million home loan](#item-finance-news-1) ⭐️ 7.0/10
2. [Commerce Secretary Lutnick faces questions over Nvidia ties as his family&\#x27;s firm cut its stake](#item-finance-news-2) ⭐️ 7.0/10
3. [Nvidia board not considering Jensen Huang&\#x27;s return, sources say](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [vLLM v0.34.0 ships extensible KV cache by default and removes Model Runner V1](https://github.com/vllm-project/vllm/releases/tag/v0.34.0) ⭐️ 8.0/10

vLLM v0.34.0 is a major release built from 1,061 commits by 412 contributors, including 120 new contributors. It adds 10 new models such as Mistral Large 4, MiniMax-M3.1-Flash, and NVIDIA Nemotron-3.5-Transcribe, and enables the extensible KV cache by default on CUDA and ROCm, sizing the cache from memory actually free after CUDA graph capture and warmup rather than an estimate. The release reports larger caches and higher throughput—for example, MiniMax-M3 on H200 grows from 433k to 672k tokens—along with speedups on Blackwell and MI355X, including up to 1.95× decode on 4×GB200 for Step5 NVFP4 MoE. Model Runner V1 has been removed, making Model Runner V2 the only GPU runner, and several breaking changes require action before upgrading.

github · khluu · Nov 16, 23:22

**「Why this release matters」** vLLM is a widely used open-source inference and serving engine for large language models, and its release notes are the primary record of how its GPU execution path, memory management, and model support change between versions. The v0.34.0 changes build directly on earlier direction: vLLM 0.31 had already made Model Runner V2 the default, and this release completes that transition by removing Model Runner V1, while also turning on extensible KV-cache sizing by default. Operators upgrading from older deployments should therefore review the breaking-change list before installing, especially the new default 64 block size, the gpu\_memory\_utilization default of 1.0, and the requirement for huggingface\_hub &gt;= 2.0.0.

**「Upgrade actions」** Existing deployments must review breaking changes before upgrading: remove the VLLM\_USE\_V2\_MODEL\_RUNNER=0 flag \(it now fails at startup\), pass --block-size 16 to keep the old default block size of 16 \(the new default is 64\), and pass --gpu-memory-utilization 0.9 or --no-enable-extensible-kv-cache to retain previous KV cache sizing since gpu\_memory\_utilization now defaults to 1.0. Additional breaking changes include the removal of ROCm 7.2 artifacts \(use ROCm 10.0\), a new requirement for huggingface\_hub &gt;= 2.0.0 \(plus tokenizers &gt;= 0.23.3 and timm &gt;= 1.0.30\), removal of QuTLASS/fp\_quant and Marlin W4A8, and removal of Keye-VL models. Teams should also note the trade-off that per-token decode latency can rise on some models \(TPOT +6–18% on some H200 models at concurrency 128\) with the new default KV cache behavior.

<details><summary>References</summary>
<ul>
<li><a href="https://vllm.ai/">vLLM</a></li>
<li><a href="https://www.matthewswong.com/en/blog/vllm-0-31-fast-restart-preload-weight-cache/">vLLM 0.31 Release Notes : Fast Restart and Breaking Changes</a></li>

</ul>
</details>

**Tags**: `#vllm`, `#llm-inference`, `#release-notes`, `#gpu-performance`, `#kv-cache`

---

<a id="item-tech-news-2"></a>
### [Optimizely compromise served malware through scripts on Zoom, GitLab, and other major sites](https://blog.report-uri.com/worlds-largest-brands-infected-with-malware-via-optimizely/) ⭐️ 8.0/10

Optimizely was compromised and its JavaScript snippets were used to serve malware to visitors of major customer websites, including Zoom and GitLab. The affected code was delivered through Optimizely&\#x27;s own CDN, and Optimizely&\#x27;s own properties were also hit: the snippets for www.optimizely.com and login.optimizely.com carried the malicious code. It remains unclear how the attacker obtained write access across many unrelated customer projects; possibilities include a compromised Optimizely system or a compromised credential with cross-customer access. The incident has prompted renewed scrutiny of third-party JavaScript and tag-management security.

hackernews · kristjansson · Nov 16, 23:00 · [Discussion](https://news.ycombinator.com/item?id=50524767)

**「Why third-party script compromises matter」** Optimizely is a widely used experimentation and tag-management platform whose JavaScript snippets are embedded by many large websites, so a compromise of its delivery pipeline can propagate malicious code to visitors of those customer sites. The reported incident follows a broader pattern of software supply-chain attacks, in which attackers abuse a trusted dependency, vendor, or distribution channel rather than targeting each victim site directly. GitLab&\#x27;s own security guidance notes that a single compromised dependency can have serious real-world consequences, which is why third-party scripts and vendor access controls are central to this incident.

**「Impact」** Visitors to 178 organizations using Optimizely Web—including Zoom, GitLab, the BBC, CNN, Salesforce, IKEA, HSBC, Equifax, and Air France—were exposed to malicious JavaScript planted in the platform&\#x27;s scripts on 16 November 2026. Engineering and security teams should audit third-party tag managers and experimentation snippets, restrict who can deploy them, and consider vendoring or otherwise isolating vendor scripts rather than loading them directly from a provider&\#x27;s CDN. The incident also puts pressure on Optimizely to explain how attackers obtained write access across so many unrelated customer projects, since its CDN served exactly what it was given and even its own login and main sites carried the code.

**「Community discussion」** Commenters focused on the risks of giving marketing teams easy script deployment: stickfigure argued that Google Tag Manager&\#x27;s convenience led to large amounts of third-party JavaScript on news sites and said teams should re-evaluate that model. skybrian questioned the attack chain, asking why sites such as CNN and BBC would handle cryptocurrency or credit-card data on the same websites, or whether a browser security bug was involved. mcoliver called for accountability and argued that Optimizely and high-traffic sites should have used safeguards such as phased rollouts, automatic security checks, and vendored scripts rather than relying directly on vendor-hosted code. eax-eip emphasized that Optimizely&\#x27;s CDN served exactly what it was given, so this was not CDN cache poisoning, and noted that Optimizely&\#x27;s own sites were affected. thought-gap suggested NoScript as a way to reduce exposure to potentially malicious third-party content.

<details><summary>References</summary>
<ul>
<li><a href="https://handbook.gitlab.com/handbook/security/best-practices/supply-chain-security-for-dependencies/">Supply Chain Security for Open Source Dependencies and Libraries</a></li>
<li><a href="https://cybersecuritynews.com/optimizely-websites-hijacked/">Hackers Infect 178 Major Websites via Optimizely to Steal ...</a></li>
<li><a href="https://gizmodo.com/sprawling-malware-attack-reportedly-affects-zoom-cnn-fox-news-peacock-and-170-others-2000840831">Sprawling Malware Attack Reportedly Affects Zoom, CNN, Fox ...</a></li>

</ul>
</details>

**Tags**: `#security`, `#supply-chain`, `#optimizely`, `#third-party-scripts`, `#incident-response`

---

<a id="item-tech-news-3"></a>
### [Jiff 1.0: Rust datetime library reaches stable release](https://burntsushi.net/jiff/) ⭐️ 8.0/10

Jiff, a datetime library for Rust by Andrew Gallant \(burntsushi\), has reached version 1.0, marking its first stable release. The release signals that the library&\#x27;s API is considered stable and ready for production use, positioning it as a modern alternative to the widely used Chrono crate. Community discussion on Hacker News highlights strong interest, with the former Chrono maintainer praising the design and some users asking about advanced time-scale support such as TAI and UT1 for scientific applications.

hackernews · burntsushi · Nov 16, 16:53 · [Discussion](https://news.ycombinator.com/item?id=50519744)

**「Background」** Jiff is a datetime library for Rust created by Andrew Gallant \(BurntSushi\), and its 1.0 release is the point at which the project&\#x27;s API is intended to become stable. In Rust, a 1.0 release is especially meaningful because it signals a commitment to long-term compatibility, which matters for datetime APIs where small design mistakes can be hard to fix later. Jiff is often discussed alongside Chrono, the long-established Rust datetime library that many projects have used by default.

**「Why it matters」** For Rust developers, Jiff 1.0 provides a stable, production-ready option for handling dates, times, and time zones — a notoriously difficult problem in software engineering. Teams currently using Chrono or hand-rolled time handling may evaluate Jiff as a replacement, particularly for new projects where a clean, modern API and civil-time correctness \(time zones, DST, etc.\) matter. Adoption will likely depend on ecosystem fit, feature coverage, and long-term maintenance.

**「Community reaction」** The former Chrono maintainer \(quodlibetor\) explained they took over Chrono hoping to improve its API but faced resistance to change, leading to burnout, and expressed gratitude for Jiff&\#x27;s design. Other commenters praised burntsushi&\#x27;s library quality and appreciated the project&\#x27;s honest documentation about when Jiff is not the right tool, while one user working on orbital simulations asked how Jiff handles alternative time scales like TAI and UT1.

<details><summary>References</summary>
<ul>
<li><a href="https://burntsushi.net/jiff/">A datetime library for Rust - Andrew Gallant&#x27;s Blog</a></li>

</ul>
</details>

**Tags**: `#Rust`, `#datetime`, `#libraries`, `#open source`, `#software engineering`

---

<a id="item-tech-news-4"></a>
### [US and Nine Countries Sign San Francisco Declaration on AI Supply Chain Security](https://www.state.gov/releases/office-of-the-spokesman/2026/11/the-san-francisco-declaration-on-the-secure-foundations-of-enduring-prosperity/) ⭐️ 8.0/10

On November 15, 2026, the United States and nine partner countries—Australia, India, Israel, Japan, South Korea, Qatar, Singapore, the United Arab Emirates, and the United Kingdom—signed the San Francisco Declaration on the Secure Foundations of Enduring Prosperity. The declaration frames economic security as the foundation of national security and commits the signatories to jointly protect the sensitive technologies and critical infrastructure that support the superintelligence \(SI\) supply chain. It establishes five working groups covering innovation policy frameworks, applications of SI in critical sectors, full-stack SI supply chain collaboration, secure harbors and supply chain security hubs, and SI safety and resilience. This is a policy declaration and coordination framework rather than a shipped technical capability or binding enforcement mechanism.

telegram · zaihuapd · Nov 16, 10:40

**「Background」** The declaration was signed on November 15, 2026, at the Pax Silica Founders Retreat in San Francisco, convened by U.S. Under Secretary of State for Economic Affairs Jacob Helberg. It frames economic security as national security and aims to reduce participating countries&\#x27; reliance on U.S. adversaries for critical minerals, AI models, and semiconductor chips.

**「Why It Matters」** For companies and researchers in the AI hardware, semiconductor, and critical-infrastructure sectors, the declaration signals a move toward coordinated export, investment-screening, and supply-chain security policies across a bloc spanning the US, key Asian semiconductor economies, and Gulf partners. Organizations involved in advanced AI development or chip supply chains should watch the working groups&\#x27; outputs, as alignment among these governments could shape where sensitive AI compute, models, and infrastructure can be built, sold, and operated. The inclusion of Qatar, the UAE, and Singapore alongside traditional allies also suggests an effort to secure data center and energy resources for AI buildout under shared security arrangements.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/San_Francisco_Declaration_on_the_Secure_Foundations_of_Enduring_Prosperity">San Francisco Declaration on the Secure Foundations of Enduring Prosperity</a></li>
<li><a href="https://www.investing.com/news/world-news/us-nine-nations-sign-san-francisco-declaration-on-ai-security-5028448">U.S., nine nations sign San Francisco declaration on AI security By...</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#supply chain security`, `#geopolitics`, `#semiconductors`, `#international cooperation`

---

<a id="item-tech-news-5"></a>
### [Amazon says AI agents stole API keys to fund more model calls](https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/) ⭐️ 8.0/10

Amazon reported that attackers used the open-source Artex penetration-testing framework to drive AI agents that stole API keys from publicly exposed AI applications, including LiteLLM and Dify. The keys were validated and pooled, then used to pay for additional large-model calls, making the operation self-funding. Amazon said the campaign began on October 3 and was detected and blocked on November 5 by MadPot, its decoy network. With medium confidence, Amazon attributed the activity to a China-linked threat group, said not every listed target was confirmed compromised, and notified potentially affected AWS customers.

telegram · zaihuapd · Nov 16, 13:00

**「Background」** Artex is an open-source agentic AI penetration-testing framework, and MadPot is Amazon&\#x27;s globally distributed network of decoy threat sensors used to observe attacker behavior. In this campaign, reported by Amazon as running from Oct. 3 to Nov. 5, 2026, Artex-driven AI agents targeted publicly exposed AI applications such as LiteLLM and Dify, stealing API keys that were validated and pooled to pay for further LLM calls. The agents&\#x27; operating memory was captured when their requests reached MadPot decoy sensors configured to appear as vulnerable AI services.

**「What this means for AI application operators」** Teams running LiteLLM, One API, Dify, or similar AI gateways and agent platforms should treat any instance reachable from the public internet as a direct target for API-key theft, not just a web application risk. The reported campaign used stolen provider keys to pay for further model calls, so exposure can translate directly into unexpected LLM spending and abuse of downstream provider accounts. Operators should remove public exposure where possible, rotate stored provider keys, restrict key permissions, and monitor for anomalous model usage; Amazon said it notified possibly affected AWS customers, but non-AWS deployments need to check their own exposure. The reported campaign began on October 3 and was blocked by Amazon&\#x27;s MadPot decoy network on November 5, so logs from that period may reveal prior access.

<details><summary>References</summary>
<ul>
<li><a href="https://aws.amazon.com/blogs/security/amazon-threat-intelligence-observes-threat-actors-running-cybercrime-campaigns-with-artex-ai-agents/">Amazon Threat Intelligence observes threat actors running ...</a></li>
<li><a href="https://cybernews.com/security/amazon-autonomous-cybercrime-artex-framework/">AI credential theft campaign used stolen API keys to scale</a></li>
<li><a href="https://thehackernews.com/2026/11/amazon-uncovers-ai-agent-campaign.html">Amazon Uncovers AI Agent Campaign Targeting LiteLLM , Dify , and...</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#threat intelligence`, `#API key theft`, `#cloud security`, `#autonomous agents`

---

<a id="item-tech-news-6"></a>
### [US extends AI chip export controls to remote access](https://www.reuters.com/legal/litigation/us-issues-rule-protect-advanced-ai-chips-being-accessed-remotely-2026-11-16/) ⭐️ 8.0/10

On November 16, the U.S. Commerce Department issued a temporary final rule extending export controls on advanced AI chips and servers to remote access, aiming to prevent circumvention through third-country data centers. The rule also adds license requirements for re-exporting AI chips to Indonesia, Malaysia, Singapore, Thailand, and Brazil, according to The Verge. The Commerce Department&\#x27;s Bureau of Industry and Security \(BIS\) is the relevant export-control authority, and the source item says the rule was drafted with leadership from the Treasury Department and the National Security Council. Because it is a temporary final rule, it takes effect without a prior public-comment period, though the item does not specify its effective date or duration.

telegram · zaihuapd · Nov 16, 14:44

**「Background」** The U.S. Commerce Department&\#x27;s Bureau of Industry and Security \(BIS\) already restricts exports of advanced AI chips and servers, but those controls were aimed at physical shipments. The new temporary final rule extends that framework to remote access, targeting the practice of Chinese companies leasing or calling advanced computing power—such as Nvidia&\#x27;s—from data centers in third countries. Bloomberg, CNN, and CNBC reported the same-day move, with CNBC describing it as the first U.S. policy response to the Nvidia scandal that led CEO Jensen Huang to resign the week before.

**「Impact on AI developers and cloud providers」** Chinese AI developers and other users that relied on renting advanced Nvidia compute from overseas data centers—especially in Malaysia, Thailand, and similar third countries—will face a new licensing barrier, because the rule extends U.S. export controls to remote access rather than only physical chip shipments. Cloud and data-center operators reselling access to U.S. advanced AI chips will need to treat remote compute sales as export-controlled activity, and re-exports to Indonesia, Malaysia, Singapore, Thailand, and Brazil will require licenses. Organizations using such offshore capacity should review whether their existing compute arrangements remain compliant and expect reduced availability of unrestricted remote access to advanced U.S. AI chips.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/us-moves-to-limit-remote-access-to-advanced-ai-chips">US Moves to Curb China’s Remote Access to Nvidia’s AI Chips</a></li>
<li><a href="https://edition.cnn.com/2026/11/16/politics/ai-chips-restrictions-china">Trump administration tightens restrictions on flow of AI chips ahead of...</a></li>
<li><a href="https://www.cnbc.com/2026/11/16/nvidia-commerce-china-lutnick.html">Nvidia fallout: Commerce targets loophole for China&#x27;s data center use</a></li>
<li><a href="https://www.politico.com/news/2026/11/16/commerce-closes-chinas-backdoor-to-nvidia-chips-after-white-house-steps-in-01167199">Commerce closes China’s backdoor to Nvidia chips after White ...</a></li>
<li><a href="https://techcrunch.com/2026/11/16/us-tightens-ai-chip-export-controls-to-deter-chinese-companies-from-accessing-compute-remotely/">US tightens AI chip export controls to deter Chinese ...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#US policy`, `#semiconductors`, `#geopolitics`

---

<a id="item-tech-news-7"></a>
### [Carnegie Mellon launches free CS Learn lecture series on YouTube](https://www.cs.cmu.edu/learn/) ⭐️ 7.0/10

Carnegie Mellon University has launched CS Learn, a free YouTube-based collection of full computer science course lectures. The program is run by Phillip Compeau of CMU&\#x27;s Griffin School of Computer Science and is releasing full semesters of lectures from current CMU courses, with one course premiering each day during launch week and more courses planned for January. A small team can produce the material because several CMU students built tools that automate much of the production work. The launch includes courses such as Tianqi Chen&\#x27;s ML Systems and the 15-259 Probability and Computing course.

hackernews · pcompeau · Nov 16, 20:43 · [Discussion](https://news.ycombinator.com/item?id=50522980)

**「Background」** Carnegie Mellon&\#x27;s School of Computer Science is a leading computer science institution, and its courses—such as 15-112, 15-259 Probability and Computing, and Tianqi Chen&\#x27;s ML Systems—already have a public footprint through student projects, textbooks, and online materials. The new CS Learn effort extends that visibility by publishing full semesters of current course lectures on YouTube, following the open-courseware model popularized by MIT about 25 years earlier but using student-built automation tools to reduce production work.

**「Impact」** Self-learners and developers can now watch complete CMU course lectures for free, including Tianqi Chen&\#x27;s Machine Learning Systems, rather than relying on isolated talks or paid materials. The practical limitation is that lectures alone may not be enough: commenters note that projects, notes, and feedback are often needed to make courseware useful, so learners should check whether CS Learn provides those materials. The automated production tooling also makes it feasible for a small CMU team to publish more courses, with additional courses planned for January.

**「Community reaction」** Commenters welcomed the release, with alumni specifically interested in ML Systems and Probability and Computing, and some requested additional courses such as distributed systems, operating systems, and statistics. Others argued that lectures alone are not enough: ecshafer said courseware such as projects, slides, and feedback mechanisms is important, and warned that introductory courses are often published while advanced courses are left out. JSR\_FDED framed the material as valuable in the AI era because understanding fundamentals helps people use AI effectively.

<details><summary>References</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=zxg7O8dWBHk">CMU 15-112 Term Project - Fall 2016 - YouTube</a></li>
<li><a href="https://www.cmu.edu/admission/majors-programs/school-of-computer-science">School of Computer Science - Undergraduate Admission - Carnegie ...</a></li>
<li><a href="https://www.youtube.com/watch?v=LkCZlsAuQNA">Machine Learning Systems - YouTube Tianqi Chen Tianqi Chen | Teaching | Carnegie Mellon University Teaching - tqchen.com Machine Learning Systems - Carnegie Mellon University Tianqi Chen | Carnegie Mellon University Computer Science ...</a></li>

</ul>
</details>

**Tags**: `#education`, `#computer science`, `#open courseware`, `#machine learning`, `#Carnegie Mellon`

---

<a id="item-tech-news-8"></a>
### [Windows 11 Telemetry Reportedly Identifies Developers&\#x27; Coding Agents and Tools](https://xusheng.dev/posts/windows-coding-agent-telemetry/) ⭐️ 7.0/10

A blog post by cwaffles reports that Windows 11 telemetry can identify which coding agents and developer tools a user runs. According to the post, developer-tool usage can be sent to Microsoft when &quot;optimal telemetry&quot; is enabled, which the author says is on by default. The reported remedy is to disable diagnostic data under Settings → Privacy &amp; security → Diagnostics &amp; feedback. The claim comes from a personal blog rather than Microsoft documentation or an independent audit, so the exact fields collected and how they are transmitted are not established by the supplied material.

hackernews · cwaffles · Nov 16, 22:58 · [Discussion](https://news.ycombinator.com/item?id=50524736)

**「Background」** Windows 11 has long included a Diagnostics &amp; feedback telemetry system, and the new report claims that its “optimal” level can include identifiers for installed coding agents and developer tools. The discussion also follows Microsoft’s recent push to support AI agents on Windows, including the MXC sandbox announced on October 7, which one commenter said is not yet supported by Claude Code. Community members compared the practice with other software telemetry, such as GPU driver collection and VS Code enterprise telemetry settings.

**「Practical impact for developers」** Developers who want to limit this data collection can turn off optional diagnostics in Windows 11 by going to Settings → Privacy &amp; security → Diagnostics &amp; feedback, as noted in the article discussion. The distinction matters because Windows separates required diagnostic data from optional diagnostic data, and the optional level is what can include richer information about installed and used software; some telemetry settings are more limited on Windows Home than Pro. Organizations with stricter privacy or software-inventory requirements may also want to review Group Policy or mobile device management controls for diagnostic data rather than relying only on the local Settings toggle.

**「Community reaction」** In the Hacker News discussion, some readers treated the report as another reason to move to Linux, with one commenter saying most single-player games already work well on Linux in 2026 while multiplayer remains less reliable, and another advising that switching typically takes about a week for web-centric workflows. Others pushed back on the alarm: dannyw argued that Intel, AMD, and NVIDIA drivers can also collect executable names and paths unless opted out, and that Chrome and even Debian&\#x27;s opt-in popularity-contest package can collect comparable information. herf took a more sympathetic view of Microsoft&\#x27;s motive, arguing that Windows has been slow to provide AI-agent sandboxing—citing Microsoft&\#x27;s October 7 launch of &quot;MXC&quot; and saying Claude Code does not yet support it—so non-invasive telemetry could help prioritize platform work, though this remains the commenter&\#x27;s interpretation rather than a confirmed Microsoft position.

<details><summary>References</summary>
<ul>
<li><a href="https://code.visualstudio.com/docs/enterprise/telemetry">Manage telemetry in enterprise environments</a></li>
<li><a href="https://www.youtube.com/watch?v=mOeBjArKMYY">How Much Data Does Windows 11 Really Collect? - YouTube</a></li>

</ul>
</details>

**Tags**: `#privacy`, `#telemetry`, `#windows`, `#developer-tools`, `#ai-agents`

---

<a id="item-tech-news-9"></a>
### [Microsoft says July software fix caused major Exchange email outage](https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026) ⭐️ 7.0/10

Microsoft attributed a large Exchange/Outlook email outage to a software defect introduced by a July fix, according to The Register&\#x27;s incident report. The company&\#x27;s explanation prompted technical discussion about why the defect escaped testing, how service capacity was affected, and how Microsoft recovered the platform. The report is an incident analysis rather than a claim of a new product capability, and the supplied material does not include Microsoft&\#x27;s full post-mortem or precise customer-impact figures.

hackernews · Bender · Nov 16, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50517321)

**「Background」** Microsoft has attributed a recent worldwide Microsoft 365 email outage to a software defect introduced in a July code change, which reportedly combined with other infrastructure issues to trigger a cascading failure affecting more than 80% of its networking gateway servers. Reporting indicates engineers had to patch the faulty change rather than simply roll it back, and that lower-end test environments passed the July code while failing to expose a concurrency problem that appeared in higher-end production machines.

**「Why it matters operationally」** For organizations running Exchange Online or dependent on Microsoft 365 email, the incident highlights that a months-old maintenance change can trigger a platform-wide availability failure and that recovery may be constrained by load and infrastructure behavior. Teams relying on the service may want to review their own outage communications, fallback procedures, and assumptions about Microsoft&\#x27;s ability to shed load or restore capacity quickly.

**「What engineers are debating」** Commenters focused on recovery strategy and testing rather than the outage itself. One compared recovery to an electrical “black start,” while another asked why Microsoft could not deliberately drop or limit connections by client IP ranges to reduce load and bring servers back gradually. Another commenter said the notable issue was that a relatively low-end test environment passed the July code but did not expose a concurrency bug present in higher-end production hardware, asking whether that trade-off is common.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theregister.com/saas/2026/11/16/microsoft-blames-monster-email-outage-on-software-defect-introduced-in-july-fix/5310026">Microsoft blames monster email outage on software defect ...</a></li>
<li><a href="https://www.bleepingcomputer.com/news/microsoft/microsoft-says-months-old-bug-caused-global-microsoft-365-outage/">Microsoft says months-old bug caused global Microsoft 365 outage</a></li>
<li><a href="https://www.neowin.net/news/microsoft-finally-explains-why-outlook-went-down-worldwide-and-it-all-started-in-july/">Microsoft finally explains why Outlook went down worldwide ...</a></li>

</ul>
</details>

**Tags**: `#Microsoft`, `#Outage`, `#Exchange`, `#Incident Analysis`, `#Cloud Infrastructure`

---

<a id="item-tech-news-10"></a>
### [Marimba turns a frozen Qwen3-ASR encoder into a calibrated speech-question model](https://www.reddit.com/r/MachineLearning/comments/1xxsqro/marimba_a_system_one_model_for_speech_r/) ⭐️ 7.0/10

Marimba is a research speech-understanding system that reuses a frozen Qwen3-ASR-0.6B encoder: one pass over each 8-second audio window answers typed questions such as yes/no, multiple-choice, or score queries with calibrated probabilities. The authors report that on the same 1,000 public questions it matches or beats the much larger Qwen3-Omni \(30B-A3B\) on 6 of 9 tests, while Qwen3-Omni remains better on Speech Commands. Specific reported results include 100% language ID on 300 FLEURS clips, speaker-change AUROC of 0.966–0.980 on AMI and VoxConverse, and speaker count above pyannote 3.1. The paper, Apache-2.0 weights, code, and a demo are available, but the system does not generalize to unseen tasks: on CochlScene scene classification every head is at chance, and its turn-end readout trails Smart Turn v3.2 on Smart Turn&\#x27;s own test set \(AUROC 0.930 vs 0.982\).

reddit · r/MachineLearning · /u/solanotodesch · Nov 16, 15:47

**「Background」** Marimba builds on Qwen3-ASR-0.6B, a compact automatic speech recognition encoder, and reuses its frozen representations instead of training a new end-to-end audio model. The approach contrasts with large multimodal speech-language models such as Qwen3-Omni \(30B-A3B\), which answer open-ended audio questions but require far more compute per query. It also follows prior work on typed decision models, which return calibrated probabilities over declared options rather than free-form text; Marimba extends that idea to speech by pairing one encoder pass over each 8-second window with lightweight task-specific readouts.

**「Practical impact」** For speech and ML practitioners, Marimba offers a way to reuse one frozen Qwen3-ASR-0.6B encoder pass per 8-second window for multiple typed audio questions—term spotting, language ID, turn-end, speaker change, and speaker count—instead of running a much larger multimodal model such as Qwen3-Omni 30B-A3B for each task. The reported gains are strongest in language ID \(100% on 300 FLEURS clips\) and speaker-change detection \(AUROC 0.966–0.980 on AMI and VoxConverse, above ECAPA\), while turn-end detection trails Smart Turn v3.2 on its own test set \(0.930 vs 0.982 AUROC\) and the model fails to generalize to unseen tasks such as CochlScene scene classification. Teams can try it now via the Apache-2.0 weights on Hugging Face, the GitHub repo, the hosted demo, or \`pip install marimba-audio\`, but should validate it on their own domains before relying on it, especially for out-of-distribution tasks.

**「Community discussion」** The author asks whether scoring ASR hypotheses plus calibration is a fair baseline for term spotting compared with a dedicated keyword-spotting model, and how turn-end detection should be evaluated beyond Smart Turn&\#x27;s data. No substantive community comments are available in the supplied material, so these questions remain open.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.18330">[2611.18330] Marimba: A System One Model for Speech - arXiv.org</a></li>
<li><a href="https://arxiv.org/html/2611.18330v1">marimba: A System One Model for Speech - arXiv.org</a></li>
<li><a href="https://arxiv.org/pdf/2601.21337v1">Qwen3-ASR Technical Report - arXiv.org</a></li>
<li><a href="https://arxiv.org/abs/2601.21337">[2601.21337] Qwen3-ASR Technical Report - arXiv.org GitHub - QwenLM/Qwen3-ASR: Qwen3-ASR is an open-source series ... GitHub - QwenLM/Qwen3-Omni: Qwen3-omni is a natively end-to ... Marimba: a frozen 0.6B ASR backbone beats 30B… · AGI Hunt Qwen/Qwen3-Omni-30B-A3B-Captioner · Hugging Face Qwen/Qwen3-Omni-30B-A3B-Instruct · Hugging Face</a></li>

</ul>
</details>

**Tags**: `#speech recognition`, `#machine learning`, `#audio understanding`, `#model efficiency`, `#research paper`

---

<a id="item-tech-news-11"></a>
### [Duetto steers a pretrained music transformer into a real-time jazz partner](https://www.reddit.com/r/MachineLearning/comments/1xxkyh3/steering_a_pretrained_music_transformer_at/) ⭐️ 7.0/10

A developer introduced duetto, a real-time MIDI jazz accompaniment system that uses the pretrained Anticipatory Music Transformer \(Thickstun et al., 2023\) without fine-tuning. The system treats the player&\#x27;s notes and the model&\#x27;s notes as one event sequence, and before each sampled note a rule layer masks disallowed choices—such as off-beat bass notes or pitches outside a hand&\#x27;s register—and biases likely ones, such as current chord tones or guide tones on downbeats. Phrases come from the Weimar Jazz Database, segmented at soloists&\#x27; breaths and transposed to the tune&\#x27;s chords; in the Autumn Leaves demo at 160 bpm, about 61% of solo notes came from quoted phrases or the theme, with the rest generated by the model. Performance is about 12 ms per note with the medium model and 18 ms with the large model on an RTX 3080 Ti, while the large model runs at roughly 90 ms per note on a Jetson Orin Nano; the code is available free for noncommercial use.

reddit · r/MachineLearning · /u/GGAllin43 · Nov 16, 09:19

**「Background」** The Anticipatory Music Transformer, introduced by Thickstun et al. in 2023, is a pretrained model trained on the Lakh MIDI dataset that can generate music continuations and perform infilling tasks such as producing accompaniment to a given melody. Duetto builds on that capability but adds a sampling-time control layer: a rule-based logit masker and biaser that constrains the pretrained model note by note, rather than fine-tuning it. The quoted phrases come from the Weimar Jazz Database, a public collection of hundreds of manually transcribed and annotated jazz solos used in music information retrieval research.

**「Why it matters」** For musicians and developers exploring interactive symbolic music generation, duetto shows that sampling-time logit masking and biasing can control a pretrained music model in real time without training a new model. The practical trade-off is control stability: the author reports that the system can drift away from the player, its responses are hard to predict, and the balance between model behavior and rule constraints is fragile—too much bias sounds like a phrase book, while too little stops sounding like jazz.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2306.08620">[2306.08620] Anticipatory Music Transformer - arXiv.org</a></li>
<li><a href="https://github.com/jthickstun/anticipation">GitHub - jthickstun/anticipation: Anticipatory Autoregressive ... Anticipatory Music Transformer - arXiv.org Anticipatory Music Transformer - G-CLef @ CMU Anticipation and the Anticipatory Music Transformer Anticipatory Music Transformer - John Thickstun</a></li>
<li><a href="https://jazzomat.hfm-weimar.de/dbformat/dboverview.html">Weimar Jazz Database (WJazzD) — The Jazzomat Research Project</a></li>
<li><a href="https://hal.science/hal-03864122/document">The Jazz Ontology: A semantic model and large-scale RDF...</a></li>

</ul>
</details>

**Tags**: `#machine-learning`, `#music-generation`, `#transformers`, `#real-time-systems`, `#constrained-decoding`

---

<a id="item-tech-news-12"></a>
### [山东大学团队提出哥德巴赫猜想首个条件性证明](https://mrc.sdu.edu.cn/info/1018/2193.htm) ⭐️ 7.0/10

山东大学李嘉民、刘建亚在论文中提出，在狄利克雷 L 函数广义黎曼猜想成立，并满足两种附加谱假设之一时，可证明所有充分大的偶数都能表示为两个素数之和，且这两个素数位于该偶数的三分之一至三分之二之间。论文称这是首个覆盖所有充分大偶数的二元哥德巴赫猜想条件性证明，但不是无条件证明，单靠广义黎曼猜想也不足以推出结论。所用方法不同于经典筛法和圆法。

telegram · zaihuapd · Nov 16, 16:01

**「Background」** The binary Goldbach conjecture asks whether every even integer greater than 2 is the sum of two primes, and it remains unproved in full. Related partial results include Chen&\#x27;s theorem, which proves that every sufficiently large even number is the sum of a prime and a number with at most two prime factors; a June 2026 arXiv paper announced an unconditional “\(1 + 1.9\)” result, while the new Shandong work instead claims a conditional route to the full “prime + prime” statement for all sufficiently large even numbers under GRH and extra spectral assumptions.

**「研究意义」** 对解析数论研究者而言，这一结果把二元哥德巴赫问题的条件性证明推进到覆盖所有充分大偶数，并明确指出广义黎曼猜想之外还需要附加谱假设；其方法若经同行验证，可能为后续研究提供不同于筛法和圆法的路径。

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2606.05224">[2606.05224] Theorem $ (1+1.9)$ on the Goldbach Conjecture</a></li>
<li><a href="https://arxiv.org/pdf/2606.05224">Theorem (1+1.9) on the Goldbach Conjecture - arXiv.org</a></li>

</ul>
</details>

**Tags**: `#number theory`, `#Goldbach conjecture`, `#Riemann hypothesis`, `#mathematics research`, `#conditional proof`

---

<a id="item-tech-news-13"></a>
### [Chinese AI firms reportedly limit offensive cyber capabilities in new models](https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models) ⭐️ 7.0/10

Bloomberg reports that major Chinese AI companies, including Alibaba, Tencent, and Moonshot AI, have reduced offensive cyberattack capabilities in their newest models while improving defensive performance. Alibaba&\#x27;s latest flagship Qwen model is not open-weight, so users cannot download and customize the full version. The change is linked to a draft export-control rule published by China&\#x27;s Ministry of Commerce last month that would prohibit exporting AI tools capable of attacking critical infrastructure or government networks. Tencent reportedly cut cyber features before releasing Hy4 this month.

telegram · zaihuapd · Nov 17, 02:20

**「Background」** The development follows a draft export-control rule published by China&\#x27;s Ministry of Commerce last month that would prohibit exporting AI tools capable of attacking critical infrastructure or government networks. Against that backdrop, major Chinese AI developers have been adjusting their newest models: Alibaba&\#x27;s latest flagship Qwen is not open-weight, so users cannot download and customize the full version, and Tencent reportedly cut cyber features before releasing Hy4 this month.

**「Why it matters」** If the draft rule is finalized, developers and enterprises outside China may face restrictions on obtaining Chinese AI models or tools with advanced cyber capabilities, while users of Alibaba&\#x27;s Qwen may lose the ability to run or modify unrestricted full-weight versions locally. Organizations evaluating these models should watch the final export-control text and check whether the versions available to them retain the cyber functions they need.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-16/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models">China’s Top AI Firms Limit Cyber Capabilities in Latest Models</a></li>
<li><a href="https://www.business-standard.com/world-news/chinese-ai-firms-scale-back-cyber-capabilities-amid-proposed-export-ban-126111700190_1.html">Chinese AI firms scale back cyber capabilities amid proposed ...</a></li>
<li><a href="https://www.kucoin.com/news/flash/china-s-top-ai-firms-limit-cyber-capabilities-in-latest-models">China&#x27;s Top AI Firms Limit Cyber Capabilities in Latest Models</a></li>

</ul>
</details>

**Tags**: `#AI policy`, `#cybersecurity`, `#China AI`, `#export controls`, `#model safety`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Eric Trump-backed robot startup misses payroll after CEO&\#x27;s $4.6 million home loan](https://www.cnbc.com/2026/11/14/foundation-payroll-ceo-loan.html) ⭐️ 7.0/10

Foundation Future Industries, a military robotics startup backed by Eric Trump, missed its Oct. 30 payroll, and workers still have not been paid, according to people with direct knowledge of the matter. The cash crunch has drawn internal anger because CEO Sankaet Pathak borrowed $4.6 million from the company last year to buy a Sausalito, California, home.

rss · CNBC Finance · Nov 16, 17:14

**「Background」** CEO Sankaet Pathak previously founded fintech middleman Synapse, whose 2024 collapse left more than 100,000 Americans with a combined $265 million in deposits locked out of FDIC-backed accounts; a bankruptcy trustee said as much as $96 million in customer funds went missing. Foundation, founded in April 2024, acquired Florida-based Boardwalk Robotics in late 2024, and government research contracts won by that firm account for the widely reported $24 million in Pentagon contract claims, according to a person with knowledge of the matter.

**「Why it matters」** The missed payroll puts employees at immediate financial risk and raises governance concerns for investors because Pathak is the company&\#x27;s sole board member and majority shareholder, while he seeks to raise hundreds of millions of dollars at a claimed $3 billion valuation.

**Tags**: `#corporate governance`, `#startup finance`, `#defense industry`, `#payroll crisis`, `#political connections`

---

<a id="item-finance-news-2"></a>
### [Commerce Secretary Lutnick faces questions over Nvidia ties as his family&\#x27;s firm cut its stake](https://www.cnbc.com/2026/11/13/howard-lutnick-nvidia-jensen-huang-china-cantor-fitzgerald.html) ⭐️ 7.0/10

CNBC reports that Commerce Secretary Howard Lutnick is facing scrutiny because Cantor Fitzgerald, the Wall Street firm formerly run by him and now led by his sons, reported a 49% drop in its Nvidia shares—from 3.5 million at the end of 2024 to 1.78 million by March 2026—while he received classified warnings about Nvidia CEO Jensen Huang and resisted a crackdown on a Singapore firm suspected of smuggling Nvidia chips to China. There is no evidence of wrongdoing, and Cantor says the filings reflect client-related positions rather than a directional bet on Nvidia.

rss · CNBC Finance · Nov 16, 12:14

**「Background」** Howard Lutnick left Cantor Fitzgerald, the Wall Street firm now run by his sons Brandon and Kyle, to become commerce secretary in February 2025; the Commerce Department oversees export controls, including the &quot;entity list&quot; of restricted companies. The scrutiny follows Axios reports that Lutnick resisted a crackdown on Megaspeed, a Singapore-based firm suspected of funneling Nvidia AI chips to China, and a classified warning about Nvidia CEO Jensen Huang&\#x27;s ties to a suspected Chinese spy; Huang resigned Thursday, and President Trump says he retains &quot;complete confidence&quot; in Lutnick.

**「Why it matters」** The episode could intensify political and ethics pressure around U.S. export-control decisions affecting Nvidia and its AI-chip partners, and investors may watch Cantor&\#x27;s next quarterly filing, due Monday, for further disclosure.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/16/opinion/nvidia-trump-jensen-huang-lutnick.html">Opinion | The Enraging Hypocrisy at the Heart of the Nvidia Scandal</a></li>
<li><a href="https://www.zerohedge.com/markets/i-dont-know-she-was-spy-all-trump-defends-lutnick-and-jensen-china-trip">&quot;I Don&#x27;t Know That She Was A Spy At All&quot;: Trump Defends Lutnick .....</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Howard Lutnick`, `#Cantor Fitzgerald`, `#export controls`, `#government ethics`

---

<a id="item-finance-news-3"></a>
### [Nvidia board not considering Jensen Huang&\#x27;s return, sources say](https://www.cnbc.com/2026/11/16/nvidia-ceo-jensen-huang.html) ⭐️ 7.0/10

People familiar with the matter told CNBC that Nvidia&\#x27;s board is not considering bringing Jensen Huang back as CEO and is instead focused on investigating his conduct. The board has hired law firm Wachtell Lipton to examine whether his actions endangered national security or company secrets.

telegram · zaihuapd · Nov 17, 01:39

**「Background」** Jensen Huang had been Nvidia&\#x27;s longtime CEO, and the current report says the board is instead focused on a national-security investigation into his conduct rather than any return discussions. The claims come from a person familiar with the matter cited by CNBC, so they are sourced but not an official company statement.

**「Why it matters」** The report, attributed to unnamed sources and not confirmed by Nvidia, raises uncertainty over leadership and governance at one of the world&\#x27;s most valuable chipmakers, which could affect investor confidence and strategic direction.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/16/nvidia-ceo-jensen-huang.html">Nvidia board not considering bringing Huang back as CEO : Source</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#Jensen Huang`, `#corporate governance`, `#CEO succession`, `#board investigation`

---