# T1641.001 - Transmitted Data Manipulation

[Mobile](../../../../README.md) / [Impact](../../README.md) / [T1641 - Data Manipulation](../README.md)

Adversaries may alter data en route to storage or other systems in order to manipulate external outcomes or hide activity. By manipulating transmitted data, adversaries may attempt to affect a business process, organizational understanding, or decision making.

Manipulation may be possible over a network connection or between system processes where there is an opportunity to deploy a tool that will intercept and change information. The type of modification and the impact it will have depends on the target transmission mechanism as well as the goals and objectives of the adversary. For complex systems, an adversary would likely need special expertise and possibly access to specialized software related to the system, typically gained through a prolonged information gathering campaign, in order to have the desired impact.

One method to achieve [Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1641/001) is by modifying the contents of the device clipboard. Malicious applications may monitor clipboard activity through the `ClipboardManager.OnPrimaryClipChangedListener` interface on Android to determine when clipboard contents have changed. Listening to clipboard activity, reading clipboard contents, and modifying clipboard contents requires no explicit application permissions and can be performed by applications running in the background. However, this behavior has changed with the release of Android 10.

Adversaries may use [Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1641/001) to replace text prior to being pasted. For example, replacing a copied Bitcoin wallet address with a wallet address that is under adversarial control.

[Transmitted Data Manipulation](https://attack.mitre.org/techniques/T1641/001) was seen within the Android/Clipper.C trojan. This sample was detected by ESET in an application distributed through the Google Play Store targeting cryptocurrency wallet numbers.(Citation: ESET Clipboard Modification February 2019)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1641/001)

**Tactics**  [Impact](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 10 prevents applications from accessing clipboard data unless the application is on the foreground or is set as the device’s default input method editor (IME).(Citation: Android 10 Privacy Changes) [Android 10 Privacy Changes](https://developer.android.com/about/versions/10/privacy/changes#clipboard-data)

## Procedure examples

- [S1094 - BRATA](../../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) has injected string contents into the device clipboard.(Citation: mcafee_brata_0421) [mcafee_brata_0421](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/brata-keeps-sneaking-into-google-play-now-targeting-usa-and-spain/)
- [S1062 - S.O.V.A.](../../../../Threat%20Intelligence/Software/Malware/S1062%20-%20S.O.V.A.md) — [S.O.V.A.](https://attack.mitre.org/software/S1062) can manipulate clipboard data to replace cryptocurrency addresses.(Citation: threatfabric_sova_0921) [threatfabric_sova_0921](https://www.threatfabric.com/blogs/sova-new-trojan-with-fowl-intentions.html)

## Detection strategies

- [DET0683 - Detection of Transmitted Data Manipulation](../../../../Defenses/Detection%20Strategies/DET0683%20-%20Detection%20of%20Transmitted%20Data%20Manipulation.md)

## Sources

- [ESET Clipboard Modification February 2019](https://www.eset.com/uk/about/newsroom/press-releases/first-clipper-malware-discovered-on-google-play-1/)
