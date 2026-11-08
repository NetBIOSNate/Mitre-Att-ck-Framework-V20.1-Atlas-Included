# T1036.006 - Space after Filename

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1036 - Masquerading](../README.md)

Adversaries can hide a program's true filetype by changing the extension of a file. With certain file types (specifically this does not work with .app extensions), appending a space to the end of a filename will change how the file is processed by the operating system.

For example, if there is a Mach-O executable file called <code>evil.bin</code>, when it is double clicked by a user, it will launch Terminal.app and execute. If this file is renamed to <code>evil.txt</code>, then when double clicked by a user, it will launch with the default text editing application (not executing the binary). However, if the file is renamed to <code>evil.txt </code> (note the space at the end), then when double clicked by a user, the true file type is determined by the OS and handled appropriately and the binary will be executed.(Citation: Mac Backdoors are back)

Adversaries can use this feature to trick users into double clicking benign-looking files of any format and ultimately executing something malicious.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1036/006)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [G0082 - APT38](../../../../Threat%20Intelligence/Groups/G0082%20-%20APT38.md) — [APT38](https://attack.mitre.org/groups/G0082) has put several spaces before a file extension to avoid detection and suspicion.(Citation: 1 - appv) [1 - appv](https://securelist.com/bluenoroff-methods-bypass-motw/108383/)
- [S0276 - Keydnap](../../../../Threat%20Intelligence/Software/Malware/S0276%20-%20Keydnap.md) — [Keydnap](https://attack.mitre.org/software/S0276) puts a space after a false .jpg extension so that execution actually goes through the Terminal.app program.(Citation: synack 2016 review) [synack 2016 review](https://objective-see.org/blog/blog_0x16.html)

## Detection strategies

- [DET0292 - Masquerading via Space After Filename - Behavioral Detection Strategy](../../../../Defenses/Detection%20Strategies/DET0292%20-%20Masquerading%20via%20Space%20After%20Filename%20-%20Behavioral%20Detection%20Strategy.md)

## Sources

- [Mac Backdoors are back](https://arstechnica.com/security/2016/07/after-hiatus-in-the-wild-mac-backdoors-are-suddenly-back/)
