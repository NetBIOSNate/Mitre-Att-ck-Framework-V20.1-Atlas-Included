# AML.T0141 - AI Service Request Metadata Sanitization

[MITRE ATLAS](../../../README.md) / [AML.TA0007 - Defense Evasion](../README.md)

Adversaries may remove or replace identifying information in request metadata before submitting requests to an AI service to impede attribution and correlation of coordinated activity. Sanitization may be enforced automatically in clients, relays, aggregators, or centralized routing infrastructure.

Metadata may include client or device identifiers, session identifiers, account identifiers, client software identifiers, forwarding headers, and attribution markers embedded in request bodies. [claude-relay-service](https://github.com/wei-shaw/claude-relay-service) Metadata fields may be sanitized via removal, or replacement with normalized, randomized, or generated values.

The NSA, CISA, and FBI reported removal of organizational identifiers in industrial-scale distillation campaigns, with indicators including the disappearance of previously consistent metadata and generic or randomized patterns replacing organizational markers. [cisa](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a)

**Tactics**  [AML.TA0007 - Defense Evasion](../README.md)

**Platforms**  [Predictive AI](../../../Platforms/Predictive%20AI.md), [Generative AI](../../../Platforms/Generative%20AI.md), [Agentic AI](../../../Platforms/Agentic%20AI.md)

**Maturity**  Realized

## Case studies

- [AML.CS0076 - China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md) · [S05](../../../Case%20Studies/Incidents/AML.CS0076%20-%20China-Based%20Artificial%20Intelligence%20Companies%20Conducting%20Industrial-Scale%20Di.md#step-s05)

## Software implementations

- [AML.S0032 - Claude Relay Service](../../../Software/Tools/AML.S0032%20-%20Claude%20Relay%20Service.md) — [Claude Relay Service](../../../Software/Tools/AML.S0032%20-%20Claude%20Relay%20Service.md) filters request headers before forwarding them upstream. Its OpenAI filtering removes client-IP, forwarding, and Cloudflare headers, while its Claude filtering forwards only an explicit allowlist. This suppresses metadata that could identify the originating client or intermediary infrastructure. [source-2](https://github.com/Wei-Shaw/claude-relay-service/blob/cf95ecc5e0ba846faaf1b11de574367de89fd00c/src/utils/headerFilter.js)

## References

- [China-Based Artificial Intelligence Companies Conducting Industrial-Scale Distillation Campaigns Against U.S. AI Companies](https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-251a)
- [Claude Relay Service GitHub](https://github.com/wei-shaw/claude-relay-service)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0141)
