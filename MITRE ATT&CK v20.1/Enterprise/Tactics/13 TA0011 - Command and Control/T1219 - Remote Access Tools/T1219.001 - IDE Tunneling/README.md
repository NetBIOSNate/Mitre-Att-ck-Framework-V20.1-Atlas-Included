# T1219.001 - IDE Tunneling

[Enterprise](../../../../README.md) / [Command and Control](../../README.md) / [T1219 - Remote Access Tools](../README.md)

Adversaries may abuse Integrated Development Environment (IDE) software with remote development features to establish an interactive command and control channel on target systems within a network. IDE tunneling combines SSH, port forwarding, file sharing, and debugging into a single secure connection, letting developers work on remote systems as if they were local. Unlike SSH and port forwarding, IDE tunneling encapsulates an entire session and may use proprietary tunneling protocols alongside SSH, allowing adversaries to blend in with legitimate development workflows. Some IDEs, like Visual Studio Code, also provide CLI tools (e.g., `code tunnel`) that adversaries may use to programmatically establish tunnels and generate web-accessible URLs for remote access. These tunnels can be authenticated through accounts such as GitHub, enabling the adversary to control the compromised system via a legitimate developer portal.(Citation: sentinelone operationDigitalEye Dec 2024)(Citation: Unit42 Chinese VSCode 06 September 2024)(Citation: Thornton tutorial VSCode shell September 2023)

Additionally, adversaries may use IDE tunneling for persistence. Some IDEs, such as Visual Studio Code and JetBrains, support automatic reconnection. Adversaries may configure the IDE to auto-launch at startup, re-establishing the tunnel upon execution. Compromised developer machines may also be exploited as jump hosts to move further into the network.

IDE tunneling tools may be built-in or installed as [IDE Extensions](https://attack.mitre.org/techniques/T1176/002).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1219/001)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Use Group Policies to require user authentication by disabling anonymous tunnel access, preventing any unauthenticated tunnel creation or usage. Disable the Visual Studio Dev Tunnels feature to block tunnel-related commands, allowing only minimal exceptions for utility functions (unset, echo, ping, and user). Restrict tunnel access to approved Microsoft Entra tenant IDs by specifying allowed tenants; all other users are denied access by default.(Citation: Microsoft Dev Tunnels Group Policy Mitigation)(Citation: Microsoft Dev Tunnels Group Policies) [Microsoft Dev Tunnels Group Policies](https://techcommunity.microsoft.com/blog/azuredevcommunityblog/manage-dev-tunnels-with-group-policies/4149472) · [Microsoft Dev Tunnels Group Policy Mitigation](https://learn.microsoft.com/en-us/azure/developer/dev-tunnels/policies)

## Detection strategies

- [DET0133 - IDE Tunneling Detection via Process, File, and Network Behaviors](../../../../Defenses/Detection%20Strategies/DET0133%20-%20IDE%20Tunneling%20Detection%20via%20Process%2C%20File%2C%20and%20Network%20Behaviors.md)

## Procedure examples

- [G0129 - Mustang Panda](../../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has utilized an established Github account to create a tunnel within the victim environment using Visual Studio Code through the `code.exe tunnel` command.(Citation: Unit42 Chinese VSCode 06 September 2024) [Unit42 Chinese VSCode 06 September 2024](https://unit42.paloaltonetworks.com/stately-taurus-abuses-vscode-southeast-asian-espionage/)
- [C0060 - Operation AkaiRyū](../../../../Threat%20Intelligence/Campaigns/C0060%20-%20Operation%20AkaiRy%C5%AB.md) — During [Operation AkaiRyū](https://attack.mitre.org/campaigns/C0060), [MirrorFace](https://attack.mitre.org/groups/G1054) abused Visual Studio Code (VS Code) remote tunnels to gain access and execute code on compromised machines.(Citation: ESET MirrorFace 2025) [ESET MirrorFace 2025](https://www.welivesecurity.com/en/eset-research/operation-akairyu-mirrorface-invites-europe-expo-2025-revives-anel-backdoor/)
- [C0061 - Operation Digital Eye](../../../../Threat%20Intelligence/Campaigns/C0061%20-%20Operation%20Digital%20Eye.md) — During [Operation Digital Eye](https://attack.mitre.org/campaigns/C0061), threat actors created Visual Studio Code dev tunnels to access targeted endpoints through the browser-based version of Visual Studio Code.(Citation: sentinelone operationDigitalEye Dec 2024) [sentinelone operationDigitalEye Dec 2024](https://www.sentinelone.com/labs/operation-digital-eye-chinese-apt-compromises-critical-digital-infrastructure-via-visual-studio-code-tunnels/)

## Sources

- [sentinelone operationDigitalEye Dec 2024](https://www.sentinelone.com/labs/operation-digital-eye-chinese-apt-compromises-critical-digital-infrastructure-via-visual-studio-code-tunnels/)
- [Unit42 Chinese VSCode 06 September 2024](https://unit42.paloaltonetworks.com/stately-taurus-abuses-vscode-southeast-asian-espionage/)
- [Thornton tutorial VSCode shell September 2023](https://medium.com/@truvis.thornton/visual-studio-code-embedded-reverse-shell-and-how-to-block-create-sentinel-detection-and-add-e864ebafaf6d)
