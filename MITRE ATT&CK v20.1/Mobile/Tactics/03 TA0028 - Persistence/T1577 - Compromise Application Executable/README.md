# T1577 - Compromise Application Executable

[Mobile](../../../README.md) / [Persistence](../README.md)

Adversaries may modify applications installed on a device to establish persistent access to a victim. These malicious modifications can be used to make legitimate applications carry out adversary tasks when these applications are in use.

There are multiple ways an adversary can inject malicious code into applications. One method is by taking advantages of device vulnerabilities, the most well-known being Janus, an Android vulnerability that allows adversaries to add extra bytes to APK (application) and DEX (executable) files without affecting the file's signature. By being able to add arbitrary bytes to valid applications, attackers can seamlessly inject code into genuine executables without the user's knowledge.(Citation: Guardsquare Janus)

Adversaries may also rebuild applications to include malicious modifications. This can be achieved by decompiling the genuine application, merging it with the malicious code, and recompiling it.(Citation: CheckPoint Agent Smith)

Adversaries may also take action to conceal modifications to application executables and bypass user consent. These actions include altering modifications to appear as an update or exploiting vulnerabilities that allow activities of the malicious application to run inside a system application.(Citation: CheckPoint Agent Smith)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1577)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S0440 - Agent Smith](../../../Threat%20Intelligence/Software/Malware/S0440%20-%20Agent%20Smith.md) — [Agent Smith](https://attack.mitre.org/software/S0440) can inject fraudulent ad modules into existing applications on a device.(Citation: CheckPoint Agent Smith) [CheckPoint Agent Smith](https://research.checkpoint.com/2019/agent-smith-a-new-species-of-mobile-malware/)
- [S1079 - BOULDSPY](../../../Threat%20Intelligence/Software/Malware/S1079%20-%20BOULDSPY.md) — [BOULDSPY](https://attack.mitre.org/software/S1079) can inject malicious packages into applications already existing on an infected device.(Citation: lookout_bouldspy_0423) [lookout_bouldspy_0423](https://www.lookout.com/blog/iranian-spyware-bouldspy)
- [S0311 - YiSpecter](../../../Threat%20Intelligence/Software/Malware/S0311%20-%20YiSpecter.md) — [YiSpecter](https://attack.mitre.org/software/S0311) has replaced device apps with ones it has downloaded.(Citation: paloalto_yispecter_1015) [paloalto_yispecter_1015](https://unit42.paloaltonetworks.com/yispecter-first-ios-malware-attacks-non-jailbroken-ios-devices-by-abusing-private-apis/)

## Mitigations

- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates frequently contain patches to vulnerabilities.
- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Many vulnerabilities related to injecting code into existing applications have been patched in previous Android releases.

## Detection strategies

- [DET0649 - Detection of Compromise Application Executable](../../../Defenses/Detection%20Strategies/DET0649%20-%20Detection%20of%20Compromise%20Application%20Executable.md)

## Sources

- [Guardsquare Janus](https://www.guardsquare.com/en/blog/new-android-vulnerability-allows-attackers-modify-apps-without-affecting-their-signatures)
- [CheckPoint Agent Smith](https://research.checkpoint.com/2019/agent-smith-a-new-species-of-mobile-malware/)
