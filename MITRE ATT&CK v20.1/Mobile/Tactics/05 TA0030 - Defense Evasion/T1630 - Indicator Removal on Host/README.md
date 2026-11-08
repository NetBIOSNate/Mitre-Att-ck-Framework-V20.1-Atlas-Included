# T1630 - Indicator Removal on Host

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

Adversaries may delete, alter, or hide generated artifacts on a device, including files, jailbreak status, or the malicious application itself. These actions may interfere with event collection, reporting, or other notifications used to detect intrusion activity. This may compromise the integrity of mobile security solutions by causing notable events or information to go unreported.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1630)

**Tactics**  [Defense Evasion](../README.md)

**Platforms**  [iOS](../../../Platforms/iOS.md), [Android](../../../Platforms/Android.md)

## Sub-techniques

- [T1630.003 - Disguise Root/Jailbreak Indicators](T1630.003%20-%20Disguise%20Root%20-%20Jailbreak%20Indicators/README.md)
- [T1630.002 - File Deletion](T1630.002%20-%20File%20Deletion/README.md)
- [T1630.001 - Uninstall Malicious Application](T1630.001%20-%20Uninstall%20Malicious%20Application/README.md)

## Procedure examples

- [S1083 - Chameleon](../../../Threat%20Intelligence/Software/Malware/S1083%20-%20Chameleon.md) — [Chameleon](https://attack.mitre.org/software/S1083) has removed artifacts of its presence and has the ability to uninstall itself.(Citation: cyble_chameleon_0423) [cyble_chameleon_0423](https://cyble.com/blog/chameleon-a-new-android-malware-spotted-in-the-wild/)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has requested for the `WRITE_EXTERNAL_STORAGE` permission to delete files in the device’s external storage.(Citation: MerkleScience_Godfather_April2023) [MerkleScience_Godfather_April2023](https://www.merklescience.com/blog/the-godfather-android-malware-threat-under-the-lens)
- [C0054 - Operation Triangulation](../../../Threat%20Intelligence/Campaigns/C0054%20-%20Operation%20Triangulation.md) — During [Operation Triangulation](https://attack.mitre.org/campaigns/C0054), the threat actors deleted the initial exploitation message and exploit attachment.(Citation: SecureList OpTriangulation 01Jun2023) [SecureList OpTriangulation 01Jun2023](https://securelist.com/operation-triangulation/109842/)

## Detection strategies

- [DET0651 - Detection of Indicator Removal on Host](../../../Defenses/Detection%20Strategies/DET0651%20-%20Detection%20of%20Indicator%20Removal%20on%20Host.md)

## Mitigations

- [M1002 - Attestation](../../../Defenses/Mitigations/M1002%20-%20Attestation.md) — Attestation can detect unauthorized modifications to devices. Mobile security software can then use this information and take appropriate mitigation action.
- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates typically provide patches for vulnerabilities that could be abused by malicious applications.
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Inform users that device rooting or granting unnecessary access to the accessibility service presents security risks that could be taken advantage of without their knowledge.

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-43.html)
