# T1556.003 - Pluggable Authentication Modules

[Enterprise](../../../../README.md) / [Credential Access](../../README.md) / [T1556 - Modify Authentication Process](../README.md)

Adversaries may modify pluggable authentication modules (PAM) to access user credentials or enable otherwise unwarranted access to accounts. PAM is a modular system of configuration files, libraries, and executable files which guide authentication for many services. The most common authentication module is <code>pam_unix.so</code>, which retrieves, sets, and verifies account authentication information in <code>/etc/passwd</code> and <code>/etc/shadow</code>.(Citation: Apple PAM)(Citation: Man Pam_Unix)(Citation: Red Hat PAM)

Adversaries may modify components of the PAM system to create backdoors. PAM components, such as <code>pam_unix.so</code>, can be patched to accept arbitrary adversary supplied values as legitimate credentials.(Citation: PAM Backdoor)

Malicious modifications to the PAM system may also be abused to steal credentials. Adversaries may infect PAM resources with code to harvest user credentials, since the values exchanged with PAM components may be plain-text since PAM does not store passwords.(Citation: PAM Creds)(Citation: Apple PAM)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1556/003)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Defense Impairment](../../../08%20TA0112%20-%20Defense%20Impairment/README.md), [Credential Access](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0377 - Ebury](../../../../Threat%20Intelligence/Software/Malware/S0377%20-%20Ebury.md) — [Ebury](https://attack.mitre.org/software/S0377) can deactivate PAM modules to tamper with the sshd configuration.(Citation: ESET Ebury Oct 2017) [ESET Ebury Oct 2017](https://www.welivesecurity.com/2017/10/30/windigo-ebury-update-2/)
- [S0468 - Skidmap](../../../../Threat%20Intelligence/Software/Malware/S0468%20-%20Skidmap.md) — [Skidmap](https://attack.mitre.org/software/S0468) has the ability to replace the pam_unix.so file on an infected machine with its own malicious version that accepts a specific backdoor password for all users.(Citation: Trend Micro Skidmap) [Trend Micro Skidmap](https://blog.trendmicro.com/trendlabs-security-intelligence/skidmap-linux-malware-uses-rootkit-capabilities-to-hide-cryptocurrency-mining-payload/)

## Mitigations

- [M1032 - Multi-factor Authentication](../../../../Defenses/Mitigations/M1032%20-%20Multi-factor%20Authentication.md) — Integrating multi-factor authentication (MFA) as part of organizational policy can greatly reduce the risk of an adversary gaining control of valid credentials that may be used for additional tactics such as initial access, lateral movement, and collecting information.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Limit access to the root account and prevent users from modifying PAM components through proper privilege separation (ex SELinux, grsecurity, AppArmor, etc.) and limiting Privilege Escalation opportunities.

## Detection strategies

- [DET0454 - Detect Malicious Modification of Pluggable Authentication Modules (PAM)](../../../../Defenses/Detection%20Strategies/DET0454%20-%20Detect%20Malicious%20Modification%20of%20Pluggable%20Authentication%20Modules%20%28PAM%29.md)

## Sources

- [Apple PAM](https://opensource.apple.com/source/dovecot/dovecot-239/dovecot/doc/wiki/PasswordDatabase.PAM.txt)
- [Man Pam_Unix](https://linux.die.net/man/8/pam_unix)
- [PAM Creds](https://web.archive.org/web/20240303094335/https://x-c3ll.github.io/posts/PAM-backdoor-DNS/)
- [Red Hat PAM](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/managing_smart_cards/pluggable_authentication_modules)
- [PAM Backdoor](https://github.com/zephrax/linux-pam-backdoor)
