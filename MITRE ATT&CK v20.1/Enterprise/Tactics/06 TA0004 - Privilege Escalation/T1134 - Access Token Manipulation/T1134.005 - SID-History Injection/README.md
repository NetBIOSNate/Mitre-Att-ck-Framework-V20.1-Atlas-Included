# T1134.005 - SID-History Injection

[Enterprise](../../../../README.md) / [Privilege Escalation](../../README.md) / [T1134 - Access Token Manipulation](../README.md)

Adversaries may use SID-History Injection to escalate privileges and bypass access controls. The Windows security identifier (SID) is a unique value that identifies a user or group account. SIDs are used by Windows security in both security descriptors and access tokens.(Citation: Microsoft SID) An account can hold additional SIDs in the SID-History Active Directory attribute, allowing inter-operable account migration between domains (e.g., all values in SID-History are included in access tokens).(Citation: Microsoft SID-History Attribute) 

With Domain Administrator (or equivalent) rights, harvested or well-known SID values(Citation: Microsoft Well Known SIDs Jun 2017) may be inserted into SID-History to enable impersonation of arbitrary users/groups such as Enterprise Administrators. This manipulation may result in elevated access to local resources and/or access to otherwise inaccessible domains via lateral movement techniques such as [Remote Services](https://attack.mitre.org/techniques/T1021), [SMB/Windows Admin Shares](https://attack.mitre.org/techniques/T1021/002), or [Windows Remote Management](https://attack.mitre.org/techniques/T1021/006).

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1134/005)

**Tactics**  [Privilege Escalation](../../README.md), [Stealth](../../../07%20TA0005%20-%20Stealth/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1015 - Active Directory Configuration](../../../../Defenses/Mitigations/M1015%20-%20Active%20Directory%20Configuration.md) — Clean up SID-History attributes after legitimate account migration is complete. Consider applying SID Filtering to interforest trusts, such as forest trusts and external trusts, to exclude SID-History from requests to access domain resources. SID Filtering ensures that any authentication requests over a trust only contain SIDs of security principals from the trusted domain (i.e preventing the trusted domain from claiming a user has membership in groups outside of the domain). SID Filtering of forest trusts is enabled by default, but may have been disabled in some cases to allow a child domain to transitively access forest trusts. SID Filtering of external trusts is automatically enabled on all created external trusts using Server 2003 or later domain controllers. (Citation: Microsoft Trust Considerations Nov 2014) (Citation: Microsoft SID Filtering Quarantining Jan 2009) However note that SID Filtering is not automatically applied to legacy trusts or may have been deliberately disabled to allow inter-domain access to resources. SID Filtering can be applied by: (Citation: Microsoft Netdom Trust Sept 2012) * Disabling SIDHistory on forest trusts using the netdom tool (<code>netdom trust /domain: /EnableSIDHistory:no</code> on the domain controller) * Applying SID Filter Quarantining to external trusts using the netdom tool (<code>netdom trust <TrustingDomainName> /domain:<TrustedDomainName> /quarantine:yes</code> on the domain controller) * Applying SID Filtering to domain trusts within a single forest is not recommended as it is an unsupported configuration and can cause breaking changes. (Citation: Microsoft Netdom Trust Sept 2012) (Citation: AdSecurity Kerberos GT Aug 2015) If a domain within a forest is untrustworthy then it should not be a member of the forest. In this situation it is necessary to first split the trusted and untrusted domains into separate forests where SID Filtering can be applied to an interforest trust [Microsoft Trust Considerations Nov 2014](https://technet.microsoft.com/library/cc755321.aspx) · [Microsoft SID Filtering Quarantining Jan 2009](https://technet.microsoft.com/library/cc794757.aspx) · [Microsoft Netdom Trust Sept 2012](https://technet.microsoft.com/library/cc835085.aspx) · [AdSecurity Kerberos GT Aug 2015](https://adsecurity.org/?p=1640)

## Procedure examples

- [S0363 - Empire](../../../../Threat%20Intelligence/Software/Tools/S0363%20-%20Empire.md) — [Empire](https://attack.mitre.org/software/S0363) can add a SID-History to a user if on a domain controller.(Citation: Github PowerShell Empire) [Github PowerShell Empire](https://github.com/PowerShellEmpire/Empire)
- [S0002 - Mimikatz](../../../../Threat%20Intelligence/Software/Tools/S0002%20-%20Mimikatz.md) — [Mimikatz](https://attack.mitre.org/software/S0002)'s <code>MISC::AddSid</code> module can append any SID or user/group account to a user's SID-History. [Mimikatz](https://attack.mitre.org/software/S0002) also utilizes [SID-History Injection](https://attack.mitre.org/techniques/T1134/005) to expand the scope of other components such as generated Kerberos Golden Tickets and DCSync beyond a single domain.(Citation: Adsecurity Mimikatz Guide)(Citation: AdSecurity Kerberos GT Aug 2015) [AdSecurity Kerberos GT Aug 2015](https://adsecurity.org/?p=1640) · [Adsecurity Mimikatz Guide](https://adsecurity.org/?page_id=1821)

## Detection strategies

- [DET0136 - Behavior-chain detection for T1134.005 Access Token Manipulation: SID-History Injection (Windows)](../../../../Defenses/Detection%20Strategies/DET0136%20-%20Behavior-chain%20detection%20for%20T1134.005%20Access%20Token%20Manipulation%20-%20SID-History%20Inject.md)

## Sources

- [Microsoft Well Known SIDs Jun 2017](https://support.microsoft.com/help/243330/well-known-security-identifiers-in-windows-operating-systems)
- [Microsoft SID-History Attribute](https://msdn.microsoft.com/library/ms679833.aspx)
- [Microsoft SID](https://msdn.microsoft.com/library/windows/desktop/aa379571.aspx)
