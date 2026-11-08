# T1176.001 - Browser Extensions

[Enterprise](../../../../README.md) / [Persistence](../../README.md) / [T1176 - Software Extensions](../README.md)

Adversaries may abuse internet browser extensions to establish persistent access to victim systems. Browser extensions or plugins are small programs that can add functionality to and customize aspects of internet browsers. They can be installed directly via a local file or custom URL or through a browser's app store - an official online platform where users can browse, install, and manage extensions for a specific web browser. Extensions generally inherit the web browser's permissions previously granted.(Citation: Wikipedia Browser Extension)(Citation: Chrome Extensions Definition) 
 
Malicious extensions can be installed into a browser through malicious app store downloads masquerading as legitimate extensions, through social engineering, or by an adversary that has already compromised a system. Security can be limited on browser app stores, so it may not be difficult for malicious extensions to defeat automated scanners.(Citation: Malicious Chrome Extension Numbers) Depending on the browser, adversaries may also manipulate an extension's update url to install updates from an adversary-controlled server or manipulate the mobile configuration file to silently install additional extensions. 

Adversaries may abuse how chromium-based browsers load extensions by modifying or replacing the Preferences and/or Secure Preferences files to silently install malicious extensions. When the browser is not running, adversaries can alter these files, ensuring the extension is loaded, granted desired permissions, and will persist in browser sessions. This method does not require user consent and extensions are silently loaded in the background from disk or from the browser's trusted store.(Citation: Pulsedive)
  
Previous to macOS 11, adversaries could silently install browser extensions via the command line using the <code>profiles</code> tool to install malicious <code>.mobileconfig</code> files. In macOS 11+, the use of the <code>profiles</code> tool can no longer install configuration profiles; however, <code>.mobileconfig</code> files can be planted and installed with user interaction.(Citation: xorrior chrome extensions macOS) 
 
Once the extension is installed, it can browse to websites in the background, steal all information that a user enters into a browser (including credentials), and be used as an installer for a RAT for persistence.(Citation: Chrome Extension Crypto Miner)(Citation: ICEBRG Chrome Extensions)(Citation: Banker Google Chrome Extension Steals Creds)(Citation: Catch All Chrome Extension) 

There have also been instances of botnets using a persistent backdoor through malicious Chrome extensions for [Command and Control](https://attack.mitre.org/tactics/TA0011).(Citation: Stantinko Botnet)(Citation: Chrome Extension C2 Malware) Adversaries may also use browser extensions to modify browser permissions and components, privacy settings, and other security controls for [Stealth](https://attack.mitre.org/tactics/TA0005).(Citation: Browers FriarFox)(Citation: Browser Adrozek)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1176/001)

**Tactics**  [Persistence](../../README.md)

**Platforms**  [Linux](../../../../Platforms/Linux.md), [Windows](../../../../Platforms/Windows.md), [macOS](../../../../Platforms/macOS.md)

## Mitigations

- [M1047 - Audit](../../../../Defenses/Mitigations/M1047%20-%20Audit.md) — Ensure extensions that are installed are the intended ones, as many malicious extensions will masquerade as legitimate ones.
- [M1038 - Execution Prevention](../../../../Defenses/Mitigations/M1038%20-%20Execution%20Prevention.md) — Set a browser extension allow or deny list as appropriate for your security policy.(Citation: Technospot Chrome Extensions GP) [Technospot Chrome Extensions GP](http://www.technospot.net/blogs/block-chrome-extensions-using-google-chrome-group-policy-settings/)
- [M1033 - Limit Software Installation](../../../../Defenses/Mitigations/M1033%20-%20Limit%20Software%20Installation.md) — Only install browser extensions from trusted sources that can be verified. Browser extensions for some browsers can be controlled through Group Policy. Change settings to prevent the browser from installing extensions without sufficient permissions.
- [M1051 - Update Software](../../../../Defenses/Mitigations/M1051%20-%20Update%20Software.md) — Ensure operating systems and browsers are using the most current version.
- [M1017 - User Training](../../../../Defenses/Mitigations/M1017%20-%20User%20Training.md) — Close out all browser sessions when finished using them to prevent any potentially malicious extensions from continuing to run.

## Procedure examples

- [S0482 - Bundlore](../../../../Threat%20Intelligence/Software/Malware/S0482%20-%20Bundlore.md) — [Bundlore](https://attack.mitre.org/software/S0482) can install malicious browser extensions that are used to hijack user searches.(Citation: MacKeeper Bundlore Apr 2019) [MacKeeper Bundlore Apr 2019](https://mackeeper.com/blog/post/610-macos-bundlore-adware-analysis/)
- [S0531 - Grandoreiro](../../../../Threat%20Intelligence/Software/Malware/S0531%20-%20Grandoreiro.md) — [Grandoreiro](https://attack.mitre.org/software/S0531) can use malicious browser extensions to steal cookies and other user information.(Citation: IBM Grandoreiro April 2020) [IBM Grandoreiro April 2020](https://securityintelligence.com/posts/grandoreiro-malware-now-targeting-banks-in-spain/)
- [G0094 - Kimsuky](../../../../Threat%20Intelligence/Groups/G0094%20-%20Kimsuky.md) — [Kimsuky](https://attack.mitre.org/groups/G0094) has used Google Chrome browser extensions to infect victims and to steal passwords and cookies.(Citation: Zdnet Kimsuky Dec 2018)(Citation: Netscout Stolen Pencil Dec 2018) [Netscout Stolen Pencil Dec 2018](https://asert.arbornetworks.com/stolen-pencil-campaign-targets-academia/) · [Zdnet Kimsuky Dec 2018](https://www.zdnet.com/article/cyber-espionage-group-uses-chrome-extension-to-infect-victims/)
- [S1213 - Lumma Stealer](../../../../Threat%20Intelligence/Software/Malware/S1213%20-%20Lumma%20Stealer.md) — [Lumma Stealer](https://attack.mitre.org/software/S1213) has installed a malicious browser extension to target Google Chrome, Microsoft Edge, Opera and Brave browsers for the purpose of stealing data.(Citation: Cybereason LumaStealer Undated) [Cybereason LumaStealer Undated](https://www.cybereason.com/blog/threat-analysis-rise-of-lummastealer)
- [S1122 - Mispadu](../../../../Threat%20Intelligence/Software/Malware/S1122%20-%20Mispadu.md) — [Mispadu](https://attack.mitre.org/software/S1122) utilizes malicious Google Chrome browser extensions to steal financial data.(Citation: ESET Security Mispadu Facebook Ads 2019) [ESET Security Mispadu Facebook Ads 2019](https://www.welivesecurity.com/2019/11/19/mispadu-advertisement-discounted-unhappy-meal/)
- [S0402 - OSX/Shlayer](../../../../Threat%20Intelligence/Software/Malware/S0402%20-%20OSX%20-%20Shlayer.md) — [OSX/Shlayer](https://attack.mitre.org/software/S0402) can install malicious Safari browser extensions to serve ads.(Citation: Intego Shlayer Apr 2018)(Citation: Malwarebytes Crossrider Apr 2018) [Malwarebytes Crossrider Apr 2018](https://blog.malwarebytes.com/threat-analysis/2018/04/new-crossrider-variant-installs-configuration-profiles-on-macs/) · [Intego Shlayer Apr 2018](https://www.intego.com/mac-security-blog/new-osxshlayer-malware-variant-found-using-a-dirty-new-trick/)
- [S1201 - TRANSLATEXT](../../../../Threat%20Intelligence/Software/Malware/S1201%20-%20TRANSLATEXT.md) — [TRANSLATEXT](https://attack.mitre.org/software/S1201) has the ability to capture credentials, cookies, browser screenshots, etc. and to exfiltrate data.(Citation: Zscaler Kimsuky TRANSLATEXT) [Zscaler Kimsuky TRANSLATEXT](https://www.zscaler.com/blogs/security-research/kimsuky-deploys-translatext-target-south-korean-academia#technical-analysis)

## Detection strategies

- [DET0044 - Detecting Malicious Browser Extensions Across Platforms](../../../../Defenses/Detection%20Strategies/DET0044%20-%20Detecting%20Malicious%20Browser%20Extensions%20Across%20Platforms.md)

## Sources

- [Pulsedive](https://blog.pulsedive.com/rilide-an-information-stealing-browser-extension/)
- [Chrome Extension Crypto Miner](https://www.ghacks.net/2017/09/19/first-chrome-extension-with-javascript-crypto-miner-detected/)
- [xorrior chrome extensions macOS](https://www.xorrior.com/No-Place-Like-Chrome/)
- [Chrome Extensions Definition](https://developer.chrome.com/extensions)
- [ICEBRG Chrome Extensions](https://www.icebrg.io/blog/malicious-chrome-extensions-enable-criminals-to-impact-over-half-a-million-users-and-global-businesses)
- [Malicious Chrome Extension Numbers](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43824.pdf)
- [Chrome Extension C2 Malware](https://web.archive.org/web/20240608001937/https://kjaer.io/extension-malware/)
- [Catch All Chrome Extension](https://isc.sans.edu/forums/diary/CatchAll+Google+Chrome+Malicious+Extension+Steals+All+Posted+Data/22976/https:/threatpost.com/malicious-chrome-extension-steals-data-posted-to-any-website/128680/%29)
- [Banker Google Chrome Extension Steals Creds](https://isc.sans.edu/forums/diary/BankerGoogleChromeExtensiontargetingBrazil/22722/)
- [Browser Adrozek](https://www.microsoft.com/en-us/security/blog/2020/12/10/widespread-malware-campaign-seeks-to-silently-inject-ads-into-search-results-affects-multiple-browsers/)
- [Browers FriarFox](https://www.proofpoint.com/uk/blog/threat-insight/ta413-leverages-new-friarfox-browser-extension-target-gmail-accounts-global)
- [Stantinko Botnet](https://www.welivesecurity.com/2017/07/20/stantinko-massive-adware-campaign-operating-covertly-since-2012/)
- [Wikipedia Browser Extension](https://en.wikipedia.org/wiki/Browser_extension)
