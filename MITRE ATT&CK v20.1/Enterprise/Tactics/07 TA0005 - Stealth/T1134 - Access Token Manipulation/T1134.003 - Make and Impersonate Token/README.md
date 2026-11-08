# T1134.003 - Make and Impersonate Token

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1134 - Access Token Manipulation](../README.md)

Adversaries may make new tokens and impersonate users to escalate privileges and bypass access controls. For example, if an adversary has a username and password but the user is not logged onto the system the adversary can then create a logon session for the user using the `LogonUser` function.(Citation: LogonUserW function) The function will return a copy of the new session's access token and the adversary can use `SetThreadToken` to assign the token to a thread.

This behavior is distinct from [Token Impersonation/Theft](https://attack.mitre.org/techniques/T1134/001) in that this refers to creating a new user token instead of stealing or duplicating an existing one.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1134/003)

**Tactics**  [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G1043 - BlackByte](../../../../Threat%20Intelligence/Groups/G1043%20-%20BlackByte.md) — [BlackByte](https://attack.mitre.org/groups/G1043) constructed a valid authentication token following Microsoft Exchange exploitation to allow for follow-on privileged command execution.(Citation: Microsoft BlackByte 2023) [Microsoft BlackByte 2023](https://www.microsoft.com/en-us/security/blog/2023/07/06/the-five-day-job-a-blackbyte-ransomware-intrusion-case-study/)
- [S0154 - Cobalt Strike](../../../../Threat%20Intelligence/Software/Malware/S0154%20-%20Cobalt%20Strike.md) — [Cobalt Strike](https://attack.mitre.org/software/S0154) can make tokens from known credentials.(Citation: cobaltstrike manual) [cobaltstrike manual](https://web.archive.org/web/20210825130434/https://cobaltstrike.com/downloads/csmanual38.pdf)
- [G1016 - FIN13](../../../../Threat%20Intelligence/Groups/G1016%20-%20FIN13.md) — [FIN13](https://attack.mitre.org/groups/G1016) has utilized tools such as Incognito V2 for token manipulation and impersonation.(Citation: Sygnia Elephant Beetle Jan 2022) [Sygnia Elephant Beetle Jan 2022](https://web.archive.org/web/20220105132433/https://f.hubspotusercontent30.net/hubfs/8776530/Sygnia-%20Elephant%20Beetle_Jan2022.pdf)
- [S1060 - Mafalda](../../../../Threat%20Intelligence/Software/Malware/S1060%20-%20Mafalda.md) — [Mafalda](https://attack.mitre.org/software/S1060) can create a token for a different user.(Citation: SentinelLabs Metador Technical Appendix Sept 2022) [SentinelLabs Metador Technical Appendix Sept 2022](https://docs.google.com/document/d/1e9ZTW9b71YwFWS_18ZwDAxa-cYbV8q1wUefmKZLYVsA/edit#heading=h.lmnbtht1ikzm)
- [S0692 - SILENTTRINITY](../../../../Threat%20Intelligence/Software/Tools/S0692%20-%20SILENTTRINITY.md) — [SILENTTRINITY](https://attack.mitre.org/software/S0692) can make tokens from known credentials.(Citation: Github_SILENTTRINITY) [Github_SILENTTRINITY](https://github.com/byt3bl33d3r/SILENTTRINITY)

## Mitigations

- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit permissions so that users and user groups cannot create tokens. This setting should be defined for the local system account only. GPO: Computer Configuration > [Policies] > Windows Settings > Security Settings > Local Policies > User Rights Assignment: Create a token object. (Citation: Microsoft Create Token) Also define who can create a process level token to only the local and network service through GPO: Computer Configuration > [Policies] > Windows Settings > Security Settings > Local Policies > User Rights Assignment: Replace a process level token.(Citation: Microsoft Replace Process Token) Administrators should log in as a standard user but run their tools with administrator privileges using the built-in access token manipulation command <code>runas</code>.(Citation: Microsoft runas) [Microsoft Create Token](https://docs.microsoft.com/windows/device-security/security-policy-settings/create-a-token-object) · [Microsoft Replace Process Token](https://docs.microsoft.com/windows/device-security/security-policy-settings/replace-a-process-level-token) · [Microsoft runas](https://technet.microsoft.com/en-us/library/bb490994.aspx)
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — An adversary must already have administrator level access on the local system to make full use of this technique; be sure to restrict users and accounts to the least privileges they require.

## Detection strategies

- [DET0498 - Behavior‑chain detection for T1134.003 Make and Impersonate Token (Windows)](../../../../Defenses/Detection%20Strategies/DET0498%20-%20Behavior%E2%80%91chain%20detection%20for%20T1134.003%20Make%20and%20Impersonate%20Token%20%28Windows%29.md)

## Sources

- [LogonUserW function](https://learn.microsoft.com/en-us/windows/win32/api/winbase/nf-winbase-logonuserw)
