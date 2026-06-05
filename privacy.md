---
layout: default
title: Privacy Policy
permalink: /privacy/
---

# Privacy Policy

**Effective date:** May 12, 2026

Selfletter is a journal you keep with yourself. We built it so that the things you write are yours, full stop. This policy explains what we do — and more importantly what we don't do — with your information.

## The short version

- We never read what you write. Your letters are encrypted in transit and at rest with our auth provider; we have no analytics or product-side access to their text.
- We do not run analytics, do not embed third-party tracking SDKs, and do not show ads.
- The only thing we know about you is how you signed in: either an opaque Apple user identifier, or the email address you used to create an email/password account.

## What we collect

**If you sign in with Apple**, Apple gives us:

- **A stable user identifier** — an opaque string that identifies your Apple account to Selfletter. We store this on your device, in the iOS Keychain, so the app remembers you between launches. We do not transmit it anywhere.
- **Your given name** (first name only, and only on the very first sign-in) — used to personalize the greeting on the Tonight screen ("Good evening, Sam."). Stored locally in the app's settings. You can change or remove it at any time.

We do not collect your Apple email address, even when Apple offers to share it.

**If you sign in with email and password**, we collect:

- **Your email address** — stored by our authentication provider (Supabase) and locally in the app's settings. Used to identify your account and to deliver account-related email (e.g. password reset).
- **An access token and refresh token** — issued by Supabase on sign-in. Stored on your device, in the iOS Keychain. Sent to Supabase on each request that needs your identity.

We do not store your password. Supabase stores only a salted hash of it.

## What we don't collect

- We do not analyze, read, or train on the text of your letters.
- We do not collect your IP address, device ID, location, or usage analytics.
- We do not use cookies or tracking pixels.
- We do not embed any third-party analytics, advertising, or attribution SDKs.
- We do not share, sell, or rent any information about you to anyone.

## Where your letters live

Where your letters are stored depends on how you signed in:

1. **On your device** in every case — Apple's SwiftData / SQLite local database holds the canonical copy you read and write.
2. **If you signed in with Apple**: your letters also sync through **your private iCloud CloudKit container** (`iCloud.app.selfletter`). The sync is end-to-end between Apple's servers and your devices. We have no servers in this path and cannot access your iCloud data — only you and Apple can. Apple's handling is governed by [Apple's Privacy Policy](https://www.apple.com/legal/privacy/).
3. **If you signed in with email and password**: your letters also sync through **our authentication provider (Supabase)** to a Postgres database. Access to the rows of that database is restricted to your own account by a row-level-security policy — no other user, and no human at our end in normal operation, can read them. We do not run a content-moderation pipeline, search index, or anything else that requires reading the text. You can permanently delete every row from our server at any time via **Settings → Account → Delete account** (see "Your rights" below).

## Our authentication provider

For email/password sign-in we use **Supabase** (supabase.com), an open-source authentication and database service. Supabase's role is limited to:

- Verifying your email and password,
- Issuing access and refresh tokens,
- Storing the salted-hash of your password.

Supabase's handling of this data is governed by [Supabase's Privacy Policy](https://supabase.com/privacy). We do not send your letter text or any usage signals to Supabase.

## Subscriptions and purchases

Subscriptions and the lifetime upgrade are processed by Apple through StoreKit. We receive only the entitlement state from Apple (whether you have an active subscription, yes or no). We do not receive your name, billing address, payment method, or transaction history. Apple's handling of payment information is governed by Apple's privacy and payments policies.

## Notifications

If you enable the evening reminder, the notification is scheduled and delivered locally on your device by iOS. We do not run a push notification server. You can turn the reminder off at any time in Settings.

## Children's privacy

Selfletter is not directed at children under 13 and we do not knowingly collect any information from children under 13. Users in the EU and UK should be 16 or older, or have parental consent in line with applicable law.

## Your rights

Because we never collect your data, there isn't anything for us to give you, correct, or delete on our end. To remove your letters:

- **Delete the app** to remove all on-device data.
- **Manage iCloud data** through iOS Settings → Apple ID → iCloud → Manage Storage → Selfletter.

If you'd like to sign out, Settings → Account → Sign Out clears the user identifier (or Supabase tokens) from your device's Keychain.

To fully delete an email/password account and every letter stored on our server, tap **Settings → Account → Delete account**. The deletion is immediate and irreversible: your Supabase account is removed and every letter row is cascade-deleted in the same transaction. Local letters on the device are wiped at the same time. If you prefer to do it by email, write to selfletterapp@gmail.com and we will delete it within 30 days.

## Changes to this policy

If we change anything material, we'll update the effective date at the top and surface the change in an app update. Continued use after a change means you accept the updated policy.

## Contact

Questions or concerns: selfletterapp@gmail.com

---

*Selfletter is built and operated by Gurshan Mann, based in California, United States.*
