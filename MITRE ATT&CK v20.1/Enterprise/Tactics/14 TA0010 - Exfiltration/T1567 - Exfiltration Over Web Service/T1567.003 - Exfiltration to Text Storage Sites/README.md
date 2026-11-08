# T1567.003 - Exfiltration to Text Storage Sites

[Enterprise](../../../../README.md) / [Exfiltration](../../README.md) / [T1567 - Exfiltration Over Web Service](../README.md)

Adversaries may exfiltrate data to text storage sites instead of their primary command and control channel. Text storage sites, such as <code>pastebin[.]com</code>, are commonly used by developers to share code and other information.  

Text storage sites are often used to host malicious code for C2 communication (e.g., [Stage Capabilities](https://attack.mitre.org/techniques/T1608)), but adversaries may also use these sites to exfiltrate collected data. Furthermore, paid features and encryption options may allow adversaries to conceal and store data more securely.(Citation: Pastebin EchoSec)

**Note:** This is distinct from [Exfiltration to Code Repository](https://attack.mitre.org/techniques/T1567/001), which highlights access to code repositories via APIs.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1567/003)

**Tactics**  [Exfiltration](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md), [ESXi](../../../../Platforms/ESXi.md)

## Detection strategies

- [DET0284 - Detection Strategy for Exfiltration to Text Storage Sites](../../../../Defenses/Detection%20Strategies/DET0284%20-%20Detection%20Strategy%20for%20Exfiltration%20to%20Text%20Storage%20Sites.md)

## Mitigations

- [M1021 - Restrict Web-Based Content](../../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — Web proxies can be used to enforce an external network communication policy that prevents use of unauthorized external services.

## Sources

- [Pastebin EchoSec](https://web.archive.org/web/20201107203304/https://www.echosec.net/blog/what-is-pastebin-and-why-do-hackers-love-it)
