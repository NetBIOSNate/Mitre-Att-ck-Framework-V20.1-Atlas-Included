# M1009 - Encrypt Network Traffic

[Mobile](../../README.md) / [Mitigations](README.md)

Application developers should encrypt all of their application network traffic using the Transport Layer Security (TLS) protocol to ensure protection of sensitive data and deter network-based attacks. If desired, application developers could perform message-based encryption of data before passing it for TLS encryption.

iOS's App Transport Security feature can be used to help ensure that all application network traffic is appropriately protected. Apple intends to mandate use of App Transport Security  (Citation: TechCrunch-ATS) for all apps in the Apple App Store unless appropriate justification is given.

Android's Network Security Configuration feature similarly can be used by app developers to help ensure that all of their application network traffic is appropriately protected  (Citation: Android-NetworkSecurityConfig).

Use of Virtual Private Network (VPN) tunnels, e.g. using the IPsec protocol, can help mitigate some types of network attacks as well.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1009)

## Mitigated techniques

- [T1638 - Adversary-in-the-Middle](../../Tactics/09%20TA0035%20-%20Collection/T1638%20-%20Adversary-in-the-Middle/README.md)
- [T1422.001 - Internet Connection Discovery](../../Tactics/07%20TA0032%20-%20Discovery/T1422%20-%20System%20Network%20Configuration%20Discovery/T1422.001%20-%20Internet%20Connection%20Discovery/README.md)

## Sources

- [TechCrunch-ATS](https://techcrunch.com/2016/06/14/apple-will-require-https-connections-for-ios-apps-by-the-end-of-2016/)
- [Android-NetworkSecurityConfig](https://developer.android.com/training/articles/security-config.html)
