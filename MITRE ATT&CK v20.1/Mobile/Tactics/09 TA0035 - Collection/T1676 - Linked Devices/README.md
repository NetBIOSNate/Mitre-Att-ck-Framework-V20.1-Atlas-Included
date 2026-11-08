# T1676 - Linked Devices

[Mobile](../../../README.md) / [Collection](../README.md)

Adversaries may abuse the “linked devices” feature on messaging applications, such as Signal and WhatsApp, to register the user’s account to an adversary-controlled device. By abusing the “linked devices” feature, adversaries may achieve and maintain persistence through the user’s account, may collect information, such as the user’s messages and contacts list, and may send future messages from the linked device.

Signal is a messaging application that uses the open-source Signal Protocol to encrypt messages and calls; similarly, WhatsApp is a messaging application that has end-to-end encryption and other security measures to protect messages and calls. Both applications have a “linked devices” feature that allows users to access their Signal and/or WhatsApp accounts from different devices, such as a Windows or Mac desktop, an iPad or an Android tablet.(Citation: WhatsApp_LinkDevice_NoDate)(Citation: Signal_LinkedDevices_NoDate)

Adversaries may use [Phishing](https://attack.mitre.org/techniques/T1660) techniques to trick the user into scanning a quick-response (QR) code, which is used to link the user’s Signal and/or WhatsApp account to an adversary-controlled device. For example, adversaries may masquerade QR codes as group invites, security alerts or as legitimate instructions for pairing linked devices. 
Upon scanning the QR code in Signal, users may click on the “Transfer Message History” option to sync the linked devices, which may allow adversaries to collect more information about the user. Upon scanning the QR code in WhatsApp, the user’s device will automatically send an end-to-end encrypted copy of recent message history to the adversary-controlled device.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1676)

**Tactics**  [Persistence](../../03%20TA0028%20-%20Persistence/README.md), [Collection](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Detection strategies

- [DET0716 - Detection of Linked Devices](../../../Defenses/Detection%20Strategies/DET0716%20-%20Detection%20of%20Linked%20Devices.md)

## Procedure examples

- [G0034 - Sandworm Team](../../../Threat%20Intelligence/Groups/G0034%20-%20Sandworm%20Team.md) — [Sandworm Team](https://attack.mitre.org/groups/G0034) has used the linked devices feature to connect Signal accounts on devices captured on the battlefield to adversary-controlled infrastructure for follow-on exploitation.(Citation: GTIG_SignalAbuse_Feb2025) [GTIG_SignalAbuse_Feb2025](https://cloud.google.com/blog/topics/threat-intelligence/russia-targeting-signal-messenger)
- [G1033 - Star Blizzard](../../../Threat%20Intelligence/Groups/G1033%20-%20Star%20Blizzard.md) — [Star Blizzard](https://attack.mitre.org/groups/G1033) has used the linked devices feature to connect WhatsApp accounts to adversary-controlled infrastructure and/or the WhatsApp Web portal for message exfiltration.(Citation: MSTI_StarBlizzard_Jan2025) [MSTI_StarBlizzard_Jan2025](https://www.microsoft.com/en-us/security/blog/2025/01/16/new-star-blizzard-spear-phishing-campaign-targets-whatsapp-accounts/)

## Mitigations

- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — For Android devices, users should be advised to enable Google Play Protect, which checks the device itself and the applications for malicious behavior. For iOS devices, users who are concerned about being targeted should consider enabling Lockdown Mode, which provides extreme protection of the device as well as data stored and transmitted. In general, users should be advised against scanning QR codes and/or clicking on suspicious links or text messages, which may masquerade as device-linking instructions by Signal or WhatsApp.

## Sources

- [Signal_LinkedDevices_NoDate](https://support.signal.org/hc/en-us/articles/360007320551-Linked-Devices)
- [WhatsApp_LinkDevice_NoDate](https://faq.whatsapp.com/1317564962315842/?helpref=faq_content&cms_platform=web)
