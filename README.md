# OPSEC & Darknet Research Guidelines

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

> As offensive AI and automated correlation tools lower the barrier to entry for threat actors, the margin for OPSEC errors approaches zero. The most successful defenders and researchers are those who assume their digital footprint is perpetually under passive surveillance. Anonymity is no longer a default state; it is an actively maintained illusion.

This repository serves as a living document for Operational Security (OPSEC) and darknet research, drawn from open military and cybersecurity reporting.

---

## Table of Contents

- [The "Nothing to Hide" Manifesto](#the-nothing-to-hide-manifesto)
- [Evolving Threat Vectors](#evolving-threat-vectors)
- [General OPSEC](#general-opsec)
- [Common OPSEC Mistakes](#common-opsec-mistakes)
- [Darknet Research & Operations](#darknet-research--operations)
- [How to Deal with OPSEC Mistakes](#how-to-deal-with-opsec-mistakes)
- [Summary](#summary)
- [Disclaimer](#disclaimer)

---

## The "Nothing to Hide" Manifesto

> **"I don't care about privacy, because I have nothing to hide!"**

If you have ever said that, you are tragically mistaken. Nobody cares what you have or do not have to hide. Least of all the corporations that monetize your private life through social platforms, smart home devices, and targeted advertising. It is accepted fact that major tech companies track your behavior and serve it back as ads, and somehow everyone is okay with that.

But not you. You go against the grain. You refuse to let modern life strip away your right to digital privacy. You have studied Tor. You have trained to master OPSEC. You have equipped yourself with the tools of the Linux ecosystem. You have even disabled JavaScript. I am proud of you.

Then you start talking. To friends, family, co-workers. And one of them utters the dreaded phrase:

> *"I don't care about privacy, because I have nothing to hide."*

So you don't have a hidden drug habit, and that makes it okay for shady CEOs to monetize your personal information? You don't care? Seriously?

It doesn't matter what you have to hide. It is about the principle: **stop taking my personal information.** Privacy should be a right. You just have to care about it.

---

## Evolving Threat Vectors

Modern adversaries have automated their intelligence gathering. Understanding their current playbooks is the first step in evasion.

| Vector | Description |
|--------|-------------|
| **AI Usage Risks** | Treat public AI tools as open forums; never paste sensitive data. |
| **IoT Exposure** | Smart devices expand attack surfaces; disable non-essential hardware. |
| **Threat Actor Playbooks** | Structured three-tier infrastructures (public, operational, extraction) are now common. |
| **Information Fusion** | Small fragments of data can be aggregated by AI into full profiles. |
| **Behavioral Randomization** | Adversaries use delayed triggers and unpredictable timing to evade detection. |
| **Deepfake Deception** | AI-generated voice and video cloning bypass traditional verification; establish verbal duress codes with family and colleagues. |
| **Harvest Now, Decrypt Later (HNDL)** | Adversaries hoard encrypted traffic for future quantum decryption; prioritize post-quantum cryptography (PQC) for sensitive communications. |
| **Stylometric Tracking** | AI analyzes writing styles (vocabulary, syntax, pacing) to link anonymous posts across platforms to a single author. |
| **Biometric Leakage** | Wearables and health apps leak behavioral patterns (sleep times, heart rate spikes) that can pinpoint real-world locations and high-stress events. |
| **Network Timing Analysis** | Adversaries correlate traffic patterns with known events to deanonymize Tor users; use padding and delay mechanisms to disrupt timing signatures. |
| **Supply Chain Compromise** | Compromised firmware and pre-installed malware on new devices can silently exfiltrate data; verify hardware integrity before operational use. |
| **Social Media Correlation** | Even indirect social media activity (likes, retweets, shared memes) can be used to build behavioral profiles that cross-reference with anonymous activity. |

---

## General OPSEC

Defensive posture requires both traditional discipline and adaptation to new technological realities.

- **Limit Metadata** — Strip EXIF data from images before posting.
- **Delay Posting** — Share travel or operational details only after events conclude.
- **Compartmentalize** — Separate identities across platforms; never reuse handles.
- **Harden Devices** — Use minimal IoT, keep firmware updated, isolate networks.
- **Audit AI Usage** — Never paste confidential text into public AI tools.
- **Phishing-Resistant MFA** — Phase out SMS and app-based codes; migrate to hardware security keys (FIDO2/WebAuthn), which are immune to real-time interception.
- **Financial Isolation** — Use single-use virtual credit cards for online purchases; never link primary banking accounts to secondary or subscription services.
- **Hardware Kill Switches** — Physically disconnect microphones and cameras via hardware switches or mic blockers when devices are not in active use.
- **Duress Protocols** — Implement panic words or digital dead-man's switches that quietly alert trusted contacts or trigger automated data wiping if you are coerced.
- **Language Randomization** — When posting anonymously, use locally run AI paraphrasing tools to mask your native writing style and neutralize stylometric analysis.
- **Browser Hardening** — Use Firefox with hardened privacy settings, NoScript, and uBlock Origin; disable WebRTC to prevent IP leaks.
- **DNS Leak Protection** — Always verify that DNS requests are routed through your anonymity network; use DNS-over-HTTPS within Tor or VPN tunnels.
- **Email Aliasing** — Use plus-addressing or email alias services to compartmentalize registrations and detect data breaches.
- **SIM Swap Protection** — Contact your mobile carrier to add a PIN or passphrase to prevent unauthorized SIM swaps that bypass SMS-based 2FA.

---

## Common OPSEC Mistakes

Understanding common failure modes is just as important as knowing best practices. Each of these mistakes has led to real-world compromises.

- **Skipping Two-Factor Authentication or Encryption** — Always enable 2FA on every account that supports it. When placing orders or transmitting sensitive information, encrypt addresses and data using local software rather than trusting third-party websites.
- **Using Weak or Outdated Cryptographic Standards** — RSA 4096-bit keys with strong, unique passphrases remain the minimum standard for PGP. Avoid legacy algorithms and ensure your key rotation schedule is documented and enforced.
- **Retaining Packaging as Proof or Trophies** — Once a package has been received and emptied, dispose of or destroy all packaging materials immediately. Shipping labels, tape, and envelopes contain forensic data that can link you to an operation.
- **Neglecting Physical and Digital Hygiene** — Establish a routine cleaning schedule for your home, workspace, and devices. Residual fingerprints, DNA, malware, or browsing artifacts can all serve as evidence.
- **Using Windows or Mobile Devices for Sensitive Operations** — Windows telemetry and mobile OS restrictions make them unsuitable for dark web activity. Use Whonix or Tails OS on dedicated hardware for anything related to darknet operations.
- **Failing to Encrypt Sensitive Files and Communications** — Encryption applies to entire files, not just text messages. Encrypt documents, archives, and containers using strong algorithms (AES-256, Argon2) before storing or transmitting them.
- **Leaving Hard Drives Unencrypted** — Use VeraCrypt or LUKS with strong passphrases to encrypt entire volumes. Full-disk encryption ensures that physical seizure of a device does not immediately compromise its contents.
- **Using Weak or Reused Passwords** — Avoid predictable patterns. Strong passwords should be 16-32 characters, mixing uppercase, lowercase, numbers, and symbols. Use a password manager to generate and store unique credentials for every service.
- **Contaminated Packaging Materials for Vendors** — Always wear gloves when handling products. Remove gloves before touching any clean surface or personal item to prevent cross-contamination and forensic transfer.
- **Self-Incrimination Through Social Media** — Never document illegal activity on social media. Avoid posting images, check-ins, or status updates that correlate with your operational timeline or location.
- **Reusing Usernames or Email Addresses Across Identities** — Even a single reused handle can serve as a pivot point for correlation. Every identity must have its own completely independent credentials and contact points.
- **Ignoring Software Updates and Security Patches** — Unpatched vulnerabilities in your OS, browser, or tools are actively exploited. Maintain a strict update cadence and verify the authenticity of all updates.
- **Downloading Files Without Verification** — Never open documents, PDFs, or executables from untrusted sources without first scanning them in a sandboxed environment. Malicious payloads are commonly distributed through seemingly innocent file shares.
- **Underestimating Browser Fingerprinting** — Even with Tor, browser canvas, font enumeration, and screen resolution can uniquely identify you. Use the Tor Browser and avoid customization that increases your fingerprint entropy.
- **Using Personal Devices for Operational Work** — Mixing personal and operational use on the same device creates cross-contamination risks. Maintain a strict separation between your civilian identity and any operational activities.
- **Failing to Verify Onion Addresses** — Phishing attacks on darknet markets are common. Always verify URLs through multiple trusted sources and bookmark legitimate addresses to avoid credential theft.
- **Neglecting Operational Security in Physical Meetings** — If physical interaction is unavoidable, choose neutral public locations, arrive via indirect routes, and avoid carrying operational devices. Leave personal phones at home.
- **Discussing Operations With Untrusted Parties** — Information shared in confidence can become evidence. Limit operational knowledge to a strict need-to-know basis, even among trusted associates.
- **Leaving Digital Traces on Shared or Public Infrastructure** — Avoid using public Wi-Fi without a VPN. If you must use public networks, ensure all traffic is tunneled through Tor or a trusted VPN before any operational activity begins.
- **Ignoring Legal and Jurisdictional Risks** — Understand the laws that apply to your location and the jurisdictions of the services you use. Legal threats are often more dangerous than technical ones.

---

## Darknet Research & Operations

For darknet researchers, maintaining a neutral presence and disciplined posting remains the safest path.

- **Neutral Alias** — Use formal, non-flashy usernames; avoid ego handles.
- **Posting Style** — Keep drops short, factual, and neutral; avoid personal details.
- **PGP Discipline** — Sign posts with clean keys; rotate keys periodically.
- **Compartmented Browsing** — Use separate VMs or sandboxes for darknet activity.
- **Avoid Direct Engagement** — Study flex posts for knowledge, but do not transact.
- **Monitor Leaks** — Track forums for data dumps to understand attacker methods.
- **Dedicated Hardware** — Conduct research on dedicated, air-gapped machines or cheap burner laptops stripped of personal identifiers, using bootable USBs (e.g., Tails OS).
- **Network Obfuscation** — Use Tor bridges or pluggable transports (like obfs4) to hide Tor usage from your ISP or network administrators.
- **Timezone Discipline** — Be hyper-aware of posting and browsing times; accessing forums at hours consistent with your local timezone destroys operational anonymity.
- **Counter-Surveillance** — Assume hostile forums log everything. Use isolated, browser-based sandboxes that reset on close, and routinely check your environment for injected tracking payloads or zero-day exploits.
- **Financial Firewall** — If absolutely required to transact for research (e.g., purchasing a leaked dataset), use privacy coins (Monero) mined or acquired through non-KYC avenues, never tied to your real identity.
- **Linguistic Compartmentalization** — Do not use the same vernacular, emojis, or grammatical quirks on the dark web that you use on clearnet social media.
- **Exit Node Awareness** — Understand that Tor exit nodes can be monitored. Never transmit unencrypted sensitive data over Tor; always use end-to-end encryption.
- **Forum Account Hygiene** — Use unique credentials for every forum. Never reuse passwords or email addresses, and consider using anonymous email services that do not require registration.
- **Research Documentation** — Keep detailed, encrypted notes of your findings. Annotate sources, timestamps, and methodology to maintain credibility and traceability.
- **Ethical Boundaries** — Do not interact with illicit content beyond observation. Do not download, redistribute, or act on material encountered during research.

---

## How to Deal with OPSEC Mistakes

OPSEC is always a trade-off between risk and reward. Most of the time, we make that assessment upfront with limited information. As situations evolve or operations deepen, you may realize that past choices now put you at risk. This guide outlines how to assess exposure, mitigate damage, and operate more securely going forward.

---

### Document Your Risks

Fixing OPSEC mistakes starts with knowing what mistakes you have made. Document key decisions where you exposed details about your real identity — whether that was sharing a shipping address with a contact, posting on a public forum with identifying information, or reusing credentials across platforms.

**Why document?**
- It eases cognitive load and reduces anxiety.
- It creates an actionable checklist of what needs to be fixed.
- It provides a timeline for assessing how long information has been exposed.

Use an encrypted, offline notes system (e.g., KeePassXC notes, local Markdown files on an encrypted volume) — never cloud-based note apps.

---

### Understand Information Persistence

**Deleting information from the internet is not possible.** Assume someone has already archived, screenshotted, or scraped it. What is out there, stays out there.

- **The Wayback Machine**, forum scrapers, and private data brokers cache content indefinitely.
- **Metadata** in images, documents, and posts often survives editing.
- **Blockchain and distributed systems** make certain records immutable.

**Implication:** Your goal is not erasure — it is **containment, obfuscation, and forward-looking hardening**.

---

### The Power of Misinformation

While removing information is rarely possible, **adding information** usually is. The key is to do this *proactively and continuously*, not just after realizing a mistake.

Investigators and correlation engines typically weight the *earliest* leaked information as the most trustworthy. OPSEC is learned gradually, and beginner mistakes are often the most damaging.

**Defensive misinformation tactics:**
- Seed false breadcrumbs early: fake locations, fake timelines, fake affiliations.
- Use deliberately inconsistent metadata (e.g., timezone mismatches, language localization settings) to poison stylometric and geolocation analysis.
- Create decoy personas that overlap slightly with your real activity to dilute signal-to-noise ratio.

> **Warning:** Misinformation as a defensive tool requires discipline. Inconsistent stories must be maintained. One slip re-establishes the link.

---

### Breaking the Chain

If you suspect exposure, it may be time to **burn the identity** and start fresh.

### Identity Switching Protocol

| Step | Action |
|------|--------|
| **1. Compartment** | Document every person, platform, and credential tied to the old identity. Treat all of them as contamination risks. |
| **2. Generate New Infrastructure** | New PGP keys, new email/XMPP handles, new usernames, new hardware fingerprints. Never reuse anything. |
| **3. Fresh Environment** | Perform a fresh OS install on dedicated hardware, or use a new burner device. Remove or securely wipe old identity data. |
| **4. Financial Separation** | Transfer any operational funds using privacy-preserving methods (e.g., Monero) with proper churning. Never link old and new wallets directly. |
| **5. Communication Hygiene** | If you must maintain contact with select individuals from the old identity, document this as a persistent risk. Use one-time bridges or dead-drop messaging, never direct association. |

> **Trade-off:** You will lose reputation, history, and trust networks. That is the cost of survival.

---

### Exiting an Operation

Sometimes switching identities is insufficient — particularly if you suspect you have been targeted and your identities are already linked.

### Sanitization Checklist

1. **Physical Sanitization**
   - Securely wipe all storage devices (use `shred`, `dd`, or physical destruction).
   - Remove any operational hardware that may be traced.
   - Sanitize your workspace for physical evidence.

2. **Digital Sanitization**
   - Review browser history, DNS caches, and application logs across all devices.
   - Revoke OAuth tokens, API keys, and session cookies.
   - Delete or securely archive encrypted backups — ensure no plaintext remnants exist.

3. **Narrative Preparation**
   - Review your documented OPSEC mistakes.
   - Prepare factual, consistent responses for each exposure point.
   - Never lie to investigators about verifiable facts — silence is safer than a detectable lie.

---

### Legal and Incident Preparation

If you operate in high-risk environments (investigative journalism, activism, security research in contested regions), prepare for the worst-case scenario *before* it happens.

- **Know your rights** under local jurisdiction. Memorize key legal phrases: *"I do not consent to a search,"* *"I wish to remain silent,"* *"I want a lawyer."*
- **Pre-arrange legal counsel** familiar with digital evidence and privacy law.
- **Establish a duress protocol** — a panic word or signal that alerts trusted contacts if you are compromised.
- **Maintain a clean personal profile** separate from any operational work. The ability to demonstrate a consistent, lawful civilian identity is a powerful defensive tool.

---

## Summary

| Mistake Type | Response |
|--------------|----------|
| Minor exposure (single post, metadata leak) | Document, assess reach, seed misinformation if needed. |
| Moderate exposure (linked accounts, reused handles) | Burn the identity, migrate infrastructure, notify trusted contacts via secure channels. |
| Severe exposure (targeted, physical risk, legal threat) | Full sanitization, legal preparation, silence, and potential physical relocation. |

---

> **OPSEC is not a state you achieve. It is a discipline you maintain.** Mistakes are inevitable. What separates professionals from casualties is the speed and thoroughness of their response.

---

## Disclaimer

The points in this repository are drawn from open military and cybersecurity reporting. They highlight how OPSEC is evolving and why continuous awareness remains essential. This document is for **educational and defensive research purposes only**. Always adhere to your local laws and organizational security policies.
