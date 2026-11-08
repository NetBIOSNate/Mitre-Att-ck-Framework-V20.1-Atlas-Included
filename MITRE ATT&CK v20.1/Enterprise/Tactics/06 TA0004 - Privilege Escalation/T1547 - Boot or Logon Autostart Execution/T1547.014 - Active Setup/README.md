# T1547.014 - Active Setup

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1547 - Boot or Logon Autostart Execution](../README.md)

Adversaries may achieve persistence by adding a Registry key to the Active Setup of the local machine. Active Setup is a Windows mechanism that is used to execute programs when a user logs in. The value stored in the Registry key will be executed after a user logs into the computer.(Citation: Klein Active Setup 2010) These programs will be executed under the context of the user and will have the account's associated permissions level.

Adversaries may abuse Active Setup by creating a key under <code> HKLM\SOFTWARE\Microsoft\Active Setup\Installed Components\</code> and setting a malicious value for <code>StubPath</code>. This value will serve as the program that will be executed when a user logs into the computer.(Citation: Mandiant Glyer APT 2010)(Citation: Citizenlab Packrat 2015)(Citation: FireEye CFR Watering Hole 2012)(Citation: SECURELIST Bright Star 2015)(Citation: paloalto Tropic Trooper 2016)

Adversaries can abuse these components to execute malware, such as remote access tools, to maintain persistence through system reboots. Adversaries may also use [Masquerading](https://attack.mitre.org/techniques/T1036) to make the Registry entries look as if they are associated with legitimate programs.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1547/014)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0012 - PoisonIvy](../../../../Threat%20Intelligence/Software/Malware/S0012%20-%20PoisonIvy.md) — [PoisonIvy](https://attack.mitre.org/software/S0012) creates a Registry key in the Active Setup pointing to a malicious executable.(Citation: Microsoft PoisonIvy 2017)(Citation: paloalto Tropic Trooper 2016)(Citation: FireEye Regsvr32 Targeting Mongolian Gov) [Microsoft PoisonIvy 2017](https://www.microsoft.com/en-us/wdsi/threats/malware-encyclopedia-description?Name=Backdoor%3aWin32%2fPoisonivy.E) · [paloalto Tropic Trooper 2016](https://unit42.paloaltonetworks.com/unit42-tropic-trooper-targets-taiwanese-government-and-fossil-fuel-provider-with-poison-ivy/) · [FireEye Regsvr32 Targeting Mongolian Gov](https://www.fireeye.com/blog/threat-research/2017/02/spear_phishing_techn.html)

## Detection strategies

- [DET0312 - Detect Active Setup Persistence via StubPath Execution](../../../../Defenses/Detection%20Strategies/DET0312%20-%20Detect%20Active%20Setup%20Persistence%20via%20StubPath%20Execution.md)

## Sources

- [SECURELIST Bright Star 2015](https://securelist.com/whos-really-spreading-through-the-bright-star/68978/)
- [Mandiant Glyer APT 2010](https://digital-forensics.sans.org/summit-archives/2010/35-glyer-apt-persistence-mechanisms.pdf)
- [FireEye CFR Watering Hole 2012](https://web.archive.org/web/20201024230407/https://www.fireeye.com/blog/threat-research/2012/12/council-foreign-relations-water-hole-attack-details.html)
- [Klein Active Setup 2010](https://helgeklein.com/blog/2010/04/active-setup-explained/)
- [paloalto Tropic Trooper 2016](https://unit42.paloaltonetworks.com/unit42-tropic-trooper-targets-taiwanese-government-and-fossil-fuel-provider-with-poison-ivy/)
- [TechNet Autoruns](https://technet.microsoft.com/en-us/sysinternals/bb963902)
- [Citizenlab Packrat 2015](https://citizenlab.ca/2015/12/packrat-report/)
