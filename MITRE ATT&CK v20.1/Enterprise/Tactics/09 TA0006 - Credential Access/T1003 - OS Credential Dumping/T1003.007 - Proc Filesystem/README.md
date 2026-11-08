# T1003.007 - Proc Filesystem

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1003 - OS Credential Dumping](../README.md)

Adversaries may gather credentials from the proc filesystem or `/proc`. The proc filesystem is a pseudo-filesystem used as an interface to kernel data structures for Linux based systems managing virtual memory. For each process, the `/proc/<PID>/maps` file shows how memory is mapped within the process’s virtual address space. And `/proc/<PID>/mem`, exposed for debugging purposes, provides access to the process’s virtual address space.(Citation: Picus Labs Proc cump 2022)(Citation: baeldung Linux proc map 2022)

When executing with root privileges, adversaries can search these memory locations for all processes on a system that contain patterns indicative of credentials. Adversaries may use regex patterns, such as <code>grep -E "^[0-9a-f-]* r" /proc/"$pid"/maps | cut -d' ' -f 1</code>, to look for fixed strings in memory structures or cached hashes.(Citation: atomic-red proc file system) When running without privileged access, processes can still view their own virtual memory locations. Some services or programs may save credentials in clear text inside the process’s memory.(Citation: MimiPenguin GitHub May 2017)(Citation: Polop Linux PrivEsc Gitbook)

If running as or with the permissions of a web browser, a process can search the `/maps` & `/mem` locations for common website credential patterns (that can also be used to find adjacent memory within the same structure) in which hashes or cleartext credentials may be located.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1003/007)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Procedure examples

- [S0349 - LaZagne](../../../../Threat%20Intelligence/Software/Tools/S0349%20-%20LaZagne.md) — [LaZagne](https://attack.mitre.org/software/S0349) can use the `<PID>/maps` and `<PID>/mem` files to identify regex patterns to dump cleartext passwords from the browser's process memory.(Citation: GitHub LaZagne Dec 2018)(Citation: Picus Labs Proc cump 2022) [Picus Labs Proc cump 2022](https://www.picussecurity.com/resource/the-mitre-attck-t1003-os-credential-dumping-technique-and-its-adversary-use) · [GitHub LaZagne Dec 2018](https://github.com/AlessandroZ/LaZagne)
- [S0179 - MimiPenguin](../../../../Threat%20Intelligence/Software/Tools/S0179%20-%20MimiPenguin.md) — [MimiPenguin](https://attack.mitre.org/software/S0179) can use the `<PID>/maps` and `<PID>/mem` file to search for regex patterns and dump the process memory.(Citation: MimiPenguin GitHub May 2017)(Citation: Picus Labs Proc cump 2022) [MimiPenguin GitHub May 2017](https://github.com/huntergregal/mimipenguin) · [Picus Labs Proc cump 2022](https://www.picussecurity.com/resource/the-mitre-attck-t1003-os-credential-dumping-technique-and-its-adversary-use)
- [S9043 - Mini Shai-Hulud](../../../../Threat%20Intelligence/Software/Malware/S9043%20-%20Mini%20Shai-Hulud.md) — [Mini Shai-Hulud](https://attack.mitre.org/software/S9043) has scraped runner process memory to extract short-lived identity tokens, which it then exchanged for per-package npm trusted-publisher tokens.(Citation: Flashpoint Mini Shai-Hulud MAY 2026) [Flashpoint Mini Shai-Hulud MAY 2026](https://flashpoint.io/blog/mini-shai-hulud-worm-new-era-ci-cd-exploitation/)
- [S1109 - PACEMAKER](../../../../Threat%20Intelligence/Software/Malware/S1109%20-%20PACEMAKER.md) — [PACEMAKER](https://attack.mitre.org/software/S1109) has the ability to extract credentials from OS memory.(Citation: Mandiant Pulse Secure Zero-Day April 2021) [Mandiant Pulse Secure Zero-Day April 2021](https://www.mandiant.com/resources/blog/suspected-apt-actors-leverage-bypass-techniques-pulse-secure-zero-day)
- [S9041 - TeamPCP Cloud Stealer](../../../../Threat%20Intelligence/Software/Malware/S9041%20-%20TeamPCP%20Cloud%20Stealer.md) — [TeamPCP Cloud Stealer](https://attack.mitre.org/software/S9041) can scrape memory from the Runner.Worker process by reading `/proc/<pid>/mem` to extract secrets including plaintext tokens.(Citation: Wiz Trivy Compromise MAR 2026)(Citation: Aqua Security Trivy Compromise MAR 2026)(Citation: Aqua Security Blog Trivy Compromise APR 2026)(Citation: Sysdig TeamPCP MAR 2026)(Citation: Wiz TeamPCP KICS MAR 2026)(Citation: Palo Alto TeamPCP MAR 2026) [Aqua Security Trivy Compromise MAR 2026](https://github.com/aquasecurity/trivy/security/advisories/GHSA-69fq-xp46-6x23) · [Aqua Security Blog Trivy Compromise APR 2026](https://www.aquasec.com/blog/trivy-supply-chain-attack-what-you-need-to-know) · [Wiz Trivy Compromise MAR 2026](https://www.wiz.io/blog/trivy-compromised-teampcp-supply-chain-attack) · [Wiz TeamPCP KICS MAR 2026](https://www.wiz.io/blog/teampcp-attack-kics-github-action) · [Sysdig TeamPCP MAR 2026](https://www.sysdig.com/blog/teampcp-expands-supply-chain-compromise-spreads-from-trivy-to-checkmarx-github-actions) · [Palo Alto TeamPCP MAR 2026](https://unit42.paloaltonetworks.com/teampcp-supply-chain-attacks/)

## Detection strategies

- [DET0593 - Detecting OS Credential Dumping via /proc Filesystem Access on Linux](../../../../Defenses/Detection%20Strategies/DET0593%20-%20Detecting%20OS%20Credential%20Dumping%20via%20-%20proc%20Filesystem%20Access%20on%20Linux.md)

## Mitigations

- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure that root accounts have complex, unique passwords across all systems on the network.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Follow best practices in restricting access to privileged accounts to avoid hostile programs from accessing sensitive information.

## Sources

- [atomic-red proc file system](https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1003.007/T1003.007.md)
- [baeldung Linux proc map 2022](https://www.baeldung.com/linux/proc-id-maps)
- [Polop Linux PrivEsc Gitbook](https://book.hacktricks.xyz/linux-hardening/privilege-escalation#proc-usdpid-maps-and-proc-usdpid-mem)
- [MimiPenguin GitHub May 2017](https://github.com/huntergregal/mimipenguin)
- [Picus Labs Proc cump 2022](https://www.picussecurity.com/resource/the-mitre-attck-t1003-os-credential-dumping-technique-and-its-adversary-use)
