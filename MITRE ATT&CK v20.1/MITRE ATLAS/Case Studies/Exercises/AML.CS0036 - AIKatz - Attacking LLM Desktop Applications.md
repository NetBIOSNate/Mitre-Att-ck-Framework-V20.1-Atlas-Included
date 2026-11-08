# AML.CS0036 - AIKatz: Attacking LLM Desktop Applications

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

Researchers at Lumia have demonstrated that it is possible to extract authentication tokens from the memory of LLM Desktop Applications. An attacker could then use those tokens to impersonate the victim to the LLM backend, thereby gaining access to the victim's conversations as well as the ability to interfere in future conversations. The attacker's access would allow them the ability to directly inject prompts to change the LLM's behavior, poison the LLM's context to have persistent effects, manipulate the user's conversation history to cover their tracks, and ultimately impact the confidentiality, integrity, and availability of the system. The researchers demonstrated this on Anthropic Claude, Microsoft M365 Copilot, and OpenAI ChatGPT.

Vendor Responses to Responsible Disclosure:
- Anthropic (HackerOne) - Closed as informational since local attack.
- Microsoft Security Response Center - Attack doesn't bypass security boundaries for CVE.
- OpenAI (BugCrowd) - Closed as informational and noted that it's up to Microsoft to patch this behavior.

**Type**  Exercise

**Target**  LLM Desktop Applications (Claude, ChatGPT, Copilot)

**Activity period**  2025

## Procedure steps

### Step S00

[AML.TA0004 - Initial Access](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/04%20AML.TA0004%20-%20Initial%20Access/AML.T0012%20-%20Valid%20Accounts/README.md)

The attacker required initial access to the victim system to carry out this attack.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0008 - Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/README.md) / [AML.T0089 - Enterprise Environment Discovery](../../Tactics/11%20AML.TA0008%20-%20Discovery/AML.T0089%20-%20Enterprise%20Environment%20Discovery/README.md)

The attacker enumerated all of the processes running on the victim's machine and identified the processes belonging to LLM desktop applications.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0090 - OS Credential Dumping](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0090%20-%20OS%20Credential%20Dumping/README.md)

The attacker attached or read memory directly from `/proc` (in Linux) or opened a handle to the LLM application's process (in Windows). The attacker then scanned the process's memory to extract the authentication token of the victim. This can be easily done by running a regex on every allocated memory page in the process.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0015 - Lateral Movement](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/README.md) / [AML.T0091.000 - Application Access Token](../../Tactics/12%20AML.TA0015%20-%20Lateral%20Movement/AML.T0091%20-%20Use%20Alternate%20Authentication%20Material/AML.T0091.000%20-%20Application%20Access%20Token/README.md)

The attacker used the extracted token to authenticate themselves with the LLM backend service.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0000 - AI Model Access](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/README.md) / [AML.T0047 - AI-Enabled Product or Service](../../Tactics/05%20AML.TA0000%20-%20AI%20Model%20Access/AML.T0047%20-%20AI-Enabled%20Product%20or%20Service/README.md)

The attacker has now obtained the access required to communicate with the LLM backend service as if they were the desktop client. This allowed them access to everything the user can do with the desktop application.

**Next**  [S05](#step-s05), [S08](#step-s08), [S09](#step-s09), [S10](#step-s10), [S11](#step-s11), [S12](#step-s12)

### Step S05

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0051.000 - Direct](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0051%20-%20LLM%20Prompt%20Injection/AML.T0051.000%20-%20Direct/README.md)

The attacker sent malicious prompts directly to the LLM under any ongoing conversation the victim has.

**Next**  [S06](#step-s06), [S07](#step-s07)

### Step S06

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0080.001 - Thread](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.001%20-%20Thread/README.md)

The attacker could craft malicious prompts that manipulate the context of a chat thread, an effect that would persist for the duration of the thread.

**Next**  End of path

### Step S07

[AML.TA0006 - Persistence](../../Tactics/07%20AML.TA0006%20-%20Persistence/README.md) / [AML.T0080.000 - Memory](../../Tactics/07%20AML.TA0006%20-%20Persistence/AML.T0080%20-%20AI%20Agent%20Context%20Poisoning/AML.T0080.000%20-%20Memory/README.md)

The attacker could then craft malicious prompts that manipulate the LLM's memory to achieve a persistent effect. Any change in memory would also propagate to any new chat threads.

**Next**  End of path

### Step S08

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0092 - Manipulate User LLM Chat History](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0092%20-%20Manipulate%20User%20LLM%20Chat%20History/README.md)

Many LLM desktop applications do not show the injected prompt for any ongoing chat, as they update chat history only once when initially opening it. This gave the attacker the opportunity to cover their tracks by manipulating the user's conversation history directly via the LLM's API. The attacker could also overwrite or delete messages to prevent detection of their actions.

**Next**  End of path

### Step S09

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.000 - Financial Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.000%20-%20Financial%20Harm/README.md)

The attacker could send spam messages while impersonating the victim. On a pay-per-token or action plans, this could increase the financial burden on the victim.

**Next**  End of path

### Step S10

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0048.003 - User Harm](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0048%20-%20External%20Harms/AML.T0048.003%20-%20User%20Harm/README.md)

The attacker could gain access to all of the victim's activity with the LLM, including previous and ongoing chats, as well as any file or content uploaded to them.

**Next**  End of path

### Step S11

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0029 - Denial of AI Service](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0029%20-%20Denial%20of%20AI%20Service/README.md)

The attacker could delete all chats the victim has, and any they are opening, thereby preventing the victim from being able to interact with the LLM.

**Next**  End of path

### Step S12

[AML.TA0011 - Impact](../../Tactics/16%20AML.TA0011%20-%20Impact/README.md) / [AML.T0029 - Denial of AI Service](../../Tactics/16%20AML.TA0011%20-%20Impact/AML.T0029%20-%20Denial%20of%20AI%20Service/README.md)

The attacker could spam messages or prompts to reach the LLM's rate-limits against bots, to cause it to ban the victim altogether.

**Next**  End of path

## Attributed to

- [AML.E0015 - Lumia Security](../../Entities/AML.E0015%20-%20Lumia%20Security.md) (Security Evaluation)

## References

- [AIKatz - All Your Chats Are Belong To Us](https://www.lumia.security/blog/aikatz)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0036)
