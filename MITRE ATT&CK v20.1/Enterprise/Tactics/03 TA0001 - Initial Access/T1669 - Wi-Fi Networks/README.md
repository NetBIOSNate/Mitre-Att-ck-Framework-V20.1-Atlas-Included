# T1669 - Wi-Fi Networks

[Enterprise](../../../README.md) / [Initial Access](../README.md)

Adversaries may gain initial access to target systems by connecting to wireless networks. They may accomplish this by exploiting open Wi-Fi networks used by target devices or by accessing secured Wi-Fi networks — requiring [Valid Accounts](https://attack.mitre.org/techniques/T1078) — belonging to a target organization.(Citation: DOJ GRU Charges 2018)(Citation: Nearest Neighbor Volexity) Establishing a connection to a Wi-Fi access point requires a certain level of proximity to both discover and maintain a stable network connection. 

Adversaries may establish a wireless connection through various methods, such as by physically positioning themselves near a Wi-Fi network to conduct close access operations. To bypass the need for physical proximity, adversaries may attempt to remotely compromise nearby third-party systems that have both wired and wireless network connections available (i.e., dual-homed systems). These third-party compromised devices can then serve as a bridge to connect to a target’s Wi-Fi network.(Citation: Nearest Neighbor Volexity)

Once an initial wireless connection is achieved, adversaries may leverage this access for follow-on activities in the victim network or further targeting of specific devices on the network. Adversaries may perform [Network Sniffing](https://attack.mitre.org/techniques/T1040) or [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) activities for [Credential Access](https://attack.mitre.org/tactics/TA0006) or [Discovery](https://attack.mitre.org/tactics/TA0007).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1669)

**Tactics**  [Initial Access](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md), [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Ensure that all wired and/or wireless traffic is encrypted appropriately. Use best practices for authentication protocols, such as Kerberos, and ensure that web traffic that may contain credentials is protected by SSL/TLS.
- [M1032 - Multi-factor Authentication](../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Harden access requirements for Wi-Fi networks through using two or more pieces of evidence to authenticate, such as a username and password in addition to a token from a physical smart card or token generator.
- [M1030 - Network Segmentation](../../../Defenses/Mitigations/M1030%20-%20Network%20Segmentation.md) — Network segmentation can be used to isolate infrastructure components that do not require broad network access. Separate networking environments for Wi-Fi and Ethernet-wired networks, particularly where Ethernet-based networks allow for access to sensitive resources.

## Procedure examples

- [G0007 - APT28](../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has exploited open Wi-Fi access points for initial access to target devices using the network.(Citation: Nearest Neighbor Volexity)(Citation: DOJ GRU Charges 2018) [Nearest Neighbor Volexity](https://www.volexity.com/blog/2024/11/22/the-nearest-neighbor-attack-how-a-russian-apt-weaponized-nearby-wi-fi-networks-for-covert-access/) · [DOJ GRU Charges 2018](https://www.justice.gov/archives/opa/pr/us-charges-russian-gru-officers-international-hacking-and-related-influence-and)
- [C0051 - APT28 Nearest Neighbor Campaign](../../../Threat%20Intelligence/Campaigns/C0051%20-%20APT28%20Nearest%20Neighbor%20Campaign.md) — During [APT28 Nearest Neighbor Campaign](https://attack.mitre.org/campaigns/C0051), [APT28](https://attack.mitre.org/groups/G0007) established wireless connections to secure, enterprise Wi-Fi networks belonging to a target organization for initial access into the environment.(Citation: Nearest Neighbor Volexity) [Nearest Neighbor Volexity](https://www.volexity.com/blog/2024/11/22/the-nearest-neighbor-attack-how-a-russian-apt-weaponized-nearby-wi-fi-networks-for-covert-access/)

## Detection strategies

- [DET0536 - Detection Strategy for Wi-Fi Networks](../../../Defenses/Detection%20Strategies/DET0536%20-%20Detection%20Strategy%20for%20Wi-Fi%20Networks.md)

## Sources

- [Nearest Neighbor Volexity](https://www.volexity.com/blog/2024/11/22/the-nearest-neighbor-attack-how-a-russian-apt-weaponized-nearby-wi-fi-networks-for-covert-access/)
- [DOJ GRU Charges 2018](https://www.justice.gov/archives/opa/pr/us-charges-russian-gru-officers-international-hacking-and-related-influence-and)
