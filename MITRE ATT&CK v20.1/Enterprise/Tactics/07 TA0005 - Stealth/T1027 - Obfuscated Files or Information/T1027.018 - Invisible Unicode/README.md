# T1027.018 - Invisible Unicode

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1027 - Obfuscated Files or Information](../README.md)

Adversaries may abuse invisible or non-printing Unicode characters to conceal malicious content within files, scripts, or text. By inserting characters that do not visibly render, adversaries may hide data, alter how content is interpreted, or make malicious code appear as benign text or whitespace. Adversaries may encode these malicious payloads, using binary, Base64, or custom schemes, to be reconstructed at runtime through scripting features such as [JavaScript](https://attack.mitre.org/techniques/T1059/007) Proxy traps, `eval()`, or other dynamic execution methods. This technique enables adversaries to evade visual inspection and basic static analysis by hiding malicious encoded content in innocuous text.(Citation: PUAs Unicode - Eriksen)(Citation: Tycoon2FA - Unicode)(Citation: Unicode - Veracode) 

Unicode is a standardized character encoding model that assigns a unique numerical value, known as a code point, to every character across writing systems, enabling consistent text representation across platforms, applications, and languages. Code points are represented as `U+` followed by a hexadecimal value and may be encoded using formats such as `UTF-8` or `UTF-16`. Adversaries may abuse the valid code points in Unicode that are not visibly rendered but still take up bytes, such as zero-width spaces, variation selectors, or bidirectional formatting controls, to conceal malicious payloads.(Citation: Tycoon2FA - Unicode)(Citation: GlassWorm - Unicode)(Citation: Unicode and Hidden Prompts - Perets)

Adversaries may additionally exploit Private Use Area (PUA) characters, a range of code points reserved for custom assignment. PUA characters that are not defined by a font or application are typically rendered blank.(Citation: PUAs Unicode - Eriksen)

Unicode characters may also be leveraged in support of other techniques such as [Phishing](https://attack.mitre.org/techniques/T1660), [Right-to-Left Override](https://attack.mitre.org/techniques/T1036/002), or [User Execution](https://attack.mitre.org/techniques/T1204). For example, some adversaries may embed artificial intelligence (AI) prompt injections using invisible Unicode characters in emails or documents that appear benign when processed by AI systems.(Citation: LLMs and Unicode - Medium)(Citation: Invisible Prompt Injection - Trend Micro)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1027/018)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S9010 - GlassWorm](../../../../Threat%20Intelligence/Software/Malware/S9010%20-%20GlassWorm.md) — [GlassWorm](https://attack.mitre.org/software/S9010) has utilized invisible Unicode Private Use Area (PUA) characters to obfuscate its malicious code so that it does not render in code editors.(Citation: Koi Glassworm New Tricks December 2025)(Citation: Koi Glassworm InvisibleCode October 2025)(Citation: Aikido GlassWorm October 2025) [Koi Glassworm New Tricks December 2025](https://www.koi.ai/blog/glassworm-goes-mac-fresh-infrastructure-new-tricks) · [Koi Glassworm InvisibleCode October 2025](https://www.koi.ai/blog/glassworm-first-self-propagating-worm-using-invisible-code-hits-openvsx-marketplace) · [Aikido GlassWorm October 2025](https://www.aikido.dev/blog/the-return-of-the-invisible-threat-hidden-pua-unicode-hits-github-repositorties)

## Detection strategies

- [DET0920 - Detection Strategy for Invisible Unicode](../../../../Defenses/Detection%20Strategies/DET0920%20-%20Detection%20Strategy%20for%20Invisible%20Unicode.md)

## Sources

- [GlassWorm - Unicode](https://www.koi.ai/blog/glassworm-first-self-propagating-worm-using-invisible-code-hits-openvsx-marketplace#heading-5)
- [PUAs Unicode - Eriksen](https://www.aikido.dev/blog/youre-invited-delivering-malware-via-google-calendar-invites-and-puas)
- [Invisible Prompt Injection - Trend Micro](https://www.trendmicro.com/en_us/research/25/a/invisible-prompt-injection-secure-ai.html)
- [LLMs and Unicode - Medium](https://idanhabler.medium.com/hiding-in-plain-sight-weaponizing-invisible-unicode-to-attack-llms-f9033865ec10)
- [Tycoon2FA - Unicode](https://www.levelblue.com/blogs/spiderlabs-blog/tycoon2fa-new-evasion-technique-for-2025)
- [Unicode and Hidden Prompts - Perets](https://cycode.com/blog/invisible-code-hidden-prompts-unicode-attacks-sast/)
- [Unicode - Veracode](https://www.veracode.com/blog/down-the-rabbit-hole-of-unicode-obfuscation/)
