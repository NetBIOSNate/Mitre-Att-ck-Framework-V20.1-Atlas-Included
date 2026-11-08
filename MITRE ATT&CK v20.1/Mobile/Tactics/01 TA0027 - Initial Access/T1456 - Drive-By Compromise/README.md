# T1456 - Drive-By Compromise

[Mobile](../../../README.md) / [Initial Access](../README.md)

Adversaries may gain access to a system through a user visiting a website over the normal course of browsing. With this technique, the user's web browser is typically targeted for exploitation, but adversaries may also use compromised websites for non-exploitation behavior such as acquiring an [Application Access Token](https://attack.mitre.org/techniques/T1550/001).

Multiple ways of delivering exploit code to a browser exist, including:

* A legitimate website is compromised where adversaries have injected some form of malicious code such as JavaScript, iFrames, and cross-site scripting.
* Malicious ads are paid for and served through legitimate ad providers.
* Built-in web application interfaces are leveraged for the insertion of any other kind of object that can be used to display web content or contain a script that executes on the visiting client (e.g. forum posts, comments, and other user controllable web content).

Often the website used by an adversary is one visited by a specific community, such as government, a particular industry, or region, where the goal is to compromise a specific user or set of users based on a shared interest. This kind of targeted attack is referred to a strategic web compromise or watering hole attack. There are several known examples of this occurring.(Citation: Lookout-StealthMango)

Typical drive-by compromise process:

1. A user visits a website that is used to host the adversary controlled content.
2. Scripts automatically execute, typically searching versions of the browser and plugins for a potentially vulnerable version. 
    * The user may be required to assist in this process by enabling scripting or active website components and ignoring warning dialog boxes.
3. Upon finding a vulnerable version, exploit code is delivered to the browser.
4. If exploitation is successful, then it will give the adversary code execution on the user's system unless other protections are in place.
    * In some cases a second visit to the website after the initial scan is required before exploit code is delivered.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1456)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [C0033 - C0033](../../../Threat%20Intelligence/Campaigns/C0033%20-%20C0033.md) — During [C0033](https://attack.mitre.org/campaigns/C0033), [PROMETHIUM](https://attack.mitre.org/groups/G0056) distributed [StrongPity](https://attack.mitre.org/software/S0491) through the compromised official Syrian E-Gov website.(Citation: trendmicro_strongpity) [trendmicro_strongpity](https://www.trendmicro.com/en_za/research/21/g/strongpity-apt-group-deploys-android-malware-for-the-first-time.html)
- [S0463 - INSOMNIA](../../../Threat%20Intelligence/Software/Malware/S0463%20-%20INSOMNIA.md) — [INSOMNIA](https://attack.mitre.org/software/S0463) has utilized malicious JavaScript and iframes to exploit WebKit running on vulnerable iOS 12 devices.(Citation: Volexity Insomnia) [Volexity Insomnia](https://www.volexity.com/blog/2020/04/21/evil-eye-threat-actor-resurfaces-with-ios-exploit-and-updated-implant/)
- [S1185 - LightSpy](../../../Threat%20Intelligence/Software/Malware/S1185%20-%20LightSpy.md) — [LightSpy](https://attack.mitre.org/software/S1185) gains initial execution when a victim visits a compromised or adversary-controlled website, including those mimicking legitimate sources such as a Hong Kong newspaper. Upon loading `index.html`, a Safari WebKit exploit is triggered, leading to the download of a Mach-O binary disguised with a `.png` extension.(Citation: FirshSecureList LightSpy 2020)(Citation: Shoshin_Kaspersky LightSpy 2020)(Citation: LinkedIn Dmitry LightSpy 2025)(Citation: Threatfabric LightSpy 2024) [LinkedIn Dmitry LightSpy 2025](https://www.linkedin.com/pulse/coordinated-kill-switch-lightspys-ios-destructive-plugin-bestuzhev-zhoye/) · [FirshSecureList LightSpy 2020](https://securelist.com/ios-exploit-chain-deploys-lightspy-malware/96407/) · [Shoshin_Kaspersky LightSpy 2020](https://usa.kaspersky.com/blog/lightspy-watering-hole-attack/21301/) · [Threatfabric LightSpy 2024](https://www.threatfabric.com/blogs/lightspy-implant-for-ios)
- [S0289 - Pegasus for iOS](../../../Threat%20Intelligence/Software/Malware/S0289%20-%20Pegasus%20for%20iOS.md) — [Pegasus for iOS](https://attack.mitre.org/software/S0289) was distributed through a web site by exploiting vulnerabilities in the Safari web browser on iOS devices.(Citation: Lookout-Pegasus) [Lookout-Pegasus](https://info.lookout.com/rs/051-ESQ-475/images/lookout-pegasus-technical-analysis.pdf)
- [S0328 - Stealth Mango](../../../Threat%20Intelligence/Software/Malware/S0328%20-%20Stealth%20Mango.md) — [Stealth Mango](https://attack.mitre.org/software/S0328) is delivered via a a watering hole website that mimics the third-party Android app store APKMonk. In at least one case, the watering hole URL was distributed through Facebook Messenger.(Citation: Lookout-StealthMango) [Lookout-StealthMango](https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf)
- [S0311 - YiSpecter](../../../Threat%20Intelligence/Software/Malware/S0311%20-%20YiSpecter.md) — [YiSpecter](https://attack.mitre.org/software/S0311) is believed to have initially infected devices using internet traffic hijacking to generate abnormal popups.(Citation: paloalto_yispecter_1015) [paloalto_yispecter_1015](https://unit42.paloaltonetworks.com/yispecter-first-ios-malware-attacks-non-jailbroken-ios-devices-by-abusing-private-apis/)

## Mitigations

- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates frequently contain patches for known exploits.

## Detection strategies

- [DET0614 - Detection of Drive-By Compromise](../../../Defenses/Detection%20Strategies/DET0614%20-%20Detection%20of%20Drive-By%20Compromise.md)

## Sources

- [Lookout-StealthMango](https://info.lookout.com/rs/051-ESQ-475/images/lookout-stealth-mango-srr-us.pdf)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-22.html)
