# DC0112 - API Calls

[Mobile](../../README.md) / [Data Components](README.md)

API calls utilized by an application that could indicate malicious activity

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0112)

## Log sources and channels

- **Application Vetting** — None
- **iOS:unifiedlog** — Repeated sandbox or policy violations by a single process or app bundle (for example, deny rules) followed by successful access to resources or APIs that normally require higher privileges
- **iOS:unifiedlog** — mmap with PROT_EXEC and PROT_WRITE by sandboxed app
- **android:logcat** — SELinux AVC related to execute_no_trans/execmem after decode/unpack activity by the same app UID
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: APK or IPA contains SystemProperties.get() calls, Runtime.exec getprop invocations, or code patterns checking for emulator artifacts (ro.product.model=sdk, IMEI=000000, screen size, sensor absence) — static detection of environment-check co
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: IPA contains UIDevice.currentDevice.model checks for Simulator strings, CMMotionManager.isDeviceMotionAvailable comparisons, or other Simulator-detection patterns — static detection of iOS environment-check code
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ClipboardManager.addOnPrimaryClipChangedListener()
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: UIPasteboard.general.string property accessed by app
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: AccessibilityEvent.TYPE_VIEW_TEXT_CHANGED received by listener_app NOT IN $AccessibilityAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: AccessibilityEvent.TYPE_VIEW_TEXT_CHANGED received by listener NOT IN $AccessibilityAllowList$ at rate > $KeystrokeEventThreshold$ per minute with source_apps spanning > $AppMonitorCountThreshold$ distinct apps
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: PackageManager.getInstalledPackages() or getInstalledApplications() called by app NOT IN $AppEnumAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: UIApplication.canOpenURL() called > $URLProbeThreshold$ times with schemes NOT declared in app's LSApplicationQueriesSchemes within $ProbeWindow$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: PackageManager.getPackageInfo() called for package names IN $SecurityToolPackageList$ by app NOT IN $AppEnumAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: UIApplication.canOpenURL() called with schemes IN $MDMToolSchemeList$ by app NOT IN $AppEnumAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: WifiInfo.getBSSID()
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: NetworkInterface.getNetworkInterfaces()
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ConnectivityManager.getActiveNetworkInfo() or InetAddress.isReachable() called by app NOT IN $ConnectivityAllowList$ at app launch or on schedule without user action
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: NWPathMonitor.start() or SCNetworkReachabilityGetFlags() called by app NOT IN $ConnectivityAllowList$ at launch or on background schedule
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: WifiManager.getScanResults()
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: CNCopyCurrentNetworkInfo() or NEHotspotHelper.register() called by app NOT IN $WiFiAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: android.os.Build field reads > $SysInfoFieldThreshold$ distinct fields within $SysInfoWindow$ by app NOT IN $SysInfoAllowList$ at launch or in background
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: UIDevice.current.model
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: AudioRecord.startRecording() or MediaRecorder.start() called by app NOT IN $AudioAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: LocationManager.requestLocationUpdates() called with minTime < $LocationUpdateFreqThreshold$ by app NOT IN $LocationAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: FirebaseMessaging.getToken() called for project_id NOT IN $FCMAllowList$ — rogue FCM project registration is the adversary enabling C2 over Google infrastructure
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: UNUserNotificationCenter or legacy UIApplication.registerForRemoteNotifications with Apple Team ID NOT IN $APNSAllowList$ — rogue APNS sender registration
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: AccessibilityService receiving events from dc(source_app) > $AccessibilityTargetThreshold$ distinct apps INCLUDING apps IN $TargetAppList$ — broad monitoring across apps distinguishes malware from single-purpose assistive tech
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: getNetworkInterfaces() OR NetworkInterface.getHardwareAddress() called within $ProcReadWindow$ of /proc reads by same app — network MAC OUI check completes hardware fingerprint
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: UIDevice.currentDevice.model
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: PackageManager.queryIntentActivities() returns handler_count > 1 for custom URI scheme
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: PackageManager reports two or more apps with identical URI scheme intent-filter
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ContentResolver.query() to sensitive provider URI (contacts, calendar, call_log, sms) with query_count > $ContentQueryThreshold$ by app NOT IN $ApprovedDataApps$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: CNContactStore.enumerateContacts or EKEventStore.fetchEvents or CLLocationManager.startUpdatingLocation called with broad scope by app NOT IN $ApprovedDataApps$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ContentResolver.query(CalendarContract) with query_count > $CalendarQueryThreshold$ by app NOT IN $ApprovedCalendarApps$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: EKEventStore.fetchEvents() or enumerateEvents() with date_range > $CalendarDateRangeThreshold$ days by app NOT IN $ApprovedCalendarApps$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ContentResolver.query(CallLog.Calls) with query_count > $CallLogQueryThreshold$ by app NOT IN $ApprovedDialerApps$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ContentResolver.query(ContactsContract) with projection=all_fields
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: CNContactStore.enumerateContacts with CNContactFetchRequest.keysToFetch containing all contact keys by app NOT IN $ApprovedContactsApps$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ContentResolver.query(Telephony.Sms) including both inbox
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: AccountManager.getAccounts() OR getAccountsByType() called > $AccountEnumThreshold$ times within $AccountEnumWindow$ by app NOT IN $ApprovedAuthenticatorApps$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: SecItemCopyMatching() called with kSecMatchLimitAll
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: InetAddress.getByName() or DnsResolver called > $DGACandidateThreshold$ times with algorithmically-distinct hostnames in $DGAWindow$ — rapid programmatic resolution attempts
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: DevicePolicyManager.resetPassword() or lockNow() or wipeData() called by caller NOT IN $MDMAgentPackageList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ContentResolver.update() called by writer_app NOT IN $LegitimateIPCPartners$ for target_app's content provider URI
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: ClipboardManager.addOnPrimaryClipChangedListener() registered
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: DevicePolicyManager.lockNow() or resetPassword() called by caller NOT IN $MDMAgentPackageList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: SmsManager.sendTextMessage() called by app NOT IN $ApprovedMessagingApps$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: NotificationListenerService.onNotificationPosted() receiving notifications from source_app IN $HighValueNotifApps$ by listener NOT IN $NotificationAllowList$
- **mobile:DynamicAnalysis** — Dynamic API/runtime trace: camera activated within app IN $MessagingAppList$ — QR scan requires camera access; activation in messaging app context is the trigger signal

## Analytics using this component

- [AN1646 - Analytic 1646](../Analytics/AN1646.md)
- [AN1647 - Analytic 1647](../Analytics/AN1647.md)
- [AN1648 - Analytic 1648](../Analytics/AN1648.md)
- [AN1649 - Analytic 1649](../Analytics/AN1649.md)
- [AN1650 - Analytic 1650](../Analytics/AN1650.md)
- [AN1655 - Analytic 1655](../Analytics/AN1655.md)
- [AN1659 - Analytic 1659](../Analytics/AN1659.md)
- [AN1667 - Analytic 1667](../Analytics/AN1667.md)
- [AN1673 - Analytic 1673](../Analytics/AN1673.md)
- [AN1674 - Analytic 1674](../Analytics/AN1674.md)
- [AN1681 - Analytic 1681](../Analytics/AN1681.md)
- [AN1682 - Analytic 1682](../Analytics/AN1682.md)
- [AN1691 - Analytic 1691](../Analytics/AN1691.md)
- [AN1692 - Analytic 1692](../Analytics/AN1692.md)
- [AN1693 - Analytic 1693](../Analytics/AN1693.md)
- [AN1695 - Analytic 1695](../Analytics/AN1695.md)
- [AN1706 - Analytic 1706](../Analytics/AN1706.md)
- [AN1708 - Analytic 1708](../Analytics/AN1708.md)
- [AN1709 - Analytic 1709](../Analytics/AN1709.md)
- [AN1710 - Analytic 1710](../Analytics/AN1710.md)
- [AN1719 - Analytic 1719](../Analytics/AN1719.md)
- [AN1720 - Analytic 1720](../Analytics/AN1720.md)
- [AN1743 - Analytic 1743](../Analytics/AN1743.md)
- [AN1750 - Analytic 1750](../Analytics/AN1750.md)
- [AN1751 - Analytic 1751](../Analytics/AN1751.md)
- [AN1772 - Analytic 1772](../Analytics/AN1772.md)
- [AN1774 - Analytic 1774](../Analytics/AN1774.md)
- [AN1775 - Analytic 1775](../Analytics/AN1775.md)
- [AN1776 - Analytic 1776](../Analytics/AN1776.md)
- [AN1782 - Analytic 1782](../Analytics/AN1782.md)
- [AN1783 - Analytic 1783](../Analytics/AN1783.md)
- [AN1784 - Analytic 1784](../Analytics/AN1784.md)
- [AN1785 - Analytic 1785](../Analytics/AN1785.md)
- [AN1786 - Analytic 1786](../Analytics/AN1786.md)
- [AN1787 - Analytic 1787](../Analytics/AN1787.md)
- [AN1790 - Analytic 1790](../Analytics/AN1790.md)
- [AN1795 - Analytic 1795](../Analytics/AN1795.md)
- [AN1798 - Analytic 1798](../Analytics/AN1798.md)
- [AN1812 - Analytic 1812](../Analytics/AN1812.md)
- [AN1825 - Analytic 1825](../Analytics/AN1825.md)
- [AN1831 - Analytic 1831](../Analytics/AN1831.md)
- [AN1832 - Analytic 1832](../Analytics/AN1832.md)
- [AN1833 - Analytic 1833](../Analytics/AN1833.md)
- [AN1834 - Analytic 1834](../Analytics/AN1834.md)
- [AN1845 - Analytic 1845](../Analytics/AN1845.md)
