# AML.T0091.000 - Application Access Token

[MITRE ATLAS](../../../../README.md) / [AML.TA0015 - Lateral Movement](../../README.md) / [AML.T0091 - Use Alternate Authentication Material](../README.md)

Adversaries may use stolen application access tokens to bypass the typical authentication process and access restricted accounts, information, or services on remote systems. These tokens are typically stolen from users or services and used in lieu of login credentials.

Application access tokens are used to make authorized API requests on behalf of a user or service and are commonly used to access resources in cloud, container-based applications, software-as-a-service (SaaS), and AI-as-a-service(AIaaS). They are commonly used for AI services such as chatbots, LLMs, and predictive inference APIs.

**Tactics**  [AML.TA0015 - Lateral Movement](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1550.001](../../../../../Enterprise/Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.001%20-%20Application%20Access%20Token/README.md) · [MITRE ATT&CK T1550.001](https://attack.mitre.org/techniques/T1550/001/)

## Case studies

- [AML.CS0036 - AIKatz: Attacking LLM Desktop Applications](../../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md) · [S03](../../../../Case%20Studies/Exercises/AML.CS0036%20-%20AIKatz%20-%20Attacking%20LLM%20Desktop%20Applications.md#step-s03)
- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S28](../../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s28), [S34](../../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s34)

## Mitigations

- [AML.M0019 - Control Access to AI Models and Data in Production](../../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Enforce authorization and monitor production AI API use for anomalous activity associated with replayed access tokens.
- [AML.M0043 - AI Agent External Resource Lifecycle Management](../../../../Mitigations/AML.M0043%20-%20AI%20Agent%20External%20Resource%20Lifecycle%20Management.md) — Expire and revoke agent-associated application access tokens to limit the window for unauthorized use.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0091.000)
