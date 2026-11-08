# T1694.002 - Hardcoded Credentials

[ICS](../../../../README.md) / [Persistence](../../README.md) / [T1694 - Insecure Credentials](../README.md)

Adversaries may leverage credentials that are hardcoded in software or firmware to gain an unauthorized interactive user session to an asset. Examples credentials that may be hardcoded in an asset include:

* Username/Passwords
* Cryptographic keys/Certificates
* API tokens

Unlike [Default Credentials](https://attack.mitre.org/techniques/T0812), these credentials are built into the system in a way that they either cannot be changed by the asset owner, or may be infeasible to change because of the impact it would cause to the control system operation. These credentials may be reused across whole product lines or device models and are often not published or known to the owner and operators of the asset.(Citation: ICS-ALERT-13-164-01)(Citation: OT IceFall)

Adversaries may utilize these hardcoded credentials to move throughout the control system environment or provide reliable access for their tools to interact with industrial assets.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1694/002)

**Tactics**  [Persistence](../../README.md), [Lateral Movement](../../../07%20TA0109%20-%20Lateral%20Movement/README.md)

**Platforms**  [Embedded](../../../../Platforms/Embedded.md)

## Procedure examples

- [S1045 - INCONTROLLER](../../../../Threat%20Intelligence/Software/Malware/S1045%20-%20INCONTROLLER.md) — [INCONTROLLER](https://attack.mitre.org/software/S1045) can login to Omron PLCs using hardcoded credentials, which is documented in CVE-2022-34151.(Citation: Wylie-22) [Wylie-22](https://media.defcon.org/DEF%20CON%2030/DEF%20CON%2030%20presentations/Jimmy%20Wylie%20-%20Analyzing%20PIPEDREAM%20Challenges%20in%20testing%20an%20ICS%20attack%20toolkit.pdf)
- [S0603 - Stuxnet](../../../../Threat%20Intelligence/Software/Malware/S0603%20-%20Stuxnet.md) — [Stuxnet](https://attack.mitre.org/software/S0603) uses a hardcoded password in the WinCC software's database server as one of the mechanisms used to propagate to nearby systems. (Citation: Nicolas Falliere, Liam O Murchu, Eric Chien February 2011) [Nicolas Falliere, Liam O Murchu, Eric Chien February 2011](https://docs.broadcom.com/doc/security-response-w32-stuxnet-dossier-11-en)

## Mitigations

- [M0801 - Access Management](../../../../Defenses/Mitigations/M0801%20-%20Access%20Management.md) — Ensure embedded controls and network devices are protected through access management, as these devices often have unknown hardcoded accounts which could be used to gain unauthorized access.

## Detection strategies

- [DET0798 - Detection of Hardcoded Credentials](../../../../Defenses/Detection%20Strategies/DET0798%20-%20Detection%20of%20Hardcoded%20Credentials.md)

## Targeted assets

- [A0013 - Field I/O](../../../../Defenses/Assets/A0013%20-%20Field%20I%20-%20O.md)

## Sources

- [ICS-ALERT-13-164-01](https://www.cisa.gov/news-events/ics-alerts/ics-alert-13-164-01)
- [OT IceFall](https://www.forescout.com/resources/ot-icefall-report/)
