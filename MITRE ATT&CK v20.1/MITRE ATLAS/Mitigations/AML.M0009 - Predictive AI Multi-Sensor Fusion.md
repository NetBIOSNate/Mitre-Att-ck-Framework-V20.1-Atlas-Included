# AML.M0009 - Predictive AI Multi-Sensor Fusion

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Use independent physical sensors (ideally across multiple modalities or from several perspectives) to avoid relying on a single sensor that may be manipulated, obstructed, or disrupted by an adversary.

Relevant sensors may include visible-light cameras, infrared cameras, depth sensors, radar, lidar, microphones, or other physical sensing systems. Corroborate observations across sensors so manipulation of one input source does not overly influence the model's predictions.

**Mitigation categories**  Technical - Cyber

**Lifecycle phases**  Business and Data Understanding, Data Preparation, AI Model Engineering

## Techniques mitigated

- [AML.T0015 - Evade AI Model](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0015%20-%20Evade%20AI%20Model/README.md) — Using a variety of sensors can make it more difficult for an attacker to compromise and produce malicious results.
- [AML.T0041 - Physical Environment Access](../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0041%20-%20Physical%20Environment%20Access/README.md) — Using a variety of sensors can make it more difficult for an attacker with physical access to compromise and produce malicious results.
- [AML.T0088 - Generate Deepfakes](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md) — Using a variety of sensors, such as IR depth cameras, can aid in detecting deepfakes.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0009)
