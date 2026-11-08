# DC0059 - File Metadata

[ICS](../../README.md) / [Data Components](README.md)

contextual information about a file, including attributes such as the file's name, size, type, content (e.g., signatures, headers, media), user/owner, permissions, timestamps, and other related properties. File metadata provides insights into a file's characteristics and can be used to detect malicious activity, unauthorized modifications, or other anomalies. Examples: 

- File Ownership and Permissions: Checking the owner and permissions of a critical configuration file like /etc/passwd on Linux or C:\Windows\System32\config\SAM on Windows.
- Timestamps: Analyzing the creation, modification, and access timestamps of a file.
- File Content and Signatures: Extracting the headers of an executable file to verify its signature or detect packing/obfuscation.
- File Attributes: Analyzing attributes like hidden, system, or read-only flags in Windows.
- File Hashes: Generating MD5, SHA-1, or SHA-256 hashes of files to compare against threat intelligence feeds.
- File Location: Monitoring files located in unusual directories or paths, such as temporary or user folders.

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0059)

## Log sources and channels

- **auditd:SYSCALL** — stat and lstat syscall results on files, including inode and permission info
- **AndroidLogs:Framework** — BroadcastReceiver registration for android.intent.action.BOOT_COMPLETED by previously unseen or recently installed apps
- **auditd:CONFIG_CHANGE** — chmod or chown of hook files indicating privilege escalation or execution permission change
- **auditd:PATH** — file path matches exclusion directories
- **auditd:PATH** — PATH
- **auditd:PATH** — file path modifications on critical system directories (/etc, /usr/bin, /usr/sbin, /var, /opt)
- **auditd:SYSCALL** — Inotify watch creation or auditctl changes on /etc/cron* or /lib/systemd/system/
- **auditd:SYSCALL** — PATH
- **auditd:SYSCALL** — file write after sleep delay
- **auditd:SYSCALL** — syscall in (chmod, fchmod, fchmodat, chown, fchown, fchownat, setxattr, lsetxattr, fsetxattr)
- **auditd:SYSCALL** — setuid or setgid bit changes
- **auditd:SYSCALL** — syscall in (chmod, fchmod, fchmodat, chown, fchown, fchownat, lchown, setxattr, lsetxattr, fsetxattr, removexattr, lremovexattr, fremovexattr)
- **auditd:SYSCALL** — setxattr or getxattr system call
- **auditd:SYSCALL** — chmod, chown, setxattr, or file writes to /etc/ssl/* or /usr/local/share/ca-certificates/*
- **ebpf:syscalls** — Unexpected container volume unmount + file deletion
- **EDR:detection** — App reputation telemetry
- **EDR:file** — File Metadata Inspection (Low String Entropy, Missing PDB)
- **EDR:file** — File Metadata Analysis (PE overlays, entropy)
- **esxi:hostd** — host daemon events related to file or VM permission changes
- **esxi:syslog** — Datastore file hidden or renamed unexpectedly
- **esxi:vmkernel** — Upload of file to datastore
- **esxi:vmkernel** — Storage access and file ops
- **esxi:vmkernel** — VMware kernel events for file system permission modifications
- **esxi:vmkernel** — Datastore modification events
- **File** — None
- **fs:fileevents** — /var/log/install.log
- **fs:filesystem** — Binary file hash changes outside of update/patch cycles
- **fs:fsevents** — file system events indicating permission or attribute changes
- **fs:fsusage** — filesystem monitoring of exec/open
- **fwupd:logs** — Firmware updates applied or failed
- **gatekeeper/quarantine database** — LaunchServices quarantine
- **journald:package** — dpkg/apt or yum/dnf transaction logs (install/update of build tools)
- **journald:package** — dpkg/apt/yum/dnf transaction logs; vendor updaters in systemd journals
- **journald:package** — dpkg/apt install, remove, upgrade events
- **journald:package** — yum/dnf install or update transactions
- **linux:osquery** — event-based
- **linux:osquery** — file_events, hash
- **linux:osquery** — hash, elf_info, file_metadata
- **linux:osquery** — file_events
- **linux:osquery** — elf_info, hash, yara_matches
- **linux:osquery** — Read headers and detect MIME type mismatch
- **linux:osquery** — file_events.path
- **linux:osquery** — Filesystem modifications to trusted paths
- **linux:osquery** — Write or modify .desktop file in XDG autostart path
- **linux:osquery** — hash, rpm_packages, deb_packages, file_events
- **linux:syslog** — Discrepancies in _VBA_PROJECT p-code vs source code extracted with oletools/pcodedmp
- **linux:syslog** — application or system execution logs
- **linux:syslog** — file permission modification events in kernel messages
- **linux:syslog** — kernel messages related to file system permission changes and security violations
- **macos:endpointsecurity** — es_event_file_rename_t or es_event_file_write_t
- **macos:endpointsecurity** — es_event_authentication
- **macos:osquery** — code_signing, file_metadata
- **macos:osquery** — file_events
- **macos:osquery** — mach_o_info, file_metadata
- **macos:unifiedlog** — softwareupdated/homebrew/install logs, pkginstalld events
- **macos:unifiedlog** — AMFI or Gatekeeper signature/notarization failures for newly installed dev components
- **macos:unifiedlog** — Detection of altered _VBA_PROJECT or PerformanceCache streams
- **macos:unifiedlog** — subsystem:syspolicyd
- **macos:unifiedlog** — File metadata updated with UF_HIDDEN flag
- **macos:unifiedlog** — Code signature validation fails or is absent post-binary modification
- **macos:unifiedlog** — Code signing verification failures or bypassed trust decisions
- **macos:unifiedlog** — Creation of new LaunchAgent or LoginItem plist files in ~/Library/LaunchAgents/
- **macos:unifiedlog** — filesystem events
- **macos:unifiedlog** — xattr -d com.apple.quarantine or similar attribute removal commands
- **macos:unifiedlog** — Gatekeeper quarantine policy decision anomalies recorded in com.apple.LaunchServices.QuarantineEventsV2
- **macos:unifiedlog** — pkginstalld/softwareupdated/Homebrew install transactions
- **macos:unifiedlog** — AMFI/Gatekeeper code signature or notarization failures
- **macos:unifiedlog** — kernel extension and system extension logs related to file system security violations or SIP bypass attempts
- **macos:unifiedlog** — Unexpected application binary modifications or altered signing status
- **macos:unifiedlog** — extended attribute write or modification
- **macos:unifiedlog** — New certificate trust settings added by unexpected process
- **macos:unifiedlog** — subsystem=com.apple.lsd
- **macos:unifiedlog** — installer or system_installd 'PackageKit: install succeeded/failed' with non-notarized or unknown signer
- **macos:unifiedlog** — Gatekeeper/AMFI 'code signature invalid' / 'not notarized' messages
- **macos:unifiedlog** — File creation or modification with com.apple.ResourceFork extended attribute
- **networkdevice:syslog** — OS version query results inconsistent with expected or approved version list
- **NSM:Flow** — Observed File Transfers
- **OpenBSM:AuditTrail** — BSM audit events for file permission modifications
- **OpenBSM:AuditTrail** — BSM audit events for file permission, ownership, and attribute modifications with user context
- **saas:RepoEvents** — New file added or modified in PR targeting CI/CD or build config (e.g., `gitlab-ci.yml`, `build.gradle`, `pom.xml`, `.github/workflows/*.yml`)
- **WinEventLog:Microsoft-Windows-CodeIntegrity/Operational** — Invalid/Unsigned image when developer tool launches newly installed binaries
- **WinEventLog:Microsoft-Windows-CodeIntegrity/Operational** — Unsigned or invalid image for newly installed/updated binaries
- **WinEventLog:Microsoft-Windows-CodeIntegrity/Operational** — Code integrity violations in boot-start drivers or firmware
- **WinEventLog:Microsoft-Windows-CodeIntegrity/Operational** — CodeIntegrity reports 'Invalid image hash' or 'Unsigned image' for new/updated binaries
- **WinEventLog:Microsoft-Windows-Windows Defender/Operational** — SmartScreen or ASR blocks on newly downloaded installer/updater
- **WinEventLog:Security** — EventCode=4663, 4670, 4656
- **WinEventLog:Security** — EventCode=4663, 4656, 4658
- **WinEventLog:Setup** — MSI/Product install, repair or update events
- **WinEventLog:Sysmon** — EventCode=15
- **WinEventLog:Windows Defender** — Operational log
- **WinEventLog:Windows Defender** — Operational
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: DEX file entropy > $PackerEntropyThreshold$ at install time for app NOT IN $MDMApprovedCatalog$
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: app_version in MDM == prior_version while dynamic code load from network is observed — confirms this is not a legitimate update
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: binary with file_permissions including setuid bit (mode & 04000) at path NOT IN $KnownSystemBinPaths$ — setuid outside system bin directories is the renamed-root-binary indicator
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: file hash changes for binary at $SystemBinaryPaths$ relative to known-good baseline — hash deviation confirms modification
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: MDM supervised integrity_check=fail following jailbreak detection — integrity check failure on supervised Jamf/Intune enrolled device indicates filesystem modifications beyond passive jailbreak presence
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: installed app package_name Levenshtein distance <= $NameDistanceThreshold$ to entry in $KnownAppCatalog$
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: bundle_id LIKE $KnownSystemNamespace$
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: app package_name distance <= $NameDistanceThreshold$ from $KnownAppCatalog$ entry
- **mobile:ForensicArtifacts** — Dynamic filesystem trace or acquired app-container/filesystem artifacts: display_name Levenshtein distance <= $NameDistanceThreshold$ from $KnownIOSAppCatalog$ entry
- **auditd:SYSCALL+PATH** — Linux Audit SYSCALL+PATH records: package installation creates files outside the documented package manifest
- **auditd:SYSCALL+PATH** — Linux Audit SYSCALL+PATH records: write to Industrial Control Systems (ICS) project file path by uid not in authorized engineering User Identifiers (UIDs) or from path not in approved project sources
- **linux:pkgintegrity** — rpm -V/dpkg --verify checksum mismatch for installed Industrial Control Systems (ICS) package binary
- **fim:hashcompare** — installed binary hash does not match vendor-published checksum for claimed version
- **WinEventLog:Sysmon** — Microsoft-Windows-Sysmon/Operational Event ID 11 FileCreate/overwrite or Event ID 2 FileCreateTime, as applicable: Process creation and file creation correlation: vendor installer creates files outside vendor install manifest or spawns undocumented child process
- **WinEventLog:Sysmon** — EventCode=11 matching Industrial Control Systems (ICS) vendor binary name in a path outside vendor install paths
- **WinEventLog:Sysmon** — Microsoft-Windows-Sysmon/Operational Event ID 11 FileCreate/overwrite or Event ID 2 FileCreateTime, as applicable: Engineering tool process opens project file from path not in approved project repository (removable media, email attachment cache, untrusted network share)

## Analytics using this component

- [AN1858 - Analytic 1858](../Analytics/AN1858.md)
- [AN1863 - Analytic 1863](../Analytics/AN1863.md)
- [AN1898 - Analytic 1898](../Analytics/AN1898.md)
- [AN2111 - Analytic 2111](../Analytics/AN2111.md)
- [AN2116 - Analytic 2116](../Analytics/AN2116.md)
- [AN2123 - Analytic 2123](../Analytics/AN2123.md)
