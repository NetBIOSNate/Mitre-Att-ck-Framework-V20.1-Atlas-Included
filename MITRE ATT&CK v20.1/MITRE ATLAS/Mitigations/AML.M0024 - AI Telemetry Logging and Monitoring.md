# AML.M0024 - AI Telemetry Logging and Monitoring

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Implement logging and monitoring across the AI lifecycle to detect suspicious activity and support investigation. Capture security-relevant access, changes, and operations across data pipelines, model development, deployment, and connected systems. Preserve sufficient context to trace activity across components and identify coordinated behavior across accounts and access pathways.

Tailor telemetry to each system's function, including relevant data and model versions, request and execution metadata, and operation results. For agentic systems, distinguish requested actions from those actually executed, using independent service records where available. Treat model-generated explanations and summaries as supporting context rather than authoritative evidence of execution.

Monitor individual events and patterns over time for anomalous access, unauthorized changes, unusual usage, and unexpected model behavior or external actions. Correlate findings with related operational activity to guide investigation and response.

Protect telemetry from unauthorized access, modification, or deletion, and monitor for gaps in coverage. Limit the collection of sensitive content through metadata, references, or redaction where these preserve investigative value, and apply appropriate retention controls.

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0005.001 - Replicate Behavior from Model Outputs](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md) — Telemetry logging can help identify if a proxy training dataset has been exfiltrated.
- [AML.T0024 - Exfiltration via AI Inference API](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0024%20-%20Exfiltration%20via%20AI%20Inference%20API/README.md) — Telemetry logging can help identify if sensitive data has been exfiltrated.
- [AML.T0040 - AI Model Inference API Access](../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md) — Telemetry logging can help audit API usage of the model.
- [AML.T0047 - AI-Enabled Product or Service](../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md) — Telemetry logging can help identify if sensitive model information has been sent to an attacker.
- [AML.T0051 - LLM Prompt Injection](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md) — Telemetry logging can help identify if unsafe prompts have been submitted to the LLM.
- [AML.T0051.000 - Direct](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.000%20-%20Direct/README.md) — Telemetry logging can help identify if unsafe prompts have been submitted to the LLM.
- [AML.T0051.001 - Indirect](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.001%20-%20Indirect/README.md) — Telemetry logging can help identify if unsafe prompts have been submitted to the LLM.
- [AML.T0051.002 - Triggered](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.002%20-%20Triggered/README.md) — Telemetry logging can help identify if unsafe prompts have been submitted to the LLM.
- [AML.T0053 - AI Agent Tool Invocation](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0053%20-%20AI%20Agent%20Tool%20Invocation/README.md) — Log AI agent tool invocations to detect malicious calls.
- [AML.T0085 - Data from AI Services](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/README.md) — Log requests to AI services to detect malicious queries for data.
- [AML.T0085.000 - RAG Databases](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.000%20-%20RAG%20Databases/README.md) — Log requests to AI services to detect malicious queries for data.
- [AML.T0085.001 - AI Agent Tools](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0085%20-%20Data%20from%20AI%20Services/AML.T0085.001%20-%20AI%20Agent%20Tools/README.md) — Log requests to AI services to detect malicious queries for data.
- [AML.T0086 - Exfiltration via AI Agent Tool Invocation](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0086%20-%20Exfiltration%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Log AI agent tool invocations to detect malicious calls.
- [AML.T0101 - Data Destruction via AI Agent Tool Invocation](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0101%20-%20Data%20Destruction%20via%20AI%20Agent%20Tool%20Invocation/README.md) — Log AI agent tool invocations to detect malicious calls.
- [AML.T0108 - AI Agent](../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0108%20-%20AI%20Agent/README.md) — Monitor agent prompts, decisions, tool use, and outputs for C2 behavior.
- [AML.T0112.000 - Local AI Agent](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0112%20-%20Machine%20Compromise/AML.T0112.000%20-%20Local%20AI%20Agent/README.md) — Monitor local agent commands, file and credential access, tool use, and system changes.
- [AML.T0114 - AI Service Web Interface](../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0114%20-%20AI%20Service%20Web%20Interface/README.md) — AI telemetry logging can help detect suspicious prompts, browser-based AI service interactions, URL-fetch requests, and AI responses used to relay command-and-control data.
- [AML.T0120 - AI Artifact Repository](../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0120%20-%20AI%20Artifact%20Repository/README.md) — Monitor repository accesses and correlate them with known workflows. Investigate repeated polling, unexpected repositories, and writes from workloads that normally only download artifacts.
- [AML.T0137.000 - Infer Membership](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.000%20-%20Infer%20Membership/README.md) — Telemetry logging can help identify if sensitive data has been exfiltrated.
- [AML.T0137.002 - Invert AI Model](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.002%20-%20Invert%20AI%20Model/README.md) — Telemetry logging can help identify if sensitive data has been exfiltrated.

## References

- [OWASP Secure AI/ML Model Ops Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secure_AI_Model_Ops_Cheat_Sheet.html#7-monitoring-logging)
- [OWASP Logging Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet.html)

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0024)
