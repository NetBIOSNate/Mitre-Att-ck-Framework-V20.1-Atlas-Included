# M1060 - Out-of-Band Communications Channel

[Enterprise](../../README.md) / [Mitigations](README.md)

Establish secure out-of-band communication channels to ensure the continuity of critical communications during security incidents, data integrity attacks, or in-network communication failures. Out-of-band communication refers to using an alternative, separate communication path that is not dependent on the potentially compromised primary network infrastructure. This method can include secure messaging apps, encrypted phone lines, satellite communications, or dedicated emergency communication systems. Leveraging these alternative channels reduces the risk of adversaries intercepting, disrupting, or tampering with sensitive communications and helps coordinate an effective incident response.(Citation: TrustedSec OOB Communications)(Citation: NIST Special Publication 800-53 Revision 5)

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1060)

## Mitigated techniques

- [T1213 - Data from Information Repositories](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/README.md)
- [T1114 - Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/README.md)
- [T1114.003 - Email Forwarding Rule](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.003%20-%20Email%20Forwarding%20Rule/README.md)
- [T1114.001 - Local Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.001%20-%20Local%20Email%20Collection/README.md)
- [T1213.005 - Messaging Applications](../../Tactics/12%20TA0009%20-%20Collection/T1213%20-%20Data%20from%20Information%20Repositories/T1213.005%20-%20Messaging%20Applications/README.md)
- [T1114.002 - Remote Email Collection](../../Tactics/12%20TA0009%20-%20Collection/T1114%20-%20Email%20Collection/T1114.002%20-%20Remote%20Email%20Collection/README.md)
- [T1489 - Service Stop](../../Tactics/15%20TA0040%20-%20Impact/T1489%20-%20Service%20Stop/README.md)

## Sources

- [NIST Special Publication 800-53 Revision 5](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf)
- [TrustedSec OOB Communications](https://trustedsec.com/blog/to-oob-or-not-to-oob-why-out-of-band-communications-are-essential-for-incident-response)
