# T0823 - Graphical User Interface

[ICS](../../../README.md) / [Execution](../README.md)

Adversaries may attempt to gain access to a machine via a Graphical User Interface (GUI) to enhance execution capabilities. Access to a GUI allows a user to interact with a computer in a more visual manner than a CLI. A GUI allows users to move a cursor and click on interface objects, with a mouse and keyboard as the main input devices, as opposed to just using the keyboard.

If physical access is not an option, then access might be possible via protocols such as VNC on Linux-based and Unix-based operating systems, and RDP on Windows operating systems. An adversary can use this access to execute programs and applications on the target machine.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0823)

**Tactics**  [Execution](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md), [Network Devices](../../../Platforms/Network%20Devices.md)

## Targeted assets

- [A0008 - Application Server](../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0016 - Firewall](../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0015 - Switch](../../../Defenses/Assets/A0015%20-%20Switch.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Mitigations

- [M0816 - Mitigation Limited or Not Effective](../../../Defenses/Mitigations/M0816%20-%20Mitigation%20Limited%20or%20Not%20Effective.md) — Once an adversary has access to a remote GUI they can abuse system features, such as required HMI functions.

## Procedure examples

- [C0028 - 2015 Ukraine Electric Power Attack](../../../Threat%20Intelligence/Campaigns/C0028%20-%202015%20Ukraine%20Electric%20Power%20Attack.md) — During the [2015 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0028), [Sandworm Team](https://attack.mitre.org/groups/G0034) utilized HMI GUIs in the SCADA environment to open breakers. (Citation: Ukraine15 - EISAC - 201603) [Ukraine15 - EISAC - 201603](https://nsarchive.gwu.edu/sites/default/files/documents/3891751/SANS-and-Electricity-Information-Sharing-and.pdf)
- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used a graphical user interface (GUI) via the Remote Desktop Protocol (RDP) to access the Mikronika HMI and to execute commands.(Citation: CERT Polska) During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used a graphical user interface (GUI) to connect to the domain controller via the Remote Desktop Protocol (RDP) to collect and exfiltrate data and attempt to destroy data on the system.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)

## Detection strategies

- [DET0772 - Detection of Graphical User Interface](../../../Defenses/Detection%20Strategies/DET0772%20-%20Detection%20of%20Graphical%20User%20Interface.md)
