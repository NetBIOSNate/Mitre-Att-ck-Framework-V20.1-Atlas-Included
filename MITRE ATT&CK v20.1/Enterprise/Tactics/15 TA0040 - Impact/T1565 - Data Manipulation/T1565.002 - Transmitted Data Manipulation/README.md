# T1565.002 - Transmitted Data Manipulation

[Enterprise](../../../../README.md) / [Impact](../../README.md) / [T1565 - Data Manipulation](../README.md)

Adversaries may alter data en route to storage or other systems in order to manipulate external outcomes or hide activity, thus threatening the integrity of the data.(Citation: FireEye APT38 Oct 2018)(Citation: DOJ Lazarus Sony 2018) By manipulating transmitted data, adversaries may attempt to affect a business process, organizational understanding, and decision making.

Manipulation may be possible over a network connection or between system processes where there is an opportunity deploy a tool that will intercept and change information. The type of modification and the impact it will have depends on the target transmission mechanism as well as the goals and objectives of the adversary. For complex systems, an adversary would likely need special expertise and possibly access to specialized software related to the system that would typically be gained through a prolonged information gathering campaign in order to have the desired impact.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1565/002)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has used DYEPACK to manipulate SWIFT messages en route to a printer.(Citation: FireEye APT38 Oct 2018) [FireEye APT38 Oct 2018](https://services.google.com/fh/files/misc/apt38-un-usual-suspects.pdf)
- [S9010 - GlassWorm](../../../../Threat%20Intelligence/Software/Malware/S9010%20-%20GlassWorm.md) — [GlassWorm](https://attack.mitre.org/software/S9010) can intercept and modify transaction details associated with hardware wallet applications before signing.(Citation: Koi Glassworm New Tricks December 2025) [Koi Glassworm New Tricks December 2025](https://www.koi.ai/blog/glassworm-goes-mac-fresh-infrastructure-new-tricks)
- [S0395 - LightNeuron](../../../../Threat%20Intelligence/Software/Malware/S0395%20-%20LightNeuron.md) — [LightNeuron](https://attack.mitre.org/software/S0395) is capable of modifying email content, headers, and attachments during transit.(Citation: ESET LightNeuron May 2019) [ESET LightNeuron May 2019](https://www.welivesecurity.com/wp-content/uploads/2019/05/ESET-LightNeuron.pdf)
- [S0530 - Melcoz](../../../../Threat%20Intelligence/Software/Malware/S0530%20-%20Melcoz.md) — [Melcoz](https://attack.mitre.org/software/S0530) can monitor the clipboard for cryptocurrency addresses and change the intended address to one controlled by the adversary.(Citation: Securelist Brazilian Banking Malware July 2020) [Securelist Brazilian Banking Malware July 2020](https://securelist.com/the-tetrade-brazilian-banking-malware/97779/)
- [S0455 - Metamorfo](../../../../Threat%20Intelligence/Software/Malware/S0455%20-%20Metamorfo.md) — [Metamorfo](https://attack.mitre.org/software/S0455) has a function that can watch the contents of the system clipboard for valid bitcoin addresses, which it then overwrites with the attacker's address.(Citation: Fortinet Metamorfo Feb 2020)(Citation: ESET Casbaneiro Oct 2019) [Fortinet Metamorfo Feb 2020](https://www.fortinet.com/blog/threat-research/another-metamorfo-variant-targeting-customers-of-financial-institutions) · [ESET Casbaneiro Oct 2019](https://www.welivesecurity.com/2019/10/03/casbaneiro-trojan-dangerous-cooking/)

## Mitigations

- [M1041 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M1041%20-%20Encrypt%20Sensitive%20Information.md) — Encrypt all important data flows to reduce the impact of tailored modifications on data in transit.

## Detection strategies

- [DET0254 - Detection Strategy of Transmitted Data Manipulation](../../../../Defenses/Detection%20Strategies/DET0254%20-%20Detection%20Strategy%20of%20Transmitted%20Data%20Manipulation.md)

## Sources

- [DOJ Lazarus Sony 2018](https://www.justice.gov/opa/press-release/file/1092091/download)
- [FireEye APT38 Oct 2018](https://services.google.com/fh/files/misc/apt38-un-usual-suspects.pdf)
