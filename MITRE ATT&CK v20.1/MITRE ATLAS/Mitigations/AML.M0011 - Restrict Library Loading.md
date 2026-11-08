# AML.M0011 - Restrict Library Loading

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Prevent abuse of library loading mechanisms in the operating system and software to load untrusted code by configuring appropriate library loading mechanisms and investigating potential vulnerable software.

File formats such as pickle files that are commonly used to store AI models can contain exploits that allow for loading of malicious libraries.

**ATT&CK mapping**  [Local ATT&CK M1044](../../Enterprise/Defenses/Mitigations/M1044%20-%20Restrict%20Library%20Loading.md) · [MITRE ATT&CK M1044](https://attack.mitre.org/mitigations/M1044/)

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Deployment

## Techniques mitigated

- [AML.T0011 - User Execution](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/README.md) — Restricting binaries from loading external libraries can limit their ability to execute malicious code.
- [AML.T0011.000 - Unsafe AI Artifacts](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.000%20-%20Unsafe%20AI%20Artifacts/README.md) — Restrict library loading by ML artifacts.
- [AML.T0011.001 - Malicious Package](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.001%20-%20Malicious%20Package/README.md) — Restricting packages from loading external libraries can limit their ability to execute malicious code.
- [AML.T0050 - Command and Scripting Interpreter](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0050%20-%20Command%20and%20Scripting%20Interpreter/README.md) — Restrict library loading so command and script interpreters cannot load untrusted libraries as an execution mechanism.
- [AML.T0074 - Masquerading](../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0074%20-%20Masquerading/README.md) — Restrict library loading to trusted locations and approved libraries so disguised malicious libraries cannot be loaded as legitimate dependencies.
- [AML.T0090 - OS Credential Dumping](../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0090%20-%20OS%20Credential%20Dumping/README.md) — Restrict library loading to block credential-dumping paths that inject or load malicious code into processes holding authentication material.
- [AML.T0119 - Exploit Automated Artifact Processing Pipeline](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0119%20-%20Exploit%20Automated%20Artifact%20Processing%20Pipeline/README.md) — Restrict library loading to limit the introduction of untrusted outside code into an automated pipeline.
- [AML.T0142 - Event Triggered Execution](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0142%20-%20Event%20Triggered%20Execution/README.md) — Restrict automatic loading to trusted locations and disable unnecessary interpreter startup hooks.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0011)
