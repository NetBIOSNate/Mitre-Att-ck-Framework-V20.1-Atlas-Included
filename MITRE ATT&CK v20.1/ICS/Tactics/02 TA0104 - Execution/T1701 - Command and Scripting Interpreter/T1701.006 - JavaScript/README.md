# T1701.006 - JavaScript

[ICS](../../../../README.md) / [Execution](../../README.md) / [T1701 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse various implementations of JavaScript for execution. JavaScript is a platform-independent scripting language (compiled just-in-time at runtime) commonly associated with scripts in webpages, though JavaScript can be executed in runtime environments outside the browser.(Citation: NodeJS)

JScript is the Microsoft implementation of the same scripting standard. JScript is interpreted via the Windows Script engine and thus integrated with many components of Windows such as the [Component Object Model](https://attack.mitre.org/techniques/T1559/001) and Internet Explorer HTML Application (HTA) pages.(Citation: JScrip May 2018)(Citation: Microsoft JScript 2007)(Citation: Microsoft Windows Scripts)

Adversaries may abuse various implementations of JavaScript to execute various behaviors. Common uses include hosting malicious scripts on websites as part of a [Drive-by Compromise](https://attack.mitre.org/techniques/T0817) or downloading and executing these script files as secondary payloads. Since these payloads are text-based, it is also very common for adversaries to obfuscate their content as part of [Obfuscated Files or Information](https://attack.mitre.org/techniques/T1027).

Within industrial control system networks, adversaries most commonly abuse the use of JavaScript on overlap assets that run on operating system platforms similar to Enterprise devices.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1701/006)

**Tactics**  [Execution](../../README.md)

## Mitigations

- [M0942 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M0942%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable or remove JavaScript/JScript execution surfaces that are not required for the documented role of an ICS asset, while preserving validated HMI, vendor, and engineering dependencies.
- [M0938 - Execution Prevention](../../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Use application control to restrict wscript.exe, cscript.exe, mshta.exe, Node.js, and other JavaScript runtimes to approved paths, parent processes, scripts, and users.
- [M0950 - Exploit Protection](../../../../Defenses/Mitigations/M0950%20-%20Exploit%20Protection.md) — Harden browsers, HTML applications, and Windows scripting hosts that can execute JavaScript/JScript on ICS overlap assets.
- [M0921 - Restrict Web-Based Content](../../../../Defenses/Mitigations/M0921%20-%20Restrict%20Web-Based%20Content.md) — Restrict untrusted web content and active scripting on ICS workstations, jump hosts, and other overlap assets, especially where browser access is not required for operations.

## Targeted assets

- [A0008 - Application Server](../../../../Defenses/Assets/A0008%20-%20Application%20Server.md)
- [A0007 - Control Server](../../../../Defenses/Assets/A0007%20-%20Control%20Server.md)
- [A0009 - Data Gateway](../../../../Defenses/Assets/A0009%20-%20Data%20Gateway.md)
- [A0006 - Data Historian](../../../../Defenses/Assets/A0006%20-%20Data%20Historian.md)
- [A0016 - Firewall](../../../../Defenses/Assets/A0016%20-%20Firewall.md)
- [A0002 - Human-Machine Interface (HMI)](../../../../Defenses/Assets/A0002%20-%20Human-Machine%20Interface%20%28HMI%29.md)
- [A0012 - Jump Host](../../../../Defenses/Assets/A0012%20-%20Jump%20Host.md)
- [A0004 - Remote Terminal Unit (RTU)](../../../../Defenses/Assets/A0004%20-%20Remote%20Terminal%20Unit%20%28RTU%29.md)
- [A0011 - Virtual Private Network (VPN) Server](../../../../Defenses/Assets/A0011%20-%20Virtual%20Private%20Network%20%28VPN%29%20Server.md)
- [A0001 - Workstation](../../../../Defenses/Assets/A0001%20-%20Workstation.md)

## Procedure examples

- [S0496 - REvil](../../../../Threat%20Intelligence/Software/Malware/S0496%20-%20REvil.md) — [REvil](https://attack.mitre.org/software/S0496) utilizes JavaScript, WScript, and PowerShell scripts to execute. The malicious JavaScript attachment has an obfuscated PowerShell script that executes the malware. (Citation: Tom Fakterman August 2019) [Tom Fakterman August 2019](https://www.cybereason.com/blog/the-sodinokibi-ransomware-attack)

## Detection strategies

- [DET0936 - Behavioral Detection of JavaScript Execution in ICS](../../../../Defenses/Detection%20Strategies/DET0936%20-%20Behavioral%20Detection%20of%20JavaScript%20Execution%20in%20ICS.md)

## Sources

- [Microsoft JScript 2007](https://docs.microsoft.com/archive/blogs/gauravseth/the-world-of-jscript-javascript-ecmascript)
- [Microsoft Windows Scripts](https://docs.microsoft.com/scripting/winscript/windows-script-interfaces)
- [JScrip May 2018](https://docs.microsoft.com/windows/win32/com/translating-to-jscript)
- [NodeJS](https://nodejs.org/)
