# T1558.005 - Ccache Files

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1558 - Steal or Forge Kerberos Tickets](../README.md)

Adversaries may attempt to steal Kerberos tickets stored in credential cache files (or ccache). These files are used for short term storage of a user's active session credentials. The ccache file is created upon user authentication and allows for access to multiple services without the user having to re-enter credentials. 

The <code>/etc/krb5.conf</code> configuration file and the <code>KRB5CCNAME</code> environment variable are used to set the storage location for ccache entries. On Linux, credentials are typically stored in the `/tmp` directory with a naming format of `krb5cc_%UID%` or `krb5.ccache`. On macOS, ccache entries are stored by default in memory with an `API:{uuid}` naming scheme. Typically, users interact with ticket storage using <code>kinit</code>, which obtains a Ticket-Granting-Ticket (TGT) for the principal; <code>klist</code>, which lists obtained tickets currently held in the credentials cache; and other built-in binaries.(Citation: Kerberos GNU/Linux)(Citation: Binary Defense Kerberos Linux)

Adversaries can collect tickets from ccache files stored on disk and authenticate as the current user without their password to perform [Pass the Ticket](https://attack.mitre.org/techniques/T1550/003) attacks. Adversaries can also use these tickets to impersonate legitimate users with elevated privileges to perform [Privilege Escalation](https://attack.mitre.org/tactics/TA0004). Tools like Kekeo can also be used by adversaries to convert ccache files to Windows format for further [Lateral Movement](https://attack.mitre.org/tactics/TA0008). On macOS, adversaries may use open-source tools or the Kerberos framework to interact with ccache files and extract TGTs or Service Tickets via lower-level APIs.(Citation: SpectorOps Bifrost Kerberos macOS 2019)(Citation: Linux Kerberos Tickets)(Citation: Brining MimiKatz to Unix)(Citation: Kekeo)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1558/005)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0024 - Detect Kerberos Ccache File Theft or Abuse (T1558.005)](../../../../Defenses/Detection%20Strategies/DET0024%20-%20Detect%20Kerberos%20Ccache%20File%20Theft%20or%20Abuse%20%28T1558.005%29.md)

## Procedure examples

- [S0357 - Impacket](../../../../Threat%20Intelligence/Software/Tools/S0357%20-%20Impacket.md) — [Impacket](https://attack.mitre.org/software/S0357) tools – such as <code>getST.py</code> or <code>ticketer.py</code> – can be used to steal or forge Kerberos tickets using ccache files given a password, hash, aesKey, or TGT.(Citation: Kerberos GNU/Linux)(Citation: on security kerberos linux) [Kerberos GNU/Linux](https://adepts.of0x.cc/kerberos-thievery-linux/) · [on security kerberos linux](https://www.onsecurity.io/blog/abusing-kerberos-from-linux/)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Enable and perform audits or scans of systems, permissions, insecure software, insecure configurations, etc. to identify potential weaknesses.(Citation: Brining MimiKatz to Unix) For example, use <code>auditd</code> to audit access to hashes, machine tickets, or <code>/tmp</code> files. If using sssd and Vintela, ensure kerberos is disabled if not being used.(Citation: audits linikatz) [Brining MimiKatz to Unix](https://labs.portcullis.co.uk/download/eu-18-Wadhwa-Brown-Where-2-worlds-collide-Bringing-Mimikatz-et-al-to-UNIX.pdf) · [audits linikatz](https://github.com/CiscoCXSecurity/linikatz/blob/master/blue/audit/audit.rules)
- [M1043 - Credential Access Protection](../../../../Defenses/Mitigations/M1043%20-%20Credential%20Access%20Protection.md) — Protect resources with Security Enhanced Linux (SELinux) by defining entry points, process types, and file labels.(Citation: Brining MimiKatz to Unix) [Brining MimiKatz to Unix](https://labs.portcullis.co.uk/download/eu-18-Wadhwa-Brown-Where-2-worlds-collide-Bringing-Mimikatz-et-al-to-UNIX.pdf)

## Sources

- [Binary Defense Kerberos Linux](https://www.binarydefense.com/resources/blog/shining-a-light-in-the-dark-how-binary-defense-uncovered-an-apt-lurking-in-shadows-of-it/)
- [Kerberos GNU/Linux](https://adepts.of0x.cc/kerberos-thievery-linux/)
- [Kekeo](https://github.com/gentilkiwi/kekeo)
- [SpectorOps Bifrost Kerberos macOS 2019](https://posts.specterops.io/when-kirbi-walks-the-bifrost-4c727807744f)
- [Brining MimiKatz to Unix](https://labs.portcullis.co.uk/download/eu-18-Wadhwa-Brown-Where-2-worlds-collide-Bringing-Mimikatz-et-al-to-UNIX.pdf)
- [Linux Kerberos Tickets](https://www.fireeye.com/blog/threat-research/2020/04/kerberos-tickets-on-linux-red-teams.html)
