# T1546.018 - Python Startup Hooks

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1546 - Event Triggered Execution](../README.md)

Adversaries may achieve persistence by leveraging Python’s startup mechanisms, including path configuration (`.pth`) files and the `sitecustomize.py` or `usercustomize.py` modules. These files are automatically processed during the initialization of the Python interpreter, allowing for the execution of arbitrary code whenever Python is invoked.(Citation: Volexity GlobalProtect CVE 2024)

Path configuration files are designed to extend Python’s module search paths through the use of import statements. If a `.pth` file is placed in Python's `site-packages` or `dist-packages` directories, any lines beginning with `import` will be executed automatically on Python invocation.(Citation: DFIR Python Persistence 2025) Similarly, if `sitecustomize.py` or `usercustomize.py` is present in the Python path, these files will be imported during interpreter startup, and any code they contain will be executed.(Citation: Python Site Configuration Hook)

Adversaries may abuse these mechanisms to establish persistence on systems where Python is widely used (e.g., for automation or scripting in production environments).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1546/018)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has utilized Python startup hooks to include the .pth import mechanism for execution.(Citation: Trend Micro TeamPCP MAY 2026) [Trend Micro TeamPCP MAY 2026](https://www.trendmicro.com/en_us/research/26/e/analyzing-teampcp-supply-chain-attacks.html)
- [S9041 - TeamPCP Cloud Stealer](../../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) has used .pth files to establish persistence on compromised hosts due to the Python interpreter's automatic processing of .pth files at startup.(Citation: Palo Alto TeamPCP MAR 2026) [Palo Alto TeamPCP MAR 2026](https://unit42.paloaltonetworks.com/teampcp-supply-chain-attacks/)

## Detection strategies

- [DET0258 - Linux Python Startup Hook Persistence via .pth and Customize Files (T1546.018)](../../../../Defenses/Detection%20Strategies/DET0258%20-%20Linux%20Python%20Startup%20Hook%20Persistence%20via%20.pth%20and%20Customize%20Files%20%28T1546.018%29.md)

## Sources

- [Python Site Configuration Hook](https://docs.python.org/3/library/site.html)
- [DFIR Python Persistence 2025](https://dfir.ch/posts/publish_python_pth_extension/)
- [Volexity GlobalProtect CVE 2024](https://www.volexity.com/blog/2024/04/12/zero-day-exploitation-of-unauthenticated-remote-code-execution-vulnerability-in-globalprotect-cve-2024-3400/)
