# T1458 - Replication Through Removable Media

[Mobile](../../../README.md) / [Initial Access](../README.md)

Adversaries may move onto devices by exploiting or copying malware to devices connected via USB. In the case of Lateral Movement, adversaries may utilize the physical connection of a device to a compromised or malicious charging station or PC to bypass application store requirements and install malicious applications directly.(Citation: Lau-Mactans) In the case of Initial Access, adversaries may attempt to exploit the device via the connection to gain access to data stored on the device.(Citation: Krebs-JuiceJacking) Examples of this include: 
 
* Exploiting insecure bootloaders in a Nexus 6 or 6P device over USB and gaining the ability to perform actions including intercepting phone calls, intercepting network traffic, and obtaining the device physical location.(Citation: IBM-NexusUSB) 
* Exploiting weakly-enforced security boundaries in Android devices such as the Google Pixel 2 over USB.(Citation: GoogleProjectZero-OATmeal) 
* Products from Cellebrite and Grayshift purportedly that can exploit some iOS devices using physical access to the data port to unlock the passcode.(Citation: Computerworld-iPhoneCracking)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1458)

**Tactics**  [Initial Access](../README.md), [Lateral Movement](../../08%20TA0033%20-%20Lateral%20Movement/README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S0315 - DualToy](../../../Threat%20Intelligence/Software/Malware/S0315%20-%20DualToy.md) — [DualToy](https://attack.mitre.org/software/S0315) side loads malicious or risky apps to both Android and iOS devices via a USB connection.(Citation: PaloAlto-DualToy) [PaloAlto-DualToy](https://researchcenter.paloaltonetworks.com/2016/09/dualtoy-new-windows-trojan-sideloads-risky-apps-to-android-and-ios-devices/)
- [S0312 - WireLurker](../../../Threat%20Intelligence/Software/Malware/S0312%20-%20WireLurker.md) — [WireLurker](https://attack.mitre.org/software/S0312) monitors for iOS devices connected via USB to an infected OSX computer and installs downloaded third-party applications or automatically generated malicious applications onto the device.(Citation: PaloAlto-WireLurker) [PaloAlto-WireLurker](https://researchcenter.paloaltonetworks.com/2014/11/wirelurker-new-era-os-x-ios-malware/)

## Mitigations

- [M1012 - Enterprise Policy](../../../Defenses/Mitigations/M1012%20-%20Enterprise%20Policy.md) — Enterprise policies should prevent enabling USB debugging on Android devices unless specifically needed (e.g., if the device is used for application development).
- [M1003 - Lock Bootloader](../../../Defenses/Mitigations/M1003%20-%20Lock%20Bootloader.md) — Users should ensure bootloaders are locked to prevent arbitrary operating system code from being flashed onto the device.
- [M1001 - Security Updates](../../../Defenses/Mitigations/M1001%20-%20Security%20Updates.md) — Security updates often contain patches for vulnerabilities.
- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — iOS 11.4.1 and higher introduce USB Restricted Mode, which disables data access through the device's charging port under certain conditions (making the port only usable for power), likely preventing this technique from working.(Citation: Elcomsoft-iOSRestricted) [Elcomsoft-iOSRestricted](https://blog.elcomsoft.com/2018/09/ios-12-enhances-usb-restricted-mode/)
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be advised not to use public charging stations or computers to charge their devices. Instead, users should be issued a charger acquired from a trustworthy source. Users should be advised not to click on device prompts to trust attached computers unless absolutely necessary.

## Detection strategies

- [DET0691 - Detection of Replication Through Removable Media](../../../Defenses/Detection%20Strategies/DET0691%20-%20Detection%20of%20Replication%20Through%20Removable%20Media.md)

## Sources

- [Krebs-JuiceJacking](http://krebsonsecurity.com/2011/08/beware-of-juice-jacking/)
- [GoogleProjectZero-OATmeal](https://googleprojectzero.blogspot.com/2018/09/oatmeal-on-universal-cereal-bus.html)
- [Lau-Mactans](https://media.blackhat.com/us-13/US-13-Lau-Mactans-Injecting-Malware-into-iOS-Devices-via-Malicious-Chargers-WP.pdf)
- [Computerworld-iPhoneCracking](https://www.techcentral.ie/two-vendors-now-sell-iphone-cracking-technology-police-buying/)
- [IBM-NexusUSB](https://securityintelligence.com/android-vulnerabilities-attacking-nexus-6-and-6p-custom-boot-modes/)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/physical-threats/PHY-1.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/physical-threats/PHY-2.html)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/stack-threats/STA-6.html)
