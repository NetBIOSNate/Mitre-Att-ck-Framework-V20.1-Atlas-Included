# M1039 - Environment Variable Permissions

[Enterprise](../../README.md) / [Mitigations](README.md)

Restrict the modification of environment variables to authorized users and processes by enforcing strict permissions and policies. This ensures the integrity of environment variables, preventing adversaries from abusing or altering them for malicious purposes. This mitigation can be implemented through the following measures:

Restrict Write Access:

- Use Case: Set file system-level permissions to restrict access to environment variable configuration files (e.g., `.bashrc`, `.bash_profile`, `.zshrc`, `systemd` service files).
- Implementation: Configure `/etc/environment` or `/etc/profile` on Linux systems to only allow root or administrators to modify the file.

Secure Access Controls:

- Use Case: Limit access to environment variable settings in application deployment tools or CI/CD pipelines to authorized personnel.
- Implementation: Use role-based access control (RBAC) in tools like Jenkins or GitLab to ensure only specific users can modify environment variables.

Restrict Process Scope:

- Use Case: Configure policies to ensure environment variables are only accessible to the processes they are explicitly intended for.
- Implementation: Use containerized environments like Docker to isolate environment variables to specific containers and ensure they are not inherited by other processes.

Audit Environment Variable Changes:

- Use Case: Enable logging for changes to critical environment variables.
- Implementation: Use `auditd` on Linux to monitor changes to files like `/etc/environment` or application-specific environment files.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1039)

## Mitigated techniques

- [T1070.003 - Clear Command History](../../Tactics/07%20TA0005%20-%20Stealth/T1070%20-%20Indicator%20Removal/T1070.003%20-%20Clear%20Command%20History/README.md)
- [T1690 - Prevent Command History Logging](../../Tactics/08%20TA0112%20-%20Defense%20Impairment/T1690%20-%20Prevent%20Command%20History%20Logging/README.md)
