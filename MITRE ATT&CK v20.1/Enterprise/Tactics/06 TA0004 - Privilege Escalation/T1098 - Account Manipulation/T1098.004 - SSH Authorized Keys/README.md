# T1098.004 - SSH Authorized Keys

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1098 - Account Manipulation](../README.md)

Adversaries may modify the SSH <code>authorized_keys</code> file to maintain persistence on a victim host. Linux distributions, macOS, and ESXi hypervisors commonly use key-based authentication to secure the authentication process of SSH sessions for remote management. The <code>authorized_keys</code> file in SSH specifies the SSH keys that can be used for logging into the user account for which the file is configured. This file is usually found in the user's home directory under <code>&lt;user-home&gt;/.ssh/authorized_keys</code> (or, on ESXi, `/etc/ssh/keys-<username>/authorized_keys`).(Citation: SSH Authorized Keys) Users may edit the system’s SSH config file to modify the directives `PubkeyAuthentication` and `RSAAuthentication` to the value `yes` to ensure public key and RSA authentication are enabled, as well as modify the directive `PermitRootLogin` to the value `yes` to enable root authentication via SSH.(Citation: Broadcom ESXi SSH) The SSH config file is usually located under <code>/etc/ssh/sshd_config</code>.

Adversaries may modify SSH <code>authorized_keys</code> files directly with scripts or shell commands to add their own adversary-supplied public keys. In cloud environments, adversaries may be able to modify the SSH authorized_keys file of a particular virtual machine via the command line interface or rest API. For example, by using the Google Cloud CLI’s “add-metadata” command an adversary may add SSH keys to a user account.(Citation: Google Cloud Add Metadata)(Citation: Google Cloud Privilege Escalation) Similarly, in Azure, an adversary may update the authorized_keys file of a virtual machine via a PATCH request to the API.(Citation: Azure Update Virtual Machines) This ensures that an adversary possessing the corresponding private key may log in as an existing user via SSH.(Citation: Venafi SSH Key Abuse)(Citation: Cybereason Linux Exim Worm) It may also lead to privilege escalation where the virtual machine or instance has distinct permissions from the requesting user.

Where authorized_keys files are modified via cloud APIs or command line interfaces, an adversary may achieve privilege escalation on the target virtual machine if they add a key to a higher-privileged user. 

SSH keys can also be added to accounts on network devices, such as with the `ip ssh pubkey-chain` [Network Device CLI](https://attack.mitre.org/techniques/T1059/008) command.(Citation: cisco_ip_ssh_pubkey_ch_cmd)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1098/004)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Privilege Escalation](../../README.md)

**Platforms**  [ESXi](../../../../Platforms/ESXi.md), [IaaS](../../../../Platforms/IaaS.md), [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Network Devices](../../../../Platforms/Network%20Devices.md)

## Procedure examples

- [C0064 - AI-Assisted Breach of Mexico's Government Infrastructure](../../../../Threat%20Intelligence/Campaigns/C0064%20-%20AI-Assisted%20Breach%20of%20Mexico%27s%20Government%20Infrastructure.md) — During the [AI-Assisted Breach of Mexico's Government Infrastructure](https://attack.mitre.org/campaigns/C0064), the adversary tasked Claude Code to establish persistence on the system by injecting an SSH key located at `/root/.ssh/authorized_keys` file via a crontab script.(Citation: AI-Mexico-Govt-Breach) [AI-Mexico-Govt-Breach](https://cdn.prod.website-files.com/69944dd945f20ca4a27a7c47/69d8bb5aea59e31efb3b8a7f_Tech_Report_ai_breach_mex_gov.pdf)
- [S0482 - Bundlore](../../../../Threat%20Intelligence/Software/Malware/S0482%20-%20Bundlore.md) — [Bundlore](https://attack.mitre.org/software/S0482) creates a new key pair with <code>ssh-keygen</code> and drops the newly created user key in <code>authorized_keys</code> to enable remote login.(Citation: MacKeeper Bundlore Apr 2019) [MacKeeper Bundlore Apr 2019](https://mackeeper.com/blog/post/610-macos-bundlore-adware-analysis/)
- [G1006 - Earth Lusca](../../../../Threat%20Intelligence/Groups/G1006%20-%20Earth%20Lusca.md) — [Earth Lusca](https://attack.mitre.org/groups/G1006) has dropped an SSH-authorized key in the `/root/.ssh` folder in order to access a compromised server with SSH.(Citation: TrendMicro EarthLusca 2022) [TrendMicro EarthLusca 2022](https://www.trendmicro.com/content/dam/trendmicro/global/en/research/22/a/earth-lusca-employs-sophisticated-infrastructure-varied-tools-and-techniques/technical-brief-delving-deep-an-analysis-of-earth-lusca-operations.pdf)
- [C0061 - Operation Digital Eye](../../../../Threat%20Intelligence/Campaigns/C0061%20-%20Operation%20Digital%20Eye.md) — During [Operation Digital Eye](https://attack.mitre.org/campaigns/C0061), threat actors used SSH access enabled by authorized_keys files for remote execution.(Citation: sentinelone operationDigitalEye Dec 2024) [sentinelone operationDigitalEye Dec 2024](https://www.sentinelone.com/labs/operation-digital-eye-chinese-apt-compromises-critical-digital-infrastructure-via-visual-studio-code-tunnels/)
- [G1045 - Salt Typhoon](../../../../Threat%20Intelligence/Groups/G1045%20-%20Salt%20Typhoon.md) — [Salt Typhoon](https://attack.mitre.org/groups/G1045) has added SSH authorized_keys under root or other users at the Linux level on compromised network devices.(Citation: Cisco Salt Typhoon FEB 2025)(Citation: CISA_AA25-239ASaltTyphoon_Sept2025) [CISA_AA25-239ASaltTyphoon_Sept2025](https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-239a) · [Cisco Salt Typhoon FEB 2025](https://blog.talosintelligence.com/salt-typhoon-analysis/)
- [S0468 - Skidmap](../../../../Threat%20Intelligence/Software/Malware/S0468%20-%20Skidmap.md) — [Skidmap](https://attack.mitre.org/software/S0468) has the ability to add the public key of its handlers to the <code>authorized_keys</code> file to maintain persistence on an infected host.(Citation: Trend Micro Skidmap) [Trend Micro Skidmap](https://blog.trendmicro.com/trendlabs-security-intelligence/skidmap-linux-malware-uses-rootkit-capabilities-to-hide-cryptocurrency-mining-payload/)
- [G0139 - TeamTNT](../../../../Threat%20Intelligence/Groups/G0139%20-%20TeamTNT.md) — [TeamTNT](https://attack.mitre.org/groups/G0139) has added RSA keys in <code>authorized_keys</code>.(Citation: Aqua TeamTNT August 2020)(Citation: Cisco Talos Intelligence Group) [Cisco Talos Intelligence Group](https://blog.talosintelligence.com/teamtnt-targeting-aws-alibaba-2/) · [Aqua TeamTNT August 2020](https://blog.aquasec.com/container-security-tnt-container-attack)
- [S0658 - XCSSET](../../../../Threat%20Intelligence/Software/Malware/S0658%20-%20XCSSET.md) — [XCSSET](https://attack.mitre.org/software/S0658) will create an ssh key if necessary with the <code>ssh-keygen -t rsa -f $HOME/.ssh/id_rsa -P</code> command. [XCSSET](https://attack.mitre.org/software/S0658) will upload a private key file to the server to remotely access the host without a password.(Citation: trendmicro xcsset xcode project 2020) [trendmicro xcsset xcode project 2020](https://documents.trendmicro.com/assets/pdf/XCSSET_Technical_Brief.pdf)

## Mitigations

- [M1042 - Disable or Remove Feature or Program](../../../../Defenses/Mitigations/M1042%20-%20Disable%20or%20Remove%20Feature%20or%20Program.md) — Disable SSH if it is not necessary on a host or restrict SSH access for specific users/groups using <code>/etc/ssh/sshd_config</code>. Setting the `PermitRootLogin` directive to `no` will prevent the root user from logging in via SSH.(Citation: Broadcom ESXi SSH) [Broadcom ESXi SSH](https://knowledge.broadcom.com/external/article/313767/allowing-ssh-access-to-vmware-vsphere-es.html)
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Restrict access to the <code>authorized_keys</code> file.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — In cloud environments, ensure that only users who explicitly require the permissions to update instance metadata or configurations can do so.

## Detection strategies

- [DET0126 - Detection Strategy for SSH Key Injection in Authorized Keys](../../../../Defenses/Detection%20Strategies/DET0126%20-%20Detection%20Strategy%20for%20SSH%20Key%20Injection%20in%20Authorized%20Keys.md)

## Sources

- [Venafi SSH Key Abuse](https://www.venafi.com/blog/growing-abuse-ssh-keys-commodity-malware-campaigns-now-equipped-ssh-capabilities)
- [Broadcom ESXi SSH](https://knowledge.broadcom.com/external/article/313767/allowing-ssh-access-to-vmware-vsphere-es.html)
- [Google Cloud Privilege Escalation](https://about.gitlab.com/blog/2020/02/12/plundering-gcp-escalating-privileges-in-google-cloud-platform/)
- [cisco_ip_ssh_pubkey_ch_cmd](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/security/d1/sec-d1-cr-book/sec-cr-i3.html#wp1254331478)
- [Cybereason Linux Exim Worm](https://www.cybereason.com/blog/new-pervasive-worm-exploiting-linux-exim-server-vulnerability)
- [Google Cloud Add Metadata](https://cloud.google.com/sdk/gcloud/reference/compute/instances/add-metadata)
- [Azure Update Virtual Machines](https://docs.microsoft.com/en-us/rest/api/compute/virtual-machines/update)
- [SSH Authorized Keys](https://www.ssh.com/ssh/authorized_keys/)
