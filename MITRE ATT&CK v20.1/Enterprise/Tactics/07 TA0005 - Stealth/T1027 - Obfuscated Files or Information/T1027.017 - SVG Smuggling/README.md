# T1027.017 - SVG Smuggling

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1027 - Obfuscated Files or Information](../README.md)

Adversaries may smuggle data and files past content filters by hiding malicious payloads inside of seemingly benign SVG files.(Citation: Trustwave SVG Smuggling 2025) SVGs, or Scalable Vector Graphics, are vector-based image files constructed using XML. As such, they can legitimately include `<script>` tags that enable adversaries to include malicious JavaScript payloads. However, SVGs may appear less suspicious to users than other types of executable files, as they are often treated as image files. 

SVG smuggling can take a number of forms. For example, threat actors may include content that: 

* Assembles malicious payloads(Citation: Talos SVG Smuggling 2022)
* Downloads malicious payloads(Citation: Cofense SVG Smuggling 2024)
* Redirects users to malicious websites(Citation: Bleeping Computer SVG Smuggling 2024)
* Displays interactive content to users, such as fake login forms and download buttons.(Citation: Bleeping Computer SVG Smuggling 2024)

SVG Smuggling may be used in conjunction with [HTML Smuggling](https://attack.mitre.org/techniques/T1027/006) where an SVG with a malicious payload is included inside an HTML file.(Citation: Talos SVG Smuggling 2022) SVGs may also be included in other types of documents, such as PDFs.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1027/017)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Detection strategies

- [DET0510 - Detection Strategy for SVG Smuggling with Script Execution and Delivery Behavior](../../../../Defenses/Detection%20Strategies/DET0510%20-%20Detection%20Strategy%20for%20SVG%20Smuggling%20with%20Script%20Execution%20and%20Delivery%20Behavior.md)

## Mitigations

- [M1048 - Application Isolation and Sandboxing](../../../../Defenses/Mitigations/M1048%20-%20Application%20Isolation%20and%20Sandboxing.md) — Browser sandboxes can be used to mitigate some of the impact of exploitation, but sandbox escapes may still exist.

## Sources

- [Talos SVG Smuggling 2022](https://blog.talosintelligence.com/html-smugglers-turn-to-svg-images/)
- [Trustwave SVG Smuggling 2025](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/pixel-perfect-trap-the-surge-of-svg-borne-phishing-attacks/)
- [Bleeping Computer SVG Smuggling 2024](https://www.bleepingcomputer.com/news/security/phishing-emails-increasingly-use-svg-attachments-to-evade-detection/)
- [Cofense SVG Smuggling 2024](https://cofense.com/blog/svg-files-abused-in-emerging-campaigns/)
