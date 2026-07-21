---
title: "Meeting Capture — GDC TRTF Track 2, 2026-07-10"
type: meeting-notes
audience: internal (co-leads)
captured: 2026-07-10
source: Notion meeting notes (Trust Registries Track 2 — Architecture & Technical Specs)
tags: [gdc, trust-registries, track2, architecture, trqp, scope, pre-transaction, input]
---

# Meeting Capture — GDC TRTF Track 2, 2026-07-10

Internal capture of the Track 2 (Architecture & Technical Specs) meeting. Darrell is co-lead / participant. Companion to the [Track 1 capture](meeting-notes-track1-2026-07-10.md). Quorum not reached; the group proceeded to gather feedback. Attendees included Darrell (Ayra/IIRA), Jason (Apple), Hisham (Apple), Mike McCaskill (AAMVA), Ruth, John, and others.

## The architectural decision that matters — scope to "known before the transaction"

The strongest outcome. Track 2 should limit scope to use cases where the **relying party can know who they trust *before* the transaction** — the full issuer list is knowable in advance. That's government-issued identity documents (driver's licenses, national ID, passports).

- Why it works: it "limits the blast radius" of the hardest complexity — dynamic, real-time trust resolution. The RP doesn't need the credential in hand to decide whether it trusts the issuer.
- What it defers: fully dynamic, real-time registry queries. Supply-chain tier-2/tier-3 suppliers (e.g. Turkey) are unknown in advance; education degrees traverse University of Waterloo → ARUCC → issuers that may sit in Credly, Credential Engine, and eduGAIN simultaneously. Those *require* live queries — out of scope for now, expand later.
- Framing recommendation: **avoid the term "digital identity"** where possible — politically radioactive (Paul Jackson flagged Canada; also Utah; "gets conspiracy theorists going"). Frame instead as **"a registry the relying party has prior to transaction."** This sidesteps the sensitivity and describes the architecture accurately.

This is the Track 2 (architecture) mirror of the Track 1 (policy) scoping: narrow to identity documents, known issuer set, before the transaction.

## Pre-transaction vs post-transaction trust

Strong consensus: RPs should know what they trust *before* requesting credentials, not decide trust after receiving them. The registry is the way an RP accesses the list of who to trust ahead of time. Out-of-band refresh is fine ("give me all the AAMVA issuer keys monthly") — what's rejected is discovering trust at transaction time and implicitly trusting whatever shows up.

## Private note (Darrell) — not for sharing yet (not confidential)

> **Concern with the static-list scoping.** Limiting to a static list scopes the work down to *not useless, but not overly useful* for most use cases. A static, pre-transaction list works for very official government identity documents — and fails immediately on the next step, where the issuer set isn't fully knowable in advance or changes too often to freeze. A dynamic capability is genuinely required. The static framing can't be the destination; it's the starting wedge.
>
> **Realistically you need both modes, not one.** The architecture has to handle *before the transaction* **and** *during the transaction*:
>
> - **Before** — the verifier keeps a local list of known issuers and their status, refreshed on a schedule (TRQP or similar polling). Fast, low-latency, and the only thing that works offline / low-connectivity (the cached-VICAL, fishing-camp-with-no-comms case). Handles the known-issuer path.
> - **During** — when the verifier hits an issuer it doesn't already know, or needs current status at transaction time, it makes a live query. Handles the unknown-issuer / fresh-status path.
>
> These are not two architectures. They're the same query capability (TRQP-style) used at two different times — cache-and-refresh vs live lookup. Designing for both from the start costs little; designing for only the static case bakes in a redesign later.
>
> **How this sits with the group's scope.** "Known before the transaction" is still the right *first delivery* — government identity documents, cached list, blast radius contained. The refinement is architectural, not a scope expansion: build the v0.1 so the during-transaction path drops in without a redesign. Keep the delivery narrow; keep the design honest that both modes exist.
>
> **Why hold the full framing for now (my read).** Leading with "we also need real-time" in the room reopens the dynamic complexity the group just deferred and blows the blast-radius discipline that made the scope shippable. Introduce it as the *design seam*, not a build-it-now demand: "let's make sure the static list is just a cached refresh of the same query we'll later run live." Extension mechanism, not expansion.

## Trust Registry Query Protocol (TRQP)

Darrell introduced TRQP (published at Trust over IP / JDF; origin: Good Health Pass / COVID credential work) as the relevant existing spec. Two endpoints only:

- **Authorization** — does entity X have authorization Y in governance framework Z?
- **Recognition** — does ecosystem A recognize trust registry B? (enables cross-recognition)

Its architectural value is separating those two questions. Cross-recognition example: ICAO recognizes AAMVA as a driver's-license authority; AAMVA recognizes ICAO as a passport authority, optionally jurisdiction-scoped. Darrell to share the TRQP spec link + diagram with the group.

## Trust registries vs "credentials all the way down"

W3C Recognized Entities (Steve Capell, tied to UN GRID) is an input: a body like AAMVA issues a credential to an issuer asserting membership; the verifier checks that credential. IIRA's position: prefer a trust registry, because credential-checking-a-credential is "turtles all the way down" — at some point you need a **root of trust**. Better to say "that came from AAMVA, I recognize AAMVA, good to go." Recognized-Entity credentials are one supported input, not the foundation.

## Governance principle — audits are inputs, not determinants

Darrell (live in the meeting): third-party accreditation (ISO 27001, SOC 2, WebTrust) does **not** automatically grant entry to a trust registry. It is the **governance body's decision** that grants entry; third-party audits are **inputs, not determinants**. Governments cannot be mandated to follow an independent auditor — try it and the conversation ends. In practice US state issuers *want* to participate (customer convenience, security) and will align to sensible guidelines. Real ID is the analogy: security became a precondition for convenience (TSA acceptance), not an outright mandate.

This is exactly the [recognition vs certification vs audit](../../../../kb/ayra-common-kb/how-we-work/recognition-vs-certification-vs-audit.md) distinction, stated independently in Track 2 — recognition is the governance body's decision; certifications are backing evidence. Strong cross-track validation.

## Wallet platform's role in governance

Consensus: the wallet platform is a **consumer of governance, not a governance decision-maker**. The wallet should not determine which issuers an RP trusts. Nuances:

- In a multi-wallet world (especially EU), the registry is also useful for wallets to verify issuers at first credential issuance.
- Derived credentials (passport → Apple Wallet mDL) *do* require the wallet platform to participate in governance for that specific function.

## Verifier scaling — proxy verifiers and dynamic lists

- Small verifiers are bad at managing trust hierarchies. The pattern is **proxy verifiers**: the Italian model (PID/CIE — two competing national ID networks) has verifiers delegating to a federation-provided proxy resolver. Consensus: verifiers need a trusted org to manage trust on their behalf to scale.
- The trusted-issuer list is inherently **dynamic**. Pre-cached/static snapshots (e.g. nightly) are practical but must be kept current — a fundamental business problem for everyone. XML metadata is the cautionary tale (three iterations due to scale).
- **Metadata approach** (SAML-inspired, one of the competing options): the verifier has a signing key pointing to a metadata document carrying trust marks from multiple organizations ("trusted by this country, that country") — avoids multiple signatures per request.

## Field notes

- **French govt digital ID pilot:** phone-based photo ID for Schengen crossing, 2 days, derived from passport, signed by French govt key, stored in the French app ("Aiden Mobile"), presented via ISO 18013-5. Very constrained (specific airport/terminal/kiosk). Compared to the early Canada–Schiphol (Ottawa↔Schiphol) Accenture digital-traveler pilot — small constrained pilots as good starting points.
- **CBP angle:** a contact recently moved TSA→CBP is being encouraged to push CBP to accept derived credentials (e.g. Apple Digital ID) for entry, particularly ESTA — CBP has authority to do this without State Department permission.
- **mDL history:** Louisiana issued the first mDL; Arizona later used three separate keys (one per limitation, to isolate their native wallet if compromised) — now optional, not required. Pattern: the first mDL is very hard; each subsequent one gets easier as muscles develop.

## Action items

- Jason to consolidate discussion notes, incorporate Hisham's input, report back.
- Define and document the agreed Track 2 scope — use cases where the RP knows who they trust *before* the transaction.
- Darrell to share the TRQP spec link (+ diagram dropped in the doc/chat).

## So-what for our co-leads work

Track 1 and Track 2 converged on the same wedge from two directions: **narrow to government-issued identity documents with a known-in-advance issuer set.** Track 1 frames it as policy/onboarding scope; Track 2 frames it as "the registry the RP has prior to transaction" and the blast-radius argument for deferring dynamic resolution. Both are [focus-enables-integration](../../../../kb/ayra-common-kb/how-we-work/focus-enables-integration.md) in practice. The two live threads to carry forward: (1) TRQP as the candidate query architecture with its authorization/recognition split, and (2) the audits-are-inputs-not-determinants principle, now stated in both tracks. Next move is a short Track 2 scope-and-architecture note that writes the "before the transaction" boundary down cleanly, the way the Track 1 simplifications doc did for policy.
