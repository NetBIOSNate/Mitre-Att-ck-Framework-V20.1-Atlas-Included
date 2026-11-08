# T1696 - Anti-Automation Evasion

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may employ various means to evade or complete automation checks. Automation checks distinguish human users from bot traffic and prevent bots from reaching the web pages protected by automation checks. For example, a user may be required to solve a CAPTCHA challenge before accessing a form or login page. Traditional CAPTCHAs ask the user to decipher a string of characters, type the characters into a box, and submit the form. reCAPTCHA asks the user to identify images, click a checkbox, or evaluate the user’s behavior from mouse movement and device cookies.(Citation: CAPTCHAS Cloudflare) 

Adversaries may pay for a service that forwards the CAPTCHA challenge to a remote human worker. The human service then solves the CAPTCHA on behalf of the bot.(Citation: CAPTCHA Bypass) AI tools, such as CapSolver, can also be used to automatically solve CAPTCHA challenges.(Citation: Capsolver)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1696)

**Tactics**  [Stealth](../README.md)

**Platforms**  [SaaS](../../../Platforms/SaaS.md)

## Sub-techniques

- [T1696.001 - Automate CAPTCHA Completion](T1696.001%20-%20Automate%20CAPTCHA%20Completion/README.md)
- [T1696.002 - Avoid CAPTCHA](T1696.002%20-%20Avoid%20CAPTCHA/README.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Use web application firewalls, bot-management controls, and application-layer traffic filtering to restrict automated access to protected resources. Apply filtering using request characteristics, client/session reputation, behavioral signals, rate limits, and validated client or bot identity. Block, rate-limit, or challenge traffic that violates established access policies.
- [M1031 - Network Intrusion Prevention](../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Deploy inline application-layer protections capable of identifying and preventing automated activity before requests reach protected application functionality. Use multiple automation signals rather than relying exclusively on successful CAPTCHA completion.

## Detection strategies

- [DET0939 - Detection of Anti-Automation Evasion](../../../Defenses/Detection%20Strategies/DET0939%20-%20Detection%20of%20Anti-Automation%20Evasion.md)

## Sources

- [CAPTCHAS Cloudflare](https://www.cloudflare.com/learning/bots/how-captchas-work/)
- [Capsolver](https://www.capsolver.com/blog/ai/agentic-browser-capsolver)
- [CAPTCHA Bypass](https://www.skyvern.com/blog/best-way-to-bypass-captcha-for-ai-browser-automation-september-2025/)
