# T1414 - Clipboard Data

[Mobile](../../../README.md) / [Credential Access](../README.md)

Adversaries may abuse clipboard manager APIs to obtain sensitive information copied to the device clipboard. For example, passwords being copied and pasted from a password manager application could be captured by a malicious application installed on the device.(Citation: Fahl-Clipboard) 

 

On Android, applications can use the `ClipboardManager.OnPrimaryClipChangedListener()` API to register as a listener and monitor the clipboard for changes. However, starting in Android 10, this can only be used if the application is in the foreground, or is set as the device’s default input method editor (IME).(Citation: Github Capture Clipboard 2019)(Citation: Android 10 Privacy Changes) 

 

On iOS, this can be accomplished by accessing the `UIPasteboard.general.string` field. However, starting in iOS 14, upon accessing the clipboard, the user will be shown a system notification if the accessed text originated in a different application. For example, if the user copies the text of an iMessage from the Messages application, the notification will read “application_name has pasted from Messages” when the text was pasted in a different application.(Citation: UIPPasteboard)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1414)

**Tactics**  [Credential Access](../README.md), [Collection](../../09%20TA0035%20-%20Collection/README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Procedure examples

- [S1079 - BOULDSPY](../../../Threat%20Intelligence/Software/Malware/S1079%20-%20BOULDSPY.md) — [BOULDSPY](https://attack.mitre.org/software/S1079) can collect clipboard data.(Citation: lookout_bouldspy_0423) [lookout_bouldspy_0423](https://www.lookout.com/blog/iranian-spyware-bouldspy)
- [S0421 - GolfSpy](../../../Threat%20Intelligence/Software/Malware/S0421%20-%20GolfSpy.md) — [GolfSpy](https://attack.mitre.org/software/S0421) can obtain clipboard contents.(Citation: Trend Micro Bouncing Golf 2019) [Trend Micro Bouncing Golf 2019](https://blog.trendmicro.com/trendlabs-security-intelligence/mobile-cyberespionage-campaign-bouncing-golf-affects-middle-east/)
- [S1241 - RatMilad](../../../Threat%20Intelligence/Software/Malware/S1241%20-%20RatMilad.md) — [RatMilad](https://attack.mitre.org/software/S1241) has collected clipboard content.(Citation: ZimperiumGupta_RatMilad_Oct2022) [ZimperiumGupta_RatMilad_Oct2022](https://zimperium.com/blog/we-smell-a-ratmilad-mobile-spyware)
- [S0295 - RCSAndroid](../../../Threat%20Intelligence/Software/Malware/S0295%20-%20RCSAndroid.md) — [RCSAndroid](https://attack.mitre.org/software/S0295) can monitor clipboard content.(Citation: TrendMicro-RCSAndroid) [TrendMicro-RCSAndroid](http://blog.trendmicro.com/trendlabs-security-intelligence/hacking-team-rcsandroid-spying-tool-listens-to-calls-roots-devices-to-get-in/)
- [S0297 - XcodeGhost](../../../Threat%20Intelligence/Software/Malware/S0297%20-%20XcodeGhost.md) — [XcodeGhost](https://attack.mitre.org/software/S0297) can read and write data in the user’s clipboard.(Citation: PaloAlto-XcodeGhost) [PaloAlto-XcodeGhost](http://researchcenter.paloaltonetworks.com/2015/09/update-xcodeghost-attacker-can-phish-passwords-and-open-urls-though-infected-apps/)

## Mitigations

- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 10 introduced changes to prevent applications from accessing clipboard data if they are not in the foreground or set as the device’s default IME.(Citation: Android 10 Privacy Changes) [Android 10 Privacy Changes](https://developer.android.com/about/versions/10/privacy/changes#clipboard-data)

## Detection strategies

- [DET0643 - Detection of Clipboard Data](../../../Defenses/Detection%20Strategies/DET0643%20-%20Detection%20of%20Clipboard%20Data.md)

## Sources

- [Android 10 Privacy Changes](https://developer.android.com/about/versions/10/privacy/changes#clipboard-data)
- [UIPPasteboard](https://developer.apple.com/documentation/uikit/uipasteboard)
- [Fahl-Clipboard](https://saschafahl.de/static/paper/pwmanagers2013.pdf)
- [Github Capture Clipboard 2019](https://github.com/grepx/android-clipboard-security)
- [NIST Mobile Threat Catalogue](https://pages.nist.gov/mobile-threat-catalogue/application-threats/APP-35.html)
