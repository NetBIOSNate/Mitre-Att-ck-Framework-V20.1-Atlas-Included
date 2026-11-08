# T1600.001 - Reduce Key Space

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1600 - Weaken Encryption](../README.md)

Adversaries may reduce the level of effort required to decrypt data transmitted over the network by reducing the cipher strength of encrypted communications.(Citation: Cisco Synful Knock Evolution)

Adversaries can weaken the encryption software on a compromised network device by reducing the key size used by the software to convert plaintext to ciphertext (e.g., from hundreds or thousands of bytes to just a couple of bytes). As a result, adversaries dramatically reduce the amount of effort needed to decrypt the protected information without the key.

Adversaries may modify the key size used and other encryption parameters using specialized commands in a [Network Device CLI](https://attack.mitre.org/techniques/T1059/008) introduced to the system through [Modify System Image](https://attack.mitre.org/techniques/T1601) to change the configuration of the device.(Citation: Cisco Blog Legacy Device Attacks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1600/001)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Detection strategies

- [DET0243 - Detection Strategy for Weaken Encryption: Reduce Key Space on Network Devices](../../../../Defenses/Detection%20Strategies/DET0243%20-%20Detection%20Strategy%20for%20Weaken%20Encryption%20-%20Reduce%20Key%20Space%20on%20Network%20Devices.md)

## Sources

- [Cisco Synful Knock Evolution](https://blogs.cisco.com/security/evolution-of-attacks-on-cisco-ios-devices)
- [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)
