# T1600.002 - Disable Crypto Hardware

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1600 - Weaken Encryption](../README.md)

Adversaries disable a network device’s dedicated hardware encryption, which may enable them to leverage weaknesses in software encryption in order to reduce the effort involved in collecting, manipulating, and exfiltrating transmitted data.

Many network devices such as routers, switches, and firewalls, perform encryption on network traffic to secure transmission across networks. Often, these devices are equipped with special, dedicated encryption hardware to greatly increase the speed of the encryption process as well as to prevent malicious tampering. When an adversary takes control of such a device, they may disable the dedicated hardware, for example, through use of [Modify System Image](https://attack.mitre.org/techniques/T1601), forcing the use of software to perform encryption on general processors. This is typically used in conjunction with attacks to weaken the strength of the cipher in software (e.g., [Reduce Key Space](https://attack.mitre.org/techniques/T1600/001)).(Citation: Cisco Blog Legacy Device Attacks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1600/002)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Detection strategies

- [DET0494 - Detection Strategy for Weaken Encryption: Disable Crypto Hardware on Network Devices](../../../../Defenses/Detection%20Strategies/DET0494%20-%20Detection%20Strategy%20for%20Weaken%20Encryption%20-%20Disable%20Crypto%20Hardware%20on%20Network%20Devices.md)

## Sources

- [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)
