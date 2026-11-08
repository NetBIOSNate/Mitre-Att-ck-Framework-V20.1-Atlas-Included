# T1696.001 - Automate CAPTCHA Completion

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1696 - Anti-Automation Evasion](../README.md)

Adversaries may attempt to use bots to successfully solve CAPTCHA challenges. CAPTCHA challenges are typically used by defenders to detect and prevent bot and spam traffic from accessing protected webpages. CAPTCHAs are automated tests often placed before login screens or form fields. Traditional CAPTCHAs ask the user to decipher a string of characters, type the characters into a box, and submit the form. reCAPTCHA asks the user to identify images, click a checkbox, or evaluate the user’s behavior from mouse movement and device cookies.(Citation: CAPTCHAS Cloudflare) 

Adversaries may use scripts or toolkits to automatically solve the CAPTCHA puzzle. For example, adversaries may develop a script that uses the ImageMagick toolkit to solve the CAPTCHA puzzles to then create multiple valid accounts. ImageMagick tool can convert the images into an RGB complemented image. The CAPTCHA challenge may be solved by identifying and comparing attributes of the RGB images to select the expected image.(Citation: Free Trial PurpleUrchin) Once the CAPTCHA challenge is solved, the adversary’s script may access the protected page. After accessing the protected the page, the adversary may submit valid forms to the target.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1696/001)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [SaaS](../../../../Platforms/SaaS.md)

## Detection strategies

- [DET0937 - Detection of Automated CAPTCHA](../../../../Defenses/Detection%20Strategies/DET0937%20-%20Detection%20of%20Automated%20CAPTCHA.md)

## Mitigations

- [M1037 - Filter Network Traffic](../../../../Defenses/Mitigations/M1037%20-%20Filter%20Network%20Traffic.md) — Do not treat successful CAPTCHA completion alone as sufficient evidence that subsequent activity is human-generated. Continue evaluating requests using bot classification, request rate, client/session characteristics, token reuse, source reputation, and behavioral signals after successful challenge completion. Block or rate-limit activity that remains inconsistent with expected human use.
- [M1031 - Network Intrusion Prevention](../../../../Defenses/Mitigations/M1031%20-%20Network%20Intrusion%20Prevention.md) — Configure inline bot-management and web application protections to continue enforcing automation controls after a client successfully completes a CAPTCHA. Use challenge-token state as one input rather than as a durable trust determination, and prevent requests that subsequently exhibit automated or abusive behavior.

## Sources

- [CAPTCHAS Cloudflare](https://www.cloudflare.com/learning/bots/how-captchas-work/)
- [Free Trial PurpleUrchin](https://unit42.paloaltonetworks.com/purpleurchin-steals-cloud-resources/)
