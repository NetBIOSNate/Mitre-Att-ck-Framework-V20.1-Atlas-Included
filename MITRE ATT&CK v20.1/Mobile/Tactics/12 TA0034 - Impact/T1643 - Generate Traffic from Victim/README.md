# T1643 - Generate Traffic from Victim

[Mobile](../../../README.md) / [Impact](../README.md)

Adversaries may generate outbound traffic from devices. This is typically performed to manipulate external outcomes, such as to achieve carrier billing fraud or to manipulate app store rankings or ratings. Outbound traffic is typically generated as SMS messages or general web traffic, but may take other forms as well.

If done via SMS messages, Android apps must hold the `SEND_SMS` permission. Additionally, sending an SMS message requires user consent if the recipient is a premium number. Applications cannot send SMS messages on iOS

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1643)

**Tactics**  [Impact](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S0440 - Agent Smith](../../../Threat%20Intelligence/Software/Malware/S0440%20-%20Agent%20Smith.md) — [Agent Smith](https://attack.mitre.org/software/S0440) shows fraudulent ads to generate revenue.(Citation: CheckPoint Agent Smith) [CheckPoint Agent Smith](https://research.checkpoint.com/2019/agent-smith-a-new-species-of-mobile-malware/)
- [S0525 - Android/AdDisplay.Ashas](../../../Threat%20Intelligence/Software/Malware/S0525%20-%20Android%20-%20AdDisplay.Ashas.md) — [Android/AdDisplay.Ashas](https://attack.mitre.org/software/S0525) can generate revenue by automatically displaying ads.(Citation: WeLiveSecurity AdDisplayAshas) [WeLiveSecurity AdDisplayAshas](https://www.welivesecurity.com/2019/10/24/tracking-down-developer-android-adware/)
- [S0293 - BrainTest](../../../Threat%20Intelligence/Software/Malware/S0293%20-%20BrainTest.md) — [BrainTest](https://attack.mitre.org/software/S0293) provided capabilities that allowed developers to use compromised devices to post positive reviews on their own malicious applications as well as download other malicious applications they had submitted to the Play Store.(Citation: Lookout-BrainTest) [Lookout-BrainTest](https://blog.lookout.com/blog/2016/01/06/brain-test-re-emerges/)
- [S0432 - Bread](../../../Threat%20Intelligence/Software/Malware/S0432%20-%20Bread.md) — [Bread](https://attack.mitre.org/software/S0432) can perform SMS fraud on older versions of the malware, and toll fraud on newer versions.(Citation: Google Bread) [Google Bread](https://security.googleblog.com/2020/01/pha-family-highlights-bread-and-friends.html)
- [S1103 - FlixOnline](../../../Threat%20Intelligence/Software/Malware/S1103%20-%20FlixOnline.md) — [FlixOnline](https://attack.mitre.org/software/S1103) can automatically send replies to a user’s incoming WhatsApp messages.(Citation: checkpoint_flixonline_0421) [checkpoint_flixonline_0421](https://research.checkpoint.com/2021/new-wormable-android-malware-spreads-by-creating-auto-replies-to-messages-in-whatsapp/)
- [S0290 - Gooligan](../../../Threat%20Intelligence/Software/Malware/S0290%20-%20Gooligan.md) — [Gooligan](https://attack.mitre.org/software/S0290) can install adware to generate revenue.(Citation: Gooligan Citation) [Gooligan Citation](http://blog.checkpoint.com/2016/11/30/1-million-google-accounts-breached-gooligan/)
- [S0322 - HummingBad](../../../Threat%20Intelligence/Software/Malware/S0322%20-%20HummingBad.md) — [HummingBad](https://attack.mitre.org/software/S0322) can create fraudulent statistics inside the official Google Play Store, and has generated revenue from installing fraudulent apps and displaying malicious advertisements.(Citation: ArsTechnica-HummingBad) [ArsTechnica-HummingBad](http://arstechnica.com/security/2016/07/virulent-auto-rooting-malware-takes-control-of-10-million-android-devices/)
- [S0321 - HummingWhale](../../../Threat%20Intelligence/Software/Malware/S0321%20-%20HummingWhale.md) — [HummingWhale](https://attack.mitre.org/software/S0321) generates revenue by displaying fraudulent ads and automatically installing apps. When victims try to close the ads, [HummingWhale](https://attack.mitre.org/software/S0321) runs in a virtual machine, creating a fake ID that allows the perpetrators to generate revenue.(Citation: ArsTechnica-HummingWhale) [ArsTechnica-HummingWhale](http://arstechnica.com/security/2017/01/virulent-android-malware-returns-gets-2-million-downloads-on-google-play/)
- [S0325 - Judy](../../../Threat%20Intelligence/Software/Malware/S0325%20-%20Judy.md) — [Judy](https://attack.mitre.org/software/S0325) uses infected devices to generate fraudulent clicks on advertisements to generate revenue.(Citation: CheckPoint-Judy) [CheckPoint-Judy](https://blog.checkpoint.com/2017/05/25/judy-malware-possibly-largest-malware-campaign-found-google-play/)
- [S0303 - MazarBOT](../../../Threat%20Intelligence/Software/Malware/S0303%20-%20MazarBOT.md) — [MazarBOT](https://attack.mitre.org/software/S0303) can send messages to premium-rate numbers.(Citation: Tripwire-MazarBOT) [Tripwire-MazarBOT](https://www.tripwire.com/state-of-security/security-data-protection/android-malware-sms/)
- [S0291 - PJApps](../../../Threat%20Intelligence/Software/Malware/S0291%20-%20PJApps.md) — [PJApps](https://attack.mitre.org/software/S0291) has the capability to send messages to premium SMS messages.(Citation: Lookout-EnterpriseApps) [Lookout-EnterpriseApps](https://blog.lookout.com/blog/2016/05/25/spoofed-apps/)
- [S0326 - RedDrop](../../../Threat%20Intelligence/Software/Malware/S0326%20-%20RedDrop.md) — [RedDrop](https://attack.mitre.org/software/S0326) tricks the user into sending SMS messages to premium services and then deletes those messages.(Citation: Wandera-RedDrop) [Wandera-RedDrop](https://web.archive.org/web/20180618225805/https://www.wandera.com/reddrop-malware/)
- [S0419 - SimBad](../../../Threat%20Intelligence/Software/Malware/S0419%20-%20SimBad.md) — [SimBad](https://attack.mitre.org/software/S0419) generates fraudulent advertising revenue by displaying ads in the background and by opening the browser and displaying ads.(Citation: CheckPoint SimBad 2019) [CheckPoint SimBad 2019](https://research.checkpoint.com/simbad-a-rogue-adware-campaign-on-google-play/)
- [S0545 - TERRACOTTA](../../../Threat%20Intelligence/Software/Malware/S0545%20-%20TERRACOTTA.md) — [TERRACOTTA](https://attack.mitre.org/software/S0545) has generated non-human advertising impressions.(Citation: WhiteOps TERRACOTTA) [WhiteOps TERRACOTTA](https://www.whiteops.com/blog/terracotta-android-malware-a-technical-study)
- [S0424 - Triada](../../../Threat%20Intelligence/Software/Malware/S0424%20-%20Triada.md) — [Triada](https://attack.mitre.org/software/S0424) can redirect ad banner URLs on websites visited by the user to specific ad URLs.(Citation: Google Triada June 2019)(Citation: Kaspersky Triada June 2016) [Kaspersky Triada June 2016](https://securelist.com/everyone-sees-not-what-they-want-to-see/74997/) · [Google Triada June 2019](https://security.googleblog.com/2019/06/pha-family-highlights-triada.html)
- [S0494 - Zen](../../../Threat%20Intelligence/Software/Malware/S0494%20-%20Zen.md) — [Zen](https://attack.mitre.org/software/S0494) can simulate user clicks on ads.(Citation: Google Security Zen) [Google Security Zen](https://security.googleblog.com/2019/01/pha-family-highlights-zen-and-its.html)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be advised that applications generally do not require permission to send SMS messages.

## Detection strategies

- [DET0608 - Detection of Generate Traffic from Victim](../../../Defenses/Detection%20Strategies/DET0608%20-%20Detection%20of%20Generate%20Traffic%20from%20Victim.md)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-16.html)
