# T1481 - Web Service

[Mobile](../../../README.md) / [Command and Control](../README.md)

Adversaries may use an existing, legitimate external Web service as a means for relaying data to/from a compromised system. Popular websites and social media, acting as a mechanism for C2, may give a significant amount of cover. This is due to the likelihood that hosts within a network are already communicating with them prior to a compromise. Using common services, such as those offered by Google or Twitter, makes it easier for adversaries to hide in expected noise. Web service providers commonly use SSL/TLS encryption, giving adversaries an added level of protection. 

 

Use of Web services may also protect back-end C2 infrastructure from discovery through malware binary analysis, or enable operational resiliency (since this infrastructure may be dynamically changed).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1481)

**Tactics**  [Command and Control](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1481.002 - Bidirectional Communication](T1481.002%20-%20Bidirectional%20Communication/README.md)
- [T1481.001 - Dead Drop Resolver](T1481.001%20-%20Dead%20Drop%20Resolver/README.md)
- [T1481.003 - One-Way Communication](T1481.003%20-%20One-Way%20Communication/README.md)

## Procedure examples

- [S1214 - Android/SpyAgent](../../../Threat%20Intelligence/Software/Malware/S1214%20-%20Android%20-%20SpyAgent.md) — [Android/SpyAgent](https://attack.mitre.org/software/S1214)’s payload has obtained the C2 address via Twitter accounts.(Citation: McAfee MoqHao 2019) [McAfee MoqHao 2019](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/moqhao-related-android-spyware-targeting-japan-and-korea-found-on-google-play/)

## Detection strategies

- [DET0672 - Detection of Web Service](../../../Defenses/Detection%20Strategies/DET0672%20-%20Detection%20of%20Web%20Service.md)
