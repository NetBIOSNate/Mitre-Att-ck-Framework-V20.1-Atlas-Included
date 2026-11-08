# T1516 - Input Injection

[Mobile](../../../README.md) / [Defense Evasion](../README.md)

A malicious application can inject input to the user interface to mimic user interaction through the abuse of Android's accessibility APIs.

[Input Injection](https://attack.mitre.org/techniques/T1516) can be achieved using any of the following methods:

* Mimicking user clicks on the screen, for example to steal money from a user's PayPal account.(Citation: android-trojan-steals-paypal-2fa)
* Injecting global actions, such as `GLOBAL_ACTION_BACK` (programatically mimicking a physical back button press), to trigger actions on behalf of the user.(Citation: Talos Gustuff Apr 2019)
* Inserting input into text fields on behalf of the user. This method is used legitimately to auto-fill text fields by applications such as password managers.(Citation: bitwarden autofill logins)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1516)

**Tactics**  [Defense Evasion](../README.md), [Impact](../../12%20TA0034%20-%20Impact/README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Procedure examples

- [S1094 - BRATA](../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) can insert a given string of text into a data field. [BRATA](https://attack.mitre.org/software/S1094) can abuse the Accessibility Service to interact with other installed applications and inject screen taps to grant permissions.(Citation: securelist_brata_0819)(Citation: mcafee_brata_0421) [mcafee_brata_0421](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/brata-keeps-sneaking-into-google-play-now-targeting-usa-and-spain/) · [securelist_brata_0819](https://securelist.com/spying-android-rat-from-brazil-brata/92775/)
- [S0480 - Cerberus](../../../Threat%20Intelligence/Software/Malware/S0480%20-%20Cerberus.md) — [Cerberus](https://attack.mitre.org/software/S0480) can inject input to grant itself additional permissions without user interaction and to prevent application removal.(Citation: Threat Fabric Cerberus)(Citation: CheckPoint Cerberus) [Threat Fabric Cerberus](https://www.threatfabric.com/blogs/cerberus-a-new-banking-trojan-from-the-underworld.html) · [CheckPoint Cerberus](https://research.checkpoint.com/2020/mobile-as-attack-vector-using-mdm/)
- [S9004 - Crocodilus](../../../Threat%20Intelligence/Software/Malware/S9004%20-%20Crocodilus.md) — [Crocodilus](https://attack.mitre.org/software/S9004) has the ability to perform clicks, swipes (left, right, up and down) on the screen and actions such as “Back,” “Home,” and “Menu.”(Citation: ThreatFabric_Crocodilus_March2025) [ThreatFabric_Crocodilus_March2025](https://www.threatfabric.com/blogs/exposing-crocodilus-new-device-takeover-malware-targeting-android-devices)
- [S0479 - DEFENSOR ID](../../../Threat%20Intelligence/Software/Malware/S0479%20-%20DEFENSOR%20ID.md) — [DEFENSOR ID](https://attack.mitre.org/software/S0479) can abuse the accessibility service to perform actions on behalf of the user, including launching attacker-specified applications to steal data.(Citation: ESET DEFENSOR ID) [ESET DEFENSOR ID](https://www.welivesecurity.com/2020/05/22/insidious-android-malware-gives-up-all-malicious-features-but-one-gain-stealth/)
- [S0423 - Ginp](../../../Threat%20Intelligence/Software/Malware/S0423%20-%20Ginp.md) — [Ginp](https://attack.mitre.org/software/S0423) can inject input to make itself the default SMS handler.(Citation: ThreatFabric Ginp) [ThreatFabric Ginp](https://www.threatfabric.com/blogs/ginp_a_malware_patchwork_borrowing_from_anubis.html)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has abused the Accessibility Service to mimic victims’ actions and to redirect victims to its StubActivity when the victims attempt to use the original, legitimate banking application.(Citation: ZimperiumOrtegaPratapagiri_GodFather_Jun2025) [ZimperiumOrtegaPratapagiri_GodFather_Jun2025](https://zimperium.com/blog/your-mobile-app-their-playground-the-dark-side-of-the-virtualization)
- [S0406 - Gustuff](../../../Threat%20Intelligence/Software/Malware/S0406%20-%20Gustuff.md) — [Gustuff](https://attack.mitre.org/software/S0406) injects the global action `GLOBAL_ACTION_BACK` to mimic pressing the back button to close the application if a call to an open antivirus application is detected.(Citation: Talos Gustuff Apr 2019) [Talos Gustuff Apr 2019](https://blog.talosintelligence.com/2019/04/gustuff-targets-australia.html)
- [S0485 - Mandrake](../../../Threat%20Intelligence/Software/Malware/S0485%20-%20Mandrake.md) — [Mandrake](https://attack.mitre.org/software/S0485) abuses the accessibility service to prevent removing administrator permissions, accessibility permissions, and to set itself as the default SMS handler.(Citation: Bitdefender Mandrake) [Bitdefender Mandrake](https://www.bitdefender.com/files/News/CaseStudies/study/329/Bitdefender-PR-Whitepaper-Mandrake-creat4464-en-EN-interactive.pdf)
- [S0403 - Riltok](../../../Threat%20Intelligence/Software/Malware/S0403%20-%20Riltok.md) — [Riltok](https://attack.mitre.org/software/S0403) injects input to set itself as the default SMS handler by clicking the appropriate places on the screen. It can also close or minimize targeted antivirus applications and the device security settings screen.(Citation: Kaspersky Riltok June 2019) [Kaspersky Riltok June 2019](https://securelist.com/mobile-banker-riltok/91374/)
- [S1062 - S.O.V.A.](../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) can programmatically tap the screen or swipe.(Citation: cleafy_sova_1122) [cleafy_sova_1122](https://www.cleafy.com/cleafy-labs/sova-malware-is-back-and-is-evolving-rapidly)
- [S1055 - SharkBot](../../../Threat%20Intelligence/Software/Malware/S1055%20-%20SharkBot.md) — [SharkBot](https://attack.mitre.org/software/S1055) can use input injection via Accessibility Services to simulate user touch inputs, prevent applications from opening, change device settings, and bypass MFA protections.(Citation: nccgroup_sharkbot_0322) [nccgroup_sharkbot_0322](https://research.nccgroup.com/2022/03/03/sharkbot-a-new-generation-android-banking-trojan-being-distributed-on-google-play-store/)
- [S0545 - TERRACOTTA](../../../Threat%20Intelligence/Software/Malware/S0545%20-%20TERRACOTTA.md) — [TERRACOTTA](https://attack.mitre.org/software/S0545) can inject clicks to launch applications, share posts on social media, and interact with WebViews to perform fraudulent actions.(Citation: WhiteOps TERRACOTTA) [WhiteOps TERRACOTTA](https://www.whiteops.com/blog/terracotta-android-malware-a-technical-study)
- [S0427 - TrickMo](../../../Threat%20Intelligence/Software/Malware/S0427%20-%20TrickMo.md) — [TrickMo](https://attack.mitre.org/software/S0427) can inject input to set itself as the default SMS handler, and to automatically click through pop-ups without giving the user any time to react.(Citation: SecurityIntelligence TrickMo) [SecurityIntelligence TrickMo](https://securityintelligence.com/posts/trickbot-pushing-a-2fa-bypass-app-to-bank-customers-in-germany/)
- [S0494 - Zen](../../../Threat%20Intelligence/Software/Malware/S0494%20-%20Zen.md) — [Zen](https://attack.mitre.org/software/S0494) can simulate user clicks on ads and system prompts to create new Google accounts.(Citation: Google Security Zen) [Google Security Zen](https://security.googleblog.com/2019/01/pha-family-highlights-zen-and-its.html)

## Mitigations

- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — An EMM/MDM can use the Android `DevicePolicyManager.setPermittedAccessibilityServices` method to set an explicit list of applications that are allowed to use Android's accessibility features.
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be warned against granting access to accessibility features, and to carefully scrutinize applications that request this dangerous permission.

## Detection strategies

- [DET0612 - Detection of Input Injection](../../../Defenses/Detection%20Strategies/DET0612%20-%20Detection%20of%20Input%20Injection.md)

## Sources

- [bitwarden autofill logins](https://help.bitwarden.com/article/auto-fill-android/)
- [android-trojan-steals-paypal-2fa](https://www.welivesecurity.com/2018/12/11/android-trojan-steals-money-paypal-accounts-2fa/)
- [Talos Gustuff Apr 2019](https://blog.talosintelligence.com/2019/04/gustuff-targets-australia.html)
