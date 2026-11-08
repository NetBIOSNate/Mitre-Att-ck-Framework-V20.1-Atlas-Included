# T0873 - Project File Infection

[ICS](../../../README.md) / [Persistence](../README.md)

Adversaries may attempt to infect project files with malicious code. These project files may consist of objects, program organization units, variables such as tags, documentation, and other configurations needed for PLC programs to function.(Citation: Beckhoff) Using built in functions of the engineering software, adversaries may be able to download an infected program to a PLC in the operating environment enabling further [Execution](https://attack.mitre.org/tactics/TA0104) and [Persistence](https://attack.mitre.org/tactics/TA0110) techniques.(Citation: PLCdev) 

Adversaries may export their own code into project files with conditions to execute at specific intervals.(Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) Malicious programs allow adversaries control of all aspects of the process enabled by the PLC. Once the project file is downloaded to a PLC the workstation device may be disconnected with the infected project file still executing.(Citation: PLCdev)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0873)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md), [Linux](../../../Platforms/Linux.md)

## Sub-techniques

- [T0873.001 - Siemens Project File Format](T0873.001%20-%20Siemens%20Project%20File%20Format/README.md)

## Targeted assets

- [A0001 - Workstation](../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Mitigations

- [M0947 - Audit](../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Review the integrity of project files to verify they have not been modified by adversary behavior. Verify a cryptographic hash for the file with a known trusted version, or look for other indicators of modification (e.g., timestamps).
- [M0945 - Code Signing](../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Allow for code signing of any project files stored at rest to prevent unauthorized tampering. Ensure the signing keys are not easily accessible on the same system.
- [M0941 - Encrypt Sensitive Information](../../../Defenses/Mitigations/M0941%20-%20Encrypt%20Sensitive%20Information.md) — When at rest, project files should be encrypted to prevent unauthorized changes.(Citation: National Institute of Standards and Technology April 2013) [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0922 - Restrict File and Directory Permissions](../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure permissions restrict project file access to only engineer and technician user groups and accounts.

## Detection strategies

- [DET0766 - Detection of Project File Infection](../../../Defenses/Detection%20Strategies/DET0766%20-%20Detection%20of%20Project%20File%20Infection.md)

## Sources

- [Beckhoff](https://infosys.beckhoff.com/english.php?content=../content/1033/tc3_sourcecontrol/18014398915785483.html&id=)
- [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
- [PLCdev](http://www.plcdev.com/book/export/html/373)
