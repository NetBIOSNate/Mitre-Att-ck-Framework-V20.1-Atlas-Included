# S1040 - Rclone

[Enterprise](../../../README.md) / [Tools](README.md)

[Rclone](https://attack.mitre.org/software/S1040) is a command line program for syncing files with cloud storage services such as Dropbox, Google Drive, Amazon S3, and MEGA. [Rclone](https://attack.mitre.org/software/S1040) has been used in a number of ransomware campaigns, including those associated with the [Conti](https://attack.mitre.org/software/S0575) and DarkSide Ransomware-as-a-Service operations.(Citation: Rclone)(Citation: Rclone Wars)(Citation: Detecting Rclone)(Citation: DarkSide Ransomware Gang)(Citation: DFIR Conti Bazar Nov 2021)

[MITRE ATT&CK record](https://attack.mitre.org/software/S1040)

**Platforms**  [Linux](../../../Platforms/Linux.md), [Windows](../../../Platforms/Windows.md), [macOS](../../../Platforms/macOS.md)

## Techniques used

- [T1560.001 - Archive via Utility](../../../Tactics/12%20TA0009%20-%20Collection/T1560%20-%20Archive%20Collected%20Data/T1560.001%20-%20Archive%20via%20Utility/README.md)
- [T1030 - Data Transfer Size Limits](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1030%20-%20Data%20Transfer%20Size%20Limits/README.md)
- [T1048.002 - Exfiltration Over Asymmetric Encrypted Non-C2 Protocol](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.002%20-%20Exfiltration%20Over%20Asymmetric%20Encrypted%20Non-C2%20Protocol/README.md)
- [T1048.003 - Exfiltration Over Unencrypted Non-C2 Protocol](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1048%20-%20Exfiltration%20Over%20Alternative%20Protocol/T1048.003%20-%20Exfiltration%20Over%20Unencrypted%20Non-C2%20Protocol/README.md)
- [T1567.002 - Exfiltration to Cloud Storage](../../../Tactics/14%20TA0010%20-%20Exfiltration/T1567%20-%20Exfiltration%20Over%20Web%20Service/T1567.002%20-%20Exfiltration%20to%20Cloud%20Storage/README.md)
- [T1083 - File and Directory Discovery](../../../Tactics/10%20TA0007%20-%20Discovery/T1083%20-%20File%20and%20Directory%20Discovery/README.md)

## Used by

- [G1024 - Akira](../../Groups/G1024%20-%20Akira.md)
- [C0015 - C0015](../../Campaigns/C0015%20-%20C0015.md)
- [G1021 - Cinnamon Tempest](../../Groups/G1021%20-%20Cinnamon%20Tempest.md)
- [G1003 - Ember Bear](../../Groups/G1003%20-%20Ember%20Bear.md)
- [G1032 - INC Ransom](../../Groups/G1032%20-%20INC%20Ransom.md)
- [G1051 - Medusa Group](../../Groups/G1051%20-%20Medusa%20Group.md)
- [G0069 - MuddyWater](../../Groups/G0069%20-%20MuddyWater.md)
- [G1015 - Scattered Spider](../../Groups/G1015%20-%20Scattered%20Spider.md)
- [G1053 - Storm-0501](../../Groups/G1053%20-%20Storm-0501.md)
- [G0090 - WIRTE](../../Groups/G0090%20-%20WIRTE.md)

## Sources

- [Detecting Rclone](https://research.nccgroup.com/2021/05/27/detecting-rclone-an-effective-tool-for-exfiltration/)
- [DFIR Conti Bazar Nov 2021](https://thedfirreport.com/2021/11/29/continuing-the-bazar-ransomware-story/)
- [Rclone Wars](https://redcanary.com/blog/rclone-mega-extortion/)
- [Rclone](https://rclone.org)
- [DarkSide Ransomware Gang](https://unit42.paloaltonetworks.com/darkside-ransomware/)
