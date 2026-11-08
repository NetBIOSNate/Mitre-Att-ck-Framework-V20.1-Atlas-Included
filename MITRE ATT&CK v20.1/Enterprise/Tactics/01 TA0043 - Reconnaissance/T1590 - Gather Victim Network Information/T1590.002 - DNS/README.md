# T1590.002 - DNS

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1590 - Gather Victim Network Information](../README.md)

Adversaries may gather information about the victim's DNS that can be used during targeting. DNS information may include a variety of details, including registered name servers as well as records that outline addressing for a target’s subdomains, mail servers, and other hosts. DNS MX, TXT, and SPF records may also reveal the use of third party cloud and SaaS providers, such as Office 365, G Suite, Salesforce, or Zendesk.(Citation: Sean Metcalf Twitter DNS Records)

Adversaries may gather this information in various ways, such as querying or otherwise collecting details via [DNS/Passive DNS](https://attack.mitre.org/techniques/T1596/001). DNS information may also be exposed to adversaries via online or other accessible data sets (ex: [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596)).(Citation: DNS Dumpster)(Citation: Circl Passive DNS) Gathering this information may reveal opportunities for other forms of reconnaissance (ex: [Search Open Technical Databases](https://attack.mitre.org/techniques/T1596), [Search Open Websites/Domains](https://attack.mitre.org/techniques/T1593), or [Active Scanning](https://attack.mitre.org/techniques/T1595)), establishing operational resources (ex: [Acquire Infrastructure](https://attack.mitre.org/techniques/T1583) or [Compromise Infrastructure](https://attack.mitre.org/techniques/T1584)), and/or initial access (ex: [External Remote Services](https://attack.mitre.org/techniques/T1133)).

Adversaries may also use DNS zone transfer (DNS query type AXFR) to collect all records from a misconfigured DNS server.(Citation: Trails-DNS)(Citation: DNS-CISA)(Citation: Alexa-dns)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1590/002)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1054 - Software Configuration](../../../../Defenses/Mitigations/M1054%20-%20Software%20Configuration.md) — Consider implementing policies for DNS servers, such as Zone Transfer Policies, that enforce a list of validated servers permitted for zone transfers.(Citation: DNS-msft) [DNS-msft](https://learn.microsoft.com/en-us/windows-server/networking/dns/deploy/dns-policies-overview)

## Detection strategies

- [DET0843 - Detection of DNS](../../../../Defenses/Detection%20Strategies/DET0843%20-%20Detection%20of%20DNS.md)

## Sources

- [Circl Passive DNS](https://www.circl.lu/services/passive-dns/)
- [DNS-CISA](https://www.cisa.gov/news-events/alerts/2015/04/13/dns-zone-transfer-axfr-requests-may-leak-domain-information)
- [DNS Dumpster](https://dnsdumpster.com/)
- [Alexa-dns](https://en.internetwache.org/scanning-alexas-top-1m-for-axfr-29-03-2015/)
- [Sean Metcalf Twitter DNS Records](https://x.com/PyroTek3/status/1126487227712921600)
- [Trails-DNS](https://web.archive.org/web/20180615055527/https://securitytrails.com/blog/russian-tlds)
