# T1583.004 - Server

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1583 - Acquire Infrastructure](../README.md)

Adversaries may buy, lease, rent, or obtain physical servers that can be used during targeting. Use of servers allows an adversary to stage, launch, and execute an operation. During post-compromise activity, adversaries may utilize servers for various tasks, such as watering hole operations in [Drive-by Compromise](https://attack.mitre.org/techniques/T1189), enabling [Phishing](https://attack.mitre.org/techniques/T1566) operations, or facilitating [Command and Control](https://attack.mitre.org/tactics/TA0011). Instead of compromising a third-party [Server](https://attack.mitre.org/techniques/T1584/004) or renting a [Virtual Private Server](https://attack.mitre.org/techniques/T1583/003), adversaries may opt to configure and run their own servers in support of operations. Free trial periods of cloud servers may also be abused.(Citation: Free Trial PurpleUrchin)(Citation: Freejacked) 

Adversaries may only need a lightweight setup if most of their activities will take place using online infrastructure. Or, they may need to build extensive infrastructure if they want to test, communicate, and control other aspects of their activities on their own systems.(Citation: NYTStuxnet)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1583/004)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0871 - Detection of Server](../../../../Defenses/Detection%20Strategies/DET0871%20-%20Detection%20of%20Server.md)

## Procedure examples

- [G1012 - CURIUM](../../../../Threat%20Intelligence/Groups/G1012%20-%20CURIUM.md) — [CURIUM](https://attack.mitre.org/groups/G1012) has created dedicated servers for command and control and exfiltration purposes.(Citation: PWC Yellow Liderc 2023) [PWC Yellow Liderc 2023](https://www.pwc.com/gx/en/issues/cybersecurity/cyber-threat-intelligence/yellow-liderc-ships-its-scripts-delivers-imaploader-malware.html)
- [G1006 - Earth Lusca](../../../../Threat%20Intelligence/Groups/G1006%20-%20Earth%20Lusca.md) — [Earth Lusca](https://attack.mitre.org/groups/G1006) has acquired multiple servers for some of their operations, using each server for a different role.(Citation: TrendMicro EarthLusca 2022) [TrendMicro EarthLusca 2022](https://www.trendmicro.com/content/dam/trendmicro/global/en/research/22/a/earth-lusca-employs-sophisticated-infrastructure-varied-tools-and-techniques/technical-brief-delving-deep-an-analysis-of-earth-lusca-operations.pdf)
- [G0093 - GALLIUM](../../../../Threat%20Intelligence/Groups/G0093%20-%20GALLIUM.md) — [GALLIUM](https://attack.mitre.org/groups/G0093) has used Taiwan-based servers that appear to be exclusive to [GALLIUM](https://attack.mitre.org/groups/G0093).(Citation: Microsoft GALLIUM December 2019) [Microsoft GALLIUM December 2019](https://www.microsoft.com/security/blog/2019/12/12/gallium-targeting-global-telecom/)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has purchased hosting servers with virtual currency and prepaid cards.(Citation: KISA Operation Muzabi) [KISA Operation Muzabi](https://web.archive.org/web/20220328121326/https://boho.or.kr/filedownload.do?attach_file_seq=2695&attach_file_id=EpF2695.pdf)
- [G1020 - Mustard Tempest](../../../../Threat%20Intelligence/Groups/G1020%20-%20Mustard%20Tempest.md) — [Mustard Tempest](https://attack.mitre.org/groups/G1020) has acquired servers to host second-stage payloads that remain active for a period of either days, weeks, or months.(Citation: SentinelOne SocGholish Infrastructure November 2022) [SentinelOne SocGholish Infrastructure November 2022](https://www.sentinelone.com/labs/socgholish-diversifies-and-expands-its-malware-staging-infrastructure-to-counter-defenders/)
- [C0002 - Night Dragon](../../../../Threat%20Intelligence/Campaigns/C0002%20-%20Night%20Dragon.md) — During [Night Dragon](https://attack.mitre.org/campaigns/C0002), threat actors purchased hosted services to use for C2.(Citation: McAfee Night Dragon) [McAfee Night Dragon](https://scadahacker.com/library/Documents/Cyber_Events/McAfee%20-%20Night%20Dragon%20-%20Global%20Energy%20Cyberattacks.pdf)
- [C0022 - Operation Dream Job](../../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — During [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) acquired servers to host their malicious tools.(Citation: ESET Lazarus Jun 2020) [ESET Lazarus Jun 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_Operation_Interception.pdf)
- [C0006 - Operation Honeybee](../../../../Threat%20Intelligence/Campaigns/C0006%20-%20Operation%20Honeybee.md) — For [Operation Honeybee](https://attack.mitre.org/campaigns/C0006), at least one identified persona was used to register for a free account for a control server.(Citation: McAfee Honeybee) [McAfee Honeybee](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/mcafee-uncovers-operation-honeybee-malicious-document-campaign-targeting-humanitarian-aid-groups/)
- [C0014 - Operation Wocao](../../../../Threat%20Intelligence/Campaigns/C0014%20-%20Operation%20Wocao.md) — For [Operation Wocao](https://attack.mitre.org/campaigns/C0014), the threat actors purchased servers with Bitcoin to use during the operation.(Citation: FoxIT Wocao December 2019) [FoxIT Wocao December 2019](https://www.fox-it.com/media/kadlze5c/201912_report_operation_wocao.pdf)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) has leased servers from resellers instead of leasing infrastructure directly from hosting companies to enable its operations.(Citation: US District Court Indictment GRU Unit 74455 October 2020) [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download)
- [G1057 - ShinyHunters](../../../../Threat%20Intelligence/Groups/G1057%20-%20ShinyHunters.md) — [ShinyHunters](https://attack.mitre.org/groups/G1057) has used five IP addresses to host Python SimpleHTTP servers on port 8888, which exposed staging materials, customized agents, and .bash_history files.(Citation: Google_SHOracle_Jun2026) [Google_SHOracle_Jun2026](https://cloud.google.com/blog/topics/threat-intelligence/shinyhunters-targets-education-sector-oracle-exploit)
- [G1056 - TeamPCP](../../../../Threat%20Intelligence/Groups/G1056%20-%20TeamPCP.md) — [TeamPCP](https://attack.mitre.org/groups/G1056) has leased infrastructure specifically for offensive operations including Google assets in AS396982.(Citation: Hunt.io TeamPCP Toolkit MAY 2026)(Citation: FBI TeamPCP JUL 2026) [FBI TeamPCP JUL 2026](https://www.ic3.gov/CSA/2026/260702.pdf) · [Hunt.io TeamPCP Toolkit MAY 2026](https://hunt.io/blog/teampcp-python-toolkit-firescale-github-c2-takedown)
- [G1055 - VOID MANTICORE](../../../../Threat%20Intelligence/Groups/G1055%20-%20VOID%20MANTICORE.md) — [VOID MANTICORE](https://attack.mitre.org/groups/G1055) has leveraged backend servers within Iran.(Citation: DOJ FBI Handala Hack March 2026) [DOJ FBI Handala Hack March 2026](https://www.justice.gov/opa/media/1431956/dl?inline)

## Sources

- [Freejacked](https://sysdig.com/blog/googles-vertex-ai-platform-freejacked/)
- [Free Trial PurpleUrchin](https://unit42.paloaltonetworks.com/purpleurchin-steals-cloud-resources/)
- [Koczwara Beacon Hunting Sep 2021](https://michaelkoczwara.medium.com/cobalt-strike-c2-hunting-with-shodan-c448d501a6e2)
- [Mandiant SCANdalous Jul 2020](https://cloud.google.com/blog/topics/threat-intelligence/scandalous-external-detection-using-network-scan-data-and-automation/)
- [ThreatConnect Infrastructure Dec 2020](https://web.archive.org/web/20221130114004/https://threatconnect.com/blog/infrastructure-research-hunting/)
- [NYTStuxnet](https://www.nytimes.com/2011/01/16/world/middleeast/16stuxnet.html)
