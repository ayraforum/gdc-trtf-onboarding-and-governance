---
title: "Track 3 — RP Onboarding Framework v0.1 (outline)"
type: draft
status: DRAFT outline for discussion with Track 3 co-leads
champion: Darrell O'Donnell (Ayra)
event: GDC 2026, Geneva — September 2026
captured: 2026-06-15
tags: [draft, gdc, trust-registries, track3, rp-onboarding, framework]
---

# Track 3 — RP Onboarding Framework v0.1 (outline)

> Draft outline for the Geneva deliverable. Built on the scope in [[07-track3-rp-onboarding-scope-gdc2026]] and the shared vocabulary in [[01-trust-management-defining-the-challenge]]. This is a skeleton to take to the co-leads (France / Apple) and the sub-group — not a finished spec.

## The one question this framework answers

**How does a relying party that wants to consume government-issued identity get recognized, onboarded, and trusted — and how does that recognition travel across ecosystems?**

Everything in v0.1 serves that sentence. If a section doesn't, it's out of scope for Geneva.

## 1. Purpose and the ask

A short statement of what an RP Onboarding Framework is for: giving verifiers a known, repeatable path to be recognized as legitimate consumers of government-issued credentials — and giving issuers and holders confidence that the verifier on the other side is who it claims to be and is asking for what it's allowed to ask for.

The ask of the reader (RP, verifier, ecosystem operator): adopt a common onboarding lifecycle and a common way of expressing "this RP is recognized to do X."

## 2. Scope

Pull the table from [[07-track3-rp-onboarding-scope-gdc2026]] verbatim. Restate the discipline up front:

- **In scope (Geneva v0.1):** RP/verifier onboarding for verifiers consuming **government-issued** identity; the privacy/security model; the governance principles for who recognizes an RP.
- **Lead toward (named, not solved):** cross-ecosystem recognition (registry-of-registries); the "discovery of trust links" gap.
- **Open scope question:** whether wallet authorization / wallet approval belongs in Track 3, or whether Track 3 only defines the verifier authorization that wallets must be able to check.
- **Out of scope:** non-government / commercial-only ecosystems; wire-format selection (defer to Track 2 / OIDF).

## 3. Where this sits in the shared vocabulary

Anchor the framework in the SIDI Hub Trust Vectors so we're not inventing a parallel language. RP onboarding is mostly about three of the six:

- **User Trusts Verifier** (Vector 3) — the holder knows the RP is legitimate and is informed before sharing.
- **Ecosystem Trusts Reader** (Vector 5) — the RP/reader can identify itself and is authorized to request a given scope (Verifier Attribute Policies).
- **Reader Trusts Issuer** (Vector 4) — the RP can validate the government credential against an authoritative issuer.

Onboarding is the process that establishes the magnitude of trust on these vectors *before* a transaction happens.

## 4. Definitions

Short, plain definitions (one line each), reusing existing terms wherever they exist:

- **Relying Party (RP) / Verifier / Reader** — distinguish the legal entity (RP), the role (verifier), and the component (reader).
- **Government-issued identity** — scope boundary for v0.1 (national ID, mDL, and equivalent public-sector credentials — exact line is an open question, see §10).
- **Trust registry** — the list that says which issuers/RPs are recognized and for what.
- **Registry-of-registries** — the coordination layer that lets one ecosystem's registry be discovered and honored by another.
- **Recognition** — the verifiable statement that an RP is allowed to perform a specific action (consume credential type Y).
- **Conformance** — meeting the ecosystem's defined requirements; the basis for recognition.

## 5. The RP onboarding lifecycle

The spine of v0.1. A small number of stages, each with a clear owner and exit criterion:

1. **Discover** — the RP finds the ecosystem's onboarding rules and registrar.
2. **Apply** — the RP submits eligibility evidence (who they are, what they want to verify, why).
3. **Assess / conform** — the registrar checks the RP against the ecosystem's conventions (legitimacy, purpose limitation, security, privacy posture).
4. **Recognize** — the RP is recorded as recognized to perform a scoped action; a recognition artifact is issued.
5. **Operate** — the RP verifies credentials at transaction time; holders and issuers can check the RP's recognition.
6. **Maintain / revoke** — recognition is time-bounded, renewed, suspended, or revoked.

For each stage: who acts, what's required, what the holder/issuer can see, and how it's expressed.

## 6. Trust model — what "recognized" means and how it travels

- How an RP's recognition is expressed and checked (a recognition statement an issuer or holder can validate).
- How recognition is **discovered** across ecosystem boundaries — the registry-of-registries seam. v0.1 names the requirement and the gap; it doesn't mandate a mechanism.
- Note candidate mechanisms without picking a winner (defer to Track 2): [[04-w3c-recognized-entities-v1|W3C Recognized Entities]], OpenID Federation, ToIP — and the [[08-un-cefact-global-trust-registry-gtr|UN GTR/GRID]] pattern for the registrar-recognition layer.

## 7. Privacy and security model

Government-issued ID raises the stakes; the framework has to take a position, not punt:

- **Purpose limitation and scope enforcement** — an RP is recognized for specific data, and only that (Verifier Attribute Policies). Reading a driver's licence for **age only** is a different presentation — and a different authorization — than reading it **in full**. Same credential, different recognized scope (see §8, two relationships to the governance system).
- **No phone-home** — verifying a credential must not report the transaction back to the issuing authority/government.
- **Data minimization and consent** — the holder is informed and consents; selective disclosure is the default.
- **Anti-surveillance posture** — recognition must not become a tracking channel.
- **RP authentication** — the holder can confirm the reader belongs to the recognized RP (anti-rogue-reader).

## 8. Governance — who recognizes RPs, on what basis

- The **registrar** concept: who is authorized to assess and recognize RPs (ecosystem operator, deputized registrar, or domain-specific registrar).
- The **conventions** an RP must meet to be recognized, and how those are published and enforced.
- The neutrality principle: recognition criteria are transparent and don't favor incumbents — the place to make the structural-neutrality argument concretely.

### Two relationships to the governance system

The registry has two kinds of users, and they relate to governance in fundamentally different ways. One is **governed by** it; the other **relies on** it. Miss the second and "onboarding" quietly becomes a one-way gate that only lets RPs in.

1. **The verifier / RP — the applicant.** The RP is a *client of the governance system*. It applies to be admitted, gets assessed against the conventions, and is recognized — or not — for specific presentations. Reading a driver's licence for age only is a different application than reading it in full. This is the §5 lifecycle in full: the RP is the party that lifecycle governs. Governance acts *on* the RP. (At runtime the RP also consults the registry to validate the issuer behind a credential — but its defining relationship is that it had to apply to get in.)

2. **The holder, via the wallet — the consumer.** The holder never applies to anything. They consult the registry the other way: is this verifier recognized, and recognized for what it's asking? A reader requesting full driver's-licence data when it's only recognized for age gets refused, or flagged to the holder. The holder isn't governed by the system — they're *protected* by it. Governance works *for* the holder.

In Trust Vector terms: the RP path covers **Reader Trusts Issuer** (Vector 4) and the scope side of **Ecosystem Trusts Reader** (Vector 5); the holder path is **User Trusts Verifier** (Vector 3), enforced by the wallet on the holder's behalf. v0.1 treats both as first-class. Admitting an RP is one process; the holder's right to check the verifier before presenting is another — and the registry has to serve both.

## 9. Future work — registries beyond government ID

v0.1 is scoped to government-issued identity. The same onboarding pattern has to extend to the other authoritative registries that matter, because Ayra is generically about the **registry-of-registries pattern** — not about any one credential type, and not only about person ID. Named here so the room sees the destination; sequenced as Phase 2 and beyond.

The issuer registries to bring in next:

- **Corporate / business registries** — authoritative organization and business identity (company registers, beneficial ownership, sub-national administrative bodies). The UN/CEFACT GTR/GRID is the leading example — business registries recognized by the UN, by nations, and by the administrative bodies inside them. **Organization and business ID is a first-class concern, not a footnote to person ID.** See [[08-un-cefact-global-trust-registry-gtr]].
- **Education registries** — recognized institutions and the credentials they grant. eduGAIN (84 federations, >10k entities) is the working example at scale. See [[06-edugain-and-gtr-logical-model]].
- **Travel and border contexts** — passport-derived presentations and other public-sector identity use cases where verifier authorization, purpose limitation, and cross-border reliance are central.
- **Others by domain** — healthcare, finance, professional licensing. Each is an authoritative registry of registrars in its own right.

Each of these is a source we want recognized in the registry-of-registries, so trust established in one domain can be discovered and honored in another. That is the "discovery of trust links" gap — the seam this framework eventually has to close.

## 10. Open questions for the co-leads

- Exact boundary of "government-issued identity" for v0.1.
- Are we working only on relying-party/verifier authorization, or does wallet authorization / wallet approval also belong in Track 3?
- What "onboarded" concretely produces — a recognition credential, a listing, a conformance result, or all three.
- Where the registrar role lives, and whether domain-specific registrars are in v0.1 or Phase 2.
- Is the **wallet-side check** (direction 2 — does this reader belong in the registry, for this scope?) in v0.1, or stated as a requirement with the mechanism deferred?
- How are **presentation-level authorizations** expressed and enforced — e.g., age-only vs full driver's-licence reads?

## 11. v0.1 deliverables for Geneva

- This **RP Onboarding Framework v0.1** (the lifecycle in §5 + the trust/privacy/governance positions in §6–8).
- A short **shared-terms** contribution back to Track 1 (the definitions in §4).
- A one-page **scope statement** (in / lead-toward / out) so the room holds the line.

## 12. Maps to / draws on

[[01-trust-management-defining-the-challenge]] (Trust Vectors) · [[04-w3c-recognized-entities-v1]] (candidate recognition format) · [[08-un-cefact-global-trust-registry-gtr]] (registrar-recognition pattern) · [[06-edugain-and-gtr-logical-model]] (federated trust at scale) · [[SYNTHESIS]] (Ayra positioning).
