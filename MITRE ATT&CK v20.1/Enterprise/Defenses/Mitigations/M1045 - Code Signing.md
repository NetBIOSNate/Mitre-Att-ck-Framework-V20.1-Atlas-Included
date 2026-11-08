# M1045 - Code Signing

[Enterprise](../../README.md) / [Mitigations](README.md)

Code Signing is a security process that ensures the authenticity and integrity of software by digitally signing executables, scripts, and other code artifacts. It prevents untrusted or malicious code from executing by verifying the digital signatures against trusted sources. Code signing protects against tampering, impersonation, and distribution of unauthorized or malicious software, forming a critical defense against supply chain and software exploitation attacks. This mitigation can be implemented through the following measures:

Enforce Signed Code Execution:

- Implementation: Configure operating systems (e.g., Windows with AppLocker or Linux with Secure Boot) to allow only signed code to execute.
- Use Case: Prevent the execution of malicious PowerShell scripts by requiring all scripts to be signed with a trusted certificate.

Vendor-Signed Driver Enforcement:

- Implementation: Enable kernel-mode code signing to ensure that only drivers signed by trusted vendors can be loaded.
- Use Case: A malicious driver attempting to modify system memory fails to load because it lacks a valid signature.

Certificate Revocation Management:

- Implementation: Use Online Certificate Status Protocol (OCSP) or Certificate Revocation Lists (CRLs) to block certificates associated with compromised or deprecated code.
- Use Case: A compromised certificate used to sign a malicious update is revoked, preventing further execution of the software.

Third-Party Software Verification:

- Implementation: Require software from external vendors to be signed with valid certificates before deployment.
- Use Case: An organization only deploys signed and verified third-party software to prevent supply chain attacks.

Script Integrity in CI/CD Pipelines:

- Implementation: Integrate code signing into CI/CD pipelines to sign and verify code artifacts before production release.
- Use Case: A software company ensures that all production builds are signed, preventing tampered builds from reaching customers.

**Key Components of Code Signing**

- Digital Signature Verification: Verifies the authenticity of code by ensuring it was signed by a trusted entity.
- Certificate Management: Uses Public Key Infrastructure (PKI) to manage signing certificates and revocation lists.
- Enforced Policy for Unsigned Code: Prevents the execution of unsigned or untrusted binaries and scripts.
- Hash Integrity Check: Confirms that code has not been altered since signing by comparing cryptographic hashes.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1045)

## Mitigated techniques

- [T1059.002 - AppleScript](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.002%20-%20AppleScript/README.md)
- [T1127.002 - ClickOnce](../../Tactics/04%20TA0002%20-%20Execution/T1127%20-%20Trusted%20Developer%20Utilities%20Proxy%20Execution/T1127.002%20-%20ClickOnce/README.md)
- [T1059 - Command and Scripting Interpreter](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/README.md)
- [T1554 - Compromise Host Software Binary](../../Tactics/05%20TA0003%20-%20Persistence/T1554%20-%20Compromise%20Host%20Software%20Binary/README.md)
- [T1543 - Create or Modify System Process](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/README.md)
- [T1601.002 - Downgrade System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.002%20-%20Downgrade%20System%20Image/README.md)
- [T1505.004 - IIS Components](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.004%20-%20IIS%20Components/README.md)
- [T1525 - Implant Internal Image](../../Tactics/05%20TA0003%20-%20Persistence/T1525%20-%20Implant%20Internal%20Image/README.md)
- [T1036.001 - Invalid Code Signature](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.001%20-%20Invalid%20Code%20Signature/README.md)
- [T1546.006 - LC_LOAD_DYLIB Addition](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.006%20-%20LC_LOAD_DYLIB%20Addition/README.md)
- [T1204.003 - Malicious Image](../../Tactics/04%20TA0002%20-%20Execution/T1204%20-%20User%20Execution/T1204.003%20-%20Malicious%20Image/README.md)
- [T1036 - Masquerading](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/README.md)
- [T1036.005 - Match Legitimate Resource Name or Location](../../Tactics/07%20TA0005%20-%20Stealth/T1036%20-%20Masquerading/T1036.005%20-%20Match%20Legitimate%20Resource%20Name%20or%20Location/README.md)
- [T1601 - Modify System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/README.md)
- [T1601.001 - Patch System Image](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1601%20-%20Modify%20System%20Image/T1601.001%20-%20Patch%20System%20Image/README.md)
- [T1059.001 - PowerShell](../../Tactics/04%20TA0002%20-%20Execution/T1059%20-%20Command%20and%20Scripting%20Interpreter/T1059.001%20-%20PowerShell/README.md)
- [T1546.013 - PowerShell Profile](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.013%20-%20PowerShell%20Profile/README.md)
- [T1505 - Server Software Component](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/README.md)
- [T1505.001 - SQL Stored Procedures](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.001%20-%20SQL%20Stored%20Procedures/README.md)
- [T1505.002 - Transport Agent](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.002%20-%20Transport%20Agent/README.md)
- [T1505.006 - vSphere Installation Bundles](../../Tactics/05%20TA0003%20-%20Persistence/T1505%20-%20Server%20Software%20Component/T1505.006%20-%20vSphere%20Installation%20Bundles/README.md)
- [T1543.003 - Windows Service](../../Tactics/05%20TA0003%20-%20Persistence/T1543%20-%20Create%20or%20Modify%20System%20Process/T1543.003%20-%20Windows%20Service/README.md)
