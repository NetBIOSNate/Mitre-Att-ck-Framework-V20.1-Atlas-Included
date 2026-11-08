# T1481.001 - Dead Drop Resolver

[Mobile](../../../../README.md) / [Command and Control](../../README.md) / [T1481 - Web Service](../README.md)

Adversaries may use an existing, legitimate external Web service to host information that points to additional command and control (C2) infrastructure. Adversaries may post content, known as a dead drop resolver, on Web services with embedded (and often obfuscated/encoded) domains or IP addresses. Once infected, victims will reach out to and be redirected by these resolvers. 

 

Popular websites and social media, acting as a mechanism for C2, may give a significant amount of cover. This is due to the likelihood that hosts within a network are already communicating with them prior to a compromise. Using common services, such as those offered by Google or Twitter, makes it easier for adversaries to hide in expected noise. Web service providers commonly use SSL/TLS encryption, giving adversaries an added level of protection. 

 

Use of a dead drop resolver may also protect back-end C2 infrastructure from discovery through malware binary analysis, or enable operational resiliency (since this infrastructure may be dynamically changed).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1481/001)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Detection strategies

- [DET0617 - Detection of Dead Drop Resolver](../../../../Defenses/Detection%20Strategies/DET0617%20-%20Detection%20of%20Dead%20Drop%20Resolver.md)

## Procedure examples

- [S1214 - Android/SpyAgent](../../../../Threat%20Intelligence/Software/Malware/S1214%20-%20Android%20-%20SpyAgent.md) — [Android/SpyAgent](https://attack.mitre.org/software/S1214) has used the Tencent Push Notification Service to receive commands from the C2 server.(Citation: McAfee MoqHao 2019) [McAfee MoqHao 2019](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/moqhao-related-android-spyware-targeting-japan-and-korea-found-on-google-play/)
- [S0310 - ANDROIDOS_ANSERVER.A](../../../../Threat%20Intelligence/Software/Malware/S0310%20-%20ANDROIDOS_ANSERVER.A.md) — [ANDROIDOS_ANSERVER.A](https://attack.mitre.org/software/S0310) uses encrypted content within a blog site for part of its command and control. Specifically, the encrypted content contains URLs for other servers to be used for other aspects of command and control.(Citation: TrendMicro-Anserver) [TrendMicro-Anserver](http://blog.trendmicro.com/trendlabs-security-intelligence/android-malware-uses-blog-posts-as-cc/)
- [S0422 - Anubis](../../../../Threat%20Intelligence/Software/Malware/S0422%20-%20Anubis.md) — [Anubis](https://attack.mitre.org/software/S0422) can retrieve the C2 address from Twitter and Telegram.(Citation: Cofense Anubis)(Citation: Trend Micro Anubis) [Trend Micro Anubis](https://www.trendmicro.com/en_us/research/19/a/google-play-apps-drop-anubis-banking-malware-use-motion-based-evasion-tactics.html) · [Cofense Anubis](https://web.archive.org/web/20231222134431/https://cofense.com/blog/infostealer-keylogger-ransomware-one-anubis-targets-250-android-applications/)
- [S0539 - Red Alert 2.0](../../../../Threat%20Intelligence/Software/Malware/S0539%20-%20Red%20Alert%202.0.md) — [Red Alert 2.0](https://attack.mitre.org/software/S0539) can fetch a backup C2 domain from Twitter if the primary C2 is unresponsive.(Citation: Sophos Red Alert 2.0) [Sophos Red Alert 2.0](https://news.sophos.com/en-us/2018/07/23/red-alert-2-0-android-trojan-targets-security-seekers/)
- [S0318 - XLoader for Android](../../../../Threat%20Intelligence/Software/Malware/S0318%20-%20XLoader%20for%20Android.md) — [XLoader for Android](https://attack.mitre.org/software/S0318) has fetched its C2 address from encoded Twitter names, as well as Instagram and Tumblr.(Citation: TrendMicro-XLoader-FakeSpy) [TrendMicro-XLoader-FakeSpy](https://blog.trendmicro.com/trendlabs-security-intelligence/new-version-of-xloader-that-disguises-as-android-apps-and-an-ios-profile-holds-new-links-to-fakespy/)
