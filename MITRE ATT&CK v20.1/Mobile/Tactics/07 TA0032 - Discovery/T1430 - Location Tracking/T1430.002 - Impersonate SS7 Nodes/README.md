# T1430.002 - Impersonate SS7 Nodes

[Mobile](../../../../README.md) / [Discovery](../../README.md) / [T1430 - Location Tracking](../README.md)

Adversaries may exploit the lack of authentication in signaling system network nodes to track the location of mobile devices by impersonating a node.(Citation: Engel-SS7)(Citation: Engel-SS7-2008)(Citation: 3GPP-Security)(Citation: Positive-SS7)(Citation: CSRIC5-WG10-FinalReport) 

 

By providing the victim’s MSISDN (phone number) and impersonating network internal nodes to query subscriber information from other nodes, adversaries may use data collected from each hop to eventually determine the device’s geographical cell area or nearest cell tower.(Citation: Engel-SS7)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1430/002)

**Tactics**  [Discovery](../../README.md), [Collection](../../../09%20TA0035%20-%20Collection/README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Mitigations

- [M1014 - Interconnection Filtering](../../../../Defenses/Mitigations/M1014%20-%20Interconnection%20Filtering.md) — Filtering requests by checking request origin information may provide some defense against spurious operators.(Citation: CSRIC-WG1-FinalReport)

## Procedure examples

- [S0602 - Circles](../../../../Threat%20Intelligence/Software/Malware/S0602%20-%20Circles.md) — [Circles](https://attack.mitre.org/software/S0602) can track the location of mobile devices.(Citation: CitizenLab Circles) [CitizenLab Circles](https://citizenlab.ca/2020/12/running-in-circles-uncovering-the-clients-of-cyberespionage-firm-circles/)

## Detection strategies

- [DET0662 - Detection of Impersonate SS7 Nodes](../../../../Defenses/Detection%20Strategies/DET0662%20-%20Detection%20of%20Impersonate%20SS7%20Nodes.md)

## Sources

- [3GPP-Security](http://www.3gpp.org/ftp/tsg_sa/wg3_security/_specs/33900-120.pdf)
- [CSRIC5-WG10-FinalReport](https://web.archive.org/web/20200330012714/https://www.fcc.gov/files/csric5-wg10-finalreport031517pdf)
- [Positive-SS7](https://www.ptsecurity.com/upload/ptcom/PT-SS7-AD-Data-Sheet-eng.pdf)
- [Engel-SS7-2008](https://www.youtube.com/watch?v=q0n5ySqbfdI)
- [Engel-SS7](https://berlin.ccc.de/~tobias/31c3-ss7-locate-track-manipulate.pdf)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/cellular-threats/CEL-38.html)
