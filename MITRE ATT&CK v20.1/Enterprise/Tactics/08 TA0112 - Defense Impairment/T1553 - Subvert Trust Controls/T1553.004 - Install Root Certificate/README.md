# T1553.004 - Install Root Certificate

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1553 - Subvert Trust Controls](../README.md)

Adversaries may install a root certificate on a compromised system to avoid warnings when connecting to adversary controlled web servers. Root certificates are used in public key cryptography to identify a root certificate authority (CA). When a root certificate is installed, the system or application will trust certificates in the root's chain of trust that have been signed by the root certificate.(Citation: Wikipedia Root Certificate) Certificates are commonly used for establishing secure TLS/SSL communications within a web browser. When a user attempts to browse a website that presents a certificate that is not trusted an error message will be displayed to warn the user of the security risk. Depending on the security settings, the browser may not allow the user to establish a connection to the website.

Installation of a root certificate on a compromised system would give an adversary a way to degrade the security of that system. Adversaries have used this technique to avoid security warnings prompting users when compromised systems connect over HTTPS to adversary controlled web servers that spoof legitimate websites in order to collect login credentials.(Citation: Operation Emmental)

Atypical root certificates have also been pre-installed on systems by the manufacturer or in the software supply chain and were used in conjunction with malware/adware to provide [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) capability for intercepting information transmitted over secure TLS/SSL communications.(Citation: Kaspersky Superfish)

Root certificates (and their associated chains) can also be cloned and reinstalled. Cloned certificate chains will carry many of the same metadata characteristics of the source and can be used to sign malicious code that may then bypass signature validation tools (ex: Sysinternals, antivirus, etc.) used to block execution and/or uncover artifacts of Persistence.(Citation: SpectorOps Code Signing Dec 2017)

In macOS, the Ay MaMi malware uses <code>/usr/bin/security add-trusted-cert -d -r trustRoot -k /Library/Keychains/System.keychain /path/to/malicious/cert</code> to install a malicious certificate as a trusted root certificate into the system keychain.(Citation: objective-see ay mami 2018)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1553/004)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Windows Group Policy can be used to manage root certificates and the <code>Flags</code> value of <code>HKLM\\SOFTWARE\\Policies\\Microsoft\\SystemCertificates\\Root\\ProtectedRoots</code> can be set to 1 to prevent non-administrator users from making further root installations into their own HKCU certificate store. (Citation: SpectorOps Code Signing Dec 2017) [SpectorOps Code Signing Dec 2017](https://posts.specterops.io/code-signing-certificate-cloning-attacks-and-defenses-6f98657fc6ec)
- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — HTTP Public Key Pinning (HPKP) is one method to mitigate potential [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) situations where and adversary uses a mis-issued or fraudulent certificate to intercept encrypted communications by enforcing use of an expected certificate. (Citation: Wikipedia HPKP) [Wikipedia HPKP](https://en.wikipedia.org/wiki/HTTP_Public_Key_Pinning)

## Procedure examples

- [S0160 - certutil](../../../../Threat%20Intelligence/Software/Tools/S0160%20-%20certutil.md) — [certutil](https://attack.mitre.org/software/S0160) can be used to install browser root certificates as a precursor to performing [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) between connections to banking websites. Example command: <code>certutil -addstore -f -user ROOT ProgramData\cert512121.der</code>.(Citation: Palo Alto Retefe) [Palo Alto Retefe](https://researchcenter.paloaltonetworks.com/2015/08/retefe-banking-trojan-targets-sweden-switzerland-and-japan/)
- [S0281 - Dok](../../../../Threat%20Intelligence/Software/Malware/S0281%20-%20Dok.md) — [Dok](https://attack.mitre.org/software/S0281) installs a root certificate to aid in [Adversary-in-the-Middle](https://attack.mitre.org/techniques/T1557) actions using the command <code>add-trusted-cert -d -r trustRoot -k /Library/Keychains/System.keychain /tmp/filename</code>.(Citation: objsee mac malware 2017)(Citation: hexed osx.dok analysis 2019) [hexed osx.dok analysis 2019](https://web.archive.org/web/20221007144948/http://www.hexed.in/2019/07/osxdok-analysis.html) · [objsee mac malware 2017](https://objective-see.com/blog/blog_0x25.html)
- [S9003 - evilginx2](../../../../Threat%20Intelligence/Software/Tools/S9003%20-%20evilginx2.md) — [evilginx2](https://attack.mitre.org/software/S9003) has obtained a valid SSL/TLS certificate from LetsEncrypt to provide responses to Automatic Certificate Management Environment (ACME) challenges.(Citation: Evilginx 2 July 2018) [Evilginx 2 July 2018](https://breakdev.org/evilginx-2-next-generation-of-phishing-2fa-tokens/)
- [S0009 - Hikit](../../../../Threat%20Intelligence/Software/Malware/S0009%20-%20Hikit.md) — [Hikit](https://attack.mitre.org/software/S0009) installs a self-generated certificate to the local trust store as a root CA and Trusted Publisher.(Citation: Sood and Enbody) [Sood and Enbody](https://www.techtarget.com/searchsecurity/feature/Targeted-Cyber-Attacks)
- [S0148 - RTM](../../../../Threat%20Intelligence/Software/Malware/S0148%20-%20RTM.md) — [RTM](https://attack.mitre.org/software/S0148) can add a certificate to the Windows store.(Citation: ESET RTM Feb 2017)(Citation: Unit42 Redaman January 2019) [ESET RTM Feb 2017](https://www.welivesecurity.com/wp-content/uploads/2017/02/Read-The-Manual.pdf) · [Unit42 Redaman January 2019](https://unit42.paloaltonetworks.com/russian-language-malspam-pushing-redaman-banking-malware/)

## Detection strategies

- [DET0056 - Detection Strategy for Subvert Trust Controls via Install Root Certificate.](../../../../Defenses/Detection%20Strategies/DET0056%20-%20Detection%20Strategy%20for%20Subvert%20Trust%20Controls%20via%20Install%20Root%20Certificate.md)

## Sources

- [Operation Emmental](https://www.youtube.com/watch?v=gchKFumYHWc)
- [SpectorOps Code Signing Dec 2017](https://posts.specterops.io/code-signing-certificate-cloning-attacks-and-defenses-6f98657fc6ec)
- [Kaspersky Superfish](https://www.kaspersky.com/blog/lenovo-pc-with-adware-superfish-preinstalled/7712/)
- [objective-see ay mami 2018](https://objective-see.com/blog/blog_0x26.html)
- [Wikipedia Root Certificate](https://en.wikipedia.org/wiki/Root_certificate)
