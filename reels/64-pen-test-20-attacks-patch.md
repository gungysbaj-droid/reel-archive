---
id: "r64"
url: "https://www.instagram.com/reel/DfsWbkrB6vN/"
creator: "@murphmaxxing"
title: "20 attacks a pen tester checks for, with a free guide and Claude Code audit prompt"
saved: "2026-11-20"
item_ids: [335, 336, 337, 338, 339, 340, 341, 342, 343, 344, 345, 346, 347, 348, 349, 350, 351, 352, 353, 354, 355]
---

# 20 pen-test attacks for your vibecoded app (murphmaxxing)

Source: [original reel](https://www.instagram.com/reel/DfsWbkrB6vN/) (Instagram video, @murphmaxxing, posted 2026-11-13).

**Provenance.** Sent as a bare link on 2026-11-20. Recorded here: the caption (verbatim below) and the creator's public guide page, which the guide says is "the page for anyone who commented PATCH on the pen-test video". The video itself could not be watched (no frames or audio available), so nothing is claimed about what is shown on screen.

**Caption (verbatim).** "Be a shame if someone tried these on your app. All 20 are public: the 398-million-requests-a-second attack Google Cloud stopped, Okta's 52-character username bug, GitLab's SAML patch, Spotify's Unicode account hijack. Theirs got fixed. Has yours? Comment 'PATCH' and I'll send you the guide: what each attack is, how to tell if it applies to you, the fix, and a prompt that checks your app for all 20 in Claude Code."

**Free or paid.** Free. The guide is a public web page (https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app) with the full prompt on it; no DM needed. The creator also pitches a free weekly email (Ultrastack).

## Items

#### 335. The guide and audit prompt

[https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app) - fill in one line about your app and stack, paste the prompt into Claude Code/Cursor/Codex in your project; it reports on all 20 first and fixes only what you approve.

#### 336. Attack 1: HTTP/2 Rapid Reset (CVE-2023-44487)

Open and instantly cancel HTTP/2 requests to exhaust a server. Google Cloud stopped one peaking above 398M requests/sec. Applies only if you run your own HTTP/2 server or proxy: patch it.

- [Google Cloud: largest DDoS attack, peaking above 398M rps](https://cloud.google.com/blog/products/identity-security/google-cloud-mitigated-largest-ddos-attack-peaking-above-398-million-rps)
- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 337. Attack 2: bcrypt 72-byte limit (Okta 52-character username bug)

bcrypt ignores input past 72 bytes. Okta hashed userId+username+password, so long usernames pushed the password out of the hash (fixed Oct 2024). Hash the password alone, cap at 72 bytes.

- [Okta security advisory, Nov 1 2024](https://trust.okta.com/security-advisories/okta-ad-ldap-delegated-authentication-username/)
- [The Verge coverage](https://www.theverge.com/2024/11/1/24285874/okta-52-character-login-password-authentication-bypass)
- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 338. Attack 3: SAML signature bypass (CVE-2024-45409, GitLab)

ruby-saml flaw let anyone holding a signed SAML document forge a login as any user. Fix: ruby-saml 1.17.0+, omniauth-saml 2.2.1+.

- [GitLab advisory CVE-2024-45409](https://advisories.gitlab.com/pkg/gem/ruby-saml/CVE-2024-45409/)
- [GitLab 17.3.3 critical patch release](https://docs.gitlab.com/releases/patches/patch-release-gitlab-17-3-3-released/)
- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 339. Attack 4: nOAuth (Microsoft login email spoofing)

Azure AD's email claim is mutable and unverified, so matching users by it allows account takeover. Match on oid+tid or sub instead.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 340. Attack 5: GraphQL alias batching

One request can carry many aliased copies of a login, 2FA or coupon check and dodge rate limits. Limit per operation and per account.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 341. Attack 6: TOTP replay (RFC 6238 section 5.2)

An authenticator code must be refused once accepted. Store the last accepted time step per user.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 342. Attack 7: ReDoS (regex denial of service)

Nested-repetition regexes on user input can freeze a server (Stack Overflow outage, July 2016). Cap input length, rewrite the regex.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 343. Attack 8: JWT algorithm confusion

Attacker switches RS256 to HS256 and signs with the public key. Pin the allowed algorithm in verify.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 344. Attack 9: HTTP request smuggling

Ambiguous Content-Length / Transfer-Encoding requests slip past a front proxy. Use HTTP/2 end to end, reject ambiguous requests.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 345. Attack 10: Web cache poisoning

Responses built from unkeyed headers like X-Forwarded-Host get cached and served to everyone.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 346. Attack 11: Spoofed X-Forwarded-For

Per-IP rate limits can be dodged if trust proxy is set to true. Set the real proxy count and also limit per account.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 347. Attack 12: Postgres views bypassing RLS

Views in an exposed schema run as their owner and skip row level security. Set security_invoker = true (Postgres 15+).

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 348. Attack 13: Math.random() tokens

Predictable tokens. Use crypto.getRandomValues / crypto.randomBytes for anything that guards something.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 349. Attack 14: Timing attacks on secret comparison

=== leaks via response time. Use crypto.timingSafeEqual or a constant-time compare.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 350. Attack 15: Padding oracle

Hand-rolled CBC encryption of cookies/tokens leaks via error differences. Use AES-GCM or framework sessions.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 351. Attack 16: Server-side prototype pollution

Merging request bodies into objects lets __proto__ keys reach RCE. Validate with a schema, block those keys, use Map.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 352. Attack 17: Server-side template injection

User input must be template data, never template source.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 353. Attack 18: XXE (XML external entity injection)

XML from users (SVG, office files, RSS, SAML) can read files. Disable external entities, DTDs and XInclude.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 354. Attack 19: Cross-site WebSocket hijacking

Cookie-session WebSockets need an Origin check and CSRF token on the handshake.

- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

#### 355. Attack 20: Unicode username normalization (Spotify 2013)

Unicode lookalike usernames hijacked accounts. Normalize once at sign-up, compare only that form.

- [Spotify Engineering: Creative usernames and Spotify account hijacking](https://engineering.atspotify.com/2013/06/creative-usernames)
- [Guide section](https://www.murphmaxxing.com/vault/20-pen-test-attacks-vibecoded-app)

