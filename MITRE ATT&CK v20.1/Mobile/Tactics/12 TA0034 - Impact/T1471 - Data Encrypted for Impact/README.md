# T1471 - Data Encrypted for Impact

[Mobile](../../../README.md) / [Impact](../README.md)

An adversary may encrypt files stored on a mobile device to prevent the user from accessing them. This may be done in order to extract monetary compensation from a victim in exchange for decryption or a decryption key (ransomware) or to render data permanently inaccessible in cases where the key is not saved or transmitted.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1471)

**Tactics**  [Impact](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S0422 - Anubis](../../../Threat%20Intelligence/Software/Malware/S0422%20-%20Anubis.md) — [Anubis](https://attack.mitre.org/software/S0422) can use its ransomware module to encrypt device data and hold it for ransom.(Citation: Cofense Anubis) [Cofense Anubis](https://web.archive.org/web/20231222134431/https://cofense.com/blog/infostealer-keylogger-ransomware-one-anubis-targets-250-android-applications/)
- [S1062 - S.O.V.A.](../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) has code to encrypt device data with AES.(Citation: cleafy_sova_1122) [cleafy_sova_1122](https://www.cleafy.com/cleafy-labs/sova-malware-is-back-and-is-evolving-rapidly)
- [S0298 - Xbot](../../../Threat%20Intelligence/Software/Tools/S0298%20-%20Xbot.md) — [Xbot](https://attack.mitre.org/software/S0298) can encrypt the victim's files in external storage (e.g., SD card) and then request a PayPal cash card as ransom.(Citation: PaloAlto-Xbot) [PaloAlto-Xbot](http://researchcenter.paloaltonetworks.com/2016/02/new-android-trojan-xbot-phishes-credit-cards-and-bank-accounts-encrypts-devices-for-ransom/)

## Detection strategies

- [DET0678 - Detection of Data Encrypted for Impact](../../../Defenses/Detection%20Strategies/DET0678%20-%20Detection%20of%20Data%20Encrypted%20for%20Impact.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-28.html)
