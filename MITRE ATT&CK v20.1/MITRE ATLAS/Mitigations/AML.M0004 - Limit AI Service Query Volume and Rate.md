# AML.M0004 - Limit AI Service Query Volume and Rate

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Limit the number and rate of requests that users can submit to an AI service. Apply limits by user, API key, tenant, device, or other authenticated identity. Use short-term rate, burst, and concurrency limits together with longer-term usage quotas.

Query limits can increase the time and cost required to extract model information, optimize adversarial inputs, discover system behavior, verify attacks, or overwhelm a service. Monitor for attempts to evade limits through distributed requests, account rotation, or stolen credentials. Query limits may not protect against attacks that require few requests or are performed against an offline model.

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Business and Data Understanding, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0005 - Replicate AI Model Behavior](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md) — Limit inference queries to reduce the labeled outputs available for training a proxy model.
- [AML.T0005.001 - Replicate Behavior from Model Outputs](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md) — Limit inference queries to reduce the labeled outputs available for training a proxy model.
- [AML.T0013 - Discover AI Model Ontology](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0013%20-%20Discover%20AI%20Model%20Ontology/README.md) — Limit inference queries to reduce an adversary's ability to discover the model's full output ontology.
- [AML.T0014 - Discover AI Model Family](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0014%20-%20Discover%20AI%20Model%20Family/README.md) — Limit inference queries to reduce an adversary's ability to infer the family of AI model.
- [AML.T0024 - Exfiltration via AI Inference API](../Tactics/15%20AML.TA0010%20-%20Exfiltration/AML.T0024%20-%20Exfiltration%20via%20AI%20Inference%20API/README.md) — Limit the volume of API queries in a given period of time to regulate the amount and fidelity of potentially sensitive information an attacker can learn.
- [AML.T0029 - Denial of AI Service](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0029%20-%20Denial%20of%20AI%20Service/README.md) — Limit the number of queries users can perform in a given interval to prevent a denial of service.
- [AML.T0034 - Cost Harvesting](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0034%20-%20Cost%20Harvesting/README.md) — Limit the number of queries users can perform in a given interval to hinder an attacker's ability to send computationally expensive inputs
- [AML.T0042 - Verify Attack](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md) — Limit repeated queries used to test and refine an attack against the target model.
- [AML.T0043 - Craft Adversarial Data](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) — Limit volume of model queries to prevent or slow an adversary's ability to create adversarial inputs.
- [AML.T0043.001 - Black-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md) — Limit volume of model queries to prevent or slow an adversary's ability to perform black-box optimization attacks.
- [AML.T0043.003 - Manual Modification](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.003%20-%20Manual%20Modification/README.md) — Limit volume of model queries to prevent or slow an adversary's ability to refine manually crafted adversarial inputs.
- [AML.T0046 - Spamming AI System with Chaff Data](../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0046%20-%20Spamming%20AI%20System%20with%20Chaff%20Data/README.md) — Limit volume and rate of queries to protect the system from chaff data spam.
- [AML.T0062 - Discover LLM Hallucinations](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0062%20-%20Discover%20LLM%20Hallucinations/README.md) — Limit repeated prompts used to search for exploitable hallucinations.
- [AML.T0137.000 - Infer Membership](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.000%20-%20Infer%20Membership/README.md) — Limit the volume of API queries in a given period of time to regulate the amount and fidelity of potentially sensitive information an attacker can learn.
- [AML.T0137.002 - Invert AI Model](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.002%20-%20Invert%20AI%20Model/README.md) — Limit the volume of API queries in a given period of time to regulate the amount and fidelity of potentially sensitive information an attacker can learn.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0004)
