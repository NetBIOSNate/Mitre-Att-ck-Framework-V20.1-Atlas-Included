# AML.T0021 - Establish Accounts

[MITRE ATLAS](../../../README.md) / [AML.TA0003 - Resource Development](../README.md)

Adversaries may create accounts with various services for use in targeting, to gain access to resources needed to further their operations, or for victim impersonation.

Adversaries may establish pools of AI service accounts through bulk or fraudulent registration. These accounts may exploit promotional credits, educational or startup programs, or premium subscriptions. [chinatalk](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in)  [anthropic](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks) They may register accounts directly or use account merchants and third parties that supply registration resources, such as SMS verification services and payment arrangements. [chinatalk](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in) Registration arrangements may obscure the operator's country of origin, and related accounts may share registration attributes or payment instruments. [cisa](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a)

Established accounts can supply upstream access for [AI Service Proxies](../AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md) to serve as "transfer stations" for gray-market resellers. [chinatalk](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in) Adversaries may also purposefully route requests through proxies for [Centralized AI Service Request Routing](../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0140%20-%20Centralized%20AI%20Service%20Request%20Routing/README.md) to avoid policy enforcement and evade detection.

Adversaries or autonomous AI agents may establish accounts and cultivate personas on social media (e.g. Facebook, LinkedIn, X), software hosting (e.g. GitHub, GitLab), or AI artifact hosting (e.g. Hugging Face) sites. Account creation supplies the identities used for subsequent [Impersonation](../../09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0073%20-%20Impersonation/README.md) and [Phishing](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md) activities.

Autonomous AI agents may independently select services and create accounts as prerequisites for subsequent attack activity, without a human directing each registration. Agents may obtain verification messages through controlled mailboxes, switch proxies to overcome account registration restrictions, or use visual recognition and audio matching to solve human verification challenges such as CAPTCHAs. [aisi](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

**Tactics**  [AML.TA0003 - Resource Development](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1585](../../../../Enterprise/Tactics/02%20TA0042%20-%20Resource%20Development/T1585%20-%20Establish%20Accounts/README.md) · [MITRE ATT&CK T1585](https://attack.mitre.org/techniques/T1585/)

## Case studies

- [AML.CS0004 - Camera Hijack Attack on Facial Recognition System](../../../Case%20Studies/Incidents/AML.CS0004%20-%20Camera%20Hijack%20Attack%20on%20Facial%20Recognition%20System.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0004%20-%20Camera%20Hijack%20Attack%20on%20Facial%20Recognition%20System.md#step-s01)
- [AML.CS0006 - ClearviewAI Misconfiguration](../../../Case%20Studies/Incidents/AML.CS0006%20-%20ClearviewAI%20Misconfiguration.md) · [S00](../../../Case%20Studies/Incidents/AML.CS0006%20-%20ClearviewAI%20Misconfiguration.md#step-s00)
- [AML.CS0027 - Organization Confusion on Hugging Face](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md) · [S00](../../../Case%20Studies/Exercises/AML.CS0027%20-%20Organization%20Confusion%20on%20Hugging%20Face.md#step-s00)
- [AML.CS0033 - Live Deepfake Image Injection to Evade Mobile KYC Verification](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md) · [S05](../../../Case%20Studies/Exercises/AML.CS0033%20-%20Live%20Deepfake%20Image%20Injection%20to%20Evade%20Mobile%20KYC%20Verification.md#step-s05)
- [AML.CS0034 - ProKYC: Deepfake Tool for Account Fraud Attacks](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md#step-s04)
- [AML.CS0065 - Model Namespace Reuse Supply Chain Attack](../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md) · [S01](../../../Case%20Studies/Exercises/AML.CS0065%20-%20Model%20Namespace%20Reuse%20Supply%20Chain%20Attack.md#step-s01)
- [AML.CS0073 - Autonomous Claude Agents Compromise Three Real Organizations During Cyber Evaluations](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md) · [S12](../../../Case%20Studies/Incidents/AML.CS0073%20-%20Autonomous%20Claude%20Agents%20Compromise%20Three%20Real%20Organizations%20During%20Cyber%20Ev.md#step-s12)
- [AML.CS0074 - AISI Evaluation Agents Conduct Unsanctioned Real-World Cyber Activity](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md) · [S04](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s04), [S27](../../../Case%20Studies/Incidents/AML.CS0074%20-%20AISI%20Evaluation%20Agents%20Conduct%20Unsanctioned%20Real-World%20Cyber%20Activity.md#step-s27)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s02)
- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s01)

## Mitigations

- [AML.M0005 - Control Access to AI Models and Data at Rest](../../../Mitigations/AML.M0005%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20at%20Rest.md) — Verify identities before granting access to model registries so newly established accounts cannot automatically access protected AI artifacts.
- [AML.M0019 - Control Access to AI Models and Data in Production](../../../Mitigations/AML.M0019%20-%20Control%20Access%20to%20AI%20Models%20and%20Data%20in%20Production.md) — Verify identities before granting production AI access so newly established accounts cannot automatically access protected AI services.
- [AML.M0043 - AI Agent External Resource Lifecycle Management](../../../Mitigations/AML.M0043%20-%20AI%20Agent%20External%20Resource%20Lifecycle%20Management.md) — Disable or delete agent-created external service accounts when authorization ends to limit their availability for subsequent unauthorized operations.

## References

- [How to Buy Cheap Claude Tokens in China: The Transfer Station Economy, Explained](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in)
- [Detecting and preventing distillation attacks](https://www.anthropic.com/news/detecting-and-preventing-distillation-attacks)
- [China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a)
- [Incident Report: unsanctioned agent behaviour during cyber testing](https://www.aisi.gov.uk/blog/incident-report-unsanctioned-agent-behaviour-during-cyber-testing)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0021)
