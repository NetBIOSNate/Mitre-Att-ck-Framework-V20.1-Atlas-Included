# T1608.006 - SEO Poisoning

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1608 - Stage Capabilities](../README.md)

Adversaries may poison mechanisms that influence search engine optimization (SEO) to further lure staged capabilities towards potential victims. Search engines typically display results to users based on purchased ads as well as the site’s ranking/score/reputation calculated by their web crawlers and algorithms.(Citation: Atlas SEO)(Citation: MalwareBytes SEO)

To help facilitate [Drive-by Compromise](https://attack.mitre.org/techniques/T1189), adversaries may stage content that explicitly manipulates SEO rankings in order to promote sites hosting their malicious payloads (such as [Drive-by Target](https://attack.mitre.org/techniques/T1608/004)) within search engines. Poisoning SEO rankings may involve various tricks, such as stuffing keywords (including in the form of hidden text) into compromised sites. These keywords could be related to the interests/browsing habits of the intended victim(s) as well as more broad, seasonably popular topics (e.g. elections, trending news).(Citation: ZScaler SEO)(Citation: Atlas SEO)

In addition to internet search engines (such as Google), adversaries may also aim to manipulate specific in-site searches for developer platforms (such as GitHub) to deceive users towards [Supply Chain Compromise](https://attack.mitre.org/techniques/T1195) lures. In-site searches will rank search results according to their own algorithms and metrics such as popularity(Citation: Chexmarx-seo) which may be targeted and gamed by malicious actors.(Citation: Checkmarx-oss-seo)

Adversaries may also purchase or plant incoming links to staged capabilities in order to boost the site’s calculated relevance and reputation.(Citation: MalwareBytes SEO)(Citation: DFIR Report Gootloader)

SEO poisoning may also be combined with evasive redirects and other cloaking mechanisms (such as measuring mouse movements or serving content based on browser user agents, user language/localization settings, or HTTP headers) in order to feed SEO inputs while avoiding scrutiny from defenders.(Citation: ZScaler SEO)(Citation: Sophos Gootloader)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1608/006)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0881 - Detection of SEO Poisoning](../../../../Defenses/Detection%20Strategies/DET0881%20-%20Detection%20of%20SEO%20Poisoning.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Procedure examples

- [G1020 - Mustard Tempest](../../../../Threat%20Intelligence/Groups/G1020%20-%20Mustard%20Tempest.md) — [Mustard Tempest](https://attack.mitre.org/groups/G1020) has poisoned search engine results to return fake software updates in order to distribute malware.(Citation: Microsoft Ransomware as a Service)(Citation: SocGholish-update) [SocGholish-update](https://www.proofpoint.com/us/blog/threat-insight/part-1-socgholish-very-real-threat-very-fake-update) · [Microsoft Ransomware as a Service](https://www.microsoft.com/en-us/security/blog/2022/05/09/ransomware-as-a-service-understanding-the-cybercrime-gig-economy-and-how-to-protect-yourself/)
- [G1059 - NIMBUS MANTICORE](../../../../Threat%20Intelligence/Groups/G1059%20-%20NIMBUS%20MANTICORE.md) — [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has utilized Search Engine Optimization (SEO) poisoning to deliver malware to unsuspecting victims.(Citation: CheckPoint_NimbusManticore_May2026) [NIMBUS MANTICORE](https://attack.mitre.org/groups/G1059) has also registered dozens of domains that link to a typosquatted domain to generate link-based reputation signals and incorporated keyword stuffing to improve search ranking.(Citation: CheckPoint_NimbusManticore_May2026) [CheckPoint_NimbusManticore_May2026](https://research.checkpoint.com/2026/fast-and-furious-nimbus-manticore-operations-during-the-iranian-conflict/)

## Sources

- [MalwareBytes SEO](https://www.malwarebytes.com/blog/news/2018/05/seo-poisoning-is-it-worth-it)
- [Atlas SEO](https://atlas-cybersecurity.com/cyber-threats/threat-actors-use-search-engine-optimization-tactics-to-redirect-traffic-and-install-malware/)
- [Sophos Gootloader](https://news.sophos.com/en-us/2021/03/01/gootloader-expands-its-payload-delivery-options/)
- [DFIR Report Gootloader](https://thedfirreport.com/2022/05/09/seo-poisoning-a-gootloader-story/)
- [ZScaler SEO](https://www.zscaler.com/blogs/security-research/ubiquitous-seo-poisoning-urls-0)
- [Chexmarx-seo](https://zero.checkmarx.com/the-github-black-market-gaming-the-star-ranking-game-fc42f5913fb7)
- [Checkmarx-oss-seo](https://checkmarx.com/blog/new-technique-to-trick-developers-detected-in-an-open-source-supply-chain-attack/)
