Version: NAFATH-V1
Track: Networking

## Overview
The single sign-on service combines six disciplines around one citizen login. Software engineering builds it on OpenID Connect, which handles user authentication, while OAuth 2.0 only delegates access to resources. On Android, the app is sandboxed and requests dangerous permissions, such as the camera, at runtime and only when a user action needs them. Networking uses DNS over HTTPS to encrypt DNS lookups against eavesdropping and tampering, though it does not hide the destination server or replace TLS. Cybersecurity requires phishing-resistant authentication such as passkeys (FIDO2/WebAuthn), unlike SMS codes or one-time passwords. AI fraud detection must be governed under a framework like NIST AI RMF, addressing bias, false positives, deepfakes, and explainability before launch. Data handling follows Oman's Personal Data Protection Law: consent, notice, a data protection officer, breach notification, and restricted transfers abroad.
## Software
OAuth 2.0 is a delegated authorization framework that lets an application access protected resources, such as files or contacts, on a user's behalf using an Access Token. OpenID Connect (OIDC) is an identity layer built on top of OAuth 2.0 that handles authentication, verifying who the user is through an ID Token. In a multi-agency government program, OIDC provides single sign-on through the national digital identity, while OAuth 2.0 ensures each agency's service accesses only the data the citizen has explicitly authorized.

Resource: OAuth 2.0 Simplified - OAuth.com - https://www.oauth.com/oauth2-servers/openid-connect/authorization-vs-authentication/
## AI
Using AI involves several risks, including bias against certain groups, threats to data privacy and its centralization, wrong decisions that are hard to explain, and misuse in deepfakes and cyberattacks. To address these risks, systems should be tested before launch and monitored continuously; data collection should be minimized and protected; final decisions should remain with humans, with appeals and alternatives available; and a responsible party should be assigned to each service, with periodic penetration testing.

Resource: NIST IR 8280: https://nvlpubs.nist.gov/nistpubs/ir/2019/NIST.IR.8280.pdf

## Mobile
Android enforces application sandboxing, restricting each app to its own resources unless access is explicitly granted. On Android 6.0 (API 23) and above, dangerous permissions such as CAMERA must be requested at runtime; a manifest declaration alone is insufficient. The login app should request each permission contextually, only when a user action requires it (for example, scanning a QR code), verify permission status before accessing the resource, and provide a fallback, such as manual code entry, if access is denied.

Resource: Request runtime permissions - https://developer.android.com/training/permissions/requesting

## Networking
DNS over HTTPS (DoH) encrypts DNS lookups by carrying them inside HTTPS, so anyone on the network can't read which domains you visit or tamper with the answers, even on public Wi-Fi. However, DoH doesn't hide your lookups from the resolver itself, doesn't conceal the destination IP address from your provider, and doesn't protect page content or devices already infected with malware.

Resource: RFC 8484: DNS Queries over HTTPS (DoH) - https://www.rfc-editor.org/info/rfc8484/

## Cybersecurity
An authentication method is phishing-resistant when attackers cannot trick users into handing over a usable credential, for example through a fake login page. FIDO2/WebAuthn authenticators (security keys, or platform authenticators with biometrics or PIN) and PKI-based methods such as smart cards qualify. SMS or voice codes, app-based one-time passwords, and push notifications, even with number matching, do not qualify, because they remain vulnerable to phishing or related attacks such as SIM swapping and push bombing.

Resource: Implementing Phishing-Resistant MFA (CISA fact sheet) - https://www.cisa.gov/sites/default/files/publications/fact-sheet-implementing-phishing-resistant-mfa-508c.pdf

## Data
Where the law applies, the authority acting as controller must obtain and prove explicit consent with clear notice of purpose, apply risk-based safeguards, and obtain a Ministry permit before processing biometric data. It must erase data once its purpose ends, keep processing records, appoint a data protection officer, keep data confidential, notify the Ministry and individuals of breaches, allow human review of automated decisions, and transfer data abroad only under set controls.

Resource: Royal Decree 6/2022 Issuing the Personal Data Protection Law (Consolidated) - https://decree.om/2022/l20220006/
## Misconception in My Track

## Open Question
