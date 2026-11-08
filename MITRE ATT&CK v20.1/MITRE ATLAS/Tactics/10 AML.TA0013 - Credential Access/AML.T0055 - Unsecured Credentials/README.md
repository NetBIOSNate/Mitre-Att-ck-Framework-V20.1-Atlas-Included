# AML.T0055 - Unsecured Credentials

[MITRE ATLAS](../../../README.md) / [AML.TA0013 - Credential Access](../README.md)

Adversaries may search compromised systems to find and obtain insecurely stored credentials.
These credentials can be stored and/or misplaced in many locations on a system, including plaintext files (e.g. bash history), environment variables, operating system, or application-specific repositories (e.g. Credentials in Registry), or other specialized files/artifacts (e.g. private keys).

**Tactics**  [AML.TA0013 - Credential Access](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1552](../../../../Enterprise/Tactics/09%20TA0006%20-%20Credential%20Access/T1552%20-%20Unsecured%20Credentials/README.md) · [MITRE ATT&CK T1552](https://attack.mitre.org/techniques/T1552/)

## Case studies

- [AML.CS0016 - Achieving Code Execution in MathGPT via Prompt Injection](../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md) · [S06](../../../Case%20Studies/Exercises/AML.CS0016%20-%20Achieving%20Code%20Execution%20in%20MathGPT%20via%20Prompt%20Injection.md#step-s06)
- [AML.CS0023 - ShadowRay: Hijacking Exposed Ray Clusters](../../../Case%20Studies/Incidents/AML.CS0023%20-%20ShadowRay%20-%20Hijacking%20Exposed%20Ray%20Clusters.md) · [S03](../../../Case%20Studies/Incidents/AML.CS0023%20-%20ShadowRay%20-%20Hijacking%20Exposed%20Ray%20Clusters.md#step-s03)
- [AML.CS0027 - Organization Confusion on Hugging Face](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S10](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s10)
- [AML.CS0030 - LLMjacking: Stolen Cloud Credentials Used to Access Cloud LLM Services.](../../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md#step-s01)
- [AML.CS0043 - Malware Prototype with Embedded Prompt Injection](../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0043%20-%20Malware%20Prototype%20with%20Embedded%20Prompt%20Injection.md#step-s05)
- [AML.CS0047 - Code to Deploy Destructive AI Agent Discovered in Amazon Q VS Code Extension](../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0047%20-%20Code%20to%20Deploy%20Destructive%20AI%20Agent%20Discovered%20in%20Amazon%20Q%20VS%20Code%20Extension.md#step-s01)
- [AML.CS0054 - Data Exfiltration via Remote Poisoned MCP Tool](../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0054%20-%20Data%20Exfiltration%20via%20Remote%20Poisoned%20MCP%20Tool.md#step-s07)
- [AML.CS0068 - Autonomous OpenAI Evaluation Agents Compromise Hugging Face Infrastructure](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md) · [S16](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s16), [S21](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s21), [S27](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s27), [S32](../../../Case%20Studies/Incidents/AML.CS0068%20-%20Autonomous%20OpenAI%20Evaluation%20Agents%20Compromise%20Hugging%20Face%20Infrastructure.md#step-s32)
- [AML.CS0069 - GTG-1002 Claude Code Espionage Campaign](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md) · [S14](../../../Case%20Studies/Incidents/AML.CS0069%20-%20GTG-1002%20Claude%20Code%20Espionage%20Campaign.md#step-s14)
- [AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md) · [S23](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s23)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S25](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s25), [S31](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s31), [S37](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s37), [S40](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s40)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0055)
