# T1564.009 - Resource Forking

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1564 - Hide Artifacts](../README.md)

Adversaries may abuse resource forks to hide malicious code or executables to evade detection and bypass security applications. A resource fork provides applications a structured way to store resources such as thumbnail images, menu definitions, icons, dialog boxes, and code.(Citation: macOS Hierarchical File System Overview) Usage of a resource fork is identifiable when displaying a file’s extended attributes, using <code>ls -l@</code> or <code>xattr -l</code> commands. Resource forks have been deprecated and replaced with the application bundle structure. Non-localized resources are placed at the top level directory of an application bundle, while localized resources are placed in the <code>/Resources</code> folder.(Citation: Resource and Data Forks)(Citation: ELC Extended Attributes)

Adversaries can use resource forks to hide malicious data that may otherwise be stored directly in files. Adversaries can execute content with an attached resource fork, at a specified offset, that is moved to an executable location then invoked. Resource fork content may also be obfuscated/encrypted until execution.(Citation: sentinellabs resource named fork 2020)(Citation: tau bundlore erika noerenberg 2020)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1564/009)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Procedure examples

- [S0276 - Keydnap](../../../../Threat%20Intelligence/Software/Malware/S0276%20-%20Keydnap.md) — [Keydnap](https://attack.mitre.org/software/S0276) uses a resource fork to present a macOS JPEG or text file icon rather than the executable's icon assigned by the operating system.(Citation: OSX Keydnap malware) [OSX Keydnap malware](https://www.welivesecurity.com/2016/07/06/new-osxkeydnap-malware-hungry-credentials/)
- [S0402 - OSX/Shlayer](../../../../Threat%20Intelligence/Software/Malware/S0402%20-%20OSX%20-%20Shlayer.md) — [OSX/Shlayer](https://attack.mitre.org/software/S0402) has used a resource fork to hide a compressed binary file of itself from the terminal, Finder, and potentially evade traditional scanners.(Citation: tau bundlore erika noerenberg 2020)(Citation: sentinellabs resource named fork 2020) [tau bundlore erika noerenberg 2020](https://blogs.vmware.com/security/2020/06/tau-threat-analysis-bundlore-macos-mm-install-macos.html) · [sentinellabs resource named fork 2020](https://www.sentinelone.com/labs/resourceful-macos-malware-hides-in-named-fork/)

## Detection strategies

- [DET0584 - Detection Strategy for Resource Forking on macOS](../../../../Defenses/Detection%20Strategies/DET0584%20-%20Detection%20Strategy%20for%20Resource%20Forking%20on%20macOS.md)

## Mitigations

- [M1013 - Application Developer Guidance](../../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Configure applications to use the application bundle structure which leverages the <code>/Resources</code> folder location.(Citation: Apple App Security Overview) [Apple App Security Overview](https://support.apple.com/guide/security/app-security-overview-sec35dd877d0/1/web/1)

## Sources

- [tau bundlore erika noerenberg 2020](https://blogs.vmware.com/security/2020/06/tau-threat-analysis-bundlore-macos-mm-install-macos.html)
- [Resource and Data Forks](https://flylib.com/books/en/4.395.1.192/1/)
- [ELC Extended Attributes](https://eclecticlight.co/2020/10/24/theres-more-to-files-than-data-extended-attributes/)
- [sentinellabs resource named fork 2020](https://www.sentinelone.com/labs/resourceful-macos-malware-hides-in-named-fork/)
- [macOS Hierarchical File System Overview](http://tenon.com/products/codebuilder/User_Guide/6_File_Systems.html#anchor520553)
