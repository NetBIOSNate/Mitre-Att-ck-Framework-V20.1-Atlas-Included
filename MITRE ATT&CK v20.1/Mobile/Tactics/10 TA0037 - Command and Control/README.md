# TA0037 - Command and Control

[Mobile](../../README.md) / [Tactics](../README.md)

The adversary is trying to communicate with compromised devices to control them.

The command and control tactic represents how adversaries communicate with systems under their control within a target network. There are many ways an adversary can establish command and control with various levels of covertness, depending on system configuration and network topology. Due to the wide degree of variation available to the adversary at the network level, only the most common factors were used to describe the differences in command and control. There are still a great many specific techniques within the documented methods, largely due to how easy it is to define new protocols and use existing, legitimate protocols and network services for communication. 

The resulting breakdown should help convey the concept that detecting intrusion through command and control protocols without prior knowledge is a difficult proposition over the long term. Adversaries' main constraints in network-level defense avoidance are testing and deployment of tools to rapidly change their protocols, awareness of existing defensive technologies, and access to legitimate Web services that, when used appropriately, make their tools difficult to distinguish from benign traffic.

Additionally, in the mobile environment, mobile devices are frequently connected to networks outside enterprise control such as cellular networks or public Wi-Fi networks. Adversaries could attempt to evade detection by communicating on these networks, and potentially even by using non-Internet Protocol mechanisms such as Short Message Service (SMS). However, cellular networks often have data caps and/or extra data charges that could increase the potential for adversarial communication to be detected.

[MITRE ATT&CK record](https://attack.mitre.org/tactics/TA0037)

## Techniques

- [T1437 - Application Layer Protocol](T1437%20-%20Application%20Layer%20Protocol/README.md)
- [T1616 - Call Control](T1616%20-%20Call%20Control/README.md)
- [T1637 - Dynamic Resolution](T1637%20-%20Dynamic%20Resolution/README.md)
- [T1521 - Encrypted Channel](T1521%20-%20Encrypted%20Channel/README.md)
- [T1544 - Ingress Tool Transfer](T1544%20-%20Ingress%20Tool%20Transfer/README.md)
- [T1509 - Non-Standard Port](T1509%20-%20Non-Standard%20Port/README.md)
- [T1644 - Out of Band Data](T1644%20-%20Out%20of%20Band%20Data/README.md)
- [T1663 - Remote Access Software](T1663%20-%20Remote%20Access%20Software/README.md)
- [T1481 - Web Service](T1481%20-%20Web%20Service/README.md)
