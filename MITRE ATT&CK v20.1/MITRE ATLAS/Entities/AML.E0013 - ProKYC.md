# AML.E0013 - ProKYC

[MITRE ATLAS](../README.md) / [Entities](README.md)

[ProKYC](AML.E0013%20-%20ProKYC.md) is a threat actor selling a subscription-based tool designed to bypass remote identity-verification controls. Cato CTRL, the threat-research team at [Cato Networks](AML.E0016%20-%20Cato%20Networks.md), identified the seller marketing capabilities for creating fraudulent accounts on cryptocurrency exchanges and other financial platforms. Their offering combines fabricated identity documents with synthetic facial video intended to circumvent identity-document verification, facial matching, and liveness checks. [cato](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)

The advertised workflow generates a synthetic identity, places the selected face on a fabricated identity document, and produces matching facial video. Reporting also describes using a virtual webcam to present the synthetic video to the verification system. The seller showed these capabilities against the Bybit cryptocurrency exchange. By packaging these functions as a subscription service, ProKYC lowers the technical barrier to account-creation fraud that can facilitate money laundering and mule-account activity. [cato](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/) [service-analysis](https://idscan.net/blog/prokyc-synthetic-identity-fraud/)

**Entity type**  Activity Cluster

## Uses

- [AML.S0012 - ProKYC](../Software/Tools/AML.S0012%20-%20ProKYC.md) — [ProKYC](AML.E0013%20-%20ProKYC.md) used the [ProKYC](../Software/Tools/AML.S0012%20-%20ProKYC.md) tool to create fabricated identity documents and matching synthetic facial video intended to bypass remote identity verification checks. [cato](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)

## Attributed case studies

- [AML.CS0034 - ProKYC: Deepfake Tool for Account Fraud Attacks](../Case%20Studies/Incidents/AML.CS0034%20-%20ProKYC%20-%20Deepfake%20Tool%20for%20Account%20Fraud%20Attacks.md) (Adversarial Operation)

## References

- [IDScan: ProKYC synthetic identity fraud as a service](https://idscan.net/blog/prokyc-synthetic-identity-fraud/)
- [Cato CTRL Threat Research: ProKYC - Deepfake Tool for Account Fraud Attacks](https://www.catonetworks.com/blog/prokyc-selling-deepfake-tool-for-account-fraud-attacks/)

[Official ATLAS record](https://atlas.mitre.org/entities/AML.E0013)
