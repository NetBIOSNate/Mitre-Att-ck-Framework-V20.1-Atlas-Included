# AML.S0010 - Sliver

[MITRE ATLAS](../../README.md) / [Software](../README.md)

[Sliver](AML.S0010%20-%20Sliver.md) is an open-source adversary-emulation and red-team framework supporting Windows, Linux, and macOS. It provides remote implants, operator clients, and a command-and-control server for conducting post-exploitation activities. Its implants support communication over mutual TLS, WireGuard, HTTP(S), and DNS. [canonical-source](https://github.com/BishopFox/sliver)

**Software type**  Tool

**Software categories**  program

## Used by

- [AML.CS0027 - Organization Confusion on Hugging Face](../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) — The researcher used code embedded in TensorFlow/Keras models to download and launch [Sliver](AML.S0010%20-%20Sliver.md) implants during model training and inference. The implants established remote control sessions while the models continued operating. The researcher named the implant process training.bin to resemble machine learning activity. [ref-5stars217](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/#unexpected-benefits---organization-confusion)

## Techniques implemented

- [AML.T0072 - Cyber Communication Channel](../../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0072%20-%20Cyber%20Communication%20Channel/README.md) — [Sliver](AML.S0010%20-%20Sliver.md) implants launched through TensorFlow/Keras model execution established remote sessions that allowed the researcher to execute commands and explore the host environment. [source-1](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/)

## References

- [Model Confusion: Weaponizing ML models for red teams and bounty hunters](https://5stars217.github.io/2023-08-08-red-teaming-with-ml-models/)
- [Sliver: canonical implementation source](https://github.com/BishopFox/sliver)

[Official ATLAS record](https://atlas.mitre.org/software/AML.S0010)
