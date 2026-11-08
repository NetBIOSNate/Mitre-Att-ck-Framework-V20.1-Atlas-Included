# T1509 - Non-Standard Port

[Mobile](../../../README.md) / [Command and Control](../README.md)

Adversaries may generate network traffic using a protocol and port pairing that are typically not associated. For example, HTTPS over port 8088 or port 587 as opposed to the traditional port 443. Adversaries may make changes to the standard port used by a protocol to bypass filtering or muddle analysis/parsing of network data.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1509)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S0480 - Cerberus](../../../Threat%20Intelligence/Software/Malware/S0480%20-%20Cerberus.md) — [Cerberus](https://attack.mitre.org/software/S0480) communicates with the C2 using HTTP requests over port 8888.(Citation: CheckPoint Cerberus) [CheckPoint Cerberus](https://research.checkpoint.com/2020/mobile-as-attack-vector-using-mdm/)
- [S1083 - Chameleon](../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has communicated over port 7242 using HTTP.(Citation: cyble_chameleon_0423) [cyble_chameleon_0423](https://cyble.com/blog/chameleon-a-new-android-malware-spotted-in-the-wild/)
- [S0405 - Exodus](../../../Threat%20Intelligence/Software/Malware/S0405%20-%20Exodus.md) — [Exodus](https://attack.mitre.org/software/S0405) Two attempts to connect to port 22011 to provide a remote reverse shell.(Citation: SWB Exodus March 2019) [SWB Exodus March 2019](https://web.archive.org/web/20200314194610/https://securitywithoutborders.org/blog/2019/03/29/exodus.html)
- [S0408 - FlexiSpy](../../../Threat%20Intelligence/Software/Tools/S0408%20-%20FlexiSpy.md) — [FlexiSpy](https://attack.mitre.org/software/S0408) can communicate with the command and control server over ports 12512 and 12514.(Citation: FortiGuard-FlexiSpy) [FortiGuard-FlexiSpy](https://d3gpjj9d20n0p3.cloudfront.net/fortiguard/research/Dig%20Deep%20into%20FlexiSpy%20for%20Android%28white%20paper%29_KaiLu.pdf)
- [S0463 - INSOMNIA](../../../Threat%20Intelligence/Software/Malware/S0463%20-%20INSOMNIA.md) — [INSOMNIA](https://attack.mitre.org/software/S0463) has communicated with the C2 using HTTPS requests over ports 43111, 43223, and 43773.(Citation: Volexity Insomnia) [Volexity Insomnia](https://www.volexity.com/blog/2020/04/21/evil-eye-threat-actor-resurfaces-with-ios-exploit-and-updated-implant/)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has communicated with the C2 using ports 52202, 51200, 43201, 43202, 43203, and 21202.(Citation: Threatfabric LightSpy 2023) [Threatfabric LightSpy 2023](https://www.threatfabric.com/blogs/lightspy-mapt-mobile-payment-system-attack)
- [S0485 - Mandrake](../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) has communicated with the C2 server over TCP port 7777.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0539 - Red Alert 2.0](../../../Threat%20Intelligence/Software/Malware/S0539%20-%20Red%20Alert%202.0.md) — [Red Alert 2.0](https://attack.mitre.org/software/S0539) has communicated with the C2 using HTTP requests over port 7878.(Citation: Sophos Red Alert 2.0) [Sophos Red Alert 2.0](https://news.sophos.com/en-us/2018/07/23/red-alert-2-0-android-trojan-targets-security-seekers/)

## Detection strategies

- [DET0706 - Detection of Non-Standard Port](../../../Defenses/Detection%20Strategies/DET0706%20-%20Detection%20of%20Non-Standard%20Port.md)
