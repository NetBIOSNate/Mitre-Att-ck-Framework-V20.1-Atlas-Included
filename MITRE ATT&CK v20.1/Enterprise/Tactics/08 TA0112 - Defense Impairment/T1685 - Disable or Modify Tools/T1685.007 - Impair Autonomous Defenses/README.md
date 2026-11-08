# T1685.007 - Impair Autonomous Defenses

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1685 - Disable or Modify Tools](../README.md)

Adversaries may use methods like [Indirect Prompt Injection](https://attack.mitre.org/techniques/T1698) to disrupt, disable, or otherwise impair autonomous defensive capabilities such as LLM-assisted processing of malware, artifacts, or activity.(Citation: Prompt Injection LLM-Powered SOC Assistants) This behavior may cause a system to ignore data, fail to alert on malicious activity, abort analysis, or to be disabled completely. 

Adversaries may include content in malware implants that mimic an LLM prompt scaffold that contains fake system messages in order to convince the LLM that it has encountered an error.(Citation: MacOS.Gaslight Prompt Injection)(Citation: Gaslight AI triage prompt injection) Depending on the type of error, the LLM may abort analysis, truncate, or refuse to continue. Adversaries may also embed prompts in malware intended to stop agents or systems from analyzing the malware.(Citation: Shai-Hulud May 2026)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1685/007)

**Tactics**  [Defense Impairment](../../README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md), [SaaS](../../../../Platforms/SaaS.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Require AI-assisted security analysis workflows to preserve analysis status, artifact provenance, tool execution, termination reason, and completion state so that incomplete or unexpectedly redirected analysis can be independently identified and reviewed.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Prevent content contained within an artifact under analysis from directly controlling the analysis workflow, terminating analysis, altering required analysis stages, or initiating unrelated tools and actions. Enforce workflow transitions independently of instructions generated from artifact content.
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Prevent AI-assisted analysis agents from exercising privileged capabilities solely as a consequence of artifact-derived instructions. Require independent authorization for privileged or consequential operations outside the expected analysis workflow.
- [M1022 - Restrict File and Directory Permissions](../../../../Defenses/Mitigations/M1022%20-%20Restrict%20File%20and%20Directory%20Permissions.md) — Limit AI-assisted analysis systems to the files and directories required for analysis and prevent artifacts under investigation from modifying agent configuration, instruction files, analysis state, or other trusted AI application resources.
- [M1018 - User Account Management](../../../../Defenses/Mitigations/M1018%20-%20User%20Account%20Management.md) — Run AI-assisted analysis services using dedicated identities with permissions limited to required analysis functions. Separate analysis authority from broader analyst, administrative, or production access.

## Detection strategies

- [DET0943 - Adversarial Content Inducing Autonomous Defense Impairment](../../../../Defenses/Detection%20Strategies/DET0943%20-%20Adversarial%20Content%20Inducing%20Autonomous%20Defense%20Impairment.md)

## Sources

- [Shai-Hulud May 2026](https://www.ox.security/blog/shai-hulud-open-source-malware-github/)
- [MacOS.Gaslight Prompt Injection](https://www.sentinelone.com/labs/macos-gaslight-rust-backdoor-turns-prompt-injection-on-the-analyst-not-the-sandbox/)
- [Gaslight AI triage prompt injection](https://www.rogue.security/blog/gaslight-malware-ai-triage-prompt-injection)
- [Prompt Injection LLM-Powered SOC Assistants](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7179658)
