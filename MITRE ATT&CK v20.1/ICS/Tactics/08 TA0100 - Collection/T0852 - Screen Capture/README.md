# T0852 - Screen Capture

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may attempt to perform screen capture of devices in the control system environment. Screenshots may be taken of workstations, HMIs, or other devices that display environment-relevant process, device, reporting, alarm, or related data. These device displays may reveal information regarding the ICS process, layout, control, and related schematics. In particular, an HMI can provide a lot of important industrial process information. (Citation: ICS-CERT October 2017) Analysis of screen captures may provide the adversary with an understanding of intended operations and interactions between critical devices.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0852)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md), [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Procedure examples

- [C0063 - 2025 Poland Wiper Attacks](../../../Threat%20Intelligence/Campaigns/C0063%20-%202025%20Poland%20Wiper%20Attacks.md) — During the [2025 Poland Wiper Attacks](https://attack.mitre.org/campaigns/C0063), the adversaries used the `nircmd` utility to capture screenshots of systems.(Citation: CERT Polska) [CERT Polska](https://cert.pl/uploads/docs/CERT_Polska_Energy_Sector_Incident_Report_2025.pdf)
- [G1000 - ALLANITE](../../../Threat%20Intelligence/Groups/G1000%20-%20ALLANITE.md) — [ALLANITE](https://attack.mitre.org/groups/G1000) has been identified to collect and distribute screenshots of ICS systems such as HMIs. (Citation: Dragos) (Citation: ICS-CERT October 2017) [Dragos](https://dragos.com/resource/allanite/) · [ICS-CERT October 2017](https://www.us-cert.gov/ncas/alerts/TA17-293A)
- [G0064 - APT33](../../../Threat%20Intelligence/Groups/G0064%20-%20APT33.md) — [APT33](https://attack.mitre.org/groups/G0064) utilize backdoors capable of capturing screenshots once installed on a system. (Citation: Jacqueline O'Leary et al. September 2017)(Citation: Junnosuke Yagi March 2017) [Jacqueline O'Leary et al. September 2017](https://www.fireeye.com/blog/threat-research/2017/09/apt33-insights-into-iranian-cyber-espionage.html) · [Junnosuke Yagi March 2017](https://www.symantec.com/security-center/writeup/2017-030708-4403-99)

## Detection strategies

- [DET0751 - Detection of Screen Capture](../../../Defenses/Detection%20Strategies/DET0751%20-%20Detection%20of%20Screen%20Capture.md)

## Mitigations

- [M0816 - Mitigation Limited or Not Effective](../../../Defenses/Mitigations/M0816%20-%20Mitigation%20Limited%20or%20Not%20Effective.md) — Preventing screen capture on a device may require disabling various system calls supported by the operating systems (e.g., Microsoft Windows.Graphics.Capture APIs), however, these may be needed for other critical applications.

## Targeted assets

- [A0002 - Human-Machine Interface (HMI)](../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Sources

- [ICS-CERT October 2017](https://www.us-cert.gov/ncas/alerts/TA17-293A)
