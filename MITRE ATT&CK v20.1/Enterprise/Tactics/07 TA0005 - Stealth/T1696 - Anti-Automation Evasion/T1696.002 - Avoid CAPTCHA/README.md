# T1696.002 - Avoid CAPTCHA

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1696 - Anti-Automation Evasion](../README.md)

Adversaries may avoid CAPTCHA challenges by mimicking human behavior. Automation tests, such as CAPTCHA, are typically used by defenders to detect and prevent bot and spam traffic from accessing protected webpages. CAPTCHAs are often placed before login screens or form fields. Traditional CAPTCHAs ask the user to decipher a string of characters, type the characters into a box, and submit the form. reCAPTCHA asks the user to identify images, click a checkbox, or evaluate the user’s behavior from mouse movement and device cookies.(Citation: CAPTCHAS Cloudflare) 

Adversaries may attempt to avoid CAPTCHA challenges by constructing a bot that mimics human behavior through browser automation. The automated browser may mimic a human by [Masquerading](https://attack.mitre.org/techniques/T1036) a [Browser Fingerprint](https://attack.mitre.org/techniques/T1036/012) and through attributes such as session history, IP reputation, and the use of browser APIs.(Citation: CAPTCHA Bypass Olostep) For example, adversaries may use Selenium browsers to simulate a human user. In the Selenium browsers, JavaScript is injected into the website’s Document Object Model (DOM). The injected script may modify browser attributes such as Audio Context and Voice engines, graphic rendering, installed fonts, and browser navigator objects.(Citation: Sentinel CAPTCHA Bypass)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1696/002)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Apply bot-management and application-layer filtering independently of whether a CAPTCHA challenge is triggered. Evaluate protected requests using behavioral, client/session, rate, reputation, token, and automation signals, and block or rate-limit activity that violates policy even when no CAPTCHA was presented.
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Deploy layered inline controls that prevent automated access based on observed request and session behavior rather than relying solely on challenge presentation. Use silent challenges, browser/client validation, rate controls, and bot-management signals to prevent clients that mimic legitimate users from obtaining unrestricted access to protected functionality.

## Detection strategies

- [DET0938 - Detection of Avoid CAPTCHA](../../../../Defenses/Detection%20Strategies/DET0938%20-%20Detection%20of%20Avoid%20CAPTCHA.md)

## Sources

- [Sentinel CAPTCHA Bypass](https://www.sentinelone.com/labs/akirabot-ai-powered-bot-bypasses-captchas-spams-websites-at-scale/)
- [CAPTCHA Bypass Olostep](https://www.olostep.com/blog/how-to-bypass-captcha)
- [CAPTCHAS Cloudflare](https://www.cloudflare.com/learning/bots/how-captchas-work/)
