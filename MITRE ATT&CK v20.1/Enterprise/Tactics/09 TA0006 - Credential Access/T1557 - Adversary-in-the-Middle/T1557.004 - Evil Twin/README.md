# T1557.004 - Evil Twin

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1557 - Adversary-in-the-Middle](../README.md)

Adversaries may host seemingly genuine Wi-Fi access points to deceive users into connecting to malicious networks as a way of supporting follow-on behaviors such as [Network Sniffing](https://attack.mitre.org/techniques/T1040), [Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1565/002), or [Input Capture](https://attack.mitre.org/techniques/T1056).(Citation: Australia ‘Evil Twin’)

By using a Service Set Identifier (SSID) of a legitimate Wi-Fi network, fraudulent Wi-Fi access points may trick devices or users into connecting to malicious Wi-Fi networks.(Citation: Kaspersky evil twin)(Citation: medium evil twin)  Adversaries may provide a stronger signal strength or block access to Wi-Fi access points to coerce or entice victim devices into connecting to malicious networks.(Citation: specter ops evil twin)  A Wi-Fi Pineapple – a network security auditing and penetration testing tool – may be deployed in Evil Twin attacks for ease of use and broader range. Custom certificates may be used in an attempt to intercept HTTPS traffic. 

Similarly, adversaries may also listen for client devices sending probe requests for known or previously connected networks (Preferred Network Lists or PNLs). When a malicious access point receives a probe request, adversaries can respond with the same SSID to imitate the trusted, known network.(Citation: specter ops evil twin)  Victim devices are led to believe the responding access point is from their PNL and initiate a connection to the fraudulent network.

Upon logging into the malicious Wi-Fi access point, a user may be directed to a fake login page or captive portal webpage to capture the victim’s credentials. Once a user is logged into the fraudulent Wi-Fi network, the adversary may able to monitor network activity, manipulate data, or steal additional credentials. Locations with high concentrations of public Wi-Fi access, such as airports, coffee shops, or libraries, may be targets for adversaries to set up illegitimate Wi-Fi access points.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1557/004)

**Tactics**  [Credential Access](../../README.md), [Collection](../../../12%20TA0009%20-%20Collection/README.md)

**Platforms**  [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [G0007 - APT28](../../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has used a Wi-Fi Pineapple to set up Evil Twin Wi-Fi Poisoning for the purposes of capturing victim credentials or planting espionage-oriented malware.(Citation: US District Court Indictment GRU Oct 2018) [US District Court Indictment GRU Oct 2018](https://www.justice.gov/opa/page/file/1098481/download)

## Mitigations

- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Wireless intrusion prevention systems (WIPS) can identify traffic patterns indicative of adversary-in-the-middle activity and scan for evils twins and rogue access points.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to be suspicious about access points marked as “Open” or “Unsecure” as well as certificate errors. Certificate errors may arise when the application’s certificate does not match the one expected by the host.

## Detection strategies

- [DET0379 - Detect Evil Twin Wi-Fi Access Points on Network Devices](../../../../Defenses/Detection%20Strategies/DET0379%20-%20Detect%20Evil%20Twin%20Wi-Fi%20Access%20Points%20on%20Network%20Devices.md)

## Sources

- [Kaspersky evil twin](https://usa.kaspersky.com/resource-center/preemptive-safety/evil-twin-attacks)
- [medium evil twin](https://kavigihan.medium.com/wireless-security-evil-twin-attack-d3842f4aef59)
- [specter ops evil twin](https://posts.specterops.io/modern-wireless-attacks-pt-i-basic-rogue-ap-theory-evil-twin-and-karma-attacks-35a8571550ee)
- [Australia ‘Evil Twin’](https://www.bleepingcomputer.com/news/security/australian-charged-for-evil-twin-wifi-attack-on-plane/)
