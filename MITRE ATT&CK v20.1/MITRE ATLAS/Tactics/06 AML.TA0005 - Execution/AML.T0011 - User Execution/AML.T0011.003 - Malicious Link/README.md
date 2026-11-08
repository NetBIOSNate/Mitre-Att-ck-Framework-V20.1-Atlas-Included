# AML.T0011.003 - Malicious Link

[MITRE ATLAS](../../../../README.md) / [AML.TA0005 - Execution](../../README.md) / [AML.T0011 - User Execution](../README.md)

An adversary may rely upon a user clicking a malicious link in order to gain execution. Users may be subjected to social engineering to get them to click on a link that will lead to code execution. This user action will typically be observed as follow-on behavior from Spearphishing Link. Clicking on a link may also lead to other execution techniques such as exploitation of a browser or application vulnerability via Exploitation for Client Execution. Links may also lead users to download files that require execution via Malicious File.

There are many ways an adversary can leverage malicious links to gain access to a victim system via an AI system. For example, an AI Agent that is configured to not validate website origin headers will accept connections from any website, allowing adversaries to access otherwise inaccessible networks.

**Tactics**  [AML.TA0005 - Execution](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Demonstrated

**ATT&CK mapping**  [Local ATT&CK T1204](../../../../../Enterprise/Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/README.md) · [MITRE ATT&CK T1204](https://attack.mitre.org/techniques/T1204/)

## Case studies

- [AML.CS0050 - OpenClaw 1-Click Remote Code Execution](../../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md) · [S02](../../../../Case%20Studies/Exercises/AML.CS0050%20-%20OpenClaw%201-Click%20Remote%20Code%20Execution.md#step-s02)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0011.003)
