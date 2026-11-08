# AML.M0040 - Adaptive AI Response Degradation

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Reduce the utility of AI model outputs for unauthorized model replication, knowledge distillation, or inference about training data by dynamically modifying responses when suspected extraction activity or privacy attacks are detected. Based on the assessed confidence and severity of the activity, apply targeted response modifications that limit the information available to an adversary while preserving legitimate functionality where possible.

Response degradation techniques may include:
-  Routing suspicious requests to less capable or more constrained models
- Reducing output precision, specificity, or completeness
- Withholding unnecessary reasoning details, confidence information, or auxiliary outputs
- Restricting access to high-fidelity or structured responses
- Introducing carefully controlled output perturbations

These measures can reduce the value of collected responses as training data, limit an adversary's ability to infer model behavior or capabilities, reduce disclosure of information about the model's training data, and increase the cost and difficulty of replicating a target model.

Apply response degradation proportionally to the assessed risk of adversarial query activity, using behavioral indicators and detection confidence to minimize disruption to legitimate users. Evaluate degradation mechanisms to ensure they do not introduce misleading or unsafe outputs, inadvertently disclose detection decisions, or undermine the reliability of authorized interactions.

**Mitigation categories**  Technical - AI

**Lifecycle phases**  Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0005 - Replicate AI Model Behavior](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/README.md) — Degrade responses during suspected replication activity to reduce the usefulness of collected outputs for reproducing the target model's behavior or capabilities.
- [AML.T0005.001 - Replicate Behavior from Model Outputs](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0005%20-%20Replicate%20AI%20Model%20Behavior/AML.T0005.001%20-%20Replicate%20Behavior%20from%20Model%20Outputs/README.md) — Degrade responses during suspected replication activity to reduce the usefulness of collected outputs for reproducing the target model's behavior or capabilities.
- [AML.T0042 - Verify Attack](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0042%20-%20Verify%20Attack/README.md) — Degrade responses to suspected attack verification queries to limit the reliability of feedback used to confirm an attack's effectiveness against the target model.
- [AML.T0043 - Craft Adversarial Data](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/README.md) — Degrade responses during suspected adversarial activity to limit feedback used to optimize adversarial inputs against the target model.
- [AML.T0043.001 - Black-Box Optimization](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0043%20-%20Craft%20Adversarial%20Data/AML.T0043.001%20-%20Black-Box%20Optimization/README.md) — Degrade responses during suspected adversarial activity to limit feedback used to optimize adversarial inputs against the target model.
- [AML.T0135 - Outputs from AI Models](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0135%20-%20Outputs%20from%20AI%20Models/README.md) — Degrade responses during suspected collection to reduce the information available for subsequent adversarial operations.
- [AML.T0137 - Training Data Information from AI Models](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/README.md) — Degrade responses during suspected adversarial activity to limit signals used to infer information about private data used in model training.
- [AML.T0137.000 - Infer Membership](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.000%20-%20Infer%20Membership/README.md) — Degrade responses during suspected adversarial activity to limit signals used to determine whether particular samples were included in training.
- [AML.T0137.001 - Infer Properties](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.001%20-%20Infer%20Properties/README.md) — Degrade responses during suspected adversarial activity to limit signals used to infer sensitive characteristics of the training dataset.
- [AML.T0137.002 - Invert AI Model](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.002%20-%20Invert%20AI%20Model/README.md) — Degrade responses during suspected adversarial activity to limit information used to reconstruct representative training examples.
- [AML.T0137.003 - Extract Memorized Data](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0137%20-%20Training%20Data%20Information%20from%20AI%20Models/AML.T0137.003%20-%20Extract%20Memorized%20Data/README.md) — Degrade responses during suspected adversarial activity to reduce disclosure of memorized training content.
- [AML.T0144 - Recover AI Model Internals](../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0144%20-%20Recover%20AI%20Model%20Internals/README.md) — Degrade responses during suspected adversarial activity to limit observations used to infer model architecture, internal structure, or numerical parameters.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0040)
