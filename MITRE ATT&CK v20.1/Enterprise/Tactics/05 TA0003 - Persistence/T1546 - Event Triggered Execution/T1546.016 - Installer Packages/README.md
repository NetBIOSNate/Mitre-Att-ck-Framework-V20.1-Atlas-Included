# T1546.016 - Installer Packages

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may establish persistence and elevate privileges by using an installer to trigger the execution of malicious content. Installer packages are OS specific and contain the resources an operating system needs to install applications on a system. Installer packages can include scripts that run prior to installation as well as after installation is complete. Installer scripts may inherit elevated permissions when executed. Developers often use these scripts to prepare the environment for installation, check requirements, download dependencies, and remove files after installation.(Citation: Installer Package Scripting Rich Trouton)

Using legitimate applications, adversaries have distributed applications with modified installer scripts to execute malicious content. When a user installs the application, they may be required to grant administrative permissions to allow the installation. At the end of the installation process of the legitimate application, content such as macOS `postinstall` scripts can be executed with the inherited elevated permissions. Adversaries can use these scripts to execute a malicious executable or install other malicious components (such as a [Launch Daemon](https://attack.mitre.org/techniques/T1543/004)) with the elevated permissions.(Citation: Application Bundle Manipulation Brandon Dalton)(Citation: wardle evilquest parti)(Citation: Windows AppleJeus GReAT)(Citation: Debian Manual Maintainer Scripts)

Depending on the distribution, Linux versions of package installer scripts are sometimes called maintainer scripts or post installation scripts. These scripts can include `preinst`, `postinst`, `prerm`, `postrm` scripts and run as root when executed.

For Windows, the Microsoft Installer service uses `.msi` files to manage the installing, updating, and uninstalling of applications. These installation routines may also include instructions to perform additional actions that may be abused by adversaries.(Citation: Microsoft Installation Procedures)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/016)

**Tactics**  [Persistence](../../README.md), [Privilege Escalation](../../../06%20TA0004%20-%20Privilege%20Escalation/README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0057 - 3CX Supply Chain Attack](../../../../Threat%20Intelligence/Campaigns/C0057%20-%203CX%20Supply%20Chain%20Attack.md) — During the [3CX Supply Chain Attack](https://attack.mitre.org/campaigns/C0057), [AppleJeus](https://attack.mitre.org/groups/G1049) added a malicious .dylib file to a .dmg installer package for the macOS 3CX application.(Citation: Unit42 3cx supply chain 2023) [Unit42 3cx supply chain 2023](https://unit42.paloaltonetworks.com/3cxdesktopapp-supply-chain-attack/)
- [S0584 - AppleJeus](../../../../Threat%20Intelligence/Software/Malware/S0584%20-%20AppleJeus.md) — During [AppleJeus](https://attack.mitre.org/software/S0584)'s installation process, it uses `postinstall` scripts to extract a hidden plist from the application's `/Resources` folder and execute the `plist` file as a [Launch Daemon](https://attack.mitre.org/techniques/T1543/004) with elevated permissions.(Citation: ObjectiveSee AppleJeus 2019) [ObjectiveSee AppleJeus 2019](https://objective-see.org/blog/blog_0x49.html)
- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has poisoned Axios and Mastra npm packages with malicious post-install hooks.(Citation: Microsoft Axios Compromise APR 2026)(Citation: MIcrosoft Mastra npm Compromise JUN 2026) [Microsoft Axios Compromise APR 2026](https://www.microsoft.com/en-us/security/blog/2026/04/01/mitigating-the-axios-npm-supply-chain-compromise/) · [MIcrosoft Mastra npm Compromise JUN 2026](https://www.microsoft.com/en-us/security/blog/2026/06/17/postinstall-payload-inside-mastra-npm-supply-chain-compromise/)
- [S9008 - Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9008%20-%20Shai-Hulud.md) — [Shai-Hulud](https://attack.mitre.org/software/S9008) has inserted a new lifecycle hook to include `postinstall`.(Citation: Aikido Shai-Hulud September 2025)(Citation: Palo Alto Unit 42 Shai-Hulud November 2025)(Citation: Wiz Shai-Hulud September 2025)(Citation: Socket Shai-Hulud November 2025) [Shai-Hulud](https://attack.mitre.org/software/S9008) has also leveraged the NPM lifecycle hook `preinstall`.(Citation: Netskope Shai-Hulud November 2025)(Citation: Palo Alto Unit 42 Shai-Hulud November 2025)(Citation: Microsoft Shai-Hulud December 2025)(Citation: Socket Shai-Hulud November 2025) [Aikido Shai-Hulud September 2025](https://www.aikido.dev/blog/s1ngularity-nx-attackers-strike-again) · [Netskope Shai-Hulud November 2025](https://www.netskope.com/blog/shai-hulud-2-0-aggressive-automated-one-of-fastest-spreading-npm-supply-chain-attacks-ever-observed) · [Palo Alto Unit 42 Shai-Hulud November 2025](https://unit42.paloaltonetworks.com/npm-supply-chain-attack/) · [Wiz Shai-Hulud September 2025](https://www.wiz.io/blog/shai-hulud-npm-supply-chain-attack) · [Microsoft Shai-Hulud December 2025](https://www.microsoft.com/en-us/security/blog/2025/12/09/shai-hulud-2-0-guidance-for-detecting-investigating-and-defending-against-the-supply-chain-attack/) · [Socket Shai-Hulud November 2025](https://socket.dev/blog/shai-hulud-strikes-again-v2)
- [G1056 - TeamPCP](../../../../Threat%20Intelligence/Groups/G1056%20-%20TeamPCP.md) — [TeamPCP](https://attack.mitre.org/groups/G1056) has modified software packages with preinstall scripts to download and execute malicious payloads.(Citation: Wiz Mini Shai-Hulud MAY 2026) [Wiz Mini Shai-Hulud MAY 2026](https://www.wiz.io/blog/mini-shai-hulud-strikes-again-tanstack-more-npm-packages-compromised)
- [S9041 - TeamPCP Cloud Stealer](../../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can inject malicious pre or post-install scripts within package.json for payload execution.(Citation: Palo Alto TeamPCP MAR 2026) [Palo Alto TeamPCP MAR 2026](https://unit42.paloaltonetworks.com/teampcp-supply-chain-attacks/)

## Detection strategies

- [DET0330 - Detection Strategy for T1546.016 - Event Triggered Execution via Installer Packages](../../../../Defenses/Detection%20Strategies/DET0330%20-%20Detection%20Strategy%20for%20T1546.016%20-%20Event%20Triggered%20Execution%20via%20Installer%20Packages.md)

## Sources

- [Application Bundle Manipulation Brandon Dalton](https://redcanary.com/blog/mac-application-bundles/)
- [Debian Manual Maintainer Scripts](https://www.debian.org/doc/debian-policy/ch-maintainerscripts.html#s-mscriptsinstact)
- [Windows AppleJeus GReAT](https://securelist.com/operation-applejeus/87553/)
- [Microsoft Installation Procedures](https://learn.microsoft.com/windows/win32/msi/installation-procedure-tables-group)
- [wardle evilquest parti](https://objective-see.com/blog/blog_0x59.html)
- [Installer Package Scripting Rich Trouton](https://cpb-us-e1.wpmucdn.com/sites.psu.edu/dist/4/24696/files/2019/07/psumac2019-345-Installer-Package-Scripting-Making-your-deployments-easier-one-at-a-time.pdf)
