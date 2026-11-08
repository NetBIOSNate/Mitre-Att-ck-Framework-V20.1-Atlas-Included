# T1542.002 - Component Firmware

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1542 - Pre-OS Boot](../README.md)

Adversaries may modify component firmware to persist on systems. Some adversaries may employ sophisticated means to compromise computer components and install malicious firmware that will execute adversary code outside of the operating system and main system firmware or BIOS. This technique may be similar to [System Firmware](https://attack.mitre.org/techniques/T1542/001) but conducted upon other system components/devices that may not have the same capability or level of integrity checking.

Malicious component firmware could provide both a persistent level of access to systems despite potential typical failures to maintain access and hard disk re-images, as well as a way to evade host software-based defenses and integrity checks.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1542/002)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Stealth](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0323 - Detection Strategy for T1542.002 Pre-OS Boot: Component Firmware](../../../../Defenses/Detection%20Strategies/DET0323%20-%20Detection%20Strategy%20for%20T1542.002%20Pre-OS%20Boot%20-%20Component%20Firmware.md)

## Procedure examples

- [S0687 - Cyclops Blink](../../../../Threat%20Intelligence/Software/Malware/S0687%20-%20Cyclops%20Blink.md) — [Cyclops Blink](https://attack.mitre.org/software/S0687) has maintained persistence by patching legitimate device firmware when it is downloaded, including that of WatchGuard devices.(Citation: NCSC Cyclops Blink February 2022) [NCSC Cyclops Blink February 2022](https://www.ncsc.gov.uk/files/Cyclops-Blink-Malware-Analysis-Report.pdf)
- [G0020 - Equation](../../../../Threat%20Intelligence/Groups/G0020%20-%20Equation.md) — [Equation](https://attack.mitre.org/groups/G0020) is known to have the capability to overwrite the firmware on hard drives from some manufacturers.(Citation: Kaspersky Equation QA) [Kaspersky Equation QA](https://media.kasperskycontenthub.com/wp-content/uploads/sites/43/2018/03/08064459/Equation_group_questions_and_answers.pdf)

## Mitigations

- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Perform regular firmware updates to mitigate risks of exploitation and/or abuse.
