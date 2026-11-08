# AML.T0139 - Compromise Accounts

[MITRE ATLAS](../../../README.md) / [AML.TA0003 - Resource Development](../README.md)

Adversaries may compromise existing accounts with services that can support targeting or subsequent operations. These accounts may provide established identities, trusted relationships, access to resources, or funded wallets for AI services.

Adversaries may obtain account credentials through [Phishing](../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md), password guessing or reuse, theft of access tokens, or purchase from third parties.

Adversaries may compromise AI service accounts for LLMJacking, a pattern of consuming model access and usage at the account holder's expense. [sysdig-llmjacking](https://www.sysdig.com/learn-cloud-native/what-is-llmjacking) Depending on the service, these resources may include prepaid balances or service wallets, promotional credits, subscription allowances, or usage charged to an existing payment method or enterprise billing account. Adversaries may use the acquired capacity for their own inference workloads, code generation, or tool development while exhausting the victim's available credits and quotas or generating additional charges.

Compromised accounts may also supply capacity for [AI Service Proxies](../AML.T0008%20-%20Acquire%20Infrastructure/AML.T0008.005%20-%20AI%20Service%20Proxies/README.md), allowing operators to aggregate and resell access while concealing the underlying credentials from downstream users. [sysdig-market](https://www.sysdig.com/blog/llmjacking-from-emerging-threat-to-black-market-reality) Google has reported model distillation campaigns that used proxy infrastructure to rotate requests across compromised credentials and fraudulent accounts. [google-sep](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai/) Account pooling and resale also feature in the gray-market transfer station economy, where account merchants and registration intermediaries supply access alongside discounted capacity, unused quotas, and shared subscriptions. [chinatalk](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in).

**Tactics**  [AML.TA0003 - Resource Development](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md), [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Realized

**ATT&CK mapping**  [Local ATT&CK T1586](../../../../Enterprise/Tactics/02%20TA0042%20-%20Resource%20Development/T1586%20-%20Compromise%20Accounts/README.md) · [MITRE ATT&CK T1586](https://attack.mitre.org/techniques/T1586/)

## Case studies

- [AML.CS0030 - LLMjacking: Stolen Cloud Credentials Used to Access Cloud LLM Services.](../../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md) · [S02](../../../Case%20Studies/Incidents/AML.CS0030%20-%20LLMjacking%20-%20Stolen%20Cloud%20Credentials%20Used%20to%20Access%20Cloud%20LLM%20Services.md#step-s02)
- [AML.CS0075 - Model Distillation Campaigns Targeting Google AI Services](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md) · [S01](../../../Case%20Studies/Incidents/AML.CS0075%20-%20Model%20Distillation%20Campaigns%20Targeting%20Google%20AI%20Services.md#step-s01)

## References

- [What is LLMjacking?](https://www.sysdig.com/learn-cloud-native/what-is-llmjacking)
- [LLMjacking: From Emerging Threat to Black Market Reality](https://www.sysdig.com/blog/llmjacking-from-emerging-threat-to-black-market-reality)
- [Google Threat Intelligence Group. From Prompting to Autonomy - The Evolution of Adversarial AI](https://cloud.google.com/blog/topics/threat-intelligence/from-prompting-to-autonomy-the-evolution-of-adversarial-ai/)
- [How to Buy Cheap Claude Tokens in China: The Transfer Station Economy, Explained](https://www.chinatalk.media/p/how-to-buy-cheap-claude-tokens-in)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0139)
