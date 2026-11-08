# T1624 - Event Triggered Execution

[Mobile](../../../README.md) / [Persistence](../README.md)

Adversaries may establish persistence using system mechanisms that trigger execution based on specific events. Mobile operating systems have means to subscribe to events such as receiving an SMS message, device boot completion, or other device activities. 

Adversaries may abuse these mechanisms as a means of maintaining persistent access to a victim via automatically and repeatedly executing malicious code. After gaining access to a victim’s system, adversaries may create or modify event triggers to point to malicious content that will be executed whenever the event trigger is invoked.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1624)

**Tactics**  [Persistence](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md)

## Sub-techniques

- [T1624.001 - Broadcast Receivers](T1624.001%20-%20Broadcast%20Receivers/README.md)

## Procedure examples

- [S1079 - BOULDSPY](../../../Threat%20Intelligence/Software/Malware/S1079%20-%20BOULDSPY.md) — [BOULDSPY](https://attack.mitre.org/software/S1079) uses a background service that can restart itself when the parent activity is stopped.(Citation: lookout_bouldspy_0423) [lookout_bouldspy_0423](https://www.lookout.com/blog/iranian-spyware-bouldspy)
- [S1231 - GodFather](../../../Threat%20Intelligence/Software/Malware/S1231%20-%20GodFather.md) — [GodFather](https://attack.mitre.org/software/S1231) has executed when victims utilize their trusted banking apps, as the malware redirects the victim to using a malicious version of the banking app.(Citation: ZimperiumOrtegaPratapagiri_GodFather_Jun2025) [ZimperiumOrtegaPratapagiri_GodFather_Jun2025](https://zimperium.com/blog/your-mobile-app-their-playground-the-dark-side-of-the-virtualization)

## Mitigations

- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — Android 8 introduced additional limitations on the implicit intents that an application can register for.(Citation: Android Changes to System Broadcasts) [Android Changes to System Broadcasts](https://developer.android.com/guide/components/broadcasts#changes-system-broadcasts)

## Detection strategies

- [DET0647 - Detection of Event Triggered Execution](../../../Defenses/Detection%20Strategies/DET0647%20-%20Detection%20of%20Event%20Triggered%20Execution.md)
