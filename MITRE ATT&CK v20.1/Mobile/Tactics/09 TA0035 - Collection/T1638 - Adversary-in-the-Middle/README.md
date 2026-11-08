# T1638 - Adversary-in-the-Middle

[Mobile](../../../README.md) / [Collection](../README.md)

Adversaries may attempt to position themselves between two or more networked devices to support follow-on behaviors such as [Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1565/002) or [Endpoint Denial of Service](https://attack.mitre.org/techniques/T1642).  

 

[Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1638) can be achieved through several mechanisms. For example, a malicious application may register itself as a VPN client, effectively redirecting device traffic to adversary-owned resources. Registering as a VPN client requires user consent on both Android and iOS; additionally, a special entitlement granted by Apple is needed for iOS devices. Alternatively, a malicious application with escalation privileges may utilize those privileges to gain access to network traffic.   


 Specific to Android devices, adversary-in-the-disk is a type of AiTM attack where adversaries monitor and manipulate data that is exchanged between applications and external storage.(Citation: mitd_kaspersky)(Citation: mitd_checkpoint)(Citation: mitd_checkpoint_research) To accomplish this, a malicious application firsts requests for access to multimedia files on the device (`READ_EXTERNAL STORAGE` and `WRITE_EXTERNAL_STORAGE`), then the application reads data on the device and/or writes malware to the device. Though the request for access is common, when used maliciously, adversaries may access files and other sensitive data due to abusing the permission. Multiple applications were shown to be vulnerable against this attack; however, scrutiny of permissions and input validations may mitigate this attack.    

Outside of a mobile device, adversaries may be able to capture traffic by employing a rogue base station or Wi-Fi access point. These devices will allow adversaries to capture network traffic after it has left the device, while it is flowing to its destination. On a local network, enterprise techniques could be used, such as [ARP Cache Poisoning](https://attack.mitre.org/techniques/T1557/002) or [DHCP Spoofing](https://attack.mitre.org/techniques/T1557/003).  

 

If applications properly encrypt their network traffic, sensitive data may not be accessible to adversaries, depending on the point of capture. For example, properly implementing Apple’s Application Transport Security (ATS) and Android’s Network Security Configuration (NSC) may prevent sensitive data leaks.(Citation: NSC_Android)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1638)

**Tactics**  [Collection](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Mitigations

- [M1009 - Encrypt Network Traffic](../../../Defenses/Mitigations/M1009%20-%20Encrypt%20Network%20Traffic.md) — Applications that properly encrypt network traffic may evade some forms of AiTM behavior.
- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Recent OS versions have made it more difficult for applications to register as VPN providers.

## Procedure examples

- [S0288 - KeyRaider](../../../Threat%20Intelligence/Software/Malware/S0288%20-%20KeyRaider.md) — Most [KeyRaider](https://attack.mitre.org/software/S0288) samples hook SSLRead and SSLWrite functions in the itunesstored process to intercept device communication with the Apple App Store.(Citation: Skycure-Profiles) [Skycure-Profiles](https://web.archive.org/web/20150203010257/https://www.skycure.com/blog/malicious-profiles-the-sleeping-giant-of-ios-security/)
- [S0407 - Monokle](../../../Threat%20Intelligence/Software/Malware/S0407%20-%20Monokle.md) — [Monokle](https://attack.mitre.org/software/S0407) can install attacker-specified certificates to the device's trusted certificate store, enabling an adversary to perform adversary-in-the-middle attacks.(Citation: Xiao-KeyRaider) [Xiao-KeyRaider](http://researchcenter.paloaltonetworks.com/2015/08/keyraider-ios-malware-steals-over-225000-apple-accounts-to-create-free-app-utopia/)
- [S1062 - S.O.V.A.](../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) has included adversary-in-the-middle capabilities.(Citation: threatfabric_sova_0921) [threatfabric_sova_0921](https://www.threatfabric.com/blogs/sova-new-trojan-with-fowl-intentions.html)

## Detection strategies

- [DET0623 - Detection of Adversary-in-the-Middle](../../../Defenses/Detection%20Strategies/DET0623%20-%20Detection%20of%20Adversary-in-the-Middle.md)

## Sources

- [mitd_checkpoint](https://blog.checkpoint.com/security/man-in-the-disk-a-new-attack-surface-for-android-apps/)
- [mitd_kaspersky](https://usa.kaspersky.com/blog/man-in-the-disk/16089/)
- [NSC_Android](https://www.nowsecure.com/blog/2018/08/15/a-security-analysts-guide-to-network-security-configuration-in-android-p/)
- [mitd_checkpoint_research](https://research.checkpoint.com/androids-man-in-the-disk/)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-3.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-0.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-1.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-8.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/ecosystem-threats/ECO-12.html)
