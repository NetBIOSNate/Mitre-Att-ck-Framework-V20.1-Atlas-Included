# C0043 - Indian Critical Infrastructure Intrusions

[Enterprise](../../README.md) / [Campaigns](README.md)

[Indian Critical Infrastructure Intrusions](https://attack.mitre.org/campaigns/C0043) is a sequence of intrusions from 2021 through early 2022 linked to People’s Republic of China (PRC) threat actors, particularly [RedEcho](https://attack.mitre.org/groups/G1042) and Threat Activity Group 38 (TAG38). The intrusions appear focused on IT system breach in Indian electric utility entities and logistics firms, as well as potentially managed service providers operating within India. Although focused on OT-operating entities, there is no evidence this campaign was able to progress beyond IT breach and information gathering to OT environment access.(Citation: RecordedFuture RedEcho 2021)(Citation: RecordedFuture RedEcho 2022)

[MITRE ATT&CK record](https://attack.mitre.org/campaigns/C0043)

## Techniques used

- [T1573.002 - Asymmetric Cryptography](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1573%20-%20Encrypted%20Channel/T1573.002%20-%20Asymmetric%20Cryptography/README.md)
- [T1584 - Compromise Infrastructure](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1584%20-%20Compromise%20Infrastructure/README.md)
- [T1588.004 - Digital Certificates](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1588%20-%20Obtain%20Capabilities/T1588.004%20-%20Digital%20Certificates/README.md)
- [T1583.001 - Domains](../../Tactics/02%20TA0042%20-%20Resource%20Development/T1583%20-%20Acquire%20Infrastructure/T1583.001%20-%20Domains/README.md)
- [T1568 - Dynamic Resolution](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1568%20-%20Dynamic%20Resolution/README.md)
- [T1599 - Network Boundary Bridging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1599%20-%20Network%20Boundary%20Bridging/README.md)
- [T1571 - Non-Standard Port](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1571%20-%20Non-Standard%20Port/README.md)
- [T1071.001 - Web Protocols](../../Tactics/13%20TA0011%20-%20Command%20and%20Control/T1071%20-%20Application%20Layer%20Protocol/T1071.001%20-%20Web%20Protocols/README.md)

## Software used

- [S1144 - FRP](../Software/Tools/S1144%20-%20FRP.md)
- [S0596 - ShadowPad](../Software/Malware/S0596%20-%20ShadowPad.md)

## Sources

- [RecordedFuture RedEcho 2021](https://go.recordedfuture.com/hubfs/reports/cta-2021-0228.pdf)
- [RecordedFuture RedEcho 2022](https://go.recordedfuture.com/hubfs/reports/ta-2022-0406.pdf)
