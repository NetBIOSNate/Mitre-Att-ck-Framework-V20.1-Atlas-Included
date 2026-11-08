# T1674 - Input Injection

[Enterprise](../../../README.md) / [Execution](../README.md)

Adversaries may simulate keystrokes on a victim’s computer by various means to perform any type of action on behalf of the user, such as launching the command interpreter using keyboard shortcuts,  typing an inline script to be executed, or interacting directly with a GUI-based application.  These actions can be preprogrammed into adversary tooling or executed through physical devices such as Human Interface Devices (HIDs).

For example, adversaries have used tooling that monitors the Windows message loop to detect when a user visits bank-specific URLs. If detected, the tool then simulates keystrokes to open the developer console or select the address bar, pastes malicious JavaScript from the clipboard, and executes it - enabling manipulation of content within the browser, such as replacing bank account numbers during transactions.(Citation: BleepingComputer BackSwap)(Citation: welivesecurity BackSwap)

Adversaries have also used malicious USB devices to emulate keystrokes that launch PowerShell, leading to the download and execution of malware from adversary-controlled servers.(Citation: BleepingComputer USB)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1674)

**Tactics**  [Execution](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md), [Linux](../../../Platforms/Linux.md)

## Mitigations

- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Denylist scripting and use application control where appropriate. For example, PowerShell Constrained Language mode can be used to restrict access to sensitive or otherwise dangerous language elements such as those used to execute arbitrary Windows APIs or files (e.g., `Add-Type`).(Citation: Microsoft PowerShell CLM) [Microsoft PowerShell CLM](https://devblogs.microsoft.com/powershell/powershell-constrained-language-mode/)
- [M1034 - Limit Hardware Installation](../../../Defenses/Mitigations/M1034%20-%20Limit%20Hardware%20Installation.md) — Limit the use of USB devices and removable media within a network.

## Procedure examples

- [G0046 - FIN7](../../../Threat%20Intelligence/Groups/G0046%20-%20FIN7.md) — FIN7 has used malicious USBs to emulate keystrokes to launch PowerShell to download and execute malware from the adversary's server.(Citation: FBI Flash FIN7 USB)(Citation: Gemini_FIN7_Jan2022) [Gemini_FIN7_Jan2022](https://geminiadvisory.io/fin7-flash-drives-spread-remote-access-trojan/) · [FBI Flash FIN7 USB](https://therecord.media/fbi-fin7-hackers-target-us-companies-with-badusb-devices-to-install-ransomware/)

## Detection strategies

- [DET0568 - Detection Strategy for Input Injection](../../../Defenses/Detection%20Strategies/DET0568%20-%20Detection%20Strategy%20for%20Input%20Injection.md)

## Sources

- [BleepingComputer BackSwap](https://www.bleepingcomputer.com/news/security/backswap-banking-trojan-uses-never-before-seen-techniques/)
- [BleepingComputer USB](https://www.bleepingcomputer.com/news/security/fbi-hackers-sending-malicious-usb-drives-and-teddy-bears-via-usps/)
- [welivesecurity BackSwap](https://www.welivesecurity.com/2018/05/25/backswap-malware-empty-bank-accounts/)
