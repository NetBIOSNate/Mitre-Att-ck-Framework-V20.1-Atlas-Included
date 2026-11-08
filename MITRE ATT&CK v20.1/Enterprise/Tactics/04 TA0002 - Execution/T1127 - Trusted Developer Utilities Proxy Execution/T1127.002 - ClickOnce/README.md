# T1127.002 - ClickOnce

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1127 - Trusted Developer Utilities Proxy Execution](../README.md)

Adversaries may use ClickOnce applications (.appref-ms and .application files) to proxy execution of code through a trusted Windows utility.(Citation: Burke/CISA ClickOnce BlackHat) ClickOnce is a deployment that enables a user to create self-updating Windows-based .NET applications (i.e., .XBAP, .EXE, or .DLL) that install and run from a file share or web page with minimal user interaction. The application launches as a child process of DFSVC.EXE, which is responsible for installing, launching, and updating the application.(Citation: SpectorOps Medium ClickOnce)

Because ClickOnce applications receive only limited permissions, they do not require administrative permissions to install.(Citation: Microsoft Learn ClickOnce) As such, adversaries may abuse ClickOnce to proxy execution of malicious code without needing to escalate privileges.

ClickOnce may be abused in a number of ways. For example, an adversary may rely on [User Execution](https://attack.mitre.org/techniques/T1204). When a user visits a malicious website, the .NET malware is disguised as legitimate software and a ClickOnce popup is displayed for installation.(Citation: NetSPI ClickOnce)

Adversaries may also abuse ClickOnce to execute malware via a [Rundll32](https://attack.mitre.org/techniques/T1218/011) script using the command `rundll32.exe dfshim.dll,ShOpenVerbApplication1`.(Citation: LOLBAS /Dfsvc.exe)

Additionally, an adversary can move the ClickOnce application file to a remote user’s startup folder for continued malicious code deployment (i.e., [Registry Run Keys / Startup Folder](https://attack.mitre.org/techniques/T1547/001)).(Citation: Burke/CISA ClickOnce BlackHat)(Citation: Burke/CISA ClickOnce Paper)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1127/002)

**Tactics**  [Execution](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1045 - Code Signing](../../../../Defenses/Mitigations/M1045%20-%20Code%20Signing.md) — Enforce binary and application integrity with digital signature verification to prevent untrusted code from executing.(Citation: Microsoft Learn ClickOnce and Authenticode) [Microsoft Learn ClickOnce and Authenticode](https://learn.microsoft.com/en-us/visualstudio/deployment/clickonce-and-authenticode?view=vs-2022)
- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable ClickOnce installations from the internet using the following registry key: `\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Security\TrustManager\PromptingLevel — Internet:Disabled`(Citation: NetSPI ClickOnce)(Citation: Microsoft Learn ClickOnce Config) ClickOnce may not be necessary within an environment and should be disabled if not being used. [Microsoft Learn ClickOnce Config](https://learn.microsoft.com/en-us/visualstudio/deployment/how-to-configure-the-clickonce-trust-prompt-behavior?view=vs-2022&tabs=csharp) · [NetSPI ClickOnce](https://www.netspi.com/blog/technical-blog/adversary-simulation/all-you-need-is-one-a-clickonce-love-story/)
- [M1021 - Restrict Web-Based Content](../../../../Defenses/Mitigations/M1021%20-%20Restrict%20Web-Based%20Content.md) — Disable ClickOnce installations from the internet using the following registry key: `\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Security\TrustManager\PromptingLevel — Internet:Disabled`(Citation: NetSPI ClickOnce) [NetSPI ClickOnce](https://www.netspi.com/blog/technical-blog/adversary-simulation/all-you-need-is-one-a-clickonce-love-story/)

## Detection strategies

- [DET0191 - Behavior-chain detection strategy for T1127.002 Trusted Developer Utilities Proxy Execution: ClickOnce (Windows)](../../../../Defenses/Detection%20Strategies/DET0191%20-%20Behavior-chain%20detection%20strategy%20for%20T1127.002%20Trusted%20Developer%20Utilities%20Proxy%20Exe.md)

## Sources

- [LOLBAS /Dfsvc.exe](https://lolbas-project.github.io/lolbas/Binaries/Dfsvc/)
- [Microsoft Learn ClickOnce](https://learn.microsoft.com/en-us/visualstudio/deployment/clickonce-security-and-deployment?view=vs-2022)
- [SpectorOps Medium ClickOnce](https://posts.specterops.io/less-smartscreen-more-caffeine-ab-using-clickonce-for-trusted-code-execution-1446ea8051c5)
- [NetSPI ClickOnce](https://www.netspi.com/blog/technical-blog/adversary-simulation/all-you-need-is-one-a-clickonce-love-story/)
- [Burke/CISA ClickOnce Paper](https://i.blackhat.com/USA-19/Wednesday/us-19-Burke-ClickOnce-And-Youre-In-When-Appref-Ms-Abuse-Is-Operating-As-Intended-wp.pdf?_gl=1*1jv89bf*_gcl_au*NjAyMzkzMjc3LjE3MjQ4MDk4OTQ.*_ga*MTk5OTA3ODkwMC4xNzI0ODA5ODk0*_ga_K4JK67TFYV*MTcyNDgwOTg5NC4xLjEuMTcyNDgwOTk1Ny4wLjAuMA..&_ga=2.256219723.1512103758.1724809895-1999078900.1724809894)
- [Burke/CISA ClickOnce BlackHat](https://i.blackhat.com/USA-19/Wednesday/us-19-Burke-ClickOnce-And-Youre-In-When-Appref-Ms-Abuse-Is-Operating-As-Intended.pdf?_gl=1*16njas6*_gcl_au*NjAyMzkzMjc3LjE3MjQ4MDk4OTQ.*_ga*MTk5OTA3ODkwMC4xNzI0ODA5ODk0*_ga_K4JK67TFYV*MTcyNDgwOTg5NC4xLjEuMTcyNDgwOTk1Ny4wLjAuMA..&_ga=2.253743689.1512103758.1724809895-1999078900.1724809894)
