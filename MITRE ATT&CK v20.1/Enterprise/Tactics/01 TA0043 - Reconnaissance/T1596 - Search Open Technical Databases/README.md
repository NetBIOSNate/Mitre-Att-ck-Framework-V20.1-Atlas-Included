# T1596 - Search Open Technical Databases

[Enterprise](../../../README.md) / [Reconnaissance](../README.md)

Adversaries may search freely available technical databases for information about victims that can be used during targeting. Information about victims may be available in online databases and repositories, such as registrations of domains/certificates as well as public collections of network data/artifacts gathered from traffic and/or scans.(Citation: WHOIS)(Citation: DNS Dumpster)(Citation: Circl Passive DNS)(Citation: Medium SSL Cert)(Citation: SSLShopper Lookup)(Citation: DigitalShadows CDN)(Citation: Shodan)

Adversaries may search in different open databases depending on what information they seek to gather. Information from these sources may reveal opportunities for other forms of reconnaissance (ex: [Phishing for Information](https://attack.mitre.org/techniques/T1598) or [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593)), establishing operational resources (ex: [Acquire Infrastructure](https://attack.mitre.org/techniques/T1583) or [Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133) or [Trusted Relationship](https://attack.mitre.org/techniques/T1199)).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1596)

**Tactics**  [Reconnaissance](../README.md)

**Platforms**  [PRE](../../../Platforms/PRE.md)

## Sub-techniques

- [T1596.004 - CDNs](T1596.004%20-%20CDNs/README.md)
- [T1596.003 - Digital Certificates](T1596.003%20-%20Digital%20Certificates/README.md)
- [T1596.001 - DNS/Passive DNS](T1596.001%20-%20DNS%20-%20Passive%20DNS/README.md)
- [T1596.005 - Scan Databases](T1596.005%20-%20Scan%20Databases/README.md)
- [T1596.002 - WHOIS](T1596.002%20-%20WHOIS/README.md)

## Procedure examples

- [G0007 - APT28](../../../Threat%20Intelligence/Groups/G0007%20-%20APT28.md) — [APT28](https://attack.mitre.org/groups/G0007) has used large language models (LLMs) to assist in script development and deployment.(Citation: MSFT-AI)(Citation: OpenAI-CTI) [MSFT-AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/) · [OpenAI-CTI](https://openai.com/index/disrupting-malicious-uses-of-ai-by-state-affiliated-threat-actors/)
- [G0094 - Kimsuky](../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used LLMs to better understand publicly reported vulnerabilities.(Citation: MSFT-AI)(Citation: OpenAI-CTI) [MSFT-AI](https://www.microsoft.com/en-us/security/blog/2024/02/14/staying-ahead-of-threat-actors-in-the-age-of-ai/) · [OpenAI-CTI](https://openai.com/index/disrupting-malicious-uses-of-ai-by-state-affiliated-threat-actors/)

## Mitigations

- [M1056 - Pre-compromise](../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Detection strategies

- [DET0860 - Detection of Search Open Technical Databases](../../../Defenses/Detection%20Strategies/DET0860%20-%20Detection%20of%20Search%20Open%20Technical%20Databases.md)

## Sources

- [Circl Passive DNS](https://www.circl.lu/services/passive-dns/)
- [DNS Dumpster](https://dnsdumpster.com/)
- [Medium SSL Cert](https://medium.com/@menakajain/export-download-ssl-certificate-from-server-site-url-bcfc41ea46a2)
- [WHOIS](https://who.is/)
- [Shodan](https://shodan.io)
- [SSLShopper Lookup](https://www.sslshopper.com/ssl-checker.html)
- [DigitalShadows CDN](https://www.digitalshadows.com/blog-and-research/content-delivery-networks-cdns-can-leave-you-exposed-how-you-might-be-affected-and-what-you-can-do-about-it/)
