# T1630.003 - Disguise Root/Jailbreak Indicators

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1630 - Indicator Removal on Host](../README.md)

An adversary could use knowledge of the techniques used by security software to evade detection.(Citation: Brodie)(Citation: Tan) For example, some mobile security products perform compromised device detection by searching for particular artifacts such as an installed "su" binary, but that check could be evaded by naming the binary something else. Similarly, polymorphic code techniques could be used to evade signature-based detection.(Citation: Rastogi)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1630/003)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Detection strategies

- [DET0710 - Detection of Disguise Root/Jailbreak Indicators](../../../../Defenses/Detection%20Strategies/DET0710%20-%20Detection%20of%20Disguise%20Root%20-%20Jailbreak%20Indicators.md)

## Sources

- [Brodie](https://media.blackhat.com/eu-13/briefings/Brodie/bh-eu-13-lacoon-attacks-mdm-brodie-wp.pdf)
- [Rastogi](http://pages.cs.wisc.edu/~vrastogi/static/papers/rcj13b.pdf)
- [Tan](http://www.blackhat.com/us-16/briefings.html#bad-for-enterprise-attacking-byod-enterprise-mobile-security-solutions)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/emm-threats/EMM-5.html)
