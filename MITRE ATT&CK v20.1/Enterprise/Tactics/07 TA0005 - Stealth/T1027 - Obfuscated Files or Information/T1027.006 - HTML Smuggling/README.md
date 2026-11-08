# T1027.006 - HTML Smuggling

[Enterprise](../../../../README.md) / [Stealth](../../README.md) / [T1027 - Obfuscated Files or Information](../README.md)

Adversaries may smuggle data and files past content filters by hiding malicious payloads inside of seemingly benign HTML files. HTML documents can store large binary objects known as JavaScript Blobs (immutable data that represents raw bytes) that can later be constructed into file-like objects. Data may also be stored in Data URLs, which enable embedding media type or MIME files inline of HTML documents. HTML5 also introduced a download attribute that may be used to initiate file downloads.(Citation: HTML Smuggling Menlo Security 2020)(Citation: Outlflank HTML Smuggling 2018)

Adversaries may deliver payloads to victims that bypass security controls through HTML Smuggling by abusing JavaScript Blobs and/or HTML5 download attributes. Security controls such as web content filters may not identify smuggled malicious files inside of HTML/JS files, as the content may be based on typically benign MIME types such as <code>text/plain</code> and/or <code>text/html</code>. Malicious files or data can be obfuscated and hidden inside of HTML files through Data URLs and/or JavaScript Blobs and can be deobfuscated when they reach the victim (i.e. [Deobfuscate/Decode Files or Information](https://attack.mitre.org/techniques/T1140)), potentially bypassing content filters.

For example, JavaScript Blobs can be abused to dynamically generate malicious files in the victim machine and may be dropped to disk by abusing JavaScript functions such as <code>msSaveBlob</code>.(Citation: HTML Smuggling Menlo Security 2020)(Citation: MSTIC NOBELIUM May 2021)(Citation: Outlflank HTML Smuggling 2018)(Citation: nccgroup Smuggling HTA 2017)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1027/006)

**Tactics**  [Stealth](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [macOS](../../../../Platforms/macOS.md), [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1048 - Application Isolation and Sandboxing](../../../../Defenses/Mitigations/M1048%20-%20Application%20Isolation%20and%20Sandboxing.md) — Use Browser Extensions or Built-in Security Tools that: - Monitor JavaScript API calls such as `Blob`, `URL.createObjectURL,` and `msSaveOrOpenBlob` - Intercept and analyze HTML5 `download` attributes for suspicious payload generation - Alert or block behaviors that match known HTML smuggling patterns (e.g., blob-to-disk payload construction) Apply Content Security Policy (CSP) headers to: - Restrict inline JavaScript and dynamic script generation - Disallow downloads from unauthorized sources or blob URIs - Prevent cross-origin resource sharing (CORS) abuse commonly used in smuggling chains Enable or enforce enterprise browser security controls, such as: - Endpoint's Network Protection and Attack Surface Reduction (ASR) rules, which can block Office and browser processes from creating child processes or writing to disk in suspicious ways - Google Chrome Enterprise Policies, which can control file download behavior, restrict extensions, and isolate risky browsing environments Deploy browser sandboxing solutions that can isolate JavaScript execution environments and enforce behavioral policy restrictions

## Procedure examples

- [G0016 - APT29](../../../../Threat%20Intelligence/Groups/G0016%20-%20APT29.md) — [APT29](https://attack.mitre.org/groups/G0016) has embedded an ISO file within an HTML attachment that contained JavaScript code to initiate malware execution.(Citation: ESET T3 Threat Report 2021) [ESET T3 Threat Report 2021](https://www.welivesecurity.com/wp-content/uploads/2022/02/eset_threat_report_t32021.pdf)
- [S0634 - EnvyScout](../../../../Threat%20Intelligence/Software/Malware/S0634%20-%20EnvyScout.md) — [EnvyScout](https://attack.mitre.org/software/S0634) contains JavaScript code that can extract an encoded blob from its HTML body and write it to disk.(Citation: MSTIC Nobelium Toolset May 2021) [MSTIC Nobelium Toolset May 2021](https://www.microsoft.com/security/blog/2021/05/28/breaking-down-nobeliums-latest-early-stage-toolset/)
- [S0650 - QakBot](../../../../Threat%20Intelligence/Software/Malware/S0650%20-%20QakBot.md) — [QakBot](https://attack.mitre.org/software/S0650) has been delivered in ZIP files via HTML smuggling.(Citation: Trend Micro Black Basta October 2022)(Citation: Deep Instinct Black Basta August 2022) [Trend Micro Black Basta October 2022](https://www.trendmicro.com/en_us/research/22/j/black-basta-infiltrates-networks-via-qakbot-brute-ratel-and-coba.html) · [Deep Instinct Black Basta August 2022](https://www.deepinstinct.com/blog/black-basta-ransomware-threat-emergence)

## Detection strategies

- [DET0313 - Detection Strategy for HTML Smuggling via JavaScript Blob + Dynamic File Drop](../../../../Defenses/Detection%20Strategies/DET0313%20-%20Detection%20Strategy%20for%20HTML%20Smuggling%20via%20JavaScript%20Blob%20%2B%20Dynamic%20File%20Drop.md)

## Sources

- [Outlflank HTML Smuggling 2018](https://outflank.nl/blog/2018/08/14/html-smuggling-explained/)
- [MSTIC NOBELIUM May 2021](https://www.microsoft.com/security/blog/2021/05/27/new-sophisticated-email-based-attack-from-nobelium/)
- [HTML Smuggling Menlo Security 2020](https://www.menlosecurity.com/blog/new-attack-alert-duri)
- [nccgroup Smuggling HTA 2017](https://www.nccgroup.com/us/research-blog/smuggling-hta-files-in-internet-exploreredge/)
