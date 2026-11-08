# T1176 - Software Extensions

[Enterprise](../../../README.md) / [Persistence](../README.md)

Adversaries may abuse software extensions to establish persistent access to victim systems. Software extensions are modular components that enhance or customize the functionality of software applications, including web browsers, Integrated Development Environments (IDEs), and other platforms.(Citation: Chrome Extension C2 Malware)(Citation: Abramovsky VSCode Security) Extensions are typically installed via official marketplaces, app stores, or manually loaded by users, and they often inherit the permissions and access levels of the host application. 

  
Malicious extensions can be introduced through various methods, including social engineering, compromised marketplaces, or direct installation by users or by adversaries who have already gained access to a system. Malicious extensions can be named similarly or identically to benign extensions in marketplaces. Security mechanisms in extension marketplaces may be insufficient to detect malicious components, allowing adversaries to bypass automated scanners or exploit trust established during the installation process. Adversaries may also abuse benign extensions to achieve their objectives, such as using legitimate functionality to tunnel data or bypass security controls. 

The modular nature of extensions and their integration with host applications make them an attractive target for adversaries seeking to exploit trusted software ecosystems. Detection can be challenging due to the inherent trust placed in extensions during installation and their ability to blend into normal application workflows.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1176)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Linux](../../../Platforms/Linux.md), [macOS](../../../Platforms/macOS.md), [Windows](../../../Platforms/Windows.md)

## Sub-techniques

- [T1176.001 - Browser Extensions](T1176.001%20-%20Browser%20Extensions/README.md)
- [T1176.002 - IDE Extensions](T1176.002%20-%20IDE%20Extensions/README.md)

## Mitigations

- [M1047 - Audit](../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Ensure extensions that are installed are the intended ones, as many malicious extensions may masquerade as legitimate ones.
- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Set an extension allow or deny list as appropriate for your security policy.
- [M1033 - Limit Software Installation](../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Only install extensions from trusted sources that can be verified.
- [M1051 - Update Software](../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Ensure operating systems and software are using the most current version.
- [M1017 - User Training](../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Train users to minimize extension use, and to only install trusted extensions.

## Detection strategies

- [DET0092 - Detection of Malicious or Unauthorized Software Extensions](../../../Defenses/Detection%20Strategies/DET0092%20-%20Detection%20of%20Malicious%20or%20Unauthorized%20Software%20Extensions.md)

## Sources

- [Abramovsky VSCode Security](https://blog.checkpoint.com/securing-the-cloud/malicious-vscode-extensions-with-more-than-45k-downloads-steal-pii-and-enable-backdoors/)
- [xorrior chrome extensions macOS](https://www.xorrior.com/No-Place-Like-Chrome/)
- [Chrome Extension C2 Malware](https://web.archive.org/web/20240608001937/https://kjaer.io/extension-malware/)
