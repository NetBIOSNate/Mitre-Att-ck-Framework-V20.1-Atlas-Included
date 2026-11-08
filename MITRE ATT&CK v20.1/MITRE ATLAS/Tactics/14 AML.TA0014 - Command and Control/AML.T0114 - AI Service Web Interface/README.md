# AML.T0114 - AI Service Web Interface

[MITRE ATLAS](../../../README.md) / [AML.TA0014 - Command and Control](../README.md)

Adversaries may communicate with compromised systems by abusing the web interface of an AI service as an intermediary command-and-control relay. Instead of connecting directly to attacker-controlled infrastructure or using an AI provider's API, malware may open or automate a browser, embedded browser, or WebView component to interact with a public AI assistant.

The malware may prompt the AI assistant to fetch an attacker-controlled URL, include victim data in URL parameters or prompt content, and return attacker-supplied content through the AI assistant's response. The implant can then parse the response and execute embedded instructions.

This technique is especially useful when an AI web interface permits anonymous or unauthenticated browsing, summarization, or URL-fetch behavior. In those cases, adversaries may avoid controls that depend on API keys, service accounts, user identities, or revocable credentials.

This technique allows command-and-control traffic to blend into apparently legitimate AI web traffic to trusted service domains. In this pattern, the AI service acts as a proxy between the compromised system and attacker-controlled infrastructure, shifting detection from API key and account monitoring toward browser automation, prompt content, URL-fetch behavior, and AI service telemetry.

**Tactics**  [AML.TA0014 - Command and Control](../README.md)

**Platforms**  [Enterprise](../../../Platforms/Enterprise.md)

**Maturity**  Demonstrated

## Case studies

- [AML.CS0061 - AI in the Middle: Web-Based AI Services as C2 Relays](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md) · [S07](../../../Case%20Studies/Exercises/AML.CS0061%20-%20AI%20in%20the%20Middle%20-%20Web-Based%20AI%20Services%20as%20C2%20Relays.md#step-s07)

## Mitigations

- [AML.M0024 - AI Telemetry Logging and Monitoring](../../../Mitigations/AML.M0024%20-%20AI%20Telemetry%20Logging%20and%20Monitoring.md) — AI telemetry logging can help detect suspicious prompts, browser-based AI service interactions, URL-fetch requests, and AI responses used to relay command-and-control data.

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0114)
