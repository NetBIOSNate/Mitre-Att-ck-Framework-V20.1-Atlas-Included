# DC0114 - Application Permission

[Mobile](../../README.md) / [Data Components](README.md)

Represents the permissions, entitlements, or capability grants associated with a mobile application, including both permissions declared by the application and those granted or requested during runtime.

Monitoring permission state helps defenders identify applications attempting to access protected device resources such as sensors, storage, communications interfaces, or system services.

Examples include:

Android

- Permissions declared in AndroidManifest.xml
- Runtime permission prompts
- Special access privileges (AccessibilityService, overlay, device admin)

iOS

- App entitlements in provisioning profiles
- Privacy permission prompts
- Capability grants for device services

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0114)

## Log sources and channels

- **android:logcat** — READ_EXTERNAL_STORAGE / MANAGE_EXTERNAL_STORAGE permission present or toggled at runtime
- **android:MDMLog** — policy_violation WHERE install_unknown_apps changed to enabled + MobileEDR app_install with signing_cert NOT IN EnterpriseCertList within TimeWindow where enterprise policy does not permit this cert or install source
- **android:MDMLog** — policy_violation WHERE unknown_sources=enabled OR play_protect_status=disabled + MobileEDR app_install event from non-com.android.vending source within PolicyViolationWindow where MDM policy does not permit unknown source installs
- **android:MDMLog** — root_status=false AND MobileEDR reports UID=0 binary execution within ComplianceCheckWindow where MDM-reported state does not justify observed privilege
- **android:MDMLog** — Application granted or retaining RECORD_AUDIO permission or privileged CAPTURE_AUDIO_OUTPUT capability
- **android:MDMLog** — Application granted/retaining ACCESS_FINE_LOCATION and/or ACCESS_COARSE_LOCATION; background location capability present (ACCESS_BACKGROUND_LOCATION on Android 10+)
- **android:MDMLog** — Device inventory changes involving phone number/line identifier fields (when available), eSIM profile presence, or compliance signal indicating SIM profile change
- **android:MDMLog** — New permission prompt, package install attempt, accessibility/overlay special access request, or other post-browse capability escalation following browser/WebView activity
- **android:MDMLog** — ADB_DEBUGGING_ENABLED
- **android:MDMLog** — Application gains or is observed with elevated interaction capability such as accessibility, overlay, device admin, notification access, or other authentication-adjacent special access
- **android:MDMLog** — Known application or newly updated version declares, gains, or activates expanded storage, sensor, communications, accessibility, or device-management capability inconsistent with prior baseline or app role
- **android:MDMLog** — Known application version declares, gains, or first exercises storage, communications, accessibility, advertising, analytics, overlay, or sensor-adjacent capability inconsistent with prior version baseline or business role
- **android:MDMLog** — Device enrollment or compliance event shows failed or degraded verified boot, hardware-backed attestation mismatch, patch/build/baseband inconsistency, or unexpected device property drift near first contact
- **android:MDMLog** — Managed or trusted app is newly installed or updated and presents changed package identity, signing relationship, version lineage, installer source, or permission posture inconsistent with approved baseline
- **android:MDMLog** — App communicating with legitimate web-service infrastructure is unmanaged, newly installed, recently updated, outside approved app list, or shows baseline drift in role, installer source, or expected capability profile
- **android:MDMLog** — App initiating resolver→pivot sequence was unmanaged or not authorized to communicate with detected web-service class or external infrastructure
- **android:MDMLog** — App identity performing bidirectional exchange was unmanaged, outside approved app baseline, or not permitted to use detected public web-service class for read/write operations
- **android:MDMLog** — App identity performing repeated one-way retrieval was unmanaged, outside approved app baseline, or not permitted to use detected public web-service class for background content retrieval
- **android:MDMLog** — App identity performing camera session was unmanaged, recently granted camera permission, or not approved to use camera for video or interval image capture
- **android:MDMLog** — Application granted or retaining the READ_CALL_LOG permission. 
- **android:MDMLog** — Application granted or retaining the READ_CONTACTS permission.
- **android:MDMLog** — Application granted or retaining the READ_SMS or RECEIVE_SMS permission.
- **android:MDMLog** — App identity performing screen capture had unapproved accessibility posture, capture-related special access, unmanaged state, or was not approved for screen recording or assistive observation workflows
- **android:MDMLog** — NotificationListenerService enabled OR notification access granted to app not in enterprise-approved list
- **android:MDMLog** — App not in enterprise-approved list performing network + crypto behavior inconsistent with declared functionality
- **android:MDMLog** — App not in approved cryptographic or secure communication category performing keypair + encryption + transmission behavior
- **android:MDMLog** — Managed app with undeclared secure transport behavior or app category mismatch initiates opaque TLS communications inconsistent with enterprise policy baseline
- **android:MDMLog** — Managed application with no declared backup, sync, export, or media-editing role performs bulk local packaging or encrypted archive generation
- **android:MDMLog** — Managed app granted or retaining storage-related or elevated access inconsistent with declared function prior to local data access activity
- **android:MDMLog** — Managed app without approved content-download, update, browser, or file-sync role performs remote payload retrieval and local tool staging
- **android:MDMLog** — Managed application without approved native-code role or expected high-performance/native dependency exhibits native execution behavior inconsistent with enterprise policy baseline
- **android:MDMLog** — Managed application package version, signer lineage, installer source, or app identity changes outside approved enterprise or store-mediated update workflow
- **android:MDMLog** — Managed app granted SEND_SMS or RECEIVE_SMS permission, or app role/policy indicates SMS-capable behavior inconsistent with approved enterprise function before SMS control activity
- **android:MDMLog** — Default SMS handler changes to non-baselined application or managed app unexpectedly becomes or remains device default SMS app during SMS control phase
- **android:MDMLog** — Managed app without approved VPN, enterprise tunneling, browser, or remote-access role exhibits proxy-like traffic handling inconsistent with policy baseline
- **android:MDMLog** — Managed app granted call-control-relevant permissions or telecom role state inconsistent with approved enterprise function before call-control activity
- **android:MDMLog** — Default phone or telecom-handling role changes to non-baselined application or managed app unexpectedly becomes dialer/call-handling app during call-control phase
- **android:MDMLog** — device transitions to non-compliant state + root detected or integrity attestation failure (SafetyNet/Play Integrity)
- **android:MDMLog** — application integrity mismatch or package signature inconsistency relative to expected deployment baseline
- **android:MDMLog** — application granted high-risk permission or special access (AccessibilityService, SYSTEM_ALERT_WINDOW, DeviceAdmin) with abnormal grant pattern (e.g., no recent user interaction or rapid sequence of grants)
- **android:MDMLog** — application granted Device Administrator privilege + abnormal activation pattern (e.g., rapid enablement after install or no recent user interaction)
- **android:MDMLog** — application holds permissions enabling environment validation (e.g., location, phone state, nearby device/network context) and subsequently delays protected activity until qualifying values are present
- **android:MDMLog** — application granted ACCESS_FINE_LOCATION and, when required for background operation, ACCESS_BACKGROUND_LOCATION + capability state sufficient for persistent geolocation monitoring before later guarded activity
- **android:MDMLog** — managed app inventory or launcher-visible state changes show application remains installed but user-facing entry point or launcher component becomes disabled before later runtime activity
- **android:MDMLog** — installed application remains present while launcher-visible activity or component discoverability changes to hidden, disabled, or synthesized-settings-entry state prior to later runtime activity
- **android:MDMLog** — change to security-relevant device configuration or managed policy (e.g., accessibility enablement, app admin changes, security service state change) preceding telemetry degradation
- **android:MDMLog** — application enabled as device administrator, device owner, profile owner, or equivalent elevated management role before uninstall attempt
- **android:MDMLog** — application granted accessibility service privileges capable of screen observation or global action invocation before removal attempt
- **android:MDMLog** — application enabled as device administrator, device owner, or profile owner before screen-lock or password-control activity
- **android:MDMLog** — application granted accessibility service privileges capable of intercepting UI flow or sustaining user-interaction denial before lockout event
- **android:MDMLog** — device posture changes to rooted, non-compliant, weakened security state, or elevated control role becomes active before security-tool degradation
- **android:MDMLog** — security-relevant application package state, enabled status, administrator state, or managed protection setting changes immediately before monitoring degradation
- **android:MDMLog** — device posture or compromise-state indicators change unexpectedly, including rooted or non-compliant status disappearance, after prior app or system activity suggesting persistence on device
- **android:MDMLog** — managed application state changes unexpectedly through uninstall, disappearance from expected inventory, or install-state mismatch after prior suspicious activity
- **android:MDMLog** — application holds device-owner, profile-owner, or delegated app-management authority capable of package removal before uninstall event
- **android:MDMLog** — application has accessibility service privileges immediately before package-removal UI flow and subsequent application disappearance
- **android:MDMLog** — device posture indicates rooted, compromised, or non-compliant state before package files disappear without standard managed uninstall workflow
- **android:MDMLog** — application holds device administrator, device owner, or other managed authority capable of wipe or destructive device-level action before bulk file loss or wipe event
- **android:MDMLog** — device posture indicates rooted, compromised, or non-compliant state before protected or atypical filesystem deletion activity
- **android:MDMLog ** — Application granted or retaining the READ_CALENDAR or WRITE_CALENDAR permissions. 
- **Application Vetting** — None
- **iOS:MDMLog** — MDM integrity_check=fail AND jailbreak_status=true — active integrity failure on jailbroken device confirms exploitation beyond passive jailbreak presence
- **iOS:MDMLog** — certificate trust status = user_trusted for cert NOT IN $EnterpriseCertList$ within $ProfileInstallWindow$
- **iOS:MDMLog** — profile_install where install_initiator != MDM_SERVER + cert_trust_type=enterprise within ProfileInstallWindow where MDM provisioning does not justify out-of-band profile installation
- **iOS:MDMLog** — compliance_status=pass AND MobileEDR dylib load event with lib_path matching KnownJailbreakLibPatterns within same device session where clean compliance does not justify jailbreak library presence
- **iOS:MDMLog** — Application installed with NSMicrophoneUsageDescription entitlement indicating microphone capability
- **iOS:MDMLog** — App installed with location usage declarations (WhenInUse/Always usage description) and granted authorization level via managed policy state
- **iOS:MDMLog** — Managed device inventory change indicating cellular plan/eSIM profile updates (where available via supervised iOS + MDM reporting)
- **iOS:MDMLog** — Post-browse configuration profile prompt, managed/unmanaged app handoff anomaly, or compliance-relevant state change shortly after browser activity
- **iOS:MDMLog** — Compliance posture or restriction state relevant to accessory access, USB restricted mode, supervised trust policy, or backup/pairing restrictions
- **iOS:MDMLog** — Known application version declares, activates, or exhibits new entitlements, privacy permissions, or capability use inconsistent with prior baseline or business role
- **iOS:MDMLog** — Supervised enrollment, activation, or inventory event reveals unexpected device property relationships, anomalous managed posture, unexplained configuration drift near first contact, or identity/inventory characteristics inconsistent with approved procurement baseline
- **iOS:MDMLog** — Supervised managed app is newly installed or updated and presents unexpected version transition, inventory drift, managed-state change, or app attribute mismatch against approved procurement and release baseline
- **iOS:MDMLog** — Managed app communicating with legitimate web-service infrastructure is newly installed, recently updated, outside expected managed-app set, or displays baseline drift in app role, release path, or business justification
- **iOS:MDMLog** — Bundle performing resolver→pivot sequence not present in approved managed-app baseline or lacks expected service relationship
- **iOS:MDMLog** — Bundle performing bidirectional exchange was not present in approved managed-app baseline or was not permitted to use detected public web-service class for read/write operations
- **iOS:MDMLog** — Bundle performing repeated one-way retrieval was not present in approved managed-app baseline or was not permitted to use detected public web-service class for background content retrieval
- **iOS:MDMLog** — App identity using non-standard protocol-to-port pairing was unmanaged, outside approved app baseline, or not permitted to communicate using detected protocol/service over observed destination port
- **iOS:MDMLog** — Bundle performing camera session was not present in approved managed-app baseline or was not permitted to use camera for video or interval image capture
- **iOS:MDMLog** — Supervised managed app with undeclared secure transport behavior or unexpected network role communicates with non-baselined destination over opaque TLS
- **iOS:MDMLog** — Supervised managed app without expected export, backup, or sync role performs local data staging behavior followed by opaque upload activity
- **iOS:MDMLog** — Supervised managed app without expected local export, sync, or forensic role accesses or stages local records inconsistent with policy baseline
- **iOS:MDMLog** — Supervised managed app without approved update, browser, sync, or enterprise-content role retrieves and stages secondary content inconsistent with policy baseline
- **iOS:MDMLog** — application has approved capabilities required for conditional execution (e.g., location/background modes) but observed behavior is deferred until target-specific state is present
- **iOS:MDMLog** — application authorized for when-in-use or always location access and, where relevant, background execution capability sufficient for continued geographic evaluation before later guarded behavior
- **MobileEDR:telemetry** — App with network-, telephony-, Wi-Fi-, or location-adjacent capability is impacted by abrupt repeated service loss while permissions remain unchanged
- **MobileEDR:telemetry** — Network- or location-dependent app capability state remains unchanged while the app experiences sustained communication failure
- **MobileEDR:telemetry** — Application holds or is granted broad storage, document-provider, media, or file-management capability inconsistent with its expected role before or during bulk file transformation
- **android:DevicePolicyManager** — DevicePolicyManager.getPermissionGrantState(); PackageManager manifest/requested-permission review
- **mobile:ApplicationVetting** — Code-signing entitlements and Info.plist privacy usage-description keys

## Analytics using this component

- [AN1644 - Analytic 1644](../Analytics/AN1644.md)
- [AN1645 - Analytic 1645](../Analytics/AN1645.md)
- [AN1652 - Analytic 1652](../Analytics/AN1652.md)
- [AN1653 - Analytic 1653](../Analytics/AN1653.md)
- [AN1654 - Analytic 1654](../Analytics/AN1654.md)
- [AN1655 - Analytic 1655](../Analytics/AN1655.md)
- [AN1656 - Analytic 1656](../Analytics/AN1656.md)
- [AN1661 - Analytic 1661](../Analytics/AN1661.md)
- [AN1662 - Analytic 1662](../Analytics/AN1662.md)
- [AN1663 - Analytic 1663](../Analytics/AN1663.md)
- [AN1664 - Analytic 1664](../Analytics/AN1664.md)
- [AN1665 - Analytic 1665](../Analytics/AN1665.md)
- [AN1668 - Analytic 1668](../Analytics/AN1668.md)
- [AN1675 - Analytic 1675](../Analytics/AN1675.md)
- [AN1676 - Analytic 1676](../Analytics/AN1676.md)
- [AN1678 - Analytic 1678](../Analytics/AN1678.md)
- [AN1679 - Analytic 1679](../Analytics/AN1679.md)
- [AN1680 - Analytic 1680](../Analytics/AN1680.md)
- [AN1683 - Analytic 1683](../Analytics/AN1683.md)
- [AN1688 - Analytic 1688](../Analytics/AN1688.md)
- [AN1689 - Analytic 1689](../Analytics/AN1689.md)
- [AN1690 - Analytic 1690](../Analytics/AN1690.md)
- [AN1693 - Analytic 1693](../Analytics/AN1693.md)
- [AN1694 - Analytic 1694](../Analytics/AN1694.md)
- [AN1695 - Analytic 1695](../Analytics/AN1695.md)
- [AN1696 - Analytic 1696](../Analytics/AN1696.md)
- [AN1697 - Analytic 1697](../Analytics/AN1697.md)
- [AN1698 - Analytic 1698](../Analytics/AN1698.md)
- [AN1701 - Analytic 1701](../Analytics/AN1701.md)
- [AN1702 - Analytic 1702](../Analytics/AN1702.md)
- [AN1709 - Analytic 1709](../Analytics/AN1709.md)
- [AN1712 - Analytic 1712](../Analytics/AN1712.md)
- [AN1713 - Analytic 1713](../Analytics/AN1713.md)
- [AN1715 - Analytic 1715](../Analytics/AN1715.md)
- [AN1716 - Analytic 1716](../Analytics/AN1716.md)
- [AN1718 - Analytic 1718](../Analytics/AN1718.md)
- [AN1721 - Analytic 1721](../Analytics/AN1721.md)
- [AN1723 - Analytic 1723](../Analytics/AN1723.md)
- [AN1725 - Analytic 1725](../Analytics/AN1725.md)
- [AN1726 - Analytic 1726](../Analytics/AN1726.md)
- [AN1728 - Analytic 1728](../Analytics/AN1728.md)
- [AN1729 - Analytic 1729](../Analytics/AN1729.md)
- [AN1730 - Analytic 1730](../Analytics/AN1730.md)
- [AN1731 - Analytic 1731](../Analytics/AN1731.md)
- [AN1733 - Analytic 1733](../Analytics/AN1733.md)
- [AN1734 - Analytic 1734](../Analytics/AN1734.md)
- [AN1737 - Analytic 1737](../Analytics/AN1737.md)
- [AN1738 - Analytic 1738](../Analytics/AN1738.md)
- [AN1739 - Analytic 1739](../Analytics/AN1739.md)
- [AN1740 - Analytic 1740](../Analytics/AN1740.md)
- [AN1743 - Analytic 1743](../Analytics/AN1743.md)
- [AN1744 - Analytic 1744](../Analytics/AN1744.md)
- [AN1745 - Analytic 1745](../Analytics/AN1745.md)
- [AN1746 - Analytic 1746](../Analytics/AN1746.md)
- [AN1755 - Analytic 1755](../Analytics/AN1755.md)
- [AN1756 - Analytic 1756](../Analytics/AN1756.md)
- [AN1758 - Analytic 1758](../Analytics/AN1758.md)
- [AN1762 - Analytic 1762](../Analytics/AN1762.md)
- [AN1764 - Analytic 1764](../Analytics/AN1764.md)
- [AN1765 - Analytic 1765](../Analytics/AN1765.md)
- [AN1766 - Analytic 1766](../Analytics/AN1766.md)
- [AN1767 - Analytic 1767](../Analytics/AN1767.md)
- [AN1768 - Analytic 1768](../Analytics/AN1768.md)
- [AN1770 - Analytic 1770](../Analytics/AN1770.md)
- [AN1771 - Analytic 1771](../Analytics/AN1771.md)
- [AN1773 - Analytic 1773](../Analytics/AN1773.md)
- [AN1777 - Analytic 1777](../Analytics/AN1777.md)
- [AN1779 - Analytic 1779](../Analytics/AN1779.md)
- [AN1781 - Analytic 1781](../Analytics/AN1781.md)
- [AN1785 - Analytic 1785](../Analytics/AN1785.md)
- [AN1793 - Analytic 1793](../Analytics/AN1793.md)
- [AN1794 - Analytic 1794](../Analytics/AN1794.md)
- [AN1797 - Analytic 1797](../Analytics/AN1797.md)
- [AN1799 - Analytic 1799](../Analytics/AN1799.md)
- [AN1801 - Analytic 1801](../Analytics/AN1801.md)
- [AN1802 - Analytic 1802](../Analytics/AN1802.md)
- [AN1806 - Analytic 1806](../Analytics/AN1806.md)
- [AN1808 - Analytic 1808](../Analytics/AN1808.md)
- [AN1809 - Analytic 1809](../Analytics/AN1809.md)
- [AN1816 - Analytic 1816](../Analytics/AN1816.md)
- [AN1817 - Analytic 1817](../Analytics/AN1817.md)
- [AN1822 - Analytic 1822](../Analytics/AN1822.md)
- [AN1823 - Analytic 1823](../Analytics/AN1823.md)
- [AN1824 - Analytic 1824](../Analytics/AN1824.md)
- [AN1827 - Analytic 1827](../Analytics/AN1827.md)
- [AN1828 - Analytic 1828](../Analytics/AN1828.md)
- [AN1840 - Analytic 1840](../Analytics/AN1840.md)
- [AN1841 - Analytic 1841](../Analytics/AN1841.md)
- [AN1842 - Analytic 1842](../Analytics/AN1842.md)
- [AN1843 - Analytic 1843](../Analytics/AN1843.md)
- [AN1844 - Analytic 1844](../Analytics/AN1844.md)
- [AN1847 - Analytic 1847](../Analytics/AN1847.md)
- [AN1848 - Analytic 1848](../Analytics/AN1848.md)
- [AN1849 - Analytic 1849](../Analytics/AN1849.md)
- [AN1850 - Analytic 1850](../Analytics/AN1850.md)
- [AN1852 - Analytic 1852](../Analytics/AN1852.md)
- [AN1853 - Analytic 1853](../Analytics/AN1853.md)
- [AN1854 - Analytic 1854](../Analytics/AN1854.md)
