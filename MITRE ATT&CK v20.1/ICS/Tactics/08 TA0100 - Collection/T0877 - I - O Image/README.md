# T0877 - I/O Image

[ICS](../../../README.md) / [Collection](../README.md)

Adversaries may seek to capture process values related to the inputs and outputs of a PLC. During the scan cycle, a PLC reads the status of all inputs and stores them in an image table. (Citation: Nanjundaiah, Vaidyanath) The image table is the PLCs internal storage location where values of inputs/outputs for one scan are stored while it executes the user program. After the PLC has solved the entire logic program, it updates the output image table. The contents of this output image table are written to the corresponding output points in I/O Modules.

The Input and Output Image tables described above make up the I/O Image on a PLC. This image is used by the user program instead of directly interacting with physical I/O. (Citation: Spenneberg, Ralf 2016) 

Adversaries may collect the I/O Image state of a PLC by utilizing a devices [Native API](https://attack.mitre.org/techniques/T0834) to access the memory regions directly. The collection of the PLCs I/O state could be used to replace values or inform future stages of an attack.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0877)

**Tactics**  [Collection](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md)

## Mitigations

- [M0816 - Mitigation Limited or Not Effective](../../../Defenses/Mitigations/M0816%20-%20Mitigation%20Limited%20or%20Not%20Effective.md) — This technique may not be effectively mitigated against, consider controls for assets and processes that lead to the use of this technique.

## Procedure examples

- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) copies the input area of an I/O image into data blocks with a one second interval between copies, forming a 21 second recording of the input area. The input area contains information being passed to the PLC from a peripheral. For example, the current state of a valve or the temperature of a device. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Detection strategies

- [DET0774 - Detection of I/O Image](../../../Defenses/Detection%20Strategies/DET0774%20-%20Detection%20of%20I%20-%20O%20Image.md)

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Sources

- [Nanjundaiah, Vaidyanath](https://www.ezautomation.net/industry-articles/plc-ladder-logic-basics.htm)
- [Spenneberg, Ralf 2016](https://www.blackhat.com/docs/asia-16/materials/asia-16-Spenneberg-PLC-Blaster-A-Worm-Living-Solely-In-The-PLC.pdf)
