# T1600 - Weaken Encryption

[Enterprise](../../../README.md) / [Defense Impairment](../README.md)

Adversaries may compromise a network device’s encryption capability in order to bypass encryption that would otherwise protect data communications.(Citation: Cisco Synful Knock Evolution)

Encryption can be used to protect transmitted network traffic to maintain its confidentiality (protect against unauthorized disclosure) and integrity (protect against unauthorized changes). Encryption ciphers are used to convert a plaintext message to ciphertext and can be computationally intensive to decipher without the associated decryption key. Typically, longer keys increase the cost of cryptanalysis, or decryption without the key.

Adversaries can compromise and manipulate devices that perform encryption of network traffic. For example, through behaviors such as [Modify System Image](https://attack.mitre.org/techniques/T1601), [Reduce Key Space](https://attack.mitre.org/techniques/T1600/001), and [Disable Crypto Hardware](https://attack.mitre.org/techniques/T1600/002), an adversary can negatively effect and/or eliminate a device’s ability to securely encrypt network traffic. This poses a greater risk of unauthorized disclosure and may help facilitate data manipulation, Credential Access, or Collection efforts.(Citation: Cisco Blog Legacy Device Attacks)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1600)

**Tactics**  [Defense Impairment](../README.md)

**Platforms**  [Network Devices](../../../Platforms/Network%20Devices.md)

## Sub-techniques

- [T1600.002 - Disable Crypto Hardware](T1600.002%20-%20Disable%20Crypto%20Hardware/README.md)
- [T1600.001 - Reduce Key Space](T1600.001%20-%20Reduce%20Key%20Space/README.md)

## Detection strategies

- [DET0339 - Detection Strategy for Weaken Encryption on Network Devices](../../../Defenses/Detection%20Strategies/DET0339%20-%20Detection%20Strategy%20for%20Weaken%20Encryption%20on%20Network%20Devices.md)

## Sources

- [Cisco Synful Knock Evolution](https://blogs.cisco.com/security/evolution-of-attacks-on-cisco-ios-devices)
- [Cisco Blog Legacy Device Attacks](https://community.cisco.com/t5/security-blogs/attackers-continue-to-target-legacy-devices/ba-p/4169954)
