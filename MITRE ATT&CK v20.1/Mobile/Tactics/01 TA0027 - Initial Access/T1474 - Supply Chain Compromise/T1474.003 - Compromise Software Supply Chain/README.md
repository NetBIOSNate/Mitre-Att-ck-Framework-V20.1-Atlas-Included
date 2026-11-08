# T1474.003 - Compromise Software Supply Chain

[Mobile](../../../../README.md) / [Initial Access](../../README.md) / [T1474 - Supply Chain Compromise](../README.md)

Adversaries may manipulate application software prior to receipt by a final consumer for the purpose of data or system compromise. Supply chain compromise of software can take place in a number of ways, including manipulation of the application source code, manipulation of the update/distribution mechanism for that software, or replacing compiled releases with a modified version.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1474/003)

**Tactics**  [Initial Access](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Detection strategies

- [DET0721 - Detection of Compromise Software Supply Chain](../../../../Defenses/Detection%20Strategies/DET0721%20-%20Detection%20of%20Compromise%20Software%20Supply%20Chain.md)

## Mitigations

- [M1001 - Security Updates](../../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates may contain patches that inhibit system software compromises.
- [M1004 - System Partition Integrity](../../../../Defenses/Mitigations/M1004%20-%20System%20Partition%20Integrity.md) — Ensure Verified Boot is enabled on devices with that capability.

## Procedure examples

- [S0309 - Adups](../../../../Threat%20Intelligence/Software/Malware/S0309%20-%20Adups.md) — [Adups](https://attack.mitre.org/software/S0309) was pre-installed on Android devices from some vendors.(Citation: NYTimes-BackDoor)(Citation: BankInfoSecurity-BackDoor) [BankInfoSecurity-BackDoor](http://www.bankinfosecurity.com/did-chinese-spyware-linger-in-us-phones-a-9534) · [NYTimes-BackDoor](https://www.nytimes.com/2016/11/16/us/politics/china-phones-software-security.html)
- [S0319 - Allwinner](../../../../Threat%20Intelligence/Software/Malware/S0319%20-%20Allwinner.md) — A Linux kernel distributed by [Allwinner](https://attack.mitre.org/software/S0319) reportedly contained an simple backdoor that could be used to obtain root access. It was believed to have been left in the kernel by mistake by the authors.(Citation: HackerNews-Allwinner) [HackerNews-Allwinner](https://thehackernews.com/2016/05/android-kernal-exploit.html)
- [S0555 - CHEMISTGAMES](../../../../Threat%20Intelligence/Software/Malware/S0555%20-%20CHEMISTGAMES.md) — [CHEMISTGAMES](https://attack.mitre.org/software/S0555) has been distributed as updates to legitimate applications. This was accomplished by compromising legitimate app developers, and subsequently gaining access to their Google Play Store developer account.(Citation: CYBERWARCON CHEMISTGAMES) [CYBERWARCON CHEMISTGAMES](https://www.youtube.com/watch?v=xoNSbm1aX_w)
- [S0328 - Stealth Mango](../../../../Threat%20Intelligence/Software/Malware/S0328%20-%20Stealth%20Mango.md) — In at least one case, [Stealth Mango](https://attack.mitre.org/software/S0328) may have been installed using physical access to the device by a repair shop.(Citation: Lookout-StealthMango) [Lookout-StealthMango](https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf)
- [S0424 - Triada](../../../../Threat%20Intelligence/Software/Malware/S0424%20-%20Triada.md) — [Triada](https://attack.mitre.org/software/S0424) was added into the Android system by a third-party vendor identified as Yehuo or Blazefire during the production process.(Citation: Google Triada June 2019)(Citation: Krebs-Triada June 2019) [Krebs-Triada June 2019](https://krebsonsecurity.com/2019/06/tracing-the-supply-chain-attack-on-android-2/) · [Google Triada June 2019](https://security.googleblog.com/2019/06/pha-family-highlights-triada.html)

## Sources

- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-4.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-11.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-12.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-18.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/supply-chain-threats/SPC-20.html)
