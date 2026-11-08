# T1635 - Steal Application Access Token

[Mobile](../../../README.md) / [Credential Access](../README.md)

Adversaries can steal user application access tokens as a means of acquiring credentials to access remote systems and resources. This can occur through social engineering or URI hijacking and typically requires user action to grant access, such as through a system “Open With” dialogue.  

Application access tokens are used to make authorized API requests on behalf of a user and are commonly used as a way to access resources in cloud-based applications and software-as-a-service (SaaS).(Citation: Auth0 - Why You Should Always Use Access Tokens to Secure APIs Sept 2019) OAuth is one commonly implemented framework used to issue tokens to users for access to systems. An application desiring access to cloud-based services or protected APIs can gain entry through OAuth 2.0 using a variety of authorization protocols. An example of a commonly-used sequence is Microsoft's Authorization Code Grant flow.(Citation: Microsoft Identity Platform Protocols May 2019)(Citation: Microsoft - OAuth Code Authorization flow - June 2019) An OAuth access token enables a third-party application to interact with resources containing user data in the ways requested without requiring user credentials.

[MITRE ATT&CK record](https://attack.mitre.org/techniques/T1635)

**Tactics**  [Credential Access](../README.md)

**Platforms**  [Android](../../../Platforms/Android.md), [iOS](../../../Platforms/iOS.md)

## Sub-techniques

- [T1635.001 - URI Hijacking](T1635.001%20-%20URI%20Hijacking/README.md)

## Detection strategies

- [DET0656 - Detection of Steal Application Access Token](../../../Defenses/Detection%20Strategies/DET0656%20-%20Detection%20of%20Steal%20Application%20Access%20Token.md)

## Mitigations

- [M1013 - Application Developer Guidance](../../../Defenses/Mitigations/M1013%20-%20Application%20Developer%20Guidance.md) — Developers should use Android App Links(Citation: Android App Links) and iOS Universal Links(Citation: iOS Universal Links) to provide a secure binding between URIs and applications, preventing malicious applications from intercepting redirections. Additionally, for OAuth use cases, PKCE(Citation: IETF-PKCE) should be used to prevent use of stolen authorization codes. [iOS Universal Links](https://developer.apple.com/ios/universal-links/) · [Android App Links](https://developer.android.com/training/app-links/verify-site-associations) · [IETF-PKCE](https://tools.ietf.org/html/rfc7636)
- [M1006 - Use Recent OS Version](../../../Defenses/Mitigations/M1006%20-%20Use%20Recent%20OS%20Version.md) — iOS 11 introduced a first-come-first-served principle for URIs, allowing only the prior installed app to be launched via the URI.(Citation: Trend Micro iOS URL Hijacking) Android 6 introduced App Links. [Trend Micro iOS URL Hijacking](https://web.archive.org/web/20211023221110/https://blog.trendmicro.com/trendlabs-security-intelligence/ios-url-scheme-susceptible-to-hijacking/)
- [M1011 - User Guidance](../../../Defenses/Mitigations/M1011%20-%20User%20Guidance.md) — Users should be instructed to not open links in applications they don’t recognize.

## Sources

- [Android-AppLinks](https://developer.android.com/training/app-links/index.html)
- [Auth0 - Why You Should Always Use Access Tokens to Secure APIs Sept 2019](https://auth0.com/blog/why-should-use-accesstokens-to-secure-an-api/)
- [Microsoft - OAuth Code Authorization flow - June 2019](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-auth-code-flow)
- [Microsoft Identity Platform Protocols May 2019](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-protocols)
- [IETF-OAuthNativeApps](https://tools.ietf.org/html/rfc8252)
