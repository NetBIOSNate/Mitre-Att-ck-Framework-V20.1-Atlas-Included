# TA0109 - Lateral Movement

[ICS](../../README.md) / [Tactics](../README.md)

The adversary is trying to move through your ICS environment.

Lateral Movement consists of techniques that adversaries use to enter and control remote systems on a network. These techniques abuse default credentials, known accounts, and vulnerable services, and may also leverage dual-homed devices and systems that reside on both the IT and OT networks. The adversary uses these techniques to pivot to their next point in the environment, positioning themselves to where they want to be or think they should be. Following through on their primary objective often requires [Discovery](https://attack.mitre.org/tactics/TA0102) of the network and [Collection](https://attack.mitre.org/tactics/TA0100) to develop awareness of unique ICS devices and processes, in order to find their target and subsequently gain access to it. Reaching this objective often involves pivoting through multiple systems, devices, and accounts. Adversaries may install their own remote tools to accomplish Lateral Movement or leverage default tools, programs, and manufacturer set or other legitimate credentials native to the network, which may be stealthier.

[MITRE ATT&CK record](https://attack.mitre.org/tactics/TA0109)

## Techniques

- [T0866 - Exploitation of Remote Services](T0866%20-%20Exploitation%20of%20Remote%20Services/README.md)
- [T1694 - Insecure Credentials](T1694%20-%20Insecure%20Credentials/README.md)
- [T0867 - Lateral Tool Transfer](T0867%20-%20Lateral%20Tool%20Transfer/README.md)
- [T0843 - Program Download](T0843%20-%20Program%20Download/README.md)
- [T0886 - Remote Services](T0886%20-%20Remote%20Services/README.md)
- [T0859 - Valid Accounts](T0859%20-%20Valid%20Accounts/README.md)
