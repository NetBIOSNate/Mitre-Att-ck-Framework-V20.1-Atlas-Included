# T1176.002 - IDE Extensions

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1176 - Software Extensions](../README.md)

Adversaries may abuse an integrated development environment (IDE) extension to establish persistent access to victim systems.(Citation: Mnemonic misuse visual studio) IDEs such as Visual Studio Code, IntelliJ IDEA, and Eclipse support extensions - software components that add features like code linting, auto-completion, task automation, or integration with tools like Git and Docker. A malicious extension can be installed through an extension marketplace (i.e., [Compromise Software Dependencies and Development Tools](https://attack.mitre.org/techniques/T1195/001)) or side-loaded directly into the IDE.(Citation: Abramovsky VSCode Security)(Citation: Lakshmanan Visual Studio Marketplace)   

In addition to installing malicious extensions, adversaries may also leverage benign ones. For example, adversaries may establish persistent SSH tunnels via the use of the VSCode Remote SSH extension (i.e., [IDE Tunneling](https://attack.mitre.org/techniques/T1219/001)).  

Trust is typically established through the installation process; once installed, the malicious extension is run every time that the IDE is launched. The extension can then be used to execute arbitrary code, establish a backdoor, mine cryptocurrency, or exfiltrate data.(Citation: ExtensionTotal VSCode Extensions  2025)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1176/002)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Ensure extensions that are installed are the intended ones, as many malicious extensions may masquerade as legitimate ones.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Set an IDE extension allow or deny list as appropriate for your security policy.
- [M1033 - Limit Software Installation](../../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Only install IDE extensions from trusted sources that can be verified.
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Ensure operating systems and IDEs are using the most current version.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to minimize IDE extension use, and to only install trusted extensions.

## Procedure examples

- [G0129 - Mustang Panda](../../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has leveraged Visual Studio Code’s (VSCode) embedded reverse shell feature using the command `code.exe tunnel` to execute code and deliver additional payloads.(Citation: Unit42 Chinese VSCode 06 September 2024) [Unit42 Chinese VSCode 06 September 2024](https://unit42.paloaltonetworks.com/stately-taurus-abuses-vscode-southeast-asian-espionage/)
- [G1056 - TeamPCP](../../../../Threat%20Intelligence/Groups/G1056%20-%20TeamPCP.md) — [TeamPCP](https://attack.mitre.org/groups/G1056) has compromised VS Code and Open VSX IDE extensions.(Citation: Wiz TeamPCP KICS MAR 2026)(Citation: Aikido TeamPCP Telnyx MAR 2026)(Citation: Trend Micro TeamPCP MAY 2026)(Citation: Phoenix TeamPCP 20 MAY 2026)(Citation: Flashpoint Mini Shai-Hulud MAY 2026) [Aikido TeamPCP Telnyx MAR 2026](https://www.aikido.dev/blog/telnyx-pypi-compromised-teampcp-canisterworm) · [Flashpoint Mini Shai-Hulud MAY 2026](https://flashpoint.io/blog/mini-shai-hulud-worm-new-era-ci-cd-exploitation/) · [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action) · [Trend Micro TeamPCP MAY 2026](https://www.trendmicro.com/en_us/research/26/e/analyzing-teampcp-supply-chain-attacks.html) · [Phoenix TeamPCP 20 MAY 2026](https://phoenix.security/teampcp-github-breach-durabletask-pypi-supply-chain-wave-four-2026/)

## Detection strategies

- [DET0561 - Detect malicious IDE extension install/usage and IDE tunneling](../../../../Defenses/Detection%20Strategies/DET0561%20-%20Detect%20malicious%20IDE%20extension%20install%20-%20usage%20and%20IDE%20tunneling.md)

## Sources

- [Abramovsky VSCode Security](https://blog.checkpoint.com/securing-the-cloud/malicious-vscode-extensions-with-more-than-45k-downloads-steal-pii-and-enable-backdoors/)
- [Lakshmanan Visual Studio Marketplace](https://thehackernews.com/2023/01/hackers-distributing-malicious-visual.html)
- [Mnemonic misuse visual studio](https://www.mnemonic.io/resources/blog/misuse-of-visual-studio-code-for-traffic-tunnelling/)
- [ExtensionTotal VSCode Extensions  2025](https://blog.extensiontotal.com/mining-in-plain-sight-the-vs-code-extension-cryptojacking-campaign-19ca12904b59)
