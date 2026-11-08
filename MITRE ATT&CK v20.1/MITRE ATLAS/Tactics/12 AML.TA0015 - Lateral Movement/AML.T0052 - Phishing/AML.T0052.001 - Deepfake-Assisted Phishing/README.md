# AML.T0052.001 - Deepfake-Assisted Phishing

[MITRE ATLAS](../../../../README.md) / [AML.TA0015 - Lateral Movement](../../README.md) / [AML.T0052 - Phishing](../README.md)

Adversaries may use deepfakes (AI-generated synthetic images, audio, or video) in phishing campaigns to impersonate trusted individuals, executives, or organizations. These attacks exploit human trust by presenting fraudulent voice or video communications as legitimate, enabling adversaries to manipulate targets into disclosing credentials, transferring funds, or granting access to systems.

Voice deepfakes (AI-cloned voices) are used in vishing  [vishing](https://www.social-engineer.org/framework/attack-vectors/vishing/) (voice phishing) attacks over telephone or VoIP. Adversaries can clone a target's voice using a few seconds  [valle](https://www.microsoft.com/en-us/research/project/vall-e-x/) of publicly available audio from speeches, earnings calls, podcasts, or social media  [voice](https://cloud.google.com/blog/topics/threat-intelligence/ai-powered-voice-spoofing-vishing-attacks). These cloned voices are then used in pre-recorded voicemail messages or live phone calls. Video deepfakes can impersonate a trusted individual's face and voice. Adversaries use publicly available video from company meetings, earnings calls, or social media to create convincing AI-generated video of target individuals. They are used in live video conference calls or recorded video messages. AI-generated content has advanced to the point that it is often difficult to identify as synthetic  [fbi](https://www.ic3.gov/PSA/2025/PSA250515/).

Adversaries may first perform [Obtain Capabilities](../../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/README.md): [Generative AI](../../../02%20AML.TA0003%20-%20Resource%20Development/AML.T0016%20-%20Obtain%20Capabilities/AML.T0016.002%20-%20Generative%20AI/README.md) followed by [Generate Deepfakes](../../../03%20AML.TA0001%20-%20AI%20Attack%20Adaptation/AML.T0088%20-%20Generate%20Deepfakes/README.md) in preparation for their [Phishing](../../../04%20AML.TA0004%20-%20Initial%20Access/AML.T0052%20-%20Phishing/README.md) campaign. Deepfake phishing campaigns often utilize other communication channels (such as email, SMS, or instant messaging) for layered social engineering attacks  [aiid839](https://incidentdatabase.ai/cite/839/).

These attacks span a wide range of victims and attack types, demonstrating the breadth of deepfake-enabled fraud. Adversaries have conducted extensive deepfake-assisted phishing campaigns against the individuals, including targeted scams  [aiid564](https://incidentdatabase.ai/cite/564/)  [oecd1](https://oecd.ai/en/incidents/2026-04-06-ca7a)  [aiid1280](https://incidentdatabase.ai/cite/1280/)  [aiid1285](https://incidentdatabase.ai/cite/1285/), as well as large-scale credential harvesting campaigns targeting billions of users  [aiid839](https://incidentdatabase.ai/cite/839/)  [aiid941](https://incidentdatabase.ai/cite/941/). Adversaries have used deepfakes to impersonate executives  [aiid1100](https://incidentdatabase.ai/cite/1100/), causing business entities to suffer significant financial losses from  [aiid634](https://incidentdatabase.ai/cite/634/)  [aiid147](https://incidentdatabase.ai/cite/147/). There are also reports of government officials being targeted in widespread campaigns  [fbi](https://www.ic3.gov/PSA/2025/PSA250515/)  [aiid927](https://incidentdatabase.ai/cite/927/).

The attacks span communication channels including voice deepfakes for vishing  [aiid567](https://incidentdatabase.ai/cite/567/) and video deepfakes in conference calls  [aiid634](https://incidentdatabase.ai/cite/634/), as well as multi-channel campaigns combining phone, email, and messaging platforms  [aiid839](https://incidentdatabase.ai/cite/839/).

**Tactics**  [AML.TA0004 - Initial Access](../../../04%20AML.TA0004%20-%20Initial%20Access/README.md), [AML.TA0015 - Lateral Movement](../../README.md)

**Platforms**  [Enterprise](../../../../Platforms/Enterprise.md)

**Maturity**  Realized

## Mitigations

- [AML.M0018 - User Training](../../../../Mitigations/AML.M0018%20-%20User%20Training.md) — Train users on deepfake threats, including how to recognize synthetic voice, video, and text. Recommend verification through independent channels (e.g. known call-back number) before processing sensitive requests or providing sensitive information via voice or video calls.
- [AML.M0034 - Deepfake Detection](../../../../Mitigations/AML.M0034%20-%20Deepfake%20Detection.md) — Deploy technical controls to detect and block synthetic audio and video. This includes AI-based analysis tools that examine media for artifacts indicative deepfakes.

## References

- [AI Incident Database - LastPass CEO Voice Deepfake Attempt](https://incidentdatabase.ai/cite/1100/)
- [Reported Use of AI Voice and Identity Manipulation in the 'Phantom Hacker' Fraud Scheme](https://incidentdatabase.ai/cite/1280/)
- [Purportedly AI-Generated Jason Momoa Deepfake Used in Romance Scam](https://incidentdatabase.ai/cite/1285/)
- [Reported AI-Cloned Voice Used to Deceive Hong Kong Bank Manager in Purported $35 Million Fraud Scheme](https://incidentdatabase.ai/cite/147/)
- [Voice deepfake targets bank in failed transfer scam](https://incidentdatabase.ai/cite/564/)
- [Deepfake Voice Exploit Compromises Retool's Cloud Services](https://incidentdatabase.ai/cite/567/)
- [Alleged Deepfake CFO Scam Reportedly Costs Multinational Engineering Firm Arup $25 Million](https://incidentdatabase.ai/cite/634/)
- [Purportedly AI-Driven Phishing Scam Uses Spoofed Google Call to Attempt Gmail Breach](https://incidentdatabase.ai/cite/839/)
- [Italian Defense Minister Voice Clone](https://incidentdatabase.ai/cite/927/)
- [AI-Driven Phishing Scam Uses Deepfake Robocalls to Target Gmail Users](https://incidentdatabase.ai/cite/941/)
- [FBI Public Service Advisory: Scammers are deepfaking voices of senior US government officials](https://www.ic3.gov/PSA/2025/PSA250515/)
- [AI-Generated Voice Used in Scam Targeting Drica Moraes' Contacts](https://oecd.ai/en/incidents/2026-04-06-ca7a)
- [VALL-E Family: Neural codec language models for speech synthesis](https://www.microsoft.com/en-us/research/project/vall-e-x/)
- [Vishing - Social-Engineer Framework](https://www.social-engineer.org/framework/attack-vectors/vishing/)
- [AI-powered voice spoofing: Understanding and defending against vishing attacks](https://cloud.google.com/blog/topics/threat-intelligence/ai-powered-voice-spoofing-vishing-attacks)

[Official ATLAS record](https://atlas.mitre.org/techniques/AML.T0052.001)
