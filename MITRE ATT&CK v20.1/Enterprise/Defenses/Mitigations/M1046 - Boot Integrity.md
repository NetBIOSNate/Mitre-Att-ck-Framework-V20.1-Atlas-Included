# M1046 - Boot Integrity

[Enterprise](../../README.md) / [Mitigations](README.md)

Boot Integrity ensures that a system starts securely by verifying the integrity of its boot process, operating system, and associated components. This mitigation focuses on leveraging secure boot mechanisms, hardware-rooted trust, and runtime integrity checks to prevent tampering during the boot sequence. It is designed to thwart adversaries attempting to modify system firmware, bootloaders, or critical OS components. This mitigation can be implemented through the following measures:

Implementation of Secure Boot:

- Implementation: Enable UEFI Secure Boot on all systems and configure it to allow only signed bootloaders and operating systems.
- Use Case: An adversary attempts to replace the system’s bootloader with a malicious version to gain persistence. Secure Boot prevents the untrusted bootloader from executing, halting the attack.

Utilization of TPMs:

- Implementation: Configure systems to use TPM-based attestation for boot integrity, ensuring that any modification to the firmware, bootloader, or OS is detected.
- Use Case: A compromised firmware component alters the boot sequence. The TPM detects the change and triggers an alert, allowing the organization to respond before further damage.

Enable Bootloader Passwords:

- Implementation: Protect BIOS/UEFI settings with a strong password and limit physical access to devices.
- Use Case: An attacker with physical access attempts to disable Secure Boot or modify the boot sequence. The password prevents unauthorized changes.

Runtime Integrity Monitoring:

- Implementation: Deploy solutions to verify the integrity of critical files and processes after boot.
- Use Case: A malware infection modifies kernel modules post-boot. Runtime integrity monitoring detects the modification and prevents the malicious module from loading.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1046)

## Mitigated techniques

- [T1542.003 - Bootkit](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.003%20-%20Bootkit/README.md)
- [T1553.006 - Code Signing Policy Modification](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1553%20-%20Subvert%20Trust%20Controls/T1553.006%20-%20Code%20Signing%20Policy%20Modification/README.md)
- [T1195.003 - Compromise Hardware Supply Chain](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/T1195.003%20-%20Compromise%20Hardware%20Supply%20Chain/README.md)
- [T1601.002 - Downgrade System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.002%20-%20Downgrade%20System%20Image/README.md)
- [T1495 - Firmware Corruption](../../Tactics/15%20TA0040%20-%20Impact/T1495%20-%20Firmware%20Corruption/README.md)
- [T1601 - Modify System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/README.md)
- [T1601.001 - Patch System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.001%20-%20Patch%20System%20Image/README.md)
- [T1542 - Pre-OS Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/README.md)
- [T1542.004 - ROMMONkit](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.004%20-%20ROMMONkit/README.md)
- [T1505 - Server Software Component](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/README.md)
- [T1195 - Supply Chain Compromise](../../Tactics/03%20TA0001%20-%20Initial%20Access/T1195%20-%20Supply%20Chain%20Compromise/README.md)
- [T1542.001 - System Firmware](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.001%20-%20System%20Firmware/README.md)
- [T1542.005 - TFTP Boot](../../Tactics/05%20TA0003%20-%20Persistence/T1542%20-%20Pre-OS%20Boot/T1542.005%20-%20TFTP%20Boot/README.md)
- [T1505.006 - vSphere Installation Bundles](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.006%20-%20vSphere%20Installation%20Bundles/README.md)
