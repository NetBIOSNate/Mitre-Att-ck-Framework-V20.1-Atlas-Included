# T1636.001 - Calendar Entries

[Mobile](../../../../README.md) / [Collection](../../README.md) / [T1636 - Protected User Data](../README.md)

Adversaries may utilize standard operating system APIs to gather calendar entry data. On Android, this can be accomplished using the Calendar Content Provider. On iOS, this can be accomplished using the `EventKit` framework. 

 

If the device has been jailbroken or rooted, an adversary may be able to access [Calendar Entries](https://attack.mitre.org/techniques/T1636/001) without the user’s knowledge or approval.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1636/001)

**Tactics**  [Collection](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S0405 - Exodus](../../../../Threat%20Intelligence/Software/Malware/S0405%20-%20Exodus.md) — [Exodus](https://attack.mitre.org/software/S0405) Two can exfiltrate calendar events.(Citation: SWB Exodus March 2019) [SWB Exodus March 2019](https://web.archive.org/web/20200314194610/https://securitywithoutborders.org/blog/2019/03/29/exodus.html)
- [S0408 - FlexiSpy](../../../../Threat%20Intelligence/Software/Tools/S0408%20-%20FlexiSpy.md) — [FlexiSpy](https://attack.mitre.org/software/S0408) can collect the device calendars.(Citation: CyberMerchants-FlexiSpy) [CyberMerchants-FlexiSpy](http://www.cybermerchantsofdeath.com/blog/2017/04/22/FlexiSpy.html)
- [S0407 - Monokle](../../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can retrieve calendar event information including the event name, when and where it is taking place, and the description.(Citation: Lookout-Monokle) [Lookout-Monokle](https://www.lookout.com/documents/threat-reports/lookout-discovers-monokle-threat-report.pdf)
- [S0316 - Pegasus for Android](../../../../Threat%20Intelligence/Software/Malware/S0316%20-%20Pegasus%20for%20Android.md) — [Pegasus for Android](https://attack.mitre.org/software/S0316) accesses calendar entries.(Citation: Lookout-PegasusAndroid) [Lookout-PegasusAndroid](https://blog.lookout.com/blog/2017/04/03/pegasus-android/)
- [S0328 - Stealth Mango](../../../../Threat%20Intelligence/Software/Malware/S0328%20-%20Stealth%20Mango.md) — [Stealth Mango](https://attack.mitre.org/software/S0328) uploads calendar events and reminders.(Citation: Lookout-StealthMango) [Lookout-StealthMango](https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf)
- [S1082 - Sunbird](../../../../Threat%20Intelligence/Software/Malware/S1082%20-%20Sunbird.md) — [Sunbird](https://attack.mitre.org/software/S1082) can exfiltrate calendar information.(Citation: lookout_hornbill_sunbird_0221) [lookout_hornbill_sunbird_0221](https://www.lookout.com/blog/lookout-discovers-novel-confucius-apt-android-spyware-linked-to-india-pakistan-conflict)

## Mitigations

- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Calendar access is an uncommonly needed permission, so users should be instructed to use extra scrutiny when granting access to their device calendar.

## Detection strategies

- [DET0674 - Detection of Calendar Entries](../../../../Defenses/Detection%20Strategies/DET0674%20-%20Detection%20of%20Calendar%20Entries.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-13.html)
