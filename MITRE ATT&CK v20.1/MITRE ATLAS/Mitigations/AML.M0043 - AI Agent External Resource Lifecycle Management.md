# AML.M0043 - AI Agent External Resource Lifecycle Management

[MITRE ATLAS](../README.md) / [Mitigations](README.md)

Organizations should control external resources created or acquired by AI agents during execution by treating those resources as attributable, lifecycle-managed assets. These resources may remain usable after the originating agent's environment has been destroyed, allowing unauthorized activity to persist across otherwise ephemeral sessions, and enabling discovery and reuse by other agents. External resources may include identities and access mechanisms, compute, storage and network infrastructure, hosted data, model artifacts, installed software, and externally maintained services and integrations. Where possible, agents should create such resources through a broker or management layer that records resource identifiers, ownership, purpose, creation time, authorized scope, and expiration or approved retention conditions. 

Resources should be issued with the shortest practical lifetime consistent with their authorized purpose and tied to the specific agent run, task, user, or operational objective that required them. Define expiration or retention conditions at provisioning time and require explicit authorization to extend resource lifetimes or transfer ownership. Enforce these controls outside the agent and restrict provisioning paths that bypass registration or lifecycle controls.

When the authorized need ends or authorization expires, all lifecycle-managed resources that are no longer required should be cleaned up. This includes revoking associated credentials, disabling or deleting accounts, removing hosted artifacts, and tearing down external infrastructure. Cleanup mechanisms should operate independently of the agent's execution environment, with periodic inventory reconciliation to detect residual resources and retry failed cleanup. Verify credential revocation and resource removal separately, since revoking credentials does not necessarily disable resources created using them. Where deletion is impossible or delayed, revoke access and isolate residual resources. Retained resources should be assigned to a new owner with an approved lifecycle policy.

**Mitigation categories**  Policy, Technical - AI, Technical - Cyber

**Lifecycle phases**  AI Model Evaluation, Deployment, Monitoring and Maintenance

## Techniques mitigated

- [AML.T0008 - Acquire Infrastructure](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0008%20-%20Acquire%20Infrastructure/README.md) — Decommission agent-acquired infrastructure when authorization ends to limit its continued use beyond the authorized task.
- [AML.T0012 - Valid Accounts](../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md) — Revoke credentials and disable unneeded accounts to limit reuse of agent-associated access after its authorized purpose ends.
- [AML.T0021 - Establish Accounts](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0021%20-%20Establish%20Accounts/README.md) — Disable or delete agent-created external service accounts when authorization ends to limit their availability for subsequent unauthorized operations.
- [AML.T0072 - Cyber Communication Channel](../Tactics/14%20AML.TA0014%20-%20Command%20and%20Control/AML.T0072%20-%20Cyber%20Communication%20Channel/README.md) — Disable agent-created communication infrastructure when authorization ends to disrupt persistent command-and-control channels.
- [AML.T0079 - Stage Capabilities](../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md) — Remove hosted payloads and artifacts when authorization ends to limit continued use of staged capabilities.
- [AML.T0091.000 - Application Access Token](../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0091%20-%20Use%20Alternate%20Authentication%20Material/AML.T0091.000%20-%20Application%20Access%20Token/README.md) — Expire and revoke agent-associated application access tokens to limit the window for unauthorized use.
- [AML.T0118.000 - Communication via Shared Artifacts](../Tactics/03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0118%20-%20Autonomous%20AI%20Agent%20Communication/AML.T0118.000%20-%20Communication%20via%20Shared%20Artifacts/README.md) — Remove shared artifacts and revoke associated access to limit communication and coordination across independent agent runs.
- [AML.T0121 - AI Agent Environment Reconstruction](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0121%20-%20AI%20Agent%20Environment%20Reconstruction/README.md) — Remove external operational state and revoke associated access to limit environment reconstruction and resumption of an operation.
- [AML.T0125 - Create Account](../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0125%20-%20Create%20Account/README.md) — Disable or delete agent-created accounts when authorization ends to limit persistent access through those accounts.
- [AML.T0127 - Data Staged](../Tactics/13%20AML.TA0009%20-%20Collection/AML.T0127%20-%20Data%20Staged/README.md) — Remove staged data and revoke access to managed staging locations to limit subsequent retrieval and exfiltration.

[Official ATLAS record](https://atlas.mitre.org/mitigations/AML.M0043)
