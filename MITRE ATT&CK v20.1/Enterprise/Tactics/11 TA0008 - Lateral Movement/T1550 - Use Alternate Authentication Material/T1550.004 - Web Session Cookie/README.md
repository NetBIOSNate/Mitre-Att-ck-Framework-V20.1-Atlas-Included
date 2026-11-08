# T1550.004 - Web Session Cookie

[Enterprise](../../../../README.md) / [Lateral Movement](../../README.md) / [T1550 - Use Alternate Authentication Material](../README.md)

Adversaries can use stolen session cookies to authenticate to web applications and services. This technique bypasses some multi-factor authentication protocols since the session is already authenticated.(Citation: Pass The Cookie)

Authentication cookies are commonly used in web applications, including cloud-based services, after a user has authenticated to the service so credentials are not passed and re-authentication does not need to occur as frequently. Cookies are often valid for an extended period of time, even if the web application is not actively used. After the cookie is obtained through [Steal Web Session Cookie](https://attack.mitre.org/techniques/T1539) or [Web Cookies](https://attack.mitre.org/techniques/T1606/001), the adversary may then import the cookie into a browser they control and is then able to use the site or application as the user for as long as the session cookie is active. Once logged into the site, an adversary can access sensitive information, read email, or perform actions that the victim account has permissions to perform.

There have been examples of malware targeting session cookies to bypass multi-factor authentication systems.(Citation: Unit 42 Mac Crypto Cookies January 2019)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1550/004)

**Tactics**  [Lateral Movement](../../README.md)

**Platforms**  [IaaS](../../../../Platforms/IaaS.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md)

## Mitigations

- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Configure browsers or tasks to regularly delete persistent cookies.

## Procedure examples

- [C0024 - SolarWinds Compromise](../../../../Threat%20Intelligence/Campaigns/C0024%20-%20SolarWinds%20Compromise.md) — During the [SolarWinds Compromise](https://attack.mitre.org/campaigns/C0024), [APT29](https://attack.mitre.org/groups/G0016) used stolen cookies to access cloud resources and a forged `duo-sid` cookie to bypass MFA set on an email account.(Citation: Volexity SolarWinds)(Citation: CrowdStrike StellarParticle January 2022) [Volexity SolarWinds](https://www.volexity.com/blog/2020/12/14/dark-halo-leverages-solarwinds-compromise-to-breach-organizations/) · [CrowdStrike StellarParticle January 2022](https://www.crowdstrike.com/blog/observations-from-the-stellarparticle-campaign/)
- [G1033 - Star Blizzard](../../../../Threat%20Intelligence/Groups/G1033%20-%20Star%20Blizzard.md) — [Star Blizzard](https://attack.mitre.org/groups/G1033) has bypassed multi-factor authentication on victim email accounts by using session cookies stolen using EvilGinx.(Citation: CISA Star Blizzard Advisory December 2023) [CISA Star Blizzard Advisory December 2023](https://www.cisa.gov/news-events/cybersecurity-advisories/aa23-341a)

## Detection strategies

- [DET0074 - Detect Use of Stolen Web Session Cookies Across Platforms](../../../../Defenses/Detection%20Strategies/DET0074%20-%20Detect%20Use%20of%20Stolen%20Web%20Session%20Cookies%20Across%20Platforms.md)

## Sources

- [Unit 42 Mac Crypto Cookies January 2019](https://unit42.paloaltonetworks.com/mac-malware-steals-cryptocurrency-exchanges-cookies/)
- [Pass The Cookie](https://wunderwuzzi23.github.io/blog/passthecookie.html)
