# T1595.003 - Wordlist Scanning

[Enterprise](../../../../README.md) / [Reconnaissance](../../README.md) / [T1595 - Active Scanning](../README.md)

Adversaries may iteratively probe infrastructure using brute-forcing and crawling techniques. While this technique employs similar methods to [Brute Force](https://attack.mitre.org/techniques/T1110), its goal is the identification of content and infrastructure rather than the discovery of valid credentials. Wordlists used in these scans may contain generic, commonly used names and file extensions or terms specific to a particular software. Adversaries may also create custom, target-specific wordlists using data gathered from other Reconnaissance techniques (ex: [Gather Victim Org Information](https://attack.mitre.org/techniques/T1591), or [Search Victim-Owned Websites](https://attack.mitre.org/techniques/T1594)).

For example, adversaries may use web content discovery tools such as Dirb, DirBuster, and GoBuster and generic or custom wordlists to enumerate a website’s pages and directories.(Citation: ClearSky Lebanese Cedar Jan 2021) This can help them to discover old, vulnerable pages or hidden administrative portals that could become the target of further operations (ex: [Exploit Public-Facing Application](https://attack.mitre.org/techniques/T1190) or [Brute Force](https://attack.mitre.org/techniques/T1110)).  

As cloud storage solutions typically use globally unique names, adversaries may also use target-specific wordlists and tools such as s3recon and GCPBucketBrute to enumerate public and private buckets on cloud infrastructure.(Citation: S3Recon GitHub)(Citation: GCPBucketBrute) Once storage objects are discovered, adversaries may leverage [Data from Cloud Storage](https://attack.mitre.org/techniques/T1530) to access valuable information that can be exfiltrated or used to escalate privileges and move laterally.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1595/003)

**Tactics**  [Reconnaissance](../../README.md)

**Platforms**  [PRE](../../../../Platforms/PRE.md)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Remove or disable access to any systems, resources, and infrastructure that are not explicitly required to be available externally.
- [M1056 - Pre-compromise](../../../../Defenses/Mitigations/M1056%20-%20Pre-compromise.md) — This technique cannot be easily mitigated with preventive controls since it is based on behaviors performed outside of the scope of enterprise defenses and controls. Efforts should focus on minimizing the amount and sensitivity of data available to external parties.

## Procedure examples

- [G0096 - APT41](../../../../Threat%20Intelligence/Groups/G0096%20-%20APT41.md) — [APT41](https://attack.mitre.org/groups/G0096) leverages various tools and frameworks to brute-force directories on web servers.(Citation: Rostovcev APT41 2021) [Rostovcev APT41 2021](https://www.group-ib.com/blog/apt41-world-tour-2021/)
- [G0123 - Volatile Cedar](../../../../Threat%20Intelligence/Groups/G0123%20-%20Volatile%20Cedar.md) — [Volatile Cedar](https://attack.mitre.org/groups/G0123) has used DirBuster and GoBuster to brute force web directories and DNS subdomains.(Citation: ClearSky Lebanese Cedar Jan 2021) [ClearSky Lebanese Cedar Jan 2021](https://www.clearskysec.com/wp-content/uploads/2021/01/Lebanese-Cedar-APT.pdf)

## Detection strategies

- [DET0868 - Detection of Wordlist Scanning](../../../../Defenses/Detection%20Strategies/DET0868%20-%20Detection%20of%20Wordlist%20Scanning.md)

## Sources

- [ClearSky Lebanese Cedar Jan 2021](https://www.clearskysec.com/wp-content/uploads/2021/01/Lebanese-Cedar-APT.pdf)
- [GCPBucketBrute](https://rhinosecuritylabs.com/gcp/google-cloud-platform-gcp-bucket-enumeration/)
- [S3Recon GitHub](https://github.com/clarketm/s3recon)
