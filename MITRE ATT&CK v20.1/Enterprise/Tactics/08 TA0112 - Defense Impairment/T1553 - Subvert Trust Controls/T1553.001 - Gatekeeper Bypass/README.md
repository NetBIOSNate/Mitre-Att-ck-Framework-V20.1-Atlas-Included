# T1553.001 - Gatekeeper Bypass

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1553 - Subvert Trust Controls](../README.md)

Adversaries may modify file attributes and subvert Gatekeeper functionality to evade user prompts and execute untrusted programs. Gatekeeper is a set of technologies that act as layer of Apple’s security model to ensure only trusted applications are executed on a host. Gatekeeper was built on top of File Quarantine in Snow Leopard (10.6, 2009) and has grown to include Code Signing, security policy compliance, Notarization, and more. Gatekeeper also treats applications running for the first time differently than reopened applications.(Citation: TheEclecticLightCompany Quarantine and the flag)(Citation: TheEclecticLightCompany apple notarization )

Based on an opt-in system, when files are downloaded an extended attribute (xattr) called `com.apple.quarantine` (also known as a quarantine flag) can be set on the file by the application performing the download. Launch Services opens the application in a suspended state. For first run applications with the quarantine flag set, Gatekeeper executes the following functions:

1. Checks extended attribute – Gatekeeper checks for the quarantine flag, then provides an alert prompt to the user to allow or deny execution.(Citation: OceanLotus for OS X)(Citation: 20 macOS Common Tools and Techniques)

2. Checks System Policies - Gatekeeper checks the system security policy, allowing execution of apps downloaded from either just the App Store or the App Store and identified developers.

3. Code Signing – Gatekeeper checks for a valid code signature from an Apple Developer ID.

4. Notarization - Using the `api.apple-cloudkit.com` API, Gatekeeper reaches out to Apple servers to verify or pull down the notarization ticket and ensure the ticket is not revoked. Users can override notarization, which will result in a prompt of executing an “unauthorized app” and the security policy will be modified.

Adversaries can subvert one or multiple security controls within Gatekeeper checks through logic errors (e.g. [Exploitation for Stealth](https://attack.mitre.org/techniques/T1211)), unchecked file types, and external libraries. For example, prior to macOS 13 Ventura, code signing and notarization checks were only conducted on first launch, allowing adversaries to write malicious executables to previously opened applications in order to bypass Gatekeeper security checks.(Citation: theevilbit gatekeeper bypass 2021)(Citation: Application Bundle Manipulation Brandon Dalton)

Applications and files loaded onto the system from a USB flash drive, optical disk, external hard drive, from a drive shared over the local network, or using the curl command may not set the quarantine flag. Additionally, it is possible to avoid setting the quarantine flag using [Drive-by Compromise](https://attack.mitre.org/techniques/T1189).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1553/001)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [macOS](../../../../Platforms/macOS.md)

## Detection strategies

- [DET0288 - Detect Gatekeeper Bypass via Quarantine Flag and Trust Control Manipulation](../../../../Defenses/Detection%20Strategies/DET0288%20-%20Detect%20Gatekeeper%20Bypass%20via%20Quarantine%20Flag%20and%20Trust%20Control%20Manipulation.md)

## Procedure examples

- [S0369 - CoinTicker](../../../../Threat%20Intelligence/Software/Malware/S0369%20-%20CoinTicker.md) — [CoinTicker](https://attack.mitre.org/software/S0369) downloads the EggShell mach-o binary using curl, which does not set the quarantine flag.(Citation: CoinTicker 2019) [CoinTicker 2019](https://blog.malwarebytes.com/threat-analysis/2018/10/mac-cryptocurrency-ticker-app-installs-backdoors/)
- [S1153 - Cuckoo Stealer](../../../../Threat%20Intelligence/Software/Malware/S1153%20-%20Cuckoo%20Stealer.md) — [Cuckoo Stealer](https://attack.mitre.org/software/S1153) can use `xattr -d com.apple.quarantine` to remove the quarantine flag attribute.(Citation: Kandji Cuckoo April 2024)(Citation: SentinelOne Cuckoo Stealer May 2024) [Kandji Cuckoo April 2024](https://www.kandji.io/blog/malware-cuckoo-infostealer-spyware) · [SentinelOne Cuckoo Stealer May 2024](https://www.sentinelone.com/blog/macos-cuckoo-stealer-ensuring-detection-and-defense-as-new-samples-rapidly-emerge/)
- [S1016 - MacMa](../../../../Threat%20Intelligence/Software/Malware/S1016%20-%20MacMa.md) — [MacMa](https://attack.mitre.org/software/S1016) has removed the `com.apple.quarantineattribute` from the dropped file, `$TMPDIR/airportpaird`.(Citation: ESET DazzleSpy Jan 2022) [ESET DazzleSpy Jan 2022](https://www.welivesecurity.com/2022/01/25/watering-hole-deploys-new-macos-malware-dazzlespy-asia/)
- [S0402 - OSX/Shlayer](../../../../Threat%20Intelligence/Software/Malware/S0402%20-%20OSX%20-%20Shlayer.md) — If running with elevated privileges, [OSX/Shlayer](https://attack.mitre.org/software/S0402) has used the <code>spctl</code> command to disable Gatekeeper protection for a downloaded file. [OSX/Shlayer](https://attack.mitre.org/software/S0402) can also leverage system links pointing to bash scripts in the downloaded DMG file to bypass Gatekeeper, a flaw patched in macOS 11.3 and later versions. [OSX/Shlayer](https://attack.mitre.org/software/S0402) has been Notarized by Apple, resulting in successful passing of additional Gatekeeper checks.(Citation: Carbon Black Shlayer Feb 2019)(Citation: Shlayer jamf gatekeeper bypass 2021)(Citation: objectivesee osx.shlayer apple approved 2020) [Carbon Black Shlayer Feb 2019](https://blogs.vmware.com/security/2020/02/vmware-carbon-black-tau-threat-analysis-shlayer-macos.html) · [Shlayer jamf gatekeeper bypass 2021](https://www.jamf.com/blog/shlayer-malware-abusing-gatekeeper-bypass-on-macos/) · [objectivesee osx.shlayer apple approved 2020](https://objective-see.com/blog/blog_0x4E.html)
- [S0352 - OSX_OCEANLOTUS.D](../../../../Threat%20Intelligence/Software/Malware/S0352%20-%20OSX_OCEANLOTUS.D.md) — [OSX_OCEANLOTUS.D](https://attack.mitre.org/software/S0352) uses the command <code>xattr -d com.apple.quarantine</code> to remove the quarantine file attribute used by Gatekeeper.(Citation: Trend Micro MacOS Backdoor November 2020)(Citation: 20 macOS Common Tools and Techniques) [Trend Micro MacOS Backdoor November 2020](https://www.trendmicro.com/en_us/research/20/k/new-macos-backdoor-connected-to-oceanlotus-surfaces.html) · [20 macOS Common Tools and Techniques](https://labs.sentinelone.com/20-common-tools-techniques-used-by-macos-threat-actors-malware/)
- [S0658 - XCSSET](../../../../Threat%20Intelligence/Software/Malware/S0658%20-%20XCSSET.md) — [XCSSET](https://attack.mitre.org/software/S0658) has dropped a malicious applet into an app's `.../Contents/MacOS/` folder of a previously launched app to bypass Gatekeeper's security checks on first launch apps (prior to macOS 13).(Citation: Application Bundle Manipulation Brandon Dalton) [Application Bundle Manipulation Brandon Dalton](https://redcanary.com/blog/mac-application-bundles/)

## Mitigations

- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — System settings can prevent applications from running that haven't been downloaded through the Apple Store which can help mitigate some of these issues.

## Sources

- [Application Bundle Manipulation Brandon Dalton](https://redcanary.com/blog/mac-application-bundles/)
- [theevilbit gatekeeper bypass 2021](https://theevilbit.github.io/posts/gatekeeper_not_a_bypass/)
- [OceanLotus for OS X](https://www.alienvault.com/blogs/labs-research/oceanlotus-for-os-x-an-application-bundle-pretending-to-be-an-adobe-flash-update)
- [TheEclecticLightCompany Quarantine and the flag](https://eclecticlight.co/2020/10/29/quarantine-and-the-quarantine-flag/)
- [TheEclecticLightCompany apple notarization ](https://eclecticlight.co/2020/08/28/how-notarization-works/)
- [20 macOS Common Tools and Techniques](https://labs.sentinelone.com/20-common-tools-techniques-used-by-macos-threat-actors-malware/)
