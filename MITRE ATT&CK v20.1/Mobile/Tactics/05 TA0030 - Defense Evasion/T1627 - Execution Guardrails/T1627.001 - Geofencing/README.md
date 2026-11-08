# T1627.001 - Geofencing

[Mobile](../../../../README.md) / [Defense Evasion](../../README.md) / [T1627 - Execution Guardrails](../README.md)

Adversaries may use a device’s geographical location to limit certain malicious behaviors. For example, malware operators may limit the distribution of a second stage payload to certain geographic regions.(Citation: Lookout eSurv)

[Geofencing](https://attack.mitre.org/techniques/T1627/001) is accomplished by persuading the user to grant the application permission to access location services. The application can then collect, process, and exfiltrate the device’s location to perform location-based actions, such as ceasing malicious behavior or showing region-specific advertisements. 

One method to accomplish [Geofencing](https://attack.mitre.org/techniques/T1627/001) on Android is to use the built-in Geofencing API to automatically trigger certain behaviors when the device enters or exits a specified radius around a geographical location. Similar to  other [Geofencing](https://attack.mitre.org/techniques/T1627/001) methods, this requires that the user has granted the `ACCESS_FINE_LOCATION` and `ACCESS_BACKGROUND_LOCATION` permissions. The latter is only required if the application targets Android 10 (API level 29) or higher. However, Android 11 introduced additional permission controls that may restrict background location collection based on user permission choices at runtime. These additional controls include "Allow only while using the app", which will effectively prohibit background location collection.  

Similarly, on iOS, developers can use built-in APIs to setup and execute geofencing. Depending on the use case, the app will either need to call `requestWhenInUseAuthorization()` or `requestAlwaysAuthorization()`, depending on when access to the location services is required. Similar to Android, users also have the option to limit when the application can access the device’s location, including one-time use and only when the application is running in the foreground.  

[Geofencing](https://attack.mitre.org/techniques/T1627/001) can be used to prevent exposure of capabilities in environments that are not intended to be compromised or operated within. For example, location data could be used to limit malware spread and/or capabilities, which could also potentially evade application analysis environments (ex: malware analysis outside of the target geographic area). Other malicious usages could include showing language-specific input prompts and/or advertisements.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1627/001)

**Tactics**  [Defense Evasion](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Procedure examples

- [S1094 - BRATA](../../../../Threat%20Intelligence/Software/Malware/S1094%20-%20BRATA.md) — [BRATA](https://attack.mitre.org/software/S1094) has performed country and language checks.(Citation: mcafee_brata_0421) [mcafee_brata_0421](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/brata-keeps-sneaking-into-google-play-now-targeting-usa-and-spain/)
- [S0507 - eSurv](../../../../Threat%20Intelligence/Software/Malware/S0507%20-%20eSurv.md) — [eSurv](https://attack.mitre.org/software/S0507) imposes geo-restrictions when delivering the second stage.(Citation: Lookout eSurv) [Lookout eSurv](https://blog.lookout.com/esurv-research)
- [G0112 - Windshift](../../../../Threat%20Intelligence/Groups/G0112%20-%20Windshift.md) — [Windshift](https://attack.mitre.org/groups/G0112) has region-locked their malicious applications during their Operation BULL campaign.(Citation: BlackBerry Bahamut) [BlackBerry Bahamut](https://www.blackberry.com/us/en/pdfviewer?file=/content/dam/blackberry-com/asset/enterprise/pdf/direct/report-spark-bahamut.pdf)

## Detection strategies

- [DET0648 - Detection of Geofencing](../../../../Defenses/Detection%20Strategies/DET0648%20-%20Detection%20of%20Geofencing.md)

## Mitigations

- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — New OS releases frequently contain additional limitations or controls around device location access.
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be advised to be extra scrutinous of applications that request location, and to deny any permissions requests for applications they do not recognize.

## Sources

- [Lookout eSurv](https://blog.lookout.com/esurv-research)
