# AML.CS0009 - Tay Poisoning

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Microsoft created Tay, a Twitter chatbot designed to engage and entertain users.
While previous chatbots used pre-programmed scripts
to respond to prompts, Tay's machine learning capabilities allowed it to be
directly influenced by its conversations.

A coordinated attack encouraged malicious users to tweet abusive and offensive language at Tay,
which eventually led to Tay generating similarly inflammatory content towards other users.

Microsoft decommissioned Tay within 24 hours of its launch and issued a public apology
with lessons learned from the bot's failure.

**Type**  Incident

**Actor**  4chan Users

**Target**  Microsoft's Tay AI Chatbot

**Reporter**  Microsoft

**Activity period**  2016-03-23 to 2016-03-24

## Procedure steps

### Step S00

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0047 - AI-Enabled Product or Service](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md)

Adversaries were able to interact with Tay via Twitter messages.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0010.002 - Data Repository](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0010%20-%20Supply%20Chain%20Compromise/AML.T0010.002%20-%20Data%20Repository/README.md)

Tay bot used the interactions with its Twitter users as training data to improve its conversations.
Adversaries were able to coordinate with the intent of defacing Tay bot by exploiting this feedback loop.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0020 - Training Data Poisoning](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0020%20-%20Training%20Data%20Poisoning/README.md)

By repeatedly interacting with Tay using racist and offensive language, they were able to skew Tay's dataset towards that language as well. This was done by adversaries using the "repeat after me" function, a command that forced Tay to repeat anything said to it.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0031 - Erode AI Model Integrity](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0031%20-%20Erode%20AI%20Model%20Integrity/README.md)

As a result of this coordinated attack, Tay's conversation algorithms began to learn to generate reprehensible material. Tay's internalization of this detestable language caused it to be unpromptedly repeated during interactions with innocent users.

**Next**  End of path

## References

- [AIID - Incident 6: TayBot](https://incidentdatabase.ai/cite/6)
- [AVID - Vulnerability: AVID-2022-v013](https://avidml.org/database/avid-2022-v013/)
- [Microsoft BlogPost, "Learning from Tay's introduction"](https://blogs.microsoft.com/blog/2016/03/25/learning-tays-introduction/)
- [IEEE Article, "In 2016, Microsoft's Racist Chatbot Revealed the Dangers of Online Conversation"](https://spectrum.ieee.org/tech-talk/artificial-intelligence/machine-learning/in-2016-microsofts-racist-chatbot-revealed-the-dangers-of-online-conversation)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0009)
