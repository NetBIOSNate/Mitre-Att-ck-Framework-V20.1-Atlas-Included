# T1559.003 - XPC Services

[Enterprise](../../../../README.md) / [Execution](../../README.md) / [T1559 - Inter-Process Communication](../README.md)

Adversaries can provide malicious content to an XPC service daemon for local code execution. macOS uses XPC services for basic inter-process communication between various processes, such as between the XPC Service daemon and third-party application privileged helper tools. Applications can send messages to the XPC Service daemon, which runs as root, using the low-level XPC Service <code>C API</code> or the high level <code>NSXPCConnection API</code> in order to handle tasks that require elevated privileges (such as network connections). Applications are responsible for providing the protocol definition which serves as a blueprint of the XPC services. Developers typically use XPC Services to provide applications stability and privilege separation between the application client and the daemon.(Citation: creatingXPCservices)(Citation: Designing Daemons Apple Dev)

Adversaries can abuse XPC services to execute malicious content. Requests for malicious execution can be passed through the application's XPC Services handler.(Citation: CVMServer Vuln)(Citation: Learn XPC Exploitation) This may also include identifying and abusing improper XPC client validation and/or poor sanitization of input parameters to conduct [Exploitation for Privilege Escalation](https://attack.mitre.org/techniques/T1068).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1559/003)

**Tactics**  [Execution](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0335 - Detect Abuse of XPC Services (T1559.003)](../../../../Defenses/Detection%20Strategies/DET0335%20-%20Detect%20Abuse%20of%20XPC%20Services%20%28T1559.003%29.md)

## Mitigations

- [M1013 - Application Developer Guidance](../../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Enable the Hardened Runtime capability when developing applications. Do not include the <code>com.apple.security.get-task-allow</code> entitlement with the value set to any variation of true.

## Sources

- [creatingXPCservices](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/CreatingXPCServices.html#//apple_ref/doc/uid/10000172i-SW6-SW1)
- [Designing Daemons Apple Dev](https://developer.apple.com/library/archive/documentation/MacOSX/Conceptual/BPSystemStartup/Chapters/DesigningDaemons.html)
- [CVMServer Vuln](https://www.trendmicro.com/en_us/research/21/f/CVE-2021-30724_CVMServer_Vulnerability_in_macOS_and_iOS.html)
- [Learn XPC Exploitation](https://wojciechregula.blog/post/learn-xpc-exploitation-part-3-code-injections/)
