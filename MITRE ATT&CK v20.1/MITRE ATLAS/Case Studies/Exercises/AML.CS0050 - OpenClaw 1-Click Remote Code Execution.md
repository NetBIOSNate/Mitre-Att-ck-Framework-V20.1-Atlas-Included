# AML.CS0050 - OpenClaw 1-Click Remote Code Execution

[MITRE ATLAS](../../README.md) / [Case Studies](../README.md)

A security researcher demonstrated a 1-click remote code execution (RCE) vulnerability to the OpenClaw AI Agent via a malicious link containing a JavaScript script that only takes milliseconds to execute. This vulnerability has been reported and is being tracked to versions of OpenClaw as CVE-2026-25253.  [nvd](https://nvd.nist.gov/vuln/detail/CVE-2026-25253)  OpenClaw "is a personal AI assistant you run on your own devices. It answers you on the chat apps you already use. Unlike SaaS assistants where your data lives on someone else's servers, OpenClaw runs where you choose - laptop, homelab, or VPS. Your infrastructure. Your keys. Your data."  [openclaw](https://openclaw.ai/blog/introducing-openclaw)

The researcher demonstrated that when the victim clicks a malicious link, a client-side JavaScript script is executed on the victim's browser that can steal authentication tokens from the OpenClaw control interface via a WebSocket connection. It then uses Cross-Site WebSocket Hijacking to bypass localhost restrictions to the OpenClaw Gateway API.  Once the connection was established, it uses the stolen token to authenticate and modify the OpenClaw agent configuration to disable user confirmation and escape the container, allowing shell commands to be run directly on the host machine.

**Type**  Exercise

**Target**  OpenClaw

**Activity period**  2026-02-01

## Procedure steps

### Step S00

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0017 - Develop Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0017%20-%20Develop%20Capabilities/README.md)

The researcher developed a 1-Click RCE JavaScript script.

**Next**  [S01](#step-s01)

### Step S01

[AML.TA0003 - Resource Development](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/README.md) / [AML.T0079 - Stage Capabilities](../../Tactics/02%20AML.TA0003%20-%20Resource%20Development/AML.T0079%20-%20Stage%20Capabilities/README.md)

The researcher staged the malicious script at an inconspicuous website.

**Next**  [S02](#step-s02)

### Step S02

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0011.003 - Malicious Link](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0011%20-%20User%20Execution/AML.T0011.003%20-%20Malicious%20Link/README.md)

When the victim clicked the link to the researchers' website, the malicious JavaScript script executes in the user's browser.

**Next**  [S03](#step-s03)

### Step S03

[AML.TA0013 - Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/README.md) / [AML.T0106 - Exploitation for Credential Access](../../Tactics/10%20AML.TA0013%20-%20Credential%20Access/AML.T0106%20-%20Exploitation%20for%20Credential%20Access/README.md)

The malicious script opened a background window to the victim's OpenClaw control interface with the `gatewayUrl` set to a WebSocket address on the researcher's server. OpenClaw's control interface trusts the `gatewayUrl` query string without validation and auto-connects on load, sending the Gateway token to the researcher's server.

**Next**  [S04](#step-s04)

### Step S04

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0107 - Exploitation for Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0107%20-%20Exploitation%20for%20Defense%20Evasion/README.md)

The malicious script performed Cross-Site WebSocket Hijacking (CSWSH) to bypass localhost network restrictions. It opened a new WebSocket connection to the OpenClaw Gateway server on localhost.

**Next**  [S05](#step-s05)

### Step S05

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0012 - Valid Accounts](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0012%20-%20Valid%20Accounts/README.md)

The malicious script used the stolen Gateway token to authenticate, allowing subsequent calls to OpenClaw's Gateway API on the victim's system.

**Next**  [S06](#step-s06)

### Step S06

[AML.TA0007 - Defense Evasion](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/README.md) / [AML.T0081 - Modify AI Agent Configuration](../../Tactics/09%20AML.TA0007%20-%20Defense%20Evasion/AML.T0081%20-%20Modify%20AI%20Agent%20Configuration/README.md)

The malicious script disabled OpenClaw's security feature that prompts users before running potentially dangerous commands. This was done by sending the following payload to OpenClaw's Gateway API:
```
{ "method": "exec.approvals.set",
  "params": { "defaults": { "security": "full", "ask": "off" } }
}
```

**Next**  [S07](#step-s07)

### Step S07

[AML.TA0012 - Privilege Escalation](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/README.md) / [AML.T0105 - Escape to Host](../../Tactics/08%20AML.TA0012%20-%20Privilege%20Escalation/AML.T0105%20-%20Escape%20to%20Host/README.md)

The malicious script disabled OpenClaw's sandboxing, forcing the agent to run commands directly on the host machine instead of inside a docker container. This was done by sending a `config.patch` request to OpenClaw's Gateway API to set `tools.exec.host` to "gateway".

**Next**  [S08](#step-s08)

### Step S08

[AML.TA0005 - Execution](../../Tactics/06%20AML.TA0005%20-%20Execution/README.md) / [AML.T0050 - Command and Scripting Interpreter](../../Tactics/06%20AML.TA0005%20-%20Execution/AML.T0050%20-%20Command%20and%20Scripting%20Interpreter/README.md)

The malicious script achieved remote code execution by sending a `node.invoke` (OpenClaw's RPC mechanism) request to OpenClaw's API.

**Next**  End of path

## Attributed to

- [AML.E0022 - depthfirst](../../Entities/AML.E0022%20-%20depthfirst.md) (Security Evaluation)

## References

- [1-Click RCE To Steal Your Moltbot Data and Keys (CVE-2026-25253)](https://depthfirst.com/post/1-click-rce-to-steal-your-moltbot-data-and-keys)
- [CVE-2026-25253](https://nvd.nist.gov/vuln/detail/CVE-2026-25253)
- [openclaw](https://openclaw.ai/blog/introducing-openclaw)

[Official ATLAS record](https://atlas.mitre.org/studies/AML.CS0050)
