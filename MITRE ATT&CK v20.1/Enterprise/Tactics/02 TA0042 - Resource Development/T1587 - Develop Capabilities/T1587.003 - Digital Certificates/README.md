# T1587.003 - Digital Certificates

[Enterprise](../../../../README.md) / [Resource Development](../../README.md) / [T1587 - Develop Capabilities](../README.md)

Adversaries may create self-signed SSL/TLS certificates that can be used during targeting. SSL/TLS certificates are designed to instill trust. They include information about the key, information about its owner's identity, and the digital signature of an entity that has verified the certificate's contents are correct. If the signature is valid, and the person examining the certificate trusts the signer, then they know they can use that key to communicate with its owner. In the case of self-signing, digital certificates will lack the element of trust associated with the signature of a third-party certificate authority (CA).(Citation: Spice Works Digital Certificates)

Adversaries may create self-signed SSL/TLS certificates that can be used to further their operations, such as encrypting C2 traffic (ex: [Asymmetric Cryptography](https://attack.mitre.org/techniques/T1573/002) with [Web Protocols](https://attack.mitre.org/techniques/T1071/001)) or even enabling [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) if added to the root of trust (i.e. [Install Root Certificate](https://attack.mitre.org/techniques/T1553/004)).

After creating a digital certificate, an adversary may then install that certificate (see [Install Digital Certificate](https://attack.mitre.org/techniques/T1608/003)) on infrastructure under their control.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1587/003)

**Tactics**  [Resource Development](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Procedure examples

- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has created self-signed digital certificates to enable mutual TLS authentication for malware.(Citation: PWC WellMess July 2020)(Citation: PWC WellMess C2 August 2020) [PWC WellMess July 2020](https://www.pwc.co.uk/issues/cyber-security-services/insights/cleaning-up-after-wellmess.html) · [PWC WellMess C2 August 2020](https://www.pwc.co.uk/issues/cyber-security-services/insights/wellmess-analysis-command-control.html)
- [C0046 - ArcaneDoor](../../../../Threat%20Intelligence/Campaigns/C0046%20-%20ArcaneDoor.md) — [ArcaneDoor](https://attack.mitre.org/campaigns/C0046) included acquiring digital certificates mimicking patterns associated with Cisco ASA appliances for command and control infrastructure.(Citation: Cisco ArcaneDoor 2024) [Cisco ArcaneDoor 2024](https://blog.talosintelligence.com/arcanedoor-new-espionage-focused-campaign-found-targeting-perimeter-network-devices/)
- [C0011 - C0011](../../../../Threat%20Intelligence/Campaigns/C0011%20-%20C0011.md) — For [C0011](https://attack.mitre.org/campaigns/C0011), [Transparent Tribe](https://attack.mitre.org/groups/G0134) established SSL certificates on the typo-squatted domains the group registered.(Citation: Cisco Talos Transparent Tribe Education Campaign July 2022) [Cisco Talos Transparent Tribe Education Campaign July 2022](https://blog.talosintelligence.com/2022/07/transparent-tribe-targets-education.html)
- [G0047 - Gamaredon Group](../../../../Threat%20Intelligence/Groups/G0047%20-%20Gamaredon%20Group.md) — [Gamaredon Group](https://attack.mitre.org/groups/G0047) has used the same TLS certificate across its infrastructure.(Citation: Huntio_GamaredonFlux_Apr2025) [Huntio_GamaredonFlux_Apr2025](https://hunt.io/blog/state-sponsored-activity-gamaredon-shadowpad)
- [C0050 - J-magic Campaign](../../../../Threat%20Intelligence/Campaigns/C0050%20-%20J-magic%20Campaign.md) — During the [J-magic Campaign](https://attack.mitre.org/campaigns/C0050), threat actors used self-signed certificates on VPS C2 infrastructure.(Citation: Lumen J-Magic JAN 2025) [Lumen J-Magic JAN 2025](https://blog.lumen.com/the-j-magic-show-magic-packets-and-where-to-find-them/)
- [G0056 - PROMETHIUM](../../../../Threat%20Intelligence/Groups/G0056%20-%20PROMETHIUM.md) — [PROMETHIUM](https://attack.mitre.org/groups/G0056) has created self-signed digital certificates for use in HTTPS C2 traffic.(Citation: Talos Promethium June 2020) [Talos Promethium June 2020](https://blog.talosintelligence.com/2020/06/promethium-extends-with-strongpity3.html)
- [G1053 - Storm-0501](../../../../Threat%20Intelligence/Groups/G1053%20-%20Storm-0501.md) — [Storm-0501](https://attack.mitre.org/groups/G1053) has utilized their own self-signed TLS certificate “Microsoft IT TLS CA 5” with their infrastructure.(Citation: Google Mandiant Storm-0501 Sabbath Ransomware November 2021) [Google Mandiant Storm-0501 Sabbath Ransomware November 2021](https://cloud.google.com/blog/topics/threat-intelligence/sabbath-ransomware-affiliate/)

## Mitigations

- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Detection strategies

- [DET0844 - Detection of Digital Certificates](../../../../Defenses/Detection%20Strategies/DET0844%20-%20Detection%20of%20Digital%20Certificates.md)

## Sources

- [Spice Works Digital Certificates](https://www.spiceworks.com/security/digital-certificate/)
