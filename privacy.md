---
layout: default
title: Privacy Policy
permalink: /privacy/
---

# Privacy Policy

**Effective date:** July 2, 2026

Selfletter is a journal you keep with yourself. We built it so that the things you write are yours, full stop. This policy explains what we do — and more importantly what we don't do — with your information.

## The short version

- We never read what you write. Your letters live on your device and (optionally) in your private iCloud, or on our authentication provider's database under a row-level-security policy that restricts access to your own account.
- We don't show ads inside the app, we don't run third-party usage analytics, and we don't use your letter text to train any AI model. *(If you came from one of our own App Store ads, Apple tells us which ad worked — never who you are or what you write. See below.)*
- The only thing we know about you is how you signed in: an opaque Apple user identifier, or the email address you used to create an email/password account.

## What we collect

**If you sign in with Apple**, Apple gives us:

- **A stable user identifier** — an opaque string that identifies your Apple account to Selfletter. We store this on your device, in the iOS Keychain, so the app remembers you between launches. We do not transmit it anywhere.
- **Your given name** (first name only, and only on the very first sign-in) — used to personalize the greeting on the Tonight screen ("Good evening, Sam."). Stored locally in the app's settings. You can change or remove it at any time.

We do not collect your Apple email address, even when Apple offers to share it.

**If you sign in with email and password**, we collect:

- **Your email address** — stored by our authentication provider (Supabase) and locally in the app's settings. Used to identify your account and to deliver account-related email (e.g. password reset).
- **An access token and refresh token** — issued by Supabase on sign-in. Stored on your device, in the iOS Keychain. Sent to Supabase on each request that needs your identity.

We do not store your password. Supabase stores only a salted hash of it.

**If you installed Selfletter after tapping one of our App Store ads**, Apple's AdServices framework tells us:

- **Which ad led you here** — the ad campaign, ad group, and keyword tied to your tap (never who you are or what you write). We receive this through RevenueCat, our subscription provider, and use it only to measure how well our own App Store advertising performs. It uses no advertising identifier (IDFA), requires no App Tracking Transparency permission, and never tracks you across other apps or websites.

## What we don't collect

- We do not analyze, read, or train any AI model on the text of your letters.
- We do not collect your IP address, device ID, advertising identifier, or precise location. We do record a small set of anonymous, first-party usage events (for example, "saw the upgrade screen"), tied to a random identifier — never your name, your email, or anything you write — so we can see where the app confuses people and fix it. These events go to our own database (Supabase, listed below) and are never shared or sold.
- We do not use cookies or tracking pixels.
- Apart from RevenueCat — which manages subscriptions and, for people who arrive from our App Store ads, measures which ad led to the install (described above) — we embed no third-party analytics, advertising, or attribution SDKs.
- We do not sell or rent your information, and we don't share it with anyone except the service providers that run Selfletter on our behalf (Apple, Supabase, and RevenueCat), as described above.
- We do not track you across other apps or websites — App Tracking Transparency is not applicable to Selfletter.

## Where your letters live

Where your letters are stored depends on how you signed in:

1. **On your device** in every case — Apple's SwiftData / SQLite local database holds the canonical copy you read and write.
2. **If you signed in with Apple**: your letters also sync through **your private iCloud CloudKit container** (`iCloud.com.selfletter.app`). The sync is end-to-end between Apple's servers and your devices. We have no servers in this path and cannot access your iCloud data — only you and Apple can. Apple's handling is governed by [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).
3. **If you signed in with email and password**: your letters also sync through **our authentication provider (Supabase)** to a Postgres database. Access to the rows of that database is restricted to your own account by a row-level-security policy — no other user, and no human at our end in normal operation, can read them. We do not run a content-moderation pipeline, search index, or anything else that requires reading the text. You can permanently delete every row from our server at any time via **Settings → Account → Delete account** (see "Your rights" below).

## Data security

All communication between the app and our authentication provider (Supabase) is encrypted in transit using TLS 1.2 or higher. Letters synced via CloudKit are encrypted in transit and at rest by Apple. Letter rows stored on Supabase reside in an encrypted Postgres database; your password is stored as a salted hash, never in plaintext. We do not have a mechanism that allows a human at our end to read your letter text in normal operation.

That said, no system is perfectly secure. If we ever discover a security breach affecting your account, we will notify you by email (for email-auth users) and post a notice in the next app update.

## Data retention

Letters stay until you delete them. We do not auto-delete inactive accounts. If you sign out and never sign back in, your account on Supabase remains until you explicitly delete it via the in-app Delete Account flow, or until you email us to request deletion. Deleting the app removes all on-device letters. If you used Sign in with Apple, your iCloud copies remain in your iCloud until you remove them through iOS Settings → [Your name] → iCloud → Manage Storage → Selfletter.

## Subprocessors

We share data only with the following third-party services, and only as needed to provide the app:

- **Apple Inc.** — App Store distribution, Sign in with Apple, CloudKit sync, in-app purchases. Apple's handling is governed by [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).
- **Supabase, Inc.** — authentication and database storage for email/password users. Supabase's handling is governed by [Supabase's Privacy Policy](https://supabase.com/privacy).

We do not send your letter text to any other third party.

## Subscriptions and purchases

Subscriptions and purchases are processed by Apple through StoreKit. We receive only the entitlement state from Apple (whether you have an active subscription, yes or no). We do not receive your name, billing address, payment method, or transaction history. Apple's handling of payment information is governed by Apple's privacy and payments policies.

## Notifications

If you enable the evening reminder, the notification is scheduled and delivered locally on your device by iOS. We do not run a push notification server, do not send remote push notifications, and have no way to see whether a notification was delivered, dismissed, or tapped. You can turn the reminder off at any time in Settings.

## Diagnostic data

If you have **Settings → Privacy & Security → Analytics & Improvements → Share With App Developers** enabled in iOS, Apple may share aggregated crash and performance reports with us. These reports contain no letter content and no information that personally identifies you. You can opt out at any time in iOS Settings. We do not embed any independent crash-reporting or analytics SDK.

## Children's privacy

Selfletter is not directed at children under 13, and we do not knowingly collect any information from children under 13. Users in the EU, UK, and other jurisdictions with higher minimum ages should be 16 or older, or have parental consent in line with applicable law. If you believe a child under 13 has used Selfletter, please write to us and we will delete any data associated with that account.

## Your rights

Because we collect so little, there isn't much for us to give you, correct, or delete on our end. To exercise your rights:

- **Access and portability**: email-auth users — email us and we will send you the rows we have for your account in JSON within 30 days. Apple-auth users — your letters live in your own iCloud; access them via iOS Settings → [Your name] → iCloud → Manage Storage → Selfletter.
- **Correction**: edit any letter in the app, or write to us.
- **Deletion**: tap **Settings → Account → Delete account** (immediate, irreversible). Or write to us and we will delete within 30 days. Deleting the app removes all on-device data.
- **Withdraw consent**: sign out and delete the app.

### California residents (CCPA / CPRA)

If you are a California resident, you have the right to know what categories of personal information we collect about you, to delete it, to correct it, to opt out of any "sale" or "sharing" (we do neither), and to be free from discrimination for exercising your rights. The only categories we collect are **identifiers** (an opaque Apple user ID or your email address) and, for email-auth users, the **rows containing your own letters**. We do not sell or share your personal information for cross-context behavioral advertising. You can exercise these rights using the methods described above.

### European Economic Area, UK, and other GDPR-equivalent regions

If you are in a region with GDPR-equivalent law, you have the rights of access, rectification, erasure, restriction, portability, and objection. The legal basis for our processing is the performance of our agreement with you and, where required, your consent (which you give by signing in). You also have the right to lodge a complaint with your local data-protection authority. International transfers of your data may occur to Apple (United States) and Supabase (United States); both rely on appropriate safeguards including standard contractual clauses where applicable.

## Changes to this policy

If we change anything material, we will update the effective date at the top and surface the change in an app update. For email-auth users, we may also notify you by email when changes are material. Continued use after a change means you accept the updated policy.

## Contact

Questions or concerns: selfletterapp@gmail.com

---

*Selfletter is built and operated by Gurshan Mann, based in California, United States.*
