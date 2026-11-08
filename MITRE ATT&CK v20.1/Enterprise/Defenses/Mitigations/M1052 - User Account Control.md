# M1052 - User Account Control

[Enterprise](../../README.md) / [Mitigations](README.md)

User Account Control (UAC) is a security feature in Microsoft Windows that prevents unauthorized changes to the operating system. UAC prompts users to confirm or provide administrator credentials when an action requires elevated privileges. Proper configuration of UAC reduces the risk of privilege escalation attacks. This mitigation can be implemented through the following measures:

Enable UAC Globally:

- Ensure UAC is enabled through Group Policy by setting `User Account Control: Run all administrators in Admin Approval Mode` to `Enabled`.

Require Credential Prompt:

- Use Group Policy to configure UAC to prompt for administrative credentials instead of just confirmation (`User Account Control: Behavior of the elevation prompt`).

Restrict Built-in Administrator Account:

Set `Admin Approval Mode` for the built-in Administrator account to `Enabled` in Group Policy.

Secure the UAC Prompt:

- Configure UAC prompts to display on the secure desktop (`User Account Control: Switch to the secure desktop when prompting for elevation`).

Prevent UAC Bypass:

- Block untrusted applications from triggering UAC prompts by configuring `User Account Control: Only elevate executables that are signed and validated`.
- Use EDR tools to detect and block known UAC bypass techniques.

Monitor UAC-Related Events:

- Use Windows Event Viewer to monitor for event ID 4688 (process creation) and look for suspicious processes attempting to invoke UAC elevation.

*Tools for Implementation*

Built-in Windows Tools:

- Group Policy Editor: Configure UAC settings centrally for enterprise environments.
- Registry Editor: Modify UAC-related settings directly, such as `EnableLUA` and `ConsentPromptBehaviorAdmin`.

Endpoint Security Solutions:

- Microsoft Defender for Endpoint: Detects and blocks UAC bypass techniques.
- Sysmon: Logs process creations and monitors UAC elevation attempts for suspicious activity.

Third-Party Security Tools:

- Process Monitor (Sysinternals): Tracks real-time processes interacting with UAC.
- EventSentry: Monitors Windows Event Logs for UAC-related alerts.

[MITRE ATT&CK record](https://attack.mitre.org/mitigations/M1052)

## Mitigated techniques

- [T1548 - Abuse Elevation Control Mechanism](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/README.md)
- [T1546.011 - Application Shimming](../../Tactics/05%20TA0003%20-%20Persistence/T1546%20-%20Event%20Triggered%20Execution/T1546.011%20-%20Application%20Shimming/README.md)
- [T1548.002 - Bypass User Account Control](../../Tactics/06%20TA0004%20-%20Privilege%20Escalation/T1548%20-%20Abuse%20Elevation%20Control%20Mechanism/T1548.002%20-%20Bypass%20User%20Account%20Control/README.md)
- [T1574.005 - Executable Installer File Permissions Weakness](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.005%20-%20Executable%20Installer%20File%20Permissions%20Weakness/README.md)
- [T1574 - Hijack Execution Flow](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/README.md)
- [T1550.002 - Pass the Hash](../../Tactics/11%20TA0008%20-%20Lateral%20Movement/T1550%20-%20Use%20Alternate%20Authentication%20Material/T1550.002%20-%20Pass%20the%20Hash/README.md)
- [T1574.010 - Services File Permissions Weakness](../../Tactics/04%20TA0002%20-%20Execution/T1574%20-%20Hijack%20Execution%20Flow/T1574.010%20-%20Services%20File%20Permissions%20Weakness/README.md)
