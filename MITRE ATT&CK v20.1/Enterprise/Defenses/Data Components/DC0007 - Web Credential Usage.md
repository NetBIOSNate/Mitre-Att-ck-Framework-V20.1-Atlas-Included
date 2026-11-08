# DC0007 - Web Credential Usage

[Enterprise](../../README.md) / [Data Components](README.md)

An attempt by a user to gain access to a network or computing resource by providing web credentials (ex: Windows EID 1202)

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0007)

## Log sources and channels

- **AWS:CloudTrail** — SessionToken used without preceding MFA or login event
- **m365:unified** — SessionId reused from different device/browser fingerprint
- **AWS:CloudTrail** — AssumeRoleWithSAML
- **saas:access** — SAML token accepted without preceding login challenge
- **m365:exchange** — Mailbox access using SAML token without corresponding MFA event
- **AWS:CloudTrail** — GetSessionToken, AssumeRoleWithWebIdentity
- **macos:unifiedlog** — New session initiated using cookies without normal MFA or password validation
- **m365:unified** — Session activity without correlated login event
- **AWS:CloudTrail** — AssumeRole, GetFederationToken, GetSessionToken
- **azure:signinlogs** — TokenIssued, RefreshTokenUsed
- **saas:googleworkspace** — OAuthTokenGranted, APIRequest
- **m365:unified** — OAuthTokenIssued, FileAccessed, MailItemsAccessed
- **kubernetes:apiserver** — serviceAccount token used in API requests not tied to workload identity
- **NSM:Connections** — Pre-authentication keys generated or token signing anomalies
- **macos:unifiedlog** — Web sessions initiated with newly forged tokens
- **saas:auth** — API requests made with tokens not associated with expected user logins
- **azure:signinlogs** — TokenIssuanceStart, TokenIssuanceSuccess
- **saas:googleworkspace** — access_token issued
- **m365:unified** — TokenIssued, FileAccessed
- **AWS:CloudTrail** — GetCallerIdentity

## Analytics using this component

- [AN0201 - Analytic 0201](../Analytics/AN0201.md)
- [AN0202 - Analytic 0202](../Analytics/AN0202.md)
- [AN0419 - Analytic 0419](../Analytics/AN0419.md)
- [AN0421 - Analytic 0421](../Analytics/AN0421.md)
- [AN0422 - Analytic 0422](../Analytics/AN0422.md)
- [AN0483 - Analytic 0483](../Analytics/AN0483.md)
- [AN0486 - Analytic 0486](../Analytics/AN0486.md)
- [AN0487 - Analytic 0487](../Analytics/AN0487.md)
- [AN0526 - Analytic 0526](../Analytics/AN0526.md)
- [AN0527 - Analytic 0527](../Analytics/AN0527.md)
- [AN0528 - Analytic 0528](../Analytics/AN0528.md)
- [AN0529 - Analytic 0529](../Analytics/AN0529.md)
- [AN0530 - Analytic 0530](../Analytics/AN0530.md)
- [AN0718 - Analytic 0718](../Analytics/AN0718.md)
- [AN0721 - Analytic 0721](../Analytics/AN0721.md)
- [AN0722 - Analytic 0722](../Analytics/AN0722.md)
- [AN0956 - Analytic 0956](../Analytics/AN0956.md)
- [AN0957 - Analytic 0957](../Analytics/AN0957.md)
- [AN0959 - Analytic 0959](../Analytics/AN0959.md)
- [AN0960 - Analytic 0960](../Analytics/AN0960.md)
