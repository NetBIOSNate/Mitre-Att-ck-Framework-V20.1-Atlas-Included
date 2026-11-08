# T1548.001 - Setuid and Setgid

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1548 - Abuse Elevation Control Mechanism](../README.md)

An adversary may abuse configurations where an application has the setuid or setgid bits set in order to get code running in a different (and possibly more privileged) user’s context. On Linux or macOS, when the setuid or setgid bits are set for an application binary, the application will run with the privileges of the owning user or group respectively.(Citation: setuid man page) Normally an application is run in the current user’s context, regardless of which user or group owns the application. However, there are instances where programs need to be executed in an elevated context to function properly, but the user running them may not have the specific required privileges.

Instead of creating an entry in the sudoers file, which must be done by root, any user can specify the setuid or setgid flag to be set for their own applications (i.e. [Linux and Mac Permissions](https://attack.mitre.org/techniques/T1222/002)). The <code>chmod</code> command can set these bits with bitmasking, <code>chmod 4777 [file]</code> or via shorthand naming, <code>chmod u+s [file]</code>. This will enable the setuid bit. To enable the setgid bit, <code>chmod 2775</code> and <code>chmod g+s</code> can be used.

Adversaries can use this mechanism on their own malware to make sure they're able to execute in elevated contexts in the future.(Citation: OSX Keydnap malware) This abuse is often part of a "shell escape" or other actions to bypass an execution environment with restricted permissions.

Alternatively, adversaries may choose to find and target vulnerable binaries with the setuid or setgid bits already enabled (i.e. [File and Directory Discovery](https://attack.mitre.org/techniques/T1083)). The setuid and setgid bits are indicated with an "s" instead of an "x" when viewing a file's attributes via <code>ls -l</code>. The <code>find</code> command can also be used to search for such files. For example, <code>find / -perm +4000 2>/dev/null</code> can be used to find files with setuid set and <code>find / -perm +2000 2>/dev/null</code> may be used for setgid. Binaries that have these bits set may then be abused by adversaries.(Citation: GTFOBins Suid)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1548/001)

**Tactics**  [Privilege Escalation](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1028 - Operating System Configuration](../../../../Defenses/Mitigations/M1028%20-%20Operating%20System%20Configuration.md) — Applications with known vulnerabilities or known shell escapes should not have the setuid or setgid bits set to reduce potential damage if an application is compromised. Additionally, the number of programs with setuid or setgid bits set should be minimized across a system.

## Procedure examples

- [S0401 - Exaramel for Linux](../../../../Threat%20Intelligence/Software/Malware/S0401%20-%20Exaramel%20for%20Linux.md) — [Exaramel for Linux](https://attack.mitre.org/software/S0401) can execute commands with high privileges via a specific binary with setuid functionality.(Citation: ANSSI Sandworm January 2021) [ANSSI Sandworm January 2021](https://www.cert.ssi.gouv.fr/uploads/CERTFR-2021-CTI-005.pdf)
- [S0276 - Keydnap](../../../../Threat%20Intelligence/Software/Malware/S0276%20-%20Keydnap.md) — [Keydnap](https://attack.mitre.org/software/S0276) adds the setuid flag to a binary so it can easily elevate in the future.(Citation: OSX Keydnap malware) [OSX Keydnap malware](https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/)

## Detection strategies

- [DET0110 - Setuid/Setgid Privilege Abuse Detection (Linux/macOS)](../../../../Defenses/Detection%20Strategies/DET0110%20-%20Setuid%20-%20Setgid%20Privilege%20Abuse%20Detection%20%28Linux%20-%20macOS%29.md)

## Sources

- [GTFOBins Suid](https://gtfobins.github.io/#+suid)
- [OSX Keydnap malware](https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/)
- [setuid man page](http://man7.org/linux/man-pages/man2/setuid.2.html)
