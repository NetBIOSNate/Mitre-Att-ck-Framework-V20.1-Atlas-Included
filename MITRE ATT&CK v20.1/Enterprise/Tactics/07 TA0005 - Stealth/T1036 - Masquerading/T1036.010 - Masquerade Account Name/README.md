# T1036.010 - Masquerade Account Name

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

Adversaries may match or approximate the names of legitimate accounts to make newly created ones appear benign. This will typically occur during [Create Account](https://attack.mitre.org/techniques/T1136), although accounts may also be renamed at a later date. This may also coincide with [Account Access Removal](https://attack.mitre.org/techniques/T1531) if the actor first deletes an account before re-creating one with the same name.(Citation: Huntress MOVEit 2023)

Often, adversaries will attempt to masquerade as service accounts, such as those associated with legitimate software, data backups, or container cluster management.(Citation: Elastic CUBA Ransomware 2022)(Citation: Aquasec Kubernetes Attack 2023) They may also give accounts generic, trustworthy names, such as “admin”, “help”, or “root.”(Citation: Invictus IR Cloud Ransomware 2024) Sometimes adversaries may model account names off of those already existing in the system, as a follow-on behavior to [Account Discovery](https://attack.mitre.org/techniques/T1087).  

Note that this is distinct from [Impersonation](https://attack.mitre.org/techniques/T1684/001), which describes impersonating specific trusted individuals or organizations, rather than user or service account names.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/010)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Containers](../../../../Platforms/Containers.md), [IaaS](../../../../Platforms/IaaS.md), [Identity Provider](../../../../Platforms/Identity%20Provider.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Office Suite](../../../../Platforms/Office%20Suite.md), [SaaS](../../../../Platforms/SaaS.md), [Windows](../../../../Platforms/Windows.md)

## Procedure examples

- [C0025 - 2016 Ukraine Electric Power Attack](../../../../Threat%20Intelligence/Campaigns/C0025%20-%202016%20Ukraine%20Electric%20Power%20Attack.md) — During the [2016 Ukraine Electric Power Attack](https://attack.mitre.org/campaigns/C0025), [Sandworm Team](https://attack.mitre.org/groups/G0034) created two new accounts, “admin” and “система” (System).(Citation: Dragos Crashoverride 2018) [Dragos Crashoverride 2018](https://www.dragos.com/wp-content/uploads/CRASHOVERRIDE2018.pdf)
- [G0022 - APT3](../../../../Threat%20Intelligence/Groups/G0022%20-%20APT3.md) — [APT3](https://attack.mitre.org/groups/G0022) has been known to create or enable accounts, such as <code>support_388945a0</code>.(Citation: aptsim) [aptsim](http://carnal0wnage.attackresearch.com/2012/09/more-on-aptsim.html)
- [G0035 - Dragonfly](../../../../Threat%20Intelligence/Groups/G0035%20-%20Dragonfly.md) — [Dragonfly](https://attack.mitre.org/groups/G0035) has created accounts disguised as legitimate backup and service accounts as well as an email administration account.(Citation: US-CERT TA18-074A) [US-CERT TA18-074A](https://www.us-cert.gov/ncas/alerts/TA18-074A)
- [S0143 - Flame](../../../../Threat%20Intelligence/Software/Malware/S0143%20-%20Flame.md) — [Flame](https://attack.mitre.org/software/S0143) can create backdoor accounts with login `HelpAssistant` on domain connected systems if appropriate rights are available.(Citation: Kaspersky Flame)(Citation: Kaspersky Flame Functionality) [Kaspersky Flame](https://securelist.com/the-flame-questions-and-answers-51/34344/) · [Kaspersky Flame Functionality](https://securelist.com/flame-bunny-frog-munch-and-beetlejuice-2/32855/)
- [G0059 - Magic Hound](../../../../Threat%20Intelligence/Groups/G0059%20-%20Magic%20Hound.md) — [Magic Hound](https://attack.mitre.org/groups/G0059) has created local accounts named `help` and `DefaultAccount` on compromised machines.(Citation: DFIR Report APT35 ProxyShell March 2022)(Citation: Microsoft Iranian Threat Actor Trends November 2021) [DFIR Report APT35 ProxyShell March 2022](https://thedfirreport.com/2022/03/21/apt35-automates-initial-access-using-proxyshell) · [Microsoft Iranian Threat Actor Trends November 2021](https://www.microsoft.com/en-us/security/blog/2021/11/16/evolving-trends-in-iranian-threat-actor-activity-mstic-presentation-at-cyberwarcon-2021)
- [S0382 - ServHelper](../../../../Threat%20Intelligence/Software/Malware/S0382%20-%20ServHelper.md) — [ServHelper](https://attack.mitre.org/software/S0382) has created a new user named `supportaccount`.(Citation: Proofpoint TA505 Jan 2019) [Proofpoint TA505 Jan 2019](https://www.proofpoint.com/us/threat-insight/post/servhelper-and-flawedgrace-new-malware-introduced-ta505)
- [G1046 - Storm-1811](../../../../Threat%20Intelligence/Groups/G1046%20-%20Storm-1811.md) — [Storm-1811](https://attack.mitre.org/groups/G1046) has created Microsoft Teams accounts that spoof IT support and helpdesk members for use in application and voice phishing.(Citation: Microsoft Storm-1811 2024) [Microsoft Storm-1811 2024](https://www.microsoft.com/en-us/security/blog/2024/05/15/threat-actors-misusing-quick-assist-in-social-engineering-attacks-leading-to-ransomware/)

## Detection strategies

- [DET0383 - Detection Strategy for Masquerading via Account Name Similarity](../../../../Defenses/Detection%20Strategies/DET0383%20-%20Detection%20Strategy%20for%20Masquerading%20via%20Account%20Name%20Similarity.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Audit user accounts to ensure that each one has a defined purpose.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Consider defining and enforcing a naming convention for user accounts to more easily spot generic account names that do not fit the typical schema.

## Sources

- [Elastic CUBA Ransomware 2022](https://www.elastic.co/security-labs/cuba-ransomware-campaign-analysis)
- [Invictus IR Cloud Ransomware 2024](https://www.invictus-ir.com/news/ransomware-in-the-cloud)
- [Huntress MOVEit 2023](https://www.huntress.com/blog/moveit-transfer-critical-vulnerability-rapid-response)
- [Aquasec Kubernetes Attack 2023](https://blog.aquasec.com/leveraging-kubernetes-rbac-to-backdoor-clusters)
