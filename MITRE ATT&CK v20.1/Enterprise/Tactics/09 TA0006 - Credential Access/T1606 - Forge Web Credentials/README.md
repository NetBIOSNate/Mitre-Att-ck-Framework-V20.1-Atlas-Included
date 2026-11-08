# T1606 - Forge Web Credentials

[Enterprise](../../../README.md) / [Credential Access](../README.md)

Adversaries may forge credential materials that can be used to gain access to web applications or Internet services. Web applications and services (hosted in cloud SaaS environments or on-premise servers) often use session cookies, tokens, or other materials to authenticate and authorize user access.

Adversaries may generate these credential materials in order to gain access to web resources. This differs from [Steal Web Session Cookie](https://attack.mitre.org/techniques/T1539), [Steal Application Access Token](https://attack.mitre.org/techniques/T1528), and other similar behaviors in that the credentials are new and forged by the adversary, rather than stolen or intercepted from legitimate users.

The generation of web credentials often requires secret values, such as passwords, [Private Keys](https://attack.mitre.org/techniques/T1552/004), or other cryptographic seed values.(Citation: GitHub AWS-ADFS-Credential-Generator) Adversaries may also forge tokens by taking advantage of features such as the `AssumeRole` and `GetFederationToken` APIs in AWS, which allow users to request temporary security credentials (i.e., [Temporary Elevated Cloud Access](https://attack.mitre.org/techniques/T1548/005)), or the `zmprov gdpak` command in Zimbra, which generates a pre-authentication key that can be used to generate tokens for any user in the domain.(Citation: AWS Temporary Security Credentials)(Citation: Zimbra Preauth)

Once forged, adversaries may use these web credentials to access resources (ex: [Use Alternate Authentication Material](https://attack.mitre.org/techniques/T1550)), which may bypass multi-factor and other authentication protection mechanisms.(Citation: Pass The Cookie)(Citation: Unit 42 Mac Crypto Cookies January 2019)(Citation: Microsoft SolarWinds Customer Guidance)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1606)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [SaaS](../../../Platforms/SaaS.md), [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md), [Linux](../../../Platforms/Linux.md), [IaaS](../../../Platforms/IaaS.md), [Office Suite](../../../Platforms/Office%20Suite.md), [Identity Provider](../../../Platforms/Identity%20Provider.md)

## Sub-techniques

- [T1606.002 - SAML Tokens](T1606.002%20-%20SAML%20Tokens/README.md)
- [T1606.001 - Web Cookies](T1606.001%20-%20Web%20Cookies/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Administrators should perform an audit of all access lists and the permissions they have been granted to access web applications and services. This should be done extensively on all resources in order to establish a baseline, followed up on with periodic audits of new or updated resources. Suspicious accounts/credentials should be investigated and removed. Enable advanced auditing on ADFS. Check the success and failure audit options in the ADFS Management snap-in. Enable Audit Application Generated events on the AD FS farm via Group Policy Object.(Citation: FireEye ADFS) [FireEye ADFS](https://www.troopers.de/troopers19/agenda/fpxwmn/)
- [M1026 - Privileged Account Management](../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Restrict permissions and access to the AD FS server to only originate from privileged access workstations.(Citation: FireEye ADFS) [FireEye ADFS](https://www.troopers.de/troopers19/agenda/fpxwmn/)
- [M1054 - Software Configuration](../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Configure browsers/applications to regularly delete persistent web credentials (such as cookies).
- [M1018 - User Account Management](../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Ensure that user accounts with administrative rights follow best practices, including use of privileged access workstations, Just in Time/Just Enough Administration (JIT/JEA), and strong authentication. Reduce the number of users that are members of highly privileged Directory Roles.(Citation: Microsoft SolarWinds Customer Guidance) In AWS environments, prohibit users from calling the `sts:GetFederationToken` API unless explicitly required.(Citation: Crowdstrike AWS User Federation Persistence) [Crowdstrike AWS User Federation Persistence](https://www.crowdstrike.com/blog/how-adversaries-persist-with-aws-user-federation/) · [Microsoft SolarWinds Customer Guidance](https://msrc-blog.microsoft.com/2020/12/13/customer-guidance-on-recent-nation-state-cyber-attacks/)

## Detection strategies

- [DET0260 - Detection Strategy for Forged Web Credentials](../../../Defenses/Detection%20Strategies/DET0260%20-%20Detection%20Strategy%20for%20Forged%20Web%20Credentials.md)

## Sources

- [AWS Temporary Security Credentials](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html)
- [Unit 42 Mac Crypto Cookies January 2019](https://unit42.paloaltonetworks.com/mac-malware-steals-cryptocurrency-exchanges-cookies/)
- [GitHub AWS-ADFS-Credential-Generator](https://github.com/pvanbuijtene/aws-adfs-credential-generator)
- [Microsoft SolarWinds Customer Guidance](https://msrc-blog.microsoft.com/2020/12/13/customer-guidance-on-recent-nation-state-cyber-attacks/)
- [Pass The Cookie](https://wunderwuzzi23.github.io/blog/passthecookie.html)
- [Zimbra Preauth](https://wiki.zimbra.com/wiki/Preauth)
