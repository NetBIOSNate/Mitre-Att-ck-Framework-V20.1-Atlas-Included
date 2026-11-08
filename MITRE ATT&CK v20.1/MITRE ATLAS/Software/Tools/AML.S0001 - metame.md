# AML.S0001 - metame

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[metame](AML.S0001%20-%20metame.md) is an open-source metamorphic code engine for generating variants of executable files. It uses radare2 to parse files and analyze code, randomly replaces selected instructions with equivalents of the same logic and size, and patches a copy of the original binary. It supports 32-bit and 64-bit x86 architectures and multiple executable formats. [github](https://github.com/a0rtega/metame)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.CS0002 - VirusTotal Poisoning](../../Case%20Studies/Incidents/AML.CS0002%20-%20VirusTotal%20Poisoning.md) — The actor used [metame](AML.S0001%20-%20metame.md) to generate mutated variants of a ransomware executable.

## Techniques implemented

- [AML.T0043 - Craft Adversarial Data](../../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) — [metame](AML.S0001%20-%20metame.md) generates modified executables by randomly substituting instructions with logically equivalent, same-sized alternatives. These mutations alter the binary representation while aiming to preserve program behavior. [github](https://github.com/a0rtega/metame)

## References

- [metame GitHub](https://github.com/a0rtega/metame)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0001)
