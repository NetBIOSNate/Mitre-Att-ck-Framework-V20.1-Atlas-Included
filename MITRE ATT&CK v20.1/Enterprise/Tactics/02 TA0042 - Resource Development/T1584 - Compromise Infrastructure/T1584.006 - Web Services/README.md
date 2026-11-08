# T1584.006 - Web Services

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1584 - Compromise Infrastructure](../README.md)

Adversaries may compromise access to third-party web services that can be used during targeting. A variety of popular websites exist for legitimate users to register for web-based services, such as GitHub, Twitter, Dropbox, Google, SendGrid, etc. Adversaries may try to take ownership of a legitimate user's access to a web service and use that web service as infrastructure in support of cyber operations. Such web services can be abused during later stages of the adversary lifecycle, such as during Command and Control ([Web Service](https://attack.mitre.org/techniques/T1102)), [Exfiltration Over Web Service](https://attack.mitre.org/techniques/T1567), or [Phishing](https://attack.mitre.org/techniques/T1566).(Citation: Recorded Future Turla Infra 2020) Using common services, such as those offered by Google or Twitter, makes it easier for adversaries to hide in expected noise. By utilizing a web service, particularly when access is stolen from legitimate users, adversaries can make it difficult to physically tie back operations to them. Additionally, leveraging compromised web-based email services may allow adversaries to leverage the trust associated with legitimate domains.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1584/006)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G1012 - CURIUM](../../../../Threat%20Intelligence/Groups/G1012%20-%20CURIUM.md) — [CURIUM](https://attack.mitre.org/groups/G1012) has compromised legitimate websites to enable strategic website compromise attacks.(Citation: PWC Yellow Liderc 2023) [PWC Yellow Liderc 2023](https://www.pwc.com/gx/en/issues/cybersecurity/cyber-threat-intelligence/yellow-liderc-ships-its-scripts-delivers-imaploader-malware.html)
- [G1006 - Earth Lusca](../../../../Threat%20Intelligence/Groups/G1006%20-%20Earth%20Lusca.md) — [Earth Lusca](https://attack.mitre.org/groups/G1006) has compromised Google Drive repositories.(Citation: TrendMicro EarthLusca 2022) [TrendMicro EarthLusca 2022](https://www.trendmicro.com/content/dam/trendmicro/global/en/research/22/a/earth-lusca-employs-sophisticated-infrastructure-varied-tools-and-techniques/technical-brief-delving-deep-an-analysis-of-earth-lusca-operations.pdf)
- [S1138 - Gootloader](../../../../Threat%20Intelligence/Software/Malware/S1138%20-%20Gootloader.md) — [Gootloader](https://attack.mitre.org/software/S1138) can insert malicious scripts to compromise vulnerable content management systems (CMS).(Citation: SentinelOne Gootloader June 2021) [SentinelOne Gootloader June 2021](https://www.sentinelone.com/labs/gootloader-initial-access-as-a-service-platform-expands-its-search-for-high-value-targets/)
- [C0048 - Operation MidnightEclipse](../../../../Threat%20Intelligence/Campaigns/C0048%20-%20Operation%20MidnightEclipse.md) — During [Operation MidnightEclipse](https://attack.mitre.org/campaigns/C0048), threat actors abused compromised AWS buckets to store files.(Citation: Volexity UPSTYLE 2024) [Volexity UPSTYLE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)
- [G0010 - Turla](../../../../Threat%20Intelligence/Groups/G0010%20-%20Turla.md) — [Turla](https://attack.mitre.org/groups/G0010) has frequently used compromised WordPress sites for C2 infrastructure.(Citation: Recorded Future Turla Infra 2020) [Recorded Future Turla Infra 2020](https://www.recordedfuture.com/research/turla-apt-infrastructure)
- [G1035 - Winter Vivern](../../../../Threat%20Intelligence/Groups/G1035%20-%20Winter%20Vivern.md) — [Winter Vivern](https://attack.mitre.org/groups/G1035) has used compromised WordPress sites to host malicious payloads for download.(Citation: SentinelOne WinterVivern 2023) [SentinelOne WinterVivern 2023](https://www.sentinelone.com/labs/winter-vivern-uncovering-a-wave-of-global-espionage/)

## Detection strategies

- [DET0882 - Detection of Web Services](../../../../Defenses/Detection%20Strategies/DET0882%20-%20Detection%20of%20Web%20Services.md)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [Recorded Future Turla Infra 2020](https://www.recordedfuture.com/research/turla-apt-infrastructure)
- [ThreatConnect Infrastructure Dec 2020](https://web.archive.org/web/20221130114004/https://threatconnect.com/blog/infrastructure-research-hunting/)
