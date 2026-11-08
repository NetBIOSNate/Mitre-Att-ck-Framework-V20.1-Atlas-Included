# T1608 - Stage Capabilities

[Enterprise](../../../README.md) / [Resource Development](../README.md)

Adversaries may upload, install, or otherwise set up capabilities that can be used during targeting. To support their operations, an adversary may need to take capabilities they developed ([Develop Capabilities](https://attack.mitre.org/techniques/T1587)) or obtained ([Obtain Capabilities](https://attack.mitre.org/techniques/T1588)) and stage them on infrastructure under their control. These capabilities may be staged on infrastructure that was previously purchased/rented by the adversary ([Acquire Infrastructure](https://attack.mitre.org/techniques/T1583)) or was otherwise compromised by them ([Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)). Capabilities may also be staged on web services, such as GitHub or Pastebin, or on Platform-as-a-Service (PaaS) offerings that enable users to easily provision applications.(Citation: Volexity Ocean Lotus November 2020)(Citation: Dragos Heroku Watering Hole)(Citation: Malwarebytes Heroku Skimmers)(Citation: Netskope GCP Redirection)(Citation: Netskope Cloud Phishing)

Staging of capabilities can aid the adversary in a number of initial access and post-compromise behaviors, including (but not limited to):

* Staging web resources necessary to conduct [Drive-by Compromise](https://attack.mitre.org/techniques/T1189) when a user browses to a site.(Citation: FireEye CFR Watering Hole 2012)(Citation: Gallagher 2015)(Citation: ATT ScanBox)
* Staging web resources for a link target to be used with spearphishing.(Citation: Malwarebytes Silent Librarian October 2020)(Citation: Proofpoint TA407 September 2019)
* Uploading malware or tools to a location accessible to a victim network to enable [Ingress Tool Transfer](https://attack.mitre.org/techniques/T1105).(Citation: Volexity Ocean Lotus November 2020)
* Installing a previously acquired SSL/TLS certificate to use to encrypt command and control traffic (ex: [Asymmetric Cryptography](https://attack.mitre.org/techniques/T1573/002) with [Web Protocols](https://attack.mitre.org/techniques/T1071/001)).(Citation: DigiCert Install SSL Cert)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1608)

**Tactics**  [Resource Development](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1608.007 - AI Result Poisoning](T1608.007%20-%20AI%20Result%20Poisoning/README.md)
- [T1608.004 - Drive-by Target](T1608.004%20-%20Drive-by%20Target/README.md)
- [T1608.003 - Install Digital Certificate](T1608.003%20-%20Install%20Digital%20Certificate/README.md)
- [T1608.005 - Link Target](T1608.005%20-%20Link%20Target/README.md)
- [T1608.006 - SEO Poisoning](T1608.006%20-%20SEO%20Poisoning/README.md)
- [T1608.001 - Upload Malware](T1608.001%20-%20Upload%20Malware/README.md)
- [T1608.002 - Upload Tool](T1608.002%20-%20Upload%20Tool/README.md)

## Procedure examples

- [G0129 - Mustang Panda](../../../Threat%20Intelligence/Groups/G0129%20-%20Mustang%20Panda.md) — [Mustang Panda](https://attack.mitre.org/groups/G0129) has used servers under their control to validate tracking pixels sent to phishing victims.(Citation: Proofpoint TA416 Europe March 2022) [Proofpoint TA416 Europe March 2022](https://www.proofpoint.com/us/blog/threat-insight/good-bad-and-web-bug-ta416-increases-operational-tempo-against-european)

## Detection strategies

- [DET0839 - Detection of Stage Capabilities](../../../Defenses/Detection%20Strategies/DET0839%20-%20Detection%20of%20Stage%20Capabilities.md)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls.

## Sources

- [Volexity Ocean Lotus November 2020](https://www.volexity.com/blog/2020/11/06/oceanlotus-extending-cyber-espionage-operations-through-fake-websites/)
- [Netskope GCP Redirection](https://www.netskope.com/blog/targeted-attacks-abusing-google-cloud-platform-open-redirection)
- [Netskope Cloud Phishing](https://www.netskope.com/blog/a-big-catch-cloud-phishing-from-google-app-engine-and-azure-app-service)
- [ATT ScanBox](https://cybersecurity.att.com/blogs/labs-research/scanbox-a-reconnaissance-framework-used-on-watering-hole-attacks)
- [DigiCert Install SSL Cert](https://www.digicert.com/kb/ssl-certificate-installation.htm)
- [Gallagher 2015](http://arstechnica.com/security/2015/08/newly-discovered-chinese-hacking-group-hacked-100-websites-to-use-as-watering-holes/)
- [Malwarebytes Heroku Skimmers](https://www.malwarebytes.com/blog/news/2019/12/theres-an-app-for-that-web-skimmers-found-on-paas-heroku)
- [Dragos Heroku Watering Hole](https://www.dragos.com/blog/industry-news/a-new-water-watering-hole/)
- [FireEye CFR Watering Hole 2012](https://web.archive.org/web/20201024230407/https://www.fireeye.com/blog/threat-research/2012/12/council-foreign-relations-water-hole-attack-details.html)
- [Malwarebytes Silent Librarian October 2020](https://blog.malwarebytes.com/malwarebytes-news/2020/10/silent-librarian-apt-phishing-attack/)
- [Proofpoint TA407 September 2019](https://www.proofpoint.com/us/threat-insight/post/threat-actor-profile-ta407-silent-librarian)
