# AML.T0092 - Manipulate User LLM Chat History

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may manipulate a user's large language model (LLM) chat history to cover the tracks of their malicious behavior. They may hide persistent changes they have made to the LLM's behavior, or obscure their attempts at discovering private information about the user.

To do so, adversaries may delete or edit existing messages or create new threads as part of their coverup. This is feasible if the adversary has the victim's authentication tokens for the backend LLM service or if they have direct access to the victim's chat interface. 

Chat interfaces (especially desktop interfaces) often do not show the injected prompt for any ongoing chat, as they update chat history only once when initially opening it. This can help the adversary's manipulations go unnoticed by the victim.

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0036 - AIKatz: Attacking LLM Desktop Applications](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md) · [S08](../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s08)
- [AML.CS0048 - Exposed ClawdBot Control Interfaces Leads to Credential Access and Execution](../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0048%20-%20Exposed%20ClawdBot%20Control%20Interfaces%20Leads%20to%20Credential%20Access%20and%20Execution.md#step-s07)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0092)
