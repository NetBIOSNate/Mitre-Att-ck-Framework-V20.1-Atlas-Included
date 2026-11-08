# T1593.002 - Search Engines

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1593 - Search Open Websites/Domains](../README.md)

Adversaries may use search engines to collect information about victims that can be used during targeting. Search engine services typically crawl online sites to index content and may provide users with specialized syntax to search for specific keywords or specific types of content (i.e. filetypes).(Citation: SecurityTrails Google Hacking)(Citation: ExploitDB GoogleHacking)

Adversaries may craft various search engine queries depending on what information they seek to gather. Threat actors may use search engines to harvest general information about victims, as well as use specialized queries to look for spillages/leaks of sensitive information such as network details or credentials. Information from these sources may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)), establishing operational resources (ex: [Establish Accounts](https://attack.mitre.org/techniques/T1585) or [Compromise Accounts](https://attack.mitre.org/techniques/T1586)), and/or initial access (ex: [Valid Accounts](https://attack.mitre.org/techniques/T1078) or [Phishing](https://attack.mitre.org/techniques/T1566)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1593/002)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Detection strategies

- [DET0811 - Detection of Search Engines](../../../../Defenses/Detection%20Strategies/DET0811%20-%20Detection%20of%20Search%20Engines.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Procedure examples

- [C0040 - APT41 DUST](../../../../Threat%20Intelligence/Campaigns/C0040%20-%20APT41%20DUST.md) — [APT41 DUST](https://attack.mitre.org/campaigns/C0040) involved use of search engines to research victim servers.(Citation: Google Cloud APT41 2024) [Google Cloud APT41 2024](https://cloud.google.com/blog/topics/threat-intelligence/apt41-arisen-from-dust)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has searched for vulnerabilities, tools, and geopolitical trends on Google to target victims.(Citation: KISA Operation Muzabi) [KISA Operation Muzabi](https://web.archive.org/web/20220328121326/https://boho.or.kr/filedownload.do?attach_file_seq=2695&attach_file_id=EpF2695.pdf)

## Sources

- [SecurityTrails Google Hacking](https://www.recordedfuture.com/threat-intelligence-101/threat-analysis-techniques/google-dorks)
- [ExploitDB GoogleHacking](https://www.exploit-db.com/google-hacking-database)
