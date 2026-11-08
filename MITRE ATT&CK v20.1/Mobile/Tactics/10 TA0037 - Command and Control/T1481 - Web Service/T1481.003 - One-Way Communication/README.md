# T1481.003 - One-Way Communication

[Mobile](../../../../README.md) / [Command and Control](../../README.md) / [T1481 - Web Service](../README.md)

Adversaries may use an existing, legitimate external Web service channel as a means for sending commands to a compromised system without receiving return output. Compromised systems may leverage popular websites and social media to host command and control (C2) instructions. Those infected systems may opt to send the output from those commands back over a different C2 channel, including to another distinct Web service. Alternatively, compromised systems may return no output at all in cases where adversaries want to send instructions to systems and do not want a response. 

 

Popular websites and social media, acting as a mechanism for C2, may give a significant amount of cover. This is due to the likelihood that hosts within a network are already communicating with them prior to a compromise. Using common services, such as those offered by Google or Twitter, makes it easier for adversaries to hide in expected noise. Web service providers commonly use SSL/TLS encryption, giving adversaries an added level of protection.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1481/003)

**Tactics**  [Command and Control](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Detection strategies

- [DET0610 - Detection of One-Way Communication](../../../../Defenses/Detection%20Strategies/DET0610%20-%20Detection%20of%20One-Way%20Communication.md)

## Procedure examples

- [S0302 - Twitoor](../../../../Threat%20Intelligence/Software/Malware/S0302%20-%20Twitoor.md) — [Twitoor](https://attack.mitre.org/software/S0302) can be controlled via Twitter.(Citation: ESET-Twitoor) [ESET-Twitoor](http://www.welivesecurity.com/2016/08/24/first-twitter-controlled-android-botnet-discovered/)
