# T1628.002 - User Evasion

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1628 - Hide Artifacts](../README.md)

Adversaries may attempt to avoid detection by hiding malicious behavior from the user. By doing this, an adversary’s modifications would most likely remain installed on the device for longer, allowing the adversary to continue to operate on that device. 

While there are many ways this can be accomplished, one method is by using the device’s sensors. By utilizing the various motion sensors on a device, such as accelerometer or gyroscope, an application could detect that the device is being interacted with. That way, the application could continue to run while the device is not in use but cease operating while the user is using the device, hiding anything that would indicate malicious activity was ongoing. Accessing the sensors in this way does not require any permissions from the user, so it would be completely transparent.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1628/002)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Procedure examples

- [S1094 - BRATA](../../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can turn off or fake turning off the screen while performing malicious activities.(Citation: securelist_brata_0819) [securelist_brata_0819](https://securelist.com/spying-android-rat-from-brazil-brata/92775/)
- [S0655 - BusyGasper](../../../../Threat%20Intelligence/Software/Malware/S0655%20-%20BusyGasper.md) — [BusyGasper](https://attack.mitre.org/software/S0655) can utilize the device’s sensors to determine when the device is in use and subsequently hide malicious activity. When active, it attempts to hide its malicious activity by turning the screen’s brightness as low as possible and muting the device.(Citation: SecureList BusyGasper) [SecureList BusyGasper](https://securelist.com/busygasper-the-unfriendly-spy/87627/)
- [S9004 - Crocodilus](../../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) has displayed a black screen overlay and has muted the sound of the device to conceal all malicious actions.(Citation: ThreatFabric_Crocodilus_March2025) [ThreatFabric_Crocodilus_March2025](https://www.threatfabric.com/blogs/exposing-crocodilus-new-device-takeover-malware-targeting-android-devices)
- [S1067 - FluBot](../../../../Threat%20Intelligence/Software/Malware/S1067%20-%20FluBot.md) — [FluBot](https://attack.mitre.org/software/S1067) can use `locale.getLanguage()` to choose the language for notifications and avoid user detection.(Citation: proofpoint_flubot_0421) [proofpoint_flubot_0421](https://www.proofpoint.com/us/blog/threat-insight/flubot-android-malware-spreading-rapidly-through-europe-may-hit-us-soon)
- [S1077 - Hornbill](../../../../Threat%20Intelligence/Software/Malware/S1077%20-%20Hornbill.md) — [Hornbill](https://attack.mitre.org/software/S1077) uses an infrequent data upload schedule to avoid user detection and battery drain. It also can delete on-device data after being sent to the C2, and stores collected data in hidden folders on external storage.(Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)
- [S1195 - SpyC23](../../../../Threat%20Intelligence/Software/Malware/S1195%20-%20SpyC23.md) — [SpyC23](https://attack.mitre.org/software/S1195) has used blank screen overlays to hide malicious activity from the user.(Citation: welivesecurity_apt-c-23) [welivesecurity_apt-c-23](https://web.archive.org/web/20201123042131/www.welivesecurity.com/2020/09/30/aptc23-group-evolves-its-android-spyware/)

## Mitigations

- [M1010 - Deploy Compromised Device Detection Method](../../../../Defenses/Mitigations/M1010%20-%20Deploy%20Compromised%20Device%20Detection%20Method.md) — Mobile security products that are part of the Samsung Knox for Mobile Threat Defense program could examine running applications while the device is idle, potentially detecting malicious applications that are running primarily when the device is not being used.

## Detection strategies

- [DET0699 - Detection of User Evasion](../../../../Defenses/Detection%20Strategies/DET0699%20-%20Detection%20of%20User%20Evasion.md)
