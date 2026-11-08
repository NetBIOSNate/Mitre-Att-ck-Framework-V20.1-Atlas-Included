# T1055.004 - Asynchronous Procedure Call

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1055 - Process Injection](../README.md)

Adversaries may inject malicious code into processes via the asynchronous procedure call (APC) queue in order to evade process-based defenses as well as possibly elevate privileges. APC injection is a method of executing arbitrary code in the address space of a separate live process. 

APC injection is commonly performed by attaching malicious code to the APC Queue(Citation: Microsoft APC) of a process's thread. Queued APC functions are executed when the thread enters an alterable state.(Citation: Microsoft APC) A handle to an existing victim process is first created with native Windows API calls such as <code>OpenThread</code>. At this point <code>QueueUserAPC</code> can be used to invoke a function (such as <code>LoadLibrayA</code> pointing to a malicious DLL). 

A variation of APC injection, dubbed "Early Bird injection", involves creating a suspended process in which malicious code can be written and executed before the process' entry point (and potentially subsequent anti-malware hooks) via an APC.(Citation: CyberBit Early Bird Apr 2018) AtomBombing(Citation: ENSIL AtomBombing Oct 2016) is another variation that utilizes APCs to invoke malicious code previously written to the global atom table.(Citation: Microsoft Atom Table)

Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via APC injection may also evade detection from security products since the execution is masked under a legitimate process.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1055/004)

**Tactics**  [Privilege Escalation](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [S0438 - Attor](../../../../Threat%20Intelligence/Software/Malware/S0438%20-%20Attor.md) — [Attor](https://attack.mitre.org/software/S0438) performs the injection by attaching its code into the APC queue using NtQueueApcThread API.(Citation: ESET Attor Oct 2019) [ESET Attor Oct 2019](https://www.welivesecurity.com/wp-content/uploads/2019/10/ESET_Attor.pdf)
- [S1081 - BADHATCH](../../../../Threat%20Intelligence/Software/Malware/S1081%20-%20BADHATCH.md) — [BADHATCH](https://attack.mitre.org/software/S1081) can inject itself into a new `svchost.exe -k netsvcs` process using the asynchronous procedure call (APC) queue.(Citation: Gigamon BADHATCH Jul 2019)(Citation: BitDefender BADHATCH Mar 2021) [Gigamon BADHATCH Jul 2019](https://blog.gigamon.com/2019/07/23/abadbabe-8badf00d-discovering-badhatch-and-a-detailed-look-at-fin8s-tooling/) · [BitDefender BADHATCH Mar 2021](https://www.bitdefender.com/files/News/CaseStudies/study/394/Bitdefender-PR-Whitepaper-BADHATCH-creat5237-en-EN.pdf)
- [S1039 - Bumblebee](../../../../Threat%20Intelligence/Software/Malware/S1039%20-%20Bumblebee.md) — [Bumblebee](https://attack.mitre.org/software/S1039) can use asynchronous procedure call (APC) injection to execute commands received from C2.(Citation: Proofpoint Bumblebee April 2022) [Proofpoint Bumblebee April 2022](https://www.proofpoint.com/us/blog/threat-insight/bumblebee-is-still-transforming)
- [S0484 - Carberp](../../../../Threat%20Intelligence/Software/Malware/S0484%20-%20Carberp.md) — [Carberp](https://attack.mitre.org/software/S0484) has queued an APC routine to explorer.exe by calling ZwQueueApcThread.(Citation: Prevx Carberp March 2011) [Prevx Carberp March 2011](https://web.archive.org/web/20231227000328/http://pxnow.prevx.com/content/blog/carberp-a_modular_information_stealing_trojan.pdf)
- [G0061 - FIN8](../../../../Threat%20Intelligence/Groups/G0061%20-%20FIN8.md) — [FIN8](https://attack.mitre.org/groups/G0061) has injected malicious code into a new svchost.exe process.(Citation: Bitdefender FIN8 July 2021) [Bitdefender FIN8 July 2021](https://businessinsights.bitdefender.com/deep-dive-into-a-fin8-attack-a-forensic-investigation)
- [S9018 - HeartCrypt](../../../../Threat%20Intelligence/Software/Malware/S9018%20-%20HeartCrypt.md) — [HeartCrypt](https://attack.mitre.org/software/S9018) has the ability to use `NtQueueApcThread` as an alternate method for process injection.(Citation: Palo Alto HeartCrypt DEC 2024) [Palo Alto HeartCrypt DEC 2024](https://unit42.paloaltonetworks.com/packer-as-a-service-heartcrypt-malware/)
- [S0483 - IcedID](../../../../Threat%20Intelligence/Software/Malware/S0483%20-%20IcedID.md) — [IcedID](https://attack.mitre.org/software/S0483) has used <code>ZwQueueApcThread</code> to inject itself into remote processes.(Citation: IBM IcedID November 2017) [IBM IcedID November 2017](https://securityintelligence.com/new-banking-trojan-icedid-discovered-by-ibm-x-force-research/)
- [S0260 - InvisiMole](../../../../Threat%20Intelligence/Software/Malware/S0260%20-%20InvisiMole.md) — [InvisiMole](https://attack.mitre.org/software/S0260) can inject its code into a trusted process via the APC queue.(Citation: ESET InvisiMole June 2020) [ESET InvisiMole June 2020](https://www.welivesecurity.com/wp-content/uploads/2020/06/ESET_InvisiMole.pdf)
- [S0517 - Pillowmint](../../../../Threat%20Intelligence/Software/Malware/S0517%20-%20Pillowmint.md) — [Pillowmint](https://attack.mitre.org/software/S0517) has used the NtQueueApcThread syscall to inject code into svchost.exe.(Citation: Trustwave Pillowmint June 2020) [Trustwave Pillowmint June 2020](https://www.trustwave.com/en-us/resources/blogs/spiderlabs-blog/pillowmint-fin7s-monkey-thief/)
- [S1018 - Saint Bot](../../../../Threat%20Intelligence/Software/Malware/S1018%20-%20Saint%20Bot.md) — [Saint Bot](https://attack.mitre.org/software/S1018) has written its payload into a newly-created `EhStorAuthn.exe` process using `ZwWriteVirtualMemory` and executed it using `NtQueueApcThread` and `ZwAlertResumeThread`.(Citation: Malwarebytes Saint Bot April 2021) [Malwarebytes Saint Bot April 2021](https://blog.malwarebytes.com/threat-intelligence/2021/04/a-deep-dive-into-saint-bot-downloader/)
- [S1085 - Sardonic](../../../../Threat%20Intelligence/Software/Malware/S1085%20-%20Sardonic.md) — [Sardonic](https://attack.mitre.org/software/S1085) can use the `QueueUserAPC` API to execute shellcode on a compromised machine.(Citation: Symantec FIN8 Jul 2023) [Symantec FIN8 Jul 2023](https://symantec-enterprise-blogs.security.com/blogs/threat-intelligence/syssphinx-fin8-backdoor)
- [S0199 - TURNEDUP](../../../../Threat%20Intelligence/Software/Malware/S0199%20-%20TURNEDUP.md) — [TURNEDUP](https://attack.mitre.org/software/S0199) is capable of injecting code into the APC queue of a created [Rundll32](https://attack.mitre.org/techniques/T1218/011) process as part of an "Early Bird injection."(Citation: CyberBit Early Bird Apr 2018) [CyberBit Early Bird Apr 2018](https://www.cyberbit.com/blog/endpoint-security/new-early-bird-code-injection-technique-discovered/)
- [S1207 - XLoader](../../../../Threat%20Intelligence/Software/Malware/S1207%20-%20XLoader.md) — [XLoader](https://attack.mitre.org/software/S1207) injects code into the APC queue using `NtQueueApcThread` API.(Citation: Zscaler XLoader 2025) [Zscaler XLoader 2025](https://www.zscaler.com/blogs/security-research/technical-analysis-xloader-versions-6-and-7-part-1)

## Mitigations

- [M1040 - Behavior Prevention on Endpoint](../../../../Defenses/Mitigations/M1040%20-%20Behavior%20Prevention%20on%20Endpoint.md) — Some endpoint security solutions can be configured to block some types of process injection based on common sequences of behavior that occur during the injection process.

## Detection strategies

- [DET0100 - Behavioral Detection of Asynchronous Procedure Call (APC) Injection via Remote Thread Queuing](../../../../Defenses/Detection%20Strategies/DET0100%20-%20Behavioral%20Detection%20of%20Asynchronous%20Procedure%20Call%20%28APC%29%20Injection%20via%20Remote%20Thread.md)

## Sources

- [CyberBit Early Bird Apr 2018](https://www.cyberbit.com/blog/endpoint-security/new-early-bird-code-injection-technique-discovered/)
- [ENSIL AtomBombing Oct 2016](https://blog.ensilo.com/atombombing-brand-new-code-injection-for-windows)
- [Microsoft Atom Table](https://msdn.microsoft.com/library/windows/desktop/ms649053.aspx)
- [Microsoft APC](https://msdn.microsoft.com/library/windows/desktop/ms681951.aspx)
