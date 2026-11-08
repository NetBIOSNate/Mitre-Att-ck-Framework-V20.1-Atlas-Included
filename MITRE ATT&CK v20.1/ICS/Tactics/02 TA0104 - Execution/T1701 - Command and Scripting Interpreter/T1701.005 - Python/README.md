# T1701.005 - Python

[ICS](../../../../README.md) / [Execution](../../README.md) / [T1701 - Command and Scripting Interpreter](../README.md)

Adversaries may abuse Python commands and scripts for execution. Python is a very popular scripting/programming language, with capabilities to perform many functions. Python can be executed interactively from the command-line (via the <code>python.exe</code> interpreter) or via scripts (.py) that can be written and distributed to different systems. Python code can also be compiled into binary executables.(Citation: Zscaler APT31 Covid-19 October 2020)

Python comes with many built-in packages to interact with the underlying system, such as file operations and device I/O. Within industrial control system environments, Python libraries have been developed to implement multiple ICS protocols to establish communications with field devices. Adversaries can use these libraries or develop their own to execute commands on workstation, control server assets or send remote command messages to manipulate the industrial process through exisiting ICS protocols.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1701/005)

**Tactics**  [Execution](../../README.md)

## Procedure examples

- [S1009 - Triton](../../../../Threat%20Intelligence/Software/Malware/S1009%20-%20Triton.md) — [Triton](https://attack.mitre.org/software/S1009) communicates with Triconex controllers using a custom component framework written entirely in Python. The modules that implement the TriStation communication protocol and other supporting components are found in a separate file -- library.zip -- the main script that employs this functionality is compiled into a standalone py2exe Windows executable -- trilog.exe which includes a Python environment.(Citation: DHS CISA February 2019) [DHS CISA February 2019](https://ics-cert.us-cert.gov/sites/default/files/documents/MAR-17-352-01%20HatMan%20-%20Safety%20System%20Targeted%20Malware%20%28Update%20B%29.pdf)

## Mitigations

- [M0947 - Audit](../../../../Defenses/Mitigations/M0947%20-%20Audit.md) — Inventory and audit Python interpreters, packages, virtual environments, execution paths, and ICS protocol libraries on assets where Python is authorized. Alert on new interpreters or packages outside approved engineering baselines.
- [M0938 - Execution Prevention](../../../../Defenses/Mitigations/M0938%20-%20Execution%20Prevention.md) — Restrict Python execution to approved interpreters, scripts, libraries, accounts, and paths. On engineering systems where Python is required, use positive allowlisting rather than disabling the interpreter.
- [M0950 - Exploit Protection](../../../../Defenses/Mitigations/M0950%20-%20Exploit%20Protection.md) — Apply exploit-protection controls to Python-capable Windows/Linux ICS overlap assets where supported, particularly when Python is embedded in engineering or vendor applications.
- [M1061 - Limit Software/Package Installation](../../../../Defenses/Mitigations/M1061%20-%20Limit%20Software%20-%20Package%20Installation.md) — Prevent unauthorized installation of Python interpreters and packages on ICS assets.

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

## Detection strategies

- [DET0933 - Behavioral Detection of Python Execution in ICS](../../../../Defenses/Detection%20Strategies/DET0933%20-%20Behavioral%20Detection%20of%20Python%20Execution%20in%20ICS.md)

## Sources

- [Zscaler APT31 Covid-19 October 2020](https://www.zscaler.com/blogs/security-research/apt-31-leverages-covid-19-vaccine-theme-and-abuses-legitimate-online)
