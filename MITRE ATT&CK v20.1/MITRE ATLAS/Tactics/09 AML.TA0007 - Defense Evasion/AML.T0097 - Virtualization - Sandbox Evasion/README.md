# AML.T0097 - Virtualization/Sandbox Evasion

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may employ various means to detect and avoid virtualization and analysis environments. This may include changing behaviors based on the results of checks for the presence of artifacts indicative of a virtual machine environment (VME) or sandbox. If the adversary detects a VME, they may alter their malware to disengage from the victim or conceal the core functions of the implant. They may also search for VME artifacts before dropping secondary or additional payloads.

Adversaries may use several methods to accomplish Virtualization/Sandbox Evasion such as checking for security monitoring tools (e.g., Sysinternals, Wireshark, etc.) or other system artifacts associated with analysis or virtualization such as registry keys (e.g. substrings matching Vmware, VBOX, QEMU), environment variables (e.g. substrings matching VBOX, VMWARE, PARALLELS), NIC MAC addresses (e.g. prefixes 00-05-69 (VMWare) or 08-00-27 (VirtualBox)), running processes (e.g. vmware.exe, vboxservice.exe, qemu-ga.exe)  [research](https://research.checkpoint.com/2025/ai-evasion-prompt-injection/).

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1497](../../../../Enterprise/Tactics/07%20TA0005%20-%20Stealth/T1497%20-%20Virtualization%20-%20Sandbox%20Evasion/README.md) · [MITRE ATT&CK T1497](https://attack.mitre.org/techniques/T1497/)

## Case studies

- [AML.CS0043 - Malware Prototype with Embedded Prompt Injection](../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md#step-s04)

## References

- [New Malware Embeds Prompt Injection to Evade AI Detection - Check Point Research](https://research.checkpoint.com/2025/ai-evasion-prompt-injection/)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0097)
