# AML.M0019 - Control Access to AI Models and Data in Production

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Require users to verify their identities before accessing a production model.
Require authentication for API endpoints and monitor production model queries to ensure compliance with usage policies and to prevent model misuse.

**Mitigation categories**  Policy

**Lifecycle phases**  Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0005 - Replicate AI Model Behavior](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md) — Access controls on models APIs can reduce an adversary's ability to produce an accurate proxy model.
- [AML.T0006 - Active Scanning](../Tactics/01%20AML.TA0002%20-%20Reconnaissance/AML.T0006%20-%20Active%20Scanning/README.md) — Require authenticated access to production AI endpoints and monitor queries to limit unauthenticated probing of exposed AI services.
- [AML.T0012 - Valid Accounts](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md) — Authenticate production AI endpoints and monitor model queries for misuse of otherwise valid credentials.
- [AML.T0021 - Establish Accounts](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md) — Verify identities before granting production AI access so newly established accounts cannot automatically access protected AI services.
- [AML.T0024 - Exfiltration via AI Inference API](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0024%20-%20Exfiltration%20via%20AI%20Inference%20API/README.md) — Adversaries can use unrestricted API access to build a proxy training dataset and reveal private information.
- [AML.T0029 - Denial of AI Service](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0029%20-%20Denial%20of%20AI%20Service/README.md) — Access controls on model APIs can prevent an adversary from excessively querying and disabling the system.
- [AML.T0034 - Cost Harvesting](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0034%20-%20Cost%20Harvesting/README.md) — Access controls can limit API access and prevent cost harvesting.
- [AML.T0040 - AI Model Inference API Access](../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0040%20-%20AI%20Model%20Inference%20API%20Access/README.md) — Adversaries can use unrestricted API access to gain information about a production system, stage attacks, and introduce malicious data to the system.
- [AML.T0042 - Verify Attack](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md) — Use access controls in production to prevent adversary's ability to verify attack efficacy.
- [AML.T0043 - Craft Adversarial Data](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) — Access controls on model APIs can restrict an adversary's access required to generate adversarial data.
- [AML.T0043.001 - Black-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md) — Access controls on model APIs can deny adversaries the access required for black-box optimization methods.
- [AML.T0046 - Spamming AI System with Chaff Data](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0046%20-%20Spamming%20AI%20System%20with%20Chaff%20Data/README.md) — Authentication on production models can help prevent anonymous chaff data spam.
- [AML.T0051 - LLM Prompt Injection](../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/README.md) — Use access controls in production to prevent adversaries from injecting malicious prompts.
- [AML.T0063 - Discover AI Model Outputs](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0063%20-%20Discover%20AI%20Model%20Outputs/README.md) — Controlling access to the model in production can help prevent adversaries from inferring information from the model outputs.
- [AML.T0069 - Discover LLM System Information](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/README.md) — Authenticate and monitor access to production models and configuration interfaces.
- [AML.T0069.000 - Special Character Sets](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/AML.T0069.000%20-%20Special%20Character%20Sets/README.md) — Authenticate and monitor access to production models and prompt configuration.
- [AML.T0069.002 - System Prompt](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0069%20-%20Discover%20LLM%20System%20Information/AML.T0069.002%20-%20System%20Prompt/README.md) — Authenticate and monitor access to production models and prompt configuration.
- [AML.T0091 - Use Alternate Authentication Material](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0091%20-%20Use%20Alternate%20Authentication%20Material/README.md) — Enforce authorization and monitor production AI API use for anomalous activity associated with replayed access tokens.
- [AML.T0091.000 - Application Access Token](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0091%20-%20Use%20Alternate%20Authentication%20Material/AML.T0091.000%20-%20Application%20Access%20Token/README.md) — Enforce authorization and monitor production AI API use for anomalous activity associated with replayed access tokens.
- [AML.T0096 - AI Service API](../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0096%20-%20AI%20Service%20API/README.md) — Authenticate AI service API callers and monitor queries for policy violations and misuse.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0019)
