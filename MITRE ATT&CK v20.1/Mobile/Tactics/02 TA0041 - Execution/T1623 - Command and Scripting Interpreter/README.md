# T1623 - Command and Scripting Interpreter

[Mobile](../../../README.md) / [Execution](../README.md)

Adversaries may abuse command and script interpreters to execute commands, scripts, or binaries. These interfaces and languages provide ways of interacting with computer systems and are a common feature across many different platforms. Most systems come with some built-in command-line interface and scripting capabilities, for example, Android is a UNIX-like OS and includes a basic [Unix Shell](https://attack.mitre.org/techniques/T1623/001) that can be accessed via the Android Debug Bridge (ADB) or Java’s `Runtime` package.

Adversaries may abuse these technologies in various ways as a means of executing arbitrary commands. Commands and scripts can be embedded in [Initial Access](https://attack.mitre.org/tactics/TA0027) payloads delivered to victims as lure documents or as secondary payloads downloaded from an existing C2. Adversaries may also execute commands through interactive terminals/shells.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1623)

**Tactics**  [Execution](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1623.001 - Unix Shell](T1623.001%20-%20Unix%20Shell/README.md)

## Procedure examples

- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) has plugins for executing shell commands either from the C2 server or a library file called `zt.dylib`.(Citation: MelikovBlackBerry LightSpy 2024)(Citation: Threatfabric LightSpy 2024)(Citation: LinkedIn Dmitry LightSpy 2025) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [MelikovBlackBerry LightSpy 2024](https://blogs.blackberry.com/en/2024/04/lightspy-returns-renewed-espionage-campaign-targets-southern-asia-possibly-india) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [S9040 - NGate](../../../Threat%20Intelligence/Software/Malware/S9040%20-%20NGate.md) — [NGate](https://attack.mitre.org/software/S9040) has used Java to execute a variety of actions, such as loading and verifying runtime configuration and disabling the launcher if decryption or parsing failed.(Citation: CERTPL_NGate_Nov2025) [CERTPL_NGate_Nov2025](https://cert.pl/en/posts/2025/11/analiza-ngate/)
- [S1056 - TianySpy](../../../Threat%20Intelligence/Software/Malware/S1056%20-%20TianySpy.md) — [TianySpy](https://attack.mitre.org/software/S1056) can steal information via malicious JavaScript.(Citation: trendmicro_tianyspy_0122) [trendmicro_tianyspy_0122](https://www.trendmicro.com/en_us/research/22/a/tianyspy-malware-uses-smishing-disguised-as-message-from-telco.html)

## Detection strategies

- [DET0655 - Detection of Command and Scripting Interpreter](../../../Defenses/Detection%20Strategies/DET0655%20-%20Detection%20of%20Command%20and%20Scripting%20Interpreter.md)

## Mitigations

- [M1002 - Attestation](../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Device attestation can often detect jailbroken or rooted devices.
- [M1010 - Deploy Compromised Device Detection Method](../../../Defenses/Mitigations/M1010%20-%20Deploy%20Compromised%20Device%20Detection%20Method.md) — Mobile security products can typically detect jailbroken or rooted devices.

## Sources

- [Samsung Knox Mobile Threat Defense](https://partner.samsungknox.com/mtd)
