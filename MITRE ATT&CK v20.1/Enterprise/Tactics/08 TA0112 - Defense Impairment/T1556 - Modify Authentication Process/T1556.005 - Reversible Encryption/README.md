# T1556.005 - Reversible Encryption

[Enterprise](../../../../README.md) / [Defense Impairment](../../README.md) / [T1556 - Modify Authentication Process](../README.md)

An adversary may abuse Active Directory authentication encryption properties to gain access to credentials on Windows systems. The <code>AllowReversiblePasswordEncryption</code> property specifies whether reversible password encryption for an account is enabled or disabled. By default this property is disabled (instead storing user credentials as the output of one-way hashing functions) and should not be enabled unless legacy or other software require it.(Citation: store_pwd_rev_enc)

If the property is enabled and/or a user changes their password after it is enabled, an adversary may be able to obtain the plaintext of passwords created/changed after the property was enabled. To decrypt the passwords, an adversary needs four components:

1. Encrypted password (<code>G$RADIUSCHAP</code>) from the Active Directory user-structure <code>userParameters</code>
2. 16 byte randomly-generated value (<code>G$RADIUSCHAPKEY</code>) also from <code>userParameters</code>
3. Global LSA secret (<code>G$MSRADIUSCHAPKEY</code>)
4. Static key hardcoded in the Remote Access Subauthentication DLL (<code>RASSFM.DLL</code>)

With this information, an adversary may be able to reproduce the encryption key and subsequently decrypt the encrypted password value.(Citation: how_pwd_rev_enc_1)(Citation: how_pwd_rev_enc_2)

An adversary may set this property at various scopes through Local Group Policy Editor, user properties, Fine-Grained Password Policy (FGPP), or via the ActiveDirectory [PowerShell](https://attack.mitre.org/techniques/T1059/001) module. For example, an adversary may implement and apply an FGPP to users or groups if the Domain Functional Level is set to "Windows Server 2008" or higher.(Citation: dump_pwd_dcsync) In PowerShell, an adversary may make associated changes to user settings using commands similar to <code>Set-ADUser -AllowReversiblePasswordEncryption $true</code>.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1556/005)

**Tactics**  [Persistence](../../../05%20TA0003%20-%20Persistence/README.md), [Defense Impairment](../../README.md), [Credential Access](../../../09%20TA0006%20-%20Credential%20Access/README.md)

**Platforms**  [Windows](../../../../Platforms/Windows.md)

## Mitigations

- [M1027 - Password Policies](../../../../Defenses/Mitigations/M1027%20-%20Password%20Policies.md) — Ensure that <code>AllowReversiblePasswordEncryption</code> property is set to disabled unless there are application requirements.(Citation: store_pwd_rev_enc) [store_pwd_rev_enc](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/store-passwords-using-reversible-encryption)
- [M1026 - Privileged Account Management](../../../../Defenses/Mitigations/M1026%20-%20Privileged%20Account%20Management.md) — Audit domain and local accounts as well as their permission levels routinely to look for situations that could allow an adversary to gain wide access by obtaining credentials of a privileged account.(Citation: TechNet Credential Theft)(Citation: TechNet Least Privilege) These audits should also include if default accounts have been enabled, or if new local accounts are created that have not be authorized. Follow best practices for design and administration of an enterprise network to limit privileged account use across administrative tiers.(Citation: Microsoft Securing Privileged Access) [TechNet Credential Theft](https://technet.microsoft.com/en-us/library/dn535501.aspx) · [TechNet Least Privilege](https://technet.microsoft.com/en-us/library/dn487450.aspx) · [Microsoft Securing Privileged Access](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material#a-nameesaebmaesae-administrative-forest-design-approach)

## Detection strategies

- [DET0589 - Detect Modification of Authentication Process via Reversible Encryption](../../../../Defenses/Detection%20Strategies/DET0589%20-%20Detect%20Modification%20of%20Authentication%20Process%20via%20Reversible%20Encryption.md)

## Sources

- [dump_pwd_dcsync](https://adsecurity.org/?p=2053)
- [store_pwd_rev_enc](https://docs.microsoft.com/en-us/windows/security/threat-protection/security-policy-settings/store-passwords-using-reversible-encryption)
- [how_pwd_rev_enc_1](http://blog.teusink.net/2009/08/passwords-stored-using-reversible.html)
- [how_pwd_rev_enc_2](http://blog.teusink.net/2009/08/passwords-stored-using-reversible_26.html)
