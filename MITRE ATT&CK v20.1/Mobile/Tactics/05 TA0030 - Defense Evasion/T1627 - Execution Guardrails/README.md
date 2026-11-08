# T1627 - Execution Guardrails

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may use execution guardrails to constrain execution or actions based on adversary supplied and environment specific conditions that are expected to be present on the target. Guardrails ensure that a payload only executes against an intended target and reduces collateral damage from an adversary’s campaign. Values an adversary can provide about a target system or environment to use as guardrails may include environment information such as location.(Citation: SWB Exodus March 2019)

Guardrails can be used to prevent exposure of capabilities in environments that are not intended to be compromised or operated within. This use of guardrails is distinct from typical [System Checks](https://attack.mitre.org/techniques/T1633/001). While use of [System Checks](https://attack.mitre.org/techniques/T1633/001) may involve checking for known sandbox values and continuing with execution only if there is no match, the use of guardrails will involve checking for an expected target-specific value and only continuing with execution if there is such a match.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1627)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1627.001 - Geofencing](T1627.001%20-%20Geofencing/README.md)

## Procedure examples

- [S1215 - Binary Validator](../../../Threat%20Intelligence/Software/Malware/S1215%20-%20Binary%20Validator.md) — [Binary Validator](https://attack.mitre.org/software/S1215) has checked if the device is jailbroken.(Citation: SecureList OpTriangulation 23Oct2023) [SecureList OpTriangulation 23Oct2023](https://securelist.com/triangulation-validators-modules/110847/)
- [S9005 - DocSwap](../../../Threat%20Intelligence/Software/Malware/S9005%20-%20DocSwap.md) — [DocSwap](https://attack.mitre.org/software/S9005) has checked if the victim has accessed the malicious URL from a PC. If so, [DocSwap](https://attack.mitre.org/software/S9005) redirected the victim to scan the malicious QR code using a mobile device.(Citation: EnkiWhiteHat_KimsukyDOCSWAP_Dec2025) [EnkiWhiteHat_KimsukyDOCSWAP_Dec2025](https://www.enki.co.kr/en/media-center/blog/kimsuky-distributing-malicious-mobile-app-via-qr-code)

## Detection strategies

- [DET0653 - Detection of Execution Guardrails](../../../Defenses/Detection%20Strategies/DET0653%20-%20Detection%20of%20Execution%20Guardrails.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — New OS releases frequently contain additional limitations or controls around device location access.
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be advised to be extra scrutinous of applications that request location or sensitive phone information permissions, and to deny any permissions requests for applications they do not recognize.

## Sources

- [SWB Exodus March 2019](https://web.archive.org/web/20200314194610/https://securitywithoutborders.org/blog/2019/03/29/exodus.html)
