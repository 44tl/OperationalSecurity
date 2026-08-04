# OPSEC & Darknet Research Guidelines

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

> **Do not get caught.** Do not tell anyone you use the darknet. One slip destroys everything.

---

## Before You Start: Ask Yourself These Questions

OPSEC is not for everyone. Taking extreme privacy measures can itself become a signal that draws attention.

**Why do you want OPSEC?**
**Who is your enemy?**
**Who is the attacker?**
**What are you hiding?**
**Why are you hiding it?**

If you are an ordinary person living a normal life, extreme OPSEC measures may actually make you stand out and get tracked. Don't do these things unless you have a real, identified threat. If you don't have an enemy, you don't need this guide.

---

## Rule Number One: Do Not Get Caught & No Human Interaction

**Do not get caught being on the darknet.** Never tell people in your life. The darknet has bad connotations — one association and you're compromised.

**Never tie identities.** Always use different emails, names, and handles. Everything you can do to avoid being linked back to yourself.

- **Do not trust your VPN.**
- **Do not use a VPN before Tor.**

## Email Is Insecure

There is no secure email provider. Email is an inherently insecure form of communication. Law enforcement loves it — it provides confessions, timestamps, parties, and metadata. 

**Why email fails:**
- Messages live on servers you don't control, with unknown retention and archiving policies
- Traffic passes through many servers; any one can intercept
- SSL/TLS only protects the first leg (your computer to your email server)
- Drafts folders are commonly used as information containers
- Sniffers can read emails in transit

**Bottom line:** Never send sensitive information via email. Encrypted messages (PGP, etc.) protect content in transit, but email remains vulnerable to metadata exposure and server-side access long after delivery.

---

## 1. Threat Modeling — Know Your Enemy

Before choosing tools, ask: **who are you protecting yourself from?** A casual snooper? A determined government agency? Your threat level dictates your OPSEC posture. Higher threat levels require stronger isolation — like **Tails OS**.

---

## 2. Data Minimization — Less is More

- Think before clicking: do you really need to sign up for that site? Use a burner email if so.
- Use ephemeral services that auto-delete messages.
- Strip metadata from images and documents before sharing.
- Keep sensitive data off personal devices. **Tails OS** runs entirely in RAM and leaves no trace on shutdown.

---

## 3. Compartmentalization — Build Your Firewalls

Treat your digital life like a ship with watertight compartments. If one area is breached, damage is contained.

- **Separate devices:** Use a dedicated device for **Tails** or sensitive activities.
- **Virtual machines:** VMs provide isolated environments, though booting directly into **Tails** is preferred for maximum security.
- **Separate identities:** Never reuse the same email, username, or password across platforms.
- **Tails as a compartment:** Booting into Tails creates an isolated environment that vanishes on shutdown.

---

## 4. The Human Element — You Are the Biggest Vulnerability

**All the tech in the world won't save you if you slip up.**

- **Social engineering:** Be skeptical of unsolicited messages and requests. Phishing is still the most effective attack.
- **Operational consistency:** Develop habits and stick to them. One moment of carelessness undoes months of effort.
- **Don't trust — verify:** Applies to people and software alike.

---

## 5. Tools of the Trade

- **Tails OS** — Runs entirely in RAM. Leaves no traces. Ideal for one-time secure operations.
- **Qubes OS** — Security-focused OS using Xen-based VMs. Each activity runs in an isolated "qube."
- **Whonix OS** — Debian-based OS that routes all traffic through Tor.

---

## Core OPSEC Rules

- **Limit metadata** — Strip EXIF from images.
- **Delay posting** — Share operational details only after events conclude.
- **Compartmentalize** — Separate identities; never reuse handles.
- **Harden devices** — Minimal IoT, updated firmware, isolated networks.
- **Phishing-resistant MFA** — Use hardware security keys (FIDO2/WebAuthn), not SMS.
- **Financial isolation** — Use single-use virtual cards; never link primary banking to secondary services.
- **Browser hardening** — Use hardened Firefox with NoScript and uBlock Origin; disable WebRTC.
- **DNS leak protection** — Verify DNS routes through your anonymity network.
- **SIM swap protection** — Add a PIN to your mobile carrier account.
- **Timezone discipline** — Never access darknet forums during your local timezone hours.
- **Exit node awareness** — Never send unencrypted sensitive data over Tor.
- **Forum hygiene** — Unique credentials for every forum. Verify onion addresses through multiple trusted sources.

---

## Common OPSEC Mistakes

Each of these has led to real-world compromises:

- **Using Windows or mobile devices** for sensitive operations — use Tails or Whonix on dedicated hardware.
- **Reusing usernames or emails** across identities — even one reused handle is a pivot point.
- **Leaving hard drives unencrypted** — use VeraCrypt or LUKS with strong passphrases.
- **Weak or reused passwords** — use a password manager. Generate unique 16-32 character credentials for every service.
- **Retaining packaging** — dispose of shipping labels and materials immediately.
- **Self-incrimination via social media** — never document operational timelines or locations.
- **Skipping encryption** — encrypt addresses and sensitive data locally, never trust third-party websites.
- **Neglecting updates** — unpatched vulnerabilities are actively exploited.
- **Opening untrusted files** — scan documents and executables in a sandbox first.
- **Using personal devices for operational work** — strict separation between civilian and operational use.

---

## Darknet Research & Operations

For researchers, neutrality and discipline are paramount.

- **Neutral alias** — Formal, non-flashy usernames. No ego handles.
- **Posting style** — Keep posts short, factual, and neutral.
- **PGP discipline** — Sign posts with clean keys; rotate periodically.
- **Compartmented browsing** — Separate VMs or sandboxes for darknet activity.
- **Avoid direct engagement** — Observe, don't transact.
- **Network obfuscation** — Use Tor bridges or pluggable transports (obfs4).
- **Counter-surveillance** — Assume hostile forums log everything. Use isolated sandboxes that reset on close.
- **Financial firewall** — If transacting is required, use privacy coins (Monero) from non-KYC sources.
- **Linguistic compartmentalization** — Don't use the same vernacular or grammar as your clearnet identity.
- **Ethical boundaries** — Do not interact with illicit content beyond observation.

---

## Handling OPSEC Mistakes

OPSEC is always a trade-off between risk and reward. When past choices put you at risk:

### Document Your Risks
Document every exposure point — shared addresses, reused credentials, public posts with identifying info. Use an encrypted, offline notes system. Never cloud-based.

### Assume Persistence
Deleting information from the internet is not possible. The Wayback Machine, scrapers, and data brokers cache content indefinitely. Your goal is **containment and obfuscation**, not erasure.

### Seed Misinformation
Adding false information proactively dilutes your signal. Seed fake locations, timelines, and affiliations early. Inconsistent stories must be maintained — one slip re-establishes the link.

### Breaking the Chain
If exposure is severe, **burn the identity**:

1. **Compartment** — Document every person, platform, and credential tied to the old identity.
2. **Generate new infrastructure** — New PGP keys, emails, usernames, hardware fingerprints. Never reuse anything.
3. **Fresh environment** — Fresh OS install on dedicated hardware. Securely wipe old devices.
4. **Financial separation** — Transfer funds via privacy coins with proper churning. Never link old and new wallets.
5. **Communication hygiene** — If contact with old associates is unavoidable, use one-time bridges. Never direct association.

> **Cost of survival:** You lose reputation, history, and trust networks.

---

## Summary

| Mistake Type | Response |
|--------------|----------|
| Minor (single post, metadata leak) | Document, assess reach, seed misinformation. |
| Moderate (linked accounts, reused handles) | Burn identity, migrate infrastructure, notify trusted contacts securely. |
| Severe (targeted, physical risk, legal threat) | Full sanitization, legal preparation, silence, potential relocation. |

---

## Disclaimer

This document is drawn from open military and cybersecurity reporting.
