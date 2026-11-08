# T1218.015 - Electron Applications

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1218 - System Binary Proxy Execution](../README.md)

Adversaries may abuse components of the Electron framework to execute malicious code. The Electron framework hosts many common applications such as Signal, Slack, and Microsoft Teams.(Citation: Electron 2) Originally developed by GitHub, Electron is a cross-platform desktop application development framework that employs web technologies like JavaScript, HTML, and CSS.(Citation: Electron 3) The Chromium engine is used to display web content and Node.js runs the backend code.(Citation: Electron 1)

Due to the functional mechanics of Electron (such as allowing apps to run arbitrary commands), adversaries may also be able to perform malicious functions in the background potentially disguised as legitimate tools within the framework.(Citation: Electron 1) For example, the abuse of `teams.exe` and `chrome.exe` may allow adversaries to execute malicious commands as child processes of the legitimate application (e.g., `chrome.exe --disable-gpu-sandbox --gpu-launcher="C:\Windows\system32\cmd.exe /c calc.exe`).(Citation: Electron 6-8)

Adversaries may also execute malicious content by planting malicious [JavaScript](https://attack.mitre.org/techniques/T1059/007) within Electron applications.(Citation: Electron Security)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1218/015)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Remove or deny access to unnecessary and potentially vulnerable software and features to prevent abuse by adversaries. Many native binaries may not be necessary within a given environment: for example, consider disabling the Node.js integration in all renderers that display remote content to protect users by limiting adversaries’ power to plant malicious JavaScript within Electron applications.(Citation: Electron Security 2) [Electron Security 2](https://stackoverflow.com/questions/48854265/why-do-i-see-an-electron-security-warning-after-updating-my-electron-project-t)
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Where possible, enforce binary and application integrity with digital signature verification to prevent untrusted code from executing. For example, do not use `shell.openExternal` with untrusted content. Where possible, set `nodeIntegration` to false, which disables access to the Node.js function.(Citation: Electron Security 3) By disabling access to the Node.js function, this may limit the ability to execute malicious commands by injecting JavaScript code. Do not disable `webSecurity`, which may allow for users of the application to invoke malicious content from online sources. [Electron Security 3](https://medium.com/certik/vulnerability-in-electron-based-application-unintentionally-giving-malicious-code-room-to-run-e2e1447d01b8)
- [M1050 - Exploit Protection](../../../../Defenses/Mitigations/M1050%20-%20Exploit%20Protection.md) — Microsoft's Enhanced Mitigation Experience Toolkit (EMET) Attack Surface Reduction (ASR) feature can be used to block methods of using trusted binaries to bypass application control. Ensure that Electron is updated to the latest version and critical vulnerabilities (such as nodeIntegration bypasses) are patched and cannot be exploited.

## Detection strategies

- [DET0025 - Detecting Electron Application Abuse for Proxy Execution](../../../../Defenses/Detection%20Strategies/DET0025%20-%20Detecting%20Electron%20Application%20Abuse%20for%20Proxy%20Execution.md)

## Procedure examples

- [C0057 - 3CX Supply Chain Attack](../../../../Threat%20Intelligence/Campaigns/C0057%20-%203CX%20Supply%20Chain%20Attack.md) — During the [3CX Supply Chain Attack](https://attack.mitre.org/campaigns/C0057), [AppleJeus](https://attack.mitre.org/groups/G1049) leveraged the 3CX application's electron framework to execute its malicious libraries under the official 3CX electron application.(Citation: Unit42 3cx supply chain 2023) [Unit42 3cx supply chain 2023](https://unit42.paloaltonetworks.com/3cxdesktopapp-supply-chain-attack/)
- [S1213 - Lumma Stealer](../../../../Threat%20Intelligence/Software/Malware/S1213%20-%20Lumma%20Stealer.md) — [Lumma Stealer](https://attack.mitre.org/software/S1213) as leveraged Electron Applications to disable GPU sandboxing to avoid detection by security software.(Citation: TrendMicro LummaStealer 2025) [TrendMicro LummaStealer 2025](https://www.trendmicro.com/en_us/research/25/a/lumma-stealers-github-based-delivery-via-mdr.html)

## Sources

- [Electron 3](https://www.kaspersky.com/blog/electron-framework-security-issues/49035/)
- [Electron Security](https://www.electronjs.org/docs/latest/tutorial/using-native-node-modules)
- [Electron 6-8](https://medium.com/@MalFuzzer/one-electron-to-rule-them-all-dc2e9b263daf)
- [Electron 1](https://www.mend.io/blog/theres-a-new-stealer-variant-in-town-and-its-using-electron-to-stay-fully-undetected/)
- [Electron 2](https://www.first.org/resources/papers/conf2023/FIRSTCON23-TLP-CLEAR-Horejsi-Abusing-Electron-Based-Applications-in-Targeted-Attacks.pdf)
