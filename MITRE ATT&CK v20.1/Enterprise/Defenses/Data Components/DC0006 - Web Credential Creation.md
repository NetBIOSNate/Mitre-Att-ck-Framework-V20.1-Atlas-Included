# DC0006 - Web Credential Creation

[Enterprise](../../README.md) / [Data Components](README.md)

Initial construction of new web credential material (ex: Windows EID 1200 or 4769)

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0006)

## Log sources and channels

- **WinEventLog:ADFS** — Token issuance events showing anomalous claims or issuers
- **AWS:CloudTrail** — AssumeRole, GetFederationToken API calls by unusual or new entities
- **azure:signinlogs** — SAML/OIDC tokens issued without corresponding MFA or password validation
- **m365:unified** — Session creation without MFA or login event
- **m365:oauth** — OAuth grants or tokens issued without expected user consent

## Analytics using this component

- [AN0420 - Analytic 0420](../Analytics/AN0420.md)
- [AN0717 - Analytic 0717](../Analytics/AN0717.md)
- [AN0718 - Analytic 0718](../Analytics/AN0718.md)
- [AN0722 - Analytic 0722](../Analytics/AN0722.md)
- [AN0723 - Analytic 0723](../Analytics/AN0723.md)
