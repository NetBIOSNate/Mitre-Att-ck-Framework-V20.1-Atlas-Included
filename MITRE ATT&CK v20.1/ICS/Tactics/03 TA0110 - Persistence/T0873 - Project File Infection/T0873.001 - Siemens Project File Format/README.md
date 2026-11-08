# T0873.001 - Siemens Project File Format

[ICS](../../../../README.md) / [Persistence](../../README.md) / [T0873 - Project File Infection](../README.md)

Adversaries may infect Siemens PLC project files (i.e., Step 7, WinCC, etc.) to achieve [Execution](https://attack.mitre.org/tactics/TA0104), [Persistence](https://attack.mitre.org/tactics/TA0110), and [Lateral Movement](https://attack.mitre.org/tactics/TA0109) objectives. Adversaries may modify an existing project file or bring their own project files into the environment.(Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011)

The ability for an adversary to deploy an infected project file relies on access to a workstation with Siemens PLC programming software installed on it from which a program download can be performed.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0873/001)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [Linux](../../../../Platforms/Linux.md)

## Mitigations

- [M0947 - Audit](../../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Review the integrity of project files to verify they have not been modified by adversary behavior. Verify a cryptographic hash for the file with a known trusted version, or look for other indicators of modification (e.g., timestamps).
- [M0945 - Code Signing](../../../../Defenses/Mitigations/M0945%20-%20Code%20Signing.md) — Allow for code signing of any project files stored at rest to prevent unauthorized tampering. Ensure the signing keys are not easily accessible on the same system.
- [M0941 - Encrypt Sensitive Information](../../../../Defenses/Mitigations/M0941%20-%20Encrypt%20Sensitive%20Information.md) — When at rest, project files should be encrypted to prevent unauthorized changes.(Citation: National Institute of Standards and Technology April 2013) [National Institute of Standards and Technology April 2013](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
- [M0922 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M0922%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Ensure permissions restrict project file access to only engineer and technician user groups and accounts.

## Targeted assets

- [A0001 - Workstation](../../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [S0603 - Stuxnet](../../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) copies itself into Step 7 projects in such a way that it automatically executes when the Step 7 project is loaded. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Detection strategies

- [DET0906 - Detection of Siemens Project File Format Infection](../../../../Defenses/Detection%20Strategies/DET0906%20-%20Detection%20of%20Siemens%20Project%20File%20Format%20Infection.md)

## Sources

- [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)
