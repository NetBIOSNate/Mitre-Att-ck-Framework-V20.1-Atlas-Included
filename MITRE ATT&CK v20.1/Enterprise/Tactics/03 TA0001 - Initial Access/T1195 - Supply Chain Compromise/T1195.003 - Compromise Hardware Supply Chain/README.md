# T1195.003 - Compromise Hardware Supply Chain

[Enterprise](../../../../README.md) / [Initial Access](../../README.md) / [T1195 - Supply Chain Compromise](../README.md)

Adversaries may manipulate hardware components in products prior to receipt by a final consumer for the purpose of data or system compromise. By modifying hardware or firmware in the supply chain, adversaries can insert a backdoor into consumer networks that may be difficult to detect and give the adversary a high degree of control over the system. Hardware backdoors may be inserted into various devices, such as servers, workstations, network infrastructure, or peripherals.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1195/003)

**Tactics**  [Initial Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0368 - Hardware Supply Chain Compromise Detection via Host Status & Boot Integrity Checks](../../../../Defenses/Detection%20Strategies/DET0368%20-%20Hardware%20Supply%20Chain%20Compromise%20Detection%20via%20Host%20Status%20%26%20Boot%20Integrity%20Checks.md)

## Mitigations

- [M1046 - Boot Integrity](../../../../Defenses/Mitigations/M1046%20-%20Boot%20Integrity.md) — Use Trusted Platform Module technology and a secure or trusted boot process to prevent system integrity from being compromised. Check the integrity of the existing BIOS or EFI to determine if it is vulnerable to modification.(Citation: TCG Trusted Platform Module)(Citation: TechNet Secure Boot Process) [TechNet Secure Boot Process](https://docs.microsoft.com/en-us/windows/security/information-protection/secure-the-windows-10-boot-process) · [TCG Trusted Platform Module](http://www.trustedcomputinggroup.org/wp-content/uploads/Trusted-Platform-Module-Summary_04292008.pdf)
