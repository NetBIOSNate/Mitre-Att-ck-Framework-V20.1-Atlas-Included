# G0034 - Sandworm Team

[ICS](../../README.md) / [Groups](README.md)

[Sandworm Team](https://attack.mitre.org/groups/G0034) is a destructive threat group that has been attributed to Russia's General Staff Main Intelligence Directorate (GRU) Main Center for Special Technologies (GTsST) military unit 74455.(Citation: US District Court Indictment GRU Unit 74455 October 2020)(Citation: UK NCSC Olympic Attacks October 2020) This group has been active since at least 2009.(Citation: iSIGHT Sandworm 2014)(Citation: CrowdStrike VOODOO BEAR)(Citation: USDOJ Sandworm Feb 2020)(Citation: NCSC Sandworm Feb 2020)

In October 2020, the US indicted six GRU Unit 74455 officers associated with [Sandworm Team](https://attack.mitre.org/groups/G0034) for the following cyber operations: the 2015 and 2016 attacks against Ukrainian electrical companies and government organizations, the 2017 worldwide [NotPetya](https://attack.mitre.org/software/S0368) attack, targeting of the 2017 French presidential campaign, the 2018 [Olympic Destroyer](https://attack.mitre.org/software/S0365) attack against the Winter Olympic Games, the 2018 operation against the Organisation for the Prohibition of Chemical Weapons, and attacks against the country of Georgia in 2018 and 2019.(Citation: US District Court Indictment GRU Unit 74455 October 2020)(Citation: UK NCSC Olympic Attacks October 2020) Some of these were conducted with the assistance of GRU Unit 26165, which is also referred to as [APT28](https://attack.mitre.org/groups/G0007).(Citation: US District Court Indictment GRU Oct 2018)

[MITRE ATT&CK record](https://attack.mitre.org/groups/G0034)

## Aliases

- ELECTRUM
- Telebots
- IRON VIKING
- BlackEnergy (Group)
- Quedagh
- Voodoo Bear
- IRIDIUM
- Seashell Blizzard
- FROZENBARENTS
- APT44

## Software used

- [S0606 - Bad Rabbit](../Software/Malware/S0606%20-%20Bad%20Rabbit.md)
- [S0089 - BlackEnergy](../Software/Malware/S0089%20-%20BlackEnergy.md)
- [S0604 - Industroyer](../Software/Malware/S0604%20-%20Industroyer.md)
- [S1072 - Industroyer2](../Software/Malware/S1072%20-%20Industroyer2.md)
- [S0607 - KillDisk](../Software/Malware/S0607%20-%20KillDisk.md)
- [S0368 - NotPetya](../Software/Malware/S0368%20-%20NotPetya.md)
- [S1010 - VPNFilter](../Software/Malware/S1010%20-%20VPNFilter.md)

## Attributed campaigns

- [C0028 - 2015 Ukraine Electric Power Attack](../Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md)
- [C0025 - 2016 Ukraine Electric Power Attack](../Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md)
- [C0034 - 2022 Ukraine Electric Power Attack](../Campaigns/C0034%20-%202022%20Ukraine%20Electric%20Power%20Attack.md)

## Techniques used

- [T0884 - Connection Proxy](../../Tactics/09%20TA0101%20-%20Command%20and%20Control/T0884%20-%20Connection%20Proxy/README.md)
- [T0819 - Exploit Public-Facing Application](../../Tactics/01%20TA0108%20-%20Initial%20Access/T0819%20-%20Exploit%20Public-Facing%20Application/README.md)
- [T1701.001 - PowerShell](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.001%20-%20PowerShell/README.md)
- [T1701.002 - Windows Command Shell](../../Tactics/02%20TA0104%20-%20Execution/T1701%20-%20Command%20and%20Scripting%20Interpreter/T1701.002%20-%20Windows%20Command%20Shell/README.md)

## Sources

- [Leonard TAG 2023](https://blog.google/threat-analysis-group/ukraine-remains-russias-biggest-cyber-focus-in-2023/)
- [US District Court Indictment GRU Oct 2018](https://www.justice.gov/opa/page/file/1098481/download)
- [Dragos ELECTRUM](https://www.dragos.com/resource/electrum/)
- [F-Secure BlackEnergy 2014](https://blog-assets.f-secure.com/wp-content/uploads/2019/10/15163408/BlackEnergy_Quedagh.pdf)
- [iSIGHT Sandworm 2014](https://www.fireeye.com/blog/threat-research/2016/01/ukraine-and-sandworm-team.html)
- [CrowdStrike VOODOO BEAR](https://www.crowdstrike.com/blog/meet-crowdstrikes-adversary-of-the-month-for-january-voodoo-bear/)
- [Microsoft Threat Actor Naming July 2023](https://learn.microsoft.com/en-us/microsoft-365/security/intelligence/microsoft-threat-actor-naming?view=o365-worldwide)
- [Microsoft Prestige ransomware October 2022](https://www.microsoft.com/en-us/security/blog/2022/10/14/new-prestige-ransomware-impacts-organizations-in-ukraine-and-poland/)
- [InfoSecurity Sandworm Oct 2014](https://www.infosecurity-magazine.com/news/microsoft-zero-day-traced-russian/)
- [NCSC Sandworm Feb 2020](https://www.ncsc.gov.uk/news/ncsc-supports-sandworm-advisory)
- [USDOJ Sandworm Feb 2020](https://2017-2021.state.gov/the-united-states-condemns-russian-cyber-attack-against-the-country-of-georgia/index.html)
- [mandiant_apt44_unearthing_sandworm](https://services.google.com/fh/files/misc/apt44-unearthing-sandworm.pdf)
- [US District Court Indictment GRU Unit 74455 October 2020](https://www.justice.gov/opa/press-release/file/1328521/download)
- [Secureworks IRON VIKING ](https://www.secureworks.com/research/threat-profiles/iron-viking)
- [UK NCSC Olympic Attacks October 2020](https://www.gov.uk/government/news/uk-exposes-series-of-russian-cyber-attacks-against-olympic-and-paralympic-games)
