---
title: "Meeting Capture — GDC TRTF Track 1, 2026-07-10"
type: meeting-notes
audience: internal (co-leads)
captured: 2026-07-10
source: Notion meeting notes (Trust Registries Track 1) + Darrell manual notes (Google Doc)
tags: [gdc, trust-registries, track1, scope, assurance-levels, onboarding, input]
---

# Meeting Capture — GDC TRTF Track 1, 2026-07-10

Internal capture of the Track 1 (Policy, Taxonomy & Scope; Onboarding & Governance) meeting. Combines the Notion transcript/summary with Darrell's manual notes. This is the input to the simplifications analysis: [Track 1 Simplifications and Scope](../../track1-simplifications-and-scope-v0.1.md).

## Inputs on the table

- W3C Recognized Entities (Steve Capell)
- UN GRID
- "Narrow Ecosystems & Assurance Levels" (Darrell's share — both concepts adopted into the discussion)

## Where the group converged

**Scope to identity documents.** Driver's licenses, national ID cards, passports — not "digital identity credentials" (a sensitive term) and not all credentials. Stops the group from boiling the ocean and building a mega-credential with hundreds of attributes. Understood already in the physical world. Future scope may extend to business identity, officer identity, supply chain, device identity.

**Abstract to issuer onboarding.** Credential type is almost irrelevant. Digital passport, mDL, boarding pass — doesn't matter. The atomic problem is: *which entity are you, and what is your issuing key/certificate?* Binding cryptographic material to a legal / government / business entity. One onboarding model, not one per credential type.

**Gabriel's reframed problem statement.** "What is the identity assurance level when we allow an entity to register into a trust registry?" — i.e., are you indeed a representative of the entity you claim (the French government, Illinois DMV)? Narrow to the **binding of the entity to the registry**, not the issuance processes behind the credential.

**The key distinction — distribution vs certification of claims:**

- **Distribute / collect claims** — the issuer self-declares what they do; the registry makes those claims available to RPs. Core registry function. IN scope.
- **Certification of claims** — a third party certifies the issuer actually meets requirements. Separate problem. OUT of core scope for now. Certification bodies can own it; some registries may later provide both (self-declared + a certification feed, flagged with the certifying authority).
- Gabriel: to get somewhere in the next **six weeks**, focus on onboarding and self-declared claims; keep certification separate.

> Editorial note (added after the meeting): the word "certification" conflated three things and caused talking-past. Refined vocabulary in the analysis — **recognition** (the registry attests you meet its bar; in scope; itself a certification in substance), **backing certifications** (ISO/SOC 2 evidence shown at the door), **standing audit** (ongoing third-party audit; out of scope). See [Track 1 Simplifications and Scope](../../track1-simplifications-and-scope-v0.1.md), "A note on the word 'certification'", and the how-we-work concept [recognition-vs-certification-vs-audit](../../../../kb/ayra-common-kb/how-we-work/recognition-vs-certification-vs-audit.md).

**Assurance levels — make room, don't prescribe.** Standardizing assurance-level *meanings* globally is explicitly out of scope and deemed unachievable. The registry makes room for the field (it can be blank); each ecosystem defines its own. Steve: "This track is NOT setting opinion on the level of assurance." Darrell: "make room for it — not opinions about it." RPs know what level they need and evaluate accordingly.

## Two assurance dimensions, split by the room

- **Identity assurance of registry *entry*** (the binding / the gate) — are you really the entity you claim? IN scope (Gabriel: "BINDING").
- **Assurance of the issuance processes** behind each credential — for the registry's membership rules and certification bodies to determine. OUT of scope for Track 1.

This refines the earlier two-assurances framing (identity vs credential assurance): Track 1 owns the identity assurance of *who gets into the registry*, not the credential-assurance of *how each credential was made*.

## Registry as proxy, and the gate

- Nishant: existence in the list is a proxy for RPs/verifiers. Registries must **do something to gate entry and ongoing status** — how you got in, how you stay in, how you maintain your claims. Not a full audit; self-asserted may be trusted by the registry. Certification bodies can own the deeper layer.
- Hisham: not a place to **enforce** — a place for the issuer to **claim**. RP/verifier knows their needs; issuer says what they did; RP decides. ISO 23220-5 for namespaces / published assurance claims; ISO 18013 for the VICAL application/ingestion.
- Steve: recognize existing governance entities; the issuer holds a credential asserting their authority; chain of trust — DL presented → links to an AAMVA-issued credential → wallet knows AAMVA. "Not for us to tell a sovereign what to do."

## Architecture points

- A trust registry does two things: (1) list authoritative issuers; (2) give RPs a linkage to understand where the authority comes from.
- **Multiple registries are necessary.** No single global registry — geopolitics and sovereignty. Likely a **power law**: 4–5 mega-registries plus highly specialized ones, following existing governance structures.
- **Leverage and digitize existing governance** (AAMVA, IATA, ICAO PKD, IAF) rather than replace it.
- **W3C Recognized Entity credentials** as a mechanism — works top-down (authority issues credential to member) and bottom-up (public register).
- **UN GRID** as a meta-registry example; sovereignty is a hard constraint (COVID-era WHO resistance cited).

## AAMVA specifics (Mike McCaskill)

- VICAL entry = application + ingestion process aligned with ISO 18013: self-assertions plus rigorous conformance questions; final approval is a committee-level decision. Iterating on the process (first application took months; a recent one took days).
- AAMVA is actively working on how to communicate issuer assurance levels to RPs — unsolved even within VICAL. "How do we all agree to assurance levels, and how do I (issuer) conform?"
- "No phone home" policy = AAMVA as mouthpiece for member consensus without commanding sovereign members.
- McLovin example: a fraudulent credential not issued by an AAMVA member fails a registry check — why presence on an authoritative list matters.

## Action items

- Confirm and send speaker details to Ruth by end of July (publication deadline).
- Add comments/names to the two shared GDC docs (Start Here; Scope).
- Darrell to cross-participate in Hisham's track (Track 2) and carry over Steve's Recognized Entity input.
- Mike McCaskill to share AAMVA's application and ingestion process details with the group.

## So-what for our co-leads work

The group did the scoping we hoped for: narrow to identity documents, abstract to issuer onboarding, split distribution from certification, make room for assurance without defining it. The next move is to write those decisions down as a clean, defensible scope boundary — small enough to ship in six weeks, whole enough to stand on its own. See the [simplifications analysis](../../track1-simplifications-and-scope-v0.1.md).
