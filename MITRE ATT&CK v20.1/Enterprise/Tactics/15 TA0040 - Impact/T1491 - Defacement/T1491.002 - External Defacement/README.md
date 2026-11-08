# T1491.002 - External Defacement

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1491 - Defacement](../README.md)

An adversary may deface systems external to an organization in an attempt to deliver messaging, intimidate, or otherwise mislead an organization or users. [External Defacement](https://attack.mitre.org/techniques/T1491/002) may ultimately cause users to distrust the systems and to question/discredit the system’s integrity. Externally-facing websites are a common victim of defacement; often targeted by adversary and hacktivist groups in order to push a political message or spread propaganda.(Citation: FireEye Cyber Threats to Media Industries)(Citation: Kevin Mandia Statement to US Senate Committee on Intelligence)(Citation: Anonymous Hackers Deface Russian Govt Site) [External Defacement](https://attack.mitre.org/techniques/T1491/002) may be used as a catalyst to trigger events, or as a response to actions taken by an organization or government. Similarly, website defacement may also be used as setup, or a precursor, for future attacks such as [Drive-by Compromise](https://attack.mitre.org/techniques/T1189).(Citation: Trend Micro Deep Dive Into Defacement)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1491/002)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [IaaS](../../../../Platforms/IaaS.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [G1003 - Ember Bear](../../../../Threat%20Intelligence/Groups/G1003%20-%20Ember%20Bear.md) — [Ember Bear](https://attack.mitre.org/groups/G1003) is linked to the defacement of several Ukrainian organization websites.(Citation: Cadet Blizzard emerges as novel threat actor) [Cadet Blizzard emerges as novel threat actor](https://www.microsoft.com/en-us/security/blog/2023/06/14/cadet-blizzard-emerges-as-a-novel-and-distinct-russian-threat-actor/)
- [G0034 - Sandworm Team](../../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) defaced approximately 15,000 websites belonging to Georgian government, non-government, and private sector organizations in 2019.(Citation: US District Court Indictment GRU Unit 74455 October 2020)(Citation: UK NCSC Olympic Attacks October 2020) [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download) · [UK NCSC Olympic Attacks October 2020](https://www.gov.uk/government/news/uk-exposes-series-of-russian-cyber-attacks-against-olympic-and-paralympic-games)

## Detection strategies

- [DET0590 - Behavioral Detection of External Website Defacement across Platforms](../../../../Defenses/Detection%20Strategies/DET0590%20-%20Behavioral%20Detection%20of%20External%20Website%20Defacement%20across%20Platforms.md)

## Mitigations

- [M1053 - Data Backup](../../../../Defenses/Mitigations/M1053%20-%20Data%20Backup.md) — Consider implementing IT disaster recovery plans that contain procedures for taking regular data backups that can be used to restore organizational data.(Citation: Ready.gov IT DRP) Ensure backups are stored off system and is protected from common methods adversaries may use to gain access and destroy the backups to prevent recovery. [Ready.gov IT DRP](https://www.ready.gov/business/implementation/IT)

## Sources

- [Anonymous Hackers Deface Russian Govt Site](https://torrentfreak.com/anonymous-hackers-deface-russian-govt-site-to-protest-web-blocking-nsfw-180512/)
- [FireEye Cyber Threats to Media Industries](https://web.archive.org/web/20210719110553/https://www.fireeye.com/content/dam/fireeye-www/current-threats/pdfs/ib-entertainment.pdf)
- [Kevin Mandia Statement to US Senate Committee on Intelligence](https://www.intelligence.senate.gov/sites/default/files/documents/os-kmandia-033017.pdf)
- [Trend Micro Deep Dive Into Defacement](https://documents.trendmicro.com/assets/white_papers/wp-a-deep-dive-into-defacement.pdf)
