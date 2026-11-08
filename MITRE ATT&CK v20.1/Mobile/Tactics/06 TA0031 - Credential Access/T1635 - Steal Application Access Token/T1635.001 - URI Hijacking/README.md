# T1635.001 - URI Hijacking

[Mobile](../../../../README.md) / [Credential Access](../../README.md) / [T1635 - Steal Application Access Token](../README.md)

Adversaries may register Uniform Resource Identifiers (URIs) to intercept sensitive data. 

Applications regularly register URIs with the operating system to act as a response handler for various actions, such as logging into an app using an external account via single sign-on. This allows redirections to that specific URI to be intercepted by the application. If an adversary were to register for a URI that was already in use by a genuine application, the adversary may be able to intercept data intended for the genuine application or perform a phishing attack against the genuine application. Intercepted data may include OAuth authorization codes or tokens that could be used by the adversary to gain access to protected resources.(Citation: Trend Micro iOS URL Hijacking)(Citation: IETF-PKCE)

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1635/001)

**Tactics**  [Credential Access](../../README.md)

**Platforms**  [Android](../../../../Platforms/Android.md), [iOS](../../../../Platforms/iOS.md)

## Mitigations

- [M1013 - Application Developer Guidance](../../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Developers should use Android App Links(Citation: Android App Links) and iOS Universal Links(Citation: iOS Universal Links) to provide a secure binding between URIs and applications, preventing malicious applications from intercepting redirections. Additionally, for OAuth use cases, PKCE(Citation: IETF-PKCE) should be used to prevent use of stolen authorization codes. [iOS Universal Links](https://developer.apple.com/ios/universal-links/) · [Android App Links](https://developer.android.com/training/app-links/verify-site-associations) · [IETF-PKCE](https://tools.ietf.org/html/rfc7636)
- [M1006 - Use Recent OS Version](../../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — iOS 11 introduced a first-come-first-served principle for URIs, allowing only the prior installed app to be launched via the URI.(Citation: Trend Micro iOS URL Hijacking) Android 6 introduced App Links. [Trend Micro iOS URL Hijacking](https://web.archive.org/web/20211023221110/https://blog.trendmicro.com/trendlabs-security-intelligence/ios-url-scheme-susceptible-to-hijacking/)
- [M1011 - User Guidance](../../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be instructed to not open links in applications they don’t recognize.

## Detection strategies

- [DET0626 - Detection of URI Hijacking](../../../../Defenses/Detection%20Strategies/DET0626%20-%20Detection%20of%20URI%20Hijacking.md)

## Sources

- [Android-AppLinks](https://developer.android.com/training/app-links/index.html)
- [Trend Micro iOS URL Hijacking](https://web.archive.org/web/20211023221110/https://blog.trendmicro.com/trendlabs-security-intelligence/ios-url-scheme-susceptible-to-hijacking/)
- [IETF-PKCE](https://tools.ietf.org/html/rfc7636)
- [IETF-OAuthNativeApps](https://tools.ietf.org/html/rfc8252)
