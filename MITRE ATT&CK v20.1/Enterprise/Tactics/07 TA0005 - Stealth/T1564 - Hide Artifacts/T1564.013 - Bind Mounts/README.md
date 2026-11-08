# T1564.013 - Bind Mounts

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1564 - Hide Artifacts](../README.md)

Adversaries may abuse bind mounts on file structures to hide their activity and artifacts from native utilities. A bind mount maps a directory or file from one location on the filesystem to another, similar to a shortcut on Windows. It’s commonly used to provide access to specific files or directories across different environments, such as inside containers or chroot environments, and requires sudo access. 

Adversaries may use bind mounts to map either an empty directory or a benign `/proc` directory to a malicious process’s `/proc` directory. Using the commands `mount –o bind /proc/benign-process /proc/malicious-process` (or `mount –B`), the malicious process's `/proc` directory is overlayed with the contents of a benign process's `/proc` directory. When system utilities query process activity, such as `ps` and `top`, the kernel follows the bind mount and presents the benign directory’s contents instead of the malicious process's actual `/proc` directory. As a result, these utilities display information that appears to come from the benign process, effectively hiding the malicious process's metadata, executable, or other artifacts from detection.(Citation: Cado Security Commando Cat 2024)(Citation: Ahn Lab CoinMiner 2023)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564/013)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md)

## Detection strategies

- [DET0428 - Detection Strategy for Bind Mounts on Linux](../../../../Defenses/Detection%20Strategies/DET0428%20-%20Detection%20Strategy%20for%20Bind%20Mounts%20on%20Linux.md)

## Procedure examples

- [C0035 - KV Botnet Activity](../../../../Threat%20Intelligence/Campaigns/C0035%20-%20KV%20Botnet%20Activity.md) — [KV Botnet Activity](https://attack.mitre.org/campaigns/C0035) leveraged a bind mount to bind itself to the `/proc/` file path before deleting its files from the `/tmp/` directory.(Citation: Lumen KVBotnet 2023) [Lumen KVBotnet 2023](https://blog.lumen.com/routers-roasting-on-an-open-firewall-the-kv-botnet-investigation/)

## Sources

- [Ahn Lab CoinMiner 2023](https://asec.ahnlab.com/en/51908/)
- [Cado Security Commando Cat 2024](https://www.cadosecurity.com/blog/the-nine-lives-of-commando-cat-analysing-a-novel-malware-campaign-targeting-docker)
