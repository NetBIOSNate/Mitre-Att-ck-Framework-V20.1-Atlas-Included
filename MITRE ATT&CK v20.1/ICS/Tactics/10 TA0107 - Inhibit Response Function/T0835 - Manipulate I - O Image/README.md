# T0835 - Manipulate I/O Image

[ICS](../../../README.md) / [Inhibit Response Function](../README.md)

Adversaries may manipulate the I/O image of PLCs through various means to prevent them from functioning as expected. Methods of I/O image manipulation may include overriding the I/O table via direct memory manipulation or using the override function used for testing PLC programs. (Citation: Dr. Kelvin T. Erickson December 2010) During the scan cycle, a PLC reads the status of all inputs and stores them in an image table. (Citation: Nanjundaiah, Vaidyanath) The image table is the PLCs internal storage location where values of inputs/outputs for one scan are stored while it executes the user program. After the PLC has solved the entire logic program, it updates the output image table. The contents of this output image table are written to the corresponding output points in I/O Modules. 

One of the unique characteristics of PLCs is their ability to override the status of a physical discrete input or to override the logic driving a physical output coil and force the output to a desired status.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T0835)

**Tactics**  [Inhibit Response Function](../README.md)

**Platforms**  [Embedded](../../../Platforms/Embedded.md)

## Detection strategies

- [DET0773 - Detection of Manipulate I/O Image](../../../Defenses/Detection%20Strategies/DET0773%20-%20Detection%20of%20Manipulate%20I%20-%20O%20Image.md)

## Targeted assets

- [A0017 - Distributed Control System (DCS) Controller](../../../Defenses/Assets/A0017%20-%20Distributed%20Control%20System%20%28DCS%29%20Controller.md)
- [A0018 - Programmable Automation Controller (PAC)](../../../Defenses/Assets/A0018%20-%20Programmable%20Automation%20Controller%20%28PAC%29.md)
- [A0003 - Programmable Logic Controller (PLC)](../../../Defenses/Assets/A0003%20-%20Programmable%20Logic%20Controller%20%28PLC%29.md)
- [A0010 - Safety Controller](../../../Defenses/Assets/A0010%20-%20Safety%20Controller.md)

## Procedure examples

- [S1006 - PLC-Blaster](../../../Threat%20Intelligence/Software/Malware/S1006%20-%20PLC-Blaster.md) — [PLC-Blaster](https://attack.mitre.org/software/S1006) may manipulate any outputs of the PLC. Using the POU POKE any value within the process image may be modified. (Citation: Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016) [Spenneberg, Ralf, Maik Brggemann, and Hendrik Schwartke March 2016](https://www.blackhat.com/docs/asia-16/materials/asia-16-Spenneberg-PLC-Blaster-A-Worm-Living-Solely-In-The-PLC-wp.pdf)
- [S0603 - Stuxnet](../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — When the peripheral output is written to, sequence C intercepts the output and ensures it is not written to the process image output. The output is the instructions the PLC sends to a device to change its operating behavior. By intercepting the peripheral output, [Stuxnet](https://attack.mitre.org/software/S0603) prevents an operator from noticing unauthorized commands sent to the peripheral. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Mitigations

- [M0816 - Mitigation Limited or Not Effective](../../../Defenses/Mitigations/M0816%20-%20Mitigation%20Limited%20or%20Not%20Effective.md) — This technique may not be effectively mitigated against, consider controls for assets and processes that lead to the use of this technique.

## Sources

- [Dr. Kelvin T. Erickson December 2010](https://www.scribd.com/document/458637574/Programmable-Logic-Controllers)
- [Nanjundaiah, Vaidyanath](https://www.ezautomation.net/industry-articles/plc-ladder-logic-basics.htm)
