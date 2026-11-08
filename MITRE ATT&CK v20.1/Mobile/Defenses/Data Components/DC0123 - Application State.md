# DC0123 - Application State

[Mobile](../../README.md) / [Data Components](README.md)

Application State represents the operational status and lifecycle context of a mobile application at a given point in time. This includes whether the application is running in the foreground or background, its activity state, recent user interaction, and transitions between lifecycle states.

Monitoring application state helps defenders identify suspicious behavior where an application performs sensitive actions while inactive, in the background, or without recent user interaction.

Application state is particularly useful when detecting malicious activity that occurs outside normal user-driven workflows.

Examples
Android

- Application transitions from foreground to background
- Application running as a background service
- Application started via broadcast receiver
- Application launched automatically after device boot

iOS

- Application entering active, inactive, or background state
- Background task execution
- Background fetch activity
- Application wake events triggered by push notifications or system services

Data Collection Measures
- Mobile EDR / MTD runtime monitoring
- OS lifecycle event telemetry
- Application runtime instrumentation
- Mobile security platform behavioral monitoring

[MITRE ATT&CK record](https://attack.mitre.org/datacomponents/DC0123)

## Log sources and channels

- **iOS:MDM** — Declarative Management app.managed.list status changes, where collected
- **android:EMM** — Managed package inventory/status and package metadata
- **android:MDMLog** — Newly installed or updated application launches background service, becomes active without recent user interaction, or executes immediately after update in a pattern inconsistent with baseline
- **iOS:MDM** — InstalledApplicationList / ManagedApplicationList
- **MobileEDR:telemetry** — environment API reads occur before any user interaction at cold launch — precondition check timing
- **MobileEDR:telemetry** — environment check API burst occurs at app cold-launch or in background before user interaction — precondition check timing distinguishes guardrail from feature use
- **MobileEDR:telemetry** — pplication or service remains active, foregrounds, or overlays during device locked state or immediately at unlock transition with weak recent user interaction context
- **MobileEDR:telemetry** — Application wakes, becomes active, refreshes, or foregrounds immediately after locked or inactive state transition with weak recent user interaction
- **MobileEDR:telemetry** — Foreground or background applications remain active while network-dependent activity stalls, retries, or transitions into repeated failure state
- **MobileEDR:telemetry** — Application runs in foreground, service, or sustained background-active state while concentrated file transformation occurs with weak or no recent user interaction
- **MobileEDR:telemetry** — Updated or newly delivered application becomes active, launches background services, or executes shortly after install/update with minimal user interaction inconsistent with baseline
- **MobileEDR:telemetry** — Updated or newly delivered application wakes, foregrounds, refreshes, or becomes active shortly after version change with weak recent user interaction
- **MobileEDR:telemetry** — Protected resource use or privileged framework access occurs while device is locked, before normal setup completion, or from an app/service not in foreground and not on approved preload list
- **MobileEDR:telemetry** — Managed app or device-originated network activity occurs while the device is locked or before expected managed app initialization sequence, inconsistent with expected background refresh baseline
- **MobileEDR:telemetry** — Recently installed or updated trusted app begins background execution, persistent service activity, overlay-like behavior, or lock-state activity inconsistent with its historical baseline or expected first-run sequence
- **MobileEDR:telemetry** — Recently installed or updated managed app begins background activity, persistent refresh, or lock-state-adjacent activity inconsistent with expected first-run behavior, user interaction timing, or historical baseline
- **MobileEDR:telemetry** — App communicating with external web service is backgrounded, persistent, recently awakened, or active while device is locked or without recent user interaction in a way inconsistent with expected app behavior
- **MobileEDR:telemetry** — Managed app shows background activity, refresh, or lock-state-adjacent execution temporally aligned to web-service communication without expected foreground use or recent user interaction
- **MobileEDR:telemetry** — AppState=background or foreground_service active when resolver retrieval request occurred and pivot connection followed without foreground transition
- **MobileEDR:telemetry** — LastUserInteractionDelta exceeded threshold before resolver retrieval and subsequent pivot connection sequence
- **MobileEDR:telemetry** — DeviceLockState=locked or BackgroundRefresh active during resolver→pivot sequence
- **MobileEDR:telemetry** — LastUserInteractionDelta exceeded threshold before resolver request and pivot connection sequence
- **MobileEDR:telemetry** — AppState=background when bidirectional exchange with public web-service domain began and no foreground transition occurred between retrieval and outbound write
- **MobileEDR:telemetry** — DeviceLockState=locked during inbound retrieval and subsequent outbound write sequence to public web-service platform
- **MobileEDR:telemetry** — LastUserInteractionDelta exceeded threshold before retrieve-then-write exchange to public web-service domain from same app identity
- **MobileEDR:telemetry** — BackgroundRefresh or background activity was active when retrieve-then-write exchange with public web-service domain occurred
- **MobileEDR:telemetry** — AppState=background when repeated retrieval from public web-service domain began and no foreground transition occurred during the retrieval sequence
- **MobileEDR:telemetry** — DeviceLockState=locked during repeated inbound retrieval sequence from public web-service platform
- **MobileEDR:telemetry** — LastUserInteractionDelta exceeded threshold before repeated retrieval sequence from public web-service domain from same app identity
- **MobileEDR:telemetry** — AppState=background when non-standard-port session began and no foreground transition occurred during repeated or persistent connection sequence
- **MobileEDR:telemetry** — DeviceLockState=locked during outbound session using non-standard protocol-to-port pairing
- **MobileEDR:telemetry** — LastUserInteractionDelta exceeded threshold before app-attributed session using non-standard protocol-to-port pairing
- **MobileEDR:telemetry** — LastUserInteractionDelta exceeded threshold before camera session start and no foreground transition occurred during sustained capture interval
- **MobileEDR:telemetry** — Background activity, low-interaction device state, or DeviceLockState=locked was observed during sustained camera session or immediately before camera access from same bundle context
- **MobileEDR:telemetry** — Capturing app remained backgrounded or foreground-service-only while screen capture session occurred and another app was foregrounded during capture interval
- **MobileEDR:telemetry** — LastUserInteractionDelta exceeded threshold before screen capture session start and no expected foreground transition or consent-linked interaction occurred during capture interval
- **MobileEDR:telemetry** — Sensitive app category remained foregrounded during screen capture session from different app identity
- **MobileEDR:telemetry** — Injecting app remained backgrounded or foreground-service-only while injected click, global action, or text insertion occurred in a different foreground app
- **MobileEDR:telemetry** — LastUserInteractionDelta exceeded threshold before injected UI action and no matching touch interaction was observed for the target foreground app during injection sequence
- **MobileEDR:telemetry** — Sensitive app category remained foregrounded during injected UI sequence from different app identity
- **MobileEDR:telemetry** — Notification access event occurs while app_state=background AND device_state=locked OR no recent user interaction
- **MobileEDR:telemetry** — Crypto + data staging occurs while app_state=background OR device_locked=true OR no recent user interaction
- **MobileEDR:telemetry** — Asymmetric crypto operations occur while app_state=background OR device_locked=true OR no recent user interaction
- **MobileEDR:telemetry** — TLS trust customization and outbound HTTPS session occur while app_state=background or device_locked=true or recent_user_interaction=false
- **MobileEDR:telemetry** — Managed app initiates or resumes network-capable execution while app_state=background or device_locked=true before opaque TLS session attempt
- **MobileEDR:telemetry** — Managed app enters background-capable execution or resumes processing immediately before archive-like file creation or upload behavior
- **MobileEDR:telemetry** — Persistent foreground-service notification is created, updated, or remains visible while app behavior or notification identity is inconsistent with declared function during the persistence interval
- **MobileEDR:telemetry** — Ingress transfer and local file creation occur while app_state=background or device_locked=true or recent_user_interaction=false during the acquisition phase
- **MobileEDR:telemetry** — Ingress retrieval and staging occur while app_state=background or device_locked=true or recent_user_interaction=false during the acquisition phase
- **MobileEDR:telemetry** — Native library load or JNI-backed execution occurs while app_state=background or device_locked=true or recent_user_interaction=false during the execution phase
- **MobileEDR:telemetry** — Modified or newly replaced application begins execution or persists while recent_user_interaction=false or device_locked=true or launch context is inconsistent with expected user-driven update flow
- **MobileEDR:telemetry** — System event occurs (e.g., SMS received, device boot completed, network state changed) acting as trigger event for execution phase
- **MobileEDR:telemetry** — application remains inactive across normal execution windows and transitions into background or foreground activity burst only when qualifying device context, lock state, locale, or network condition exists
- **MobileEDR:telemetry** — application remains dormant, low-activity, or background-resident across non-qualifying locations and transitions into active execution only after geographic condition is met
- **MobileEDR:telemetry** — application reduces or halts operational activity during periods of active user interaction and resumes background execution or periodic work only during low-motion or idle intervals
- **MobileEDR:telemetry** — ecurity or monitoring application transitions to disabled, inactive, or non-reporting state while other applications remain active

## Analytics using this component

- [AN1646 - Analytic 1646](../Analytics/AN1646.md)
- [AN1647 - Analytic 1647](../Analytics/AN1647.md)
- [AN1648 - Analytic 1648](../Analytics/AN1648.md)
- [AN1649 - Analytic 1649](../Analytics/AN1649.md)
- [AN1651 - Analytic 1651](../Analytics/AN1651.md)
- [AN1653 - Analytic 1653](../Analytics/AN1653.md)
- [AN1654 - Analytic 1654](../Analytics/AN1654.md)
- [AN1656 - Analytic 1656](../Analytics/AN1656.md)
- [AN1660 - Analytic 1660](../Analytics/AN1660.md)
- [AN1663 - Analytic 1663](../Analytics/AN1663.md)
- [AN1664 - Analytic 1664](../Analytics/AN1664.md)
- [AN1665 - Analytic 1665](../Analytics/AN1665.md)
- [AN1666 - Analytic 1666](../Analytics/AN1666.md)
- [AN1675 - Analytic 1675](../Analytics/AN1675.md)
- [AN1676 - Analytic 1676](../Analytics/AN1676.md)
- [AN1684 - Analytic 1684](../Analytics/AN1684.md)
- [AN1692 - Analytic 1692](../Analytics/AN1692.md)
- [AN1697 - Analytic 1697](../Analytics/AN1697.md)
- [AN1698 - Analytic 1698](../Analytics/AN1698.md)
- [AN1705 - Analytic 1705](../Analytics/AN1705.md)
- [AN1706 - Analytic 1706](../Analytics/AN1706.md)
- [AN1707 - Analytic 1707](../Analytics/AN1707.md)
- [AN1711 - Analytic 1711](../Analytics/AN1711.md)
- [AN1714 - Analytic 1714](../Analytics/AN1714.md)
- [AN1716 - Analytic 1716](../Analytics/AN1716.md)
- [AN1719 - Analytic 1719](../Analytics/AN1719.md)
- [AN1723 - Analytic 1723](../Analytics/AN1723.md)
- [AN1724 - Analytic 1724](../Analytics/AN1724.md)
- [AN1725 - Analytic 1725](../Analytics/AN1725.md)
- [AN1726 - Analytic 1726](../Analytics/AN1726.md)
- [AN1727 - Analytic 1727](../Analytics/AN1727.md)
- [AN1728 - Analytic 1728](../Analytics/AN1728.md)
- [AN1730 - Analytic 1730](../Analytics/AN1730.md)
- [AN1731 - Analytic 1731](../Analytics/AN1731.md)
- [AN1737 - Analytic 1737](../Analytics/AN1737.md)
- [AN1738 - Analytic 1738](../Analytics/AN1738.md)
- [AN1750 - Analytic 1750](../Analytics/AN1750.md)
- [AN1752 - Analytic 1752](../Analytics/AN1752.md)
- [AN1755 - Analytic 1755](../Analytics/AN1755.md)
- [AN1757 - Analytic 1757](../Analytics/AN1757.md)
- [AN1762 - Analytic 1762](../Analytics/AN1762.md)
- [AN1764 - Analytic 1764](../Analytics/AN1764.md)
- [AN1768 - Analytic 1768](../Analytics/AN1768.md)
- [AN1770 - Analytic 1770](../Analytics/AN1770.md)
- [AN1771 - Analytic 1771](../Analytics/AN1771.md)
- [AN1778 - Analytic 1778](../Analytics/AN1778.md)
- [AN1779 - Analytic 1779](../Analytics/AN1779.md)
- [AN1781 - Analytic 1781](../Analytics/AN1781.md)
- [AN1784 - Analytic 1784](../Analytics/AN1784.md)
- [AN1788 - Analytic 1788](../Analytics/AN1788.md)
- [AN1789 - Analytic 1789](../Analytics/AN1789.md)
- [AN1790 - Analytic 1790](../Analytics/AN1790.md)
- [AN1793 - Analytic 1793](../Analytics/AN1793.md)
- [AN1794 - Analytic 1794](../Analytics/AN1794.md)
- [AN1796 - Analytic 1796](../Analytics/AN1796.md)
- [AN1805 - Analytic 1805](../Analytics/AN1805.md)
- [AN1808 - Analytic 1808](../Analytics/AN1808.md)
- [AN1809 - Analytic 1809](../Analytics/AN1809.md)
- [AN1815 - Analytic 1815](../Analytics/AN1815.md)
- [AN1816 - Analytic 1816](../Analytics/AN1816.md)
- [AN1817 - Analytic 1817](../Analytics/AN1817.md)
- [AN1821 - Analytic 1821](../Analytics/AN1821.md)
- [AN1823 - Analytic 1823](../Analytics/AN1823.md)
- [AN1824 - Analytic 1824](../Analytics/AN1824.md)
- [AN1826 - Analytic 1826](../Analytics/AN1826.md)
- [AN1827 - Analytic 1827](../Analytics/AN1827.md)
- [AN1828 - Analytic 1828](../Analytics/AN1828.md)
- [AN1831 - Analytic 1831](../Analytics/AN1831.md)
- [AN1832 - Analytic 1832](../Analytics/AN1832.md)
- [AN1836 - Analytic 1836](../Analytics/AN1836.md)
- [AN1847 - Analytic 1847](../Analytics/AN1847.md)
- [AN1848 - Analytic 1848](../Analytics/AN1848.md)
- [AN1849 - Analytic 1849](../Analytics/AN1849.md)
- [AN1853 - Analytic 1853](../Analytics/AN1853.md)
- [AN1854 - Analytic 1854](../Analytics/AN1854.md)
- [AN2290 - Analytic 2290](../Analytics/AN2290.md)
- [AN2291 - Analytic 2291](../Analytics/AN2291.md)
