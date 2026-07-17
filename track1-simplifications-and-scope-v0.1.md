# Track 1: What to Simplify, What to Cut, What Must Stay

> **RETIRED — superseded, internal note only (2026-07-17).** This was an early internal working cut and was never broadly shared. The shared, co-authored SCOPE document has since evolved past it — "the pattern is the work," the three authority options, the web-of-registries model, and the lifecycle distinction all live there now in more shareable language. Its best moves have been absorbed. Kept for provenance; do **not** circulate or cite as current. For the current position see the [SCOPE doc](https://docs.google.com/document/d/1nbVyc8MX42YPPYVvxRL7oE-B1zJ6PnZSqeJIaRR1Nac/edit), the [Start Here doc](https://docs.google.com/document/d/1Pujsh8OtIz1EhuU3FrtDss2rvhGLvcEe3xqhObGAkzY/edit), and the [next-session agenda & proposed decisions](track1-next-session-agenda-and-proposed-decisions.md).

- Status: RETIRED / superseded — internal provenance only
- Audience: GDC Trust Registry Task Force (Track 1), co-leads
- Author: Darrell O'Donnell
- Date: 2026-07-10 (retired 2026-07-17)
- Origin: Track 1 meeting, 2026-07-10 — see [meeting capture](references-and-inputs/ayra-context/meeting-notes-track1-2026-07-10.md)

## The recommendation in one paragraph

Track 1's job for the next six weeks is one thing: **how does an issuer get into a trust registry, and how does it stay in.** Bind an entity to its cryptographic material, publish what that entity says about itself, and keep the entry's status current. Everything else that came up — running a standing audit of issuers' operations, defining what assurance levels mean, judging issuance processes, onboarding relying parties — is real work that belongs to someone else or to a later phase. Cut it now. The test for every cut is the same: does the thing that's left still stand on its own? Issuer onboarding does. That's the deliverable.

## Where the group already landed

We're not starting cold. The room converged on four moves, and they're the right ones. This document just draws the lines hard enough that they hold.

- **Scope to identity documents** — driver's licenses, national ID, passports. Not "all credentials." Not a mega-credential with hundreds of attributes.
- **Abstract to issuer onboarding** — credential type is almost irrelevant; the atomic problem is binding a key/certificate to a legal or government entity.
- **Separate recognition and claim-distribution from standing audit** — the registry recognizes issuers and publishes their claims now; continuous third-party audit comes later. (See the note on the word "certification" below — this is where it kept biting us.)
- **Make room for assurance levels without defining them** — a field, possibly blank, whose meaning each ecosystem owns.

## The simplifications to make

**1. One onboarding model, not one per credential type.** The strongest simplification from the meeting: a digital passport, an mDL, and a boarding pass pose the same question — which entity are you, and what's your issuing key? Design the onboarding once, against that abstraction. Bound the *proving ground* to identity documents, but don't build identity-document-specific machinery. Narrow to prove; abstract to design.

**2. The registry recognizes issuers and distributes their claims — it is not a standing auditor.** Two things in scope. The registry *recognizes* an entity — attests that the entity meets the registry's bar for being listed — and it *distributes* that entity's self-declared claims to relying parties.

Be precise, because recognition is not nothing. **Admission is itself a certification.** When AAMVA lists an issuer, it is certifying that the issuer meets AAMVA's requirements. Behind that there may be formal certifications — ISO 27001, SOC 2, ISO 18013 conformance — but the point is that the issuer cleared the level AAMVA requires. That is a real, assurance-conferring act, and it is in scope. Relying parties treat "in VICAL" as meaningful precisely *because* that bar exists.

What's out of scope is the track building or operating a **standing, independent audit** of every issuer's ongoing operations. Recognition at the door: in. Continuous third-party audit as a service: later, owned by certification bodies, possibly attached as a separate feed. Hold that line and six weeks is realistic. Erase the recognition bar and the registry is a phone book; expand it into continuous audit and the scope is unbounded.

**3. Assurance level is a structured slot, not a standard.** Make room for the field. It can be blank. Each ecosystem defines what its levels mean; the track sets no opinion. This keeps the most contentious, sovereignty-triggering problem — agreeing on global assurance meanings — out of the room, while still letting the registry grow into it. "Make room for it, not opinions about it."

**4. Narrow "assurance" to the identity assurance of registry entry.** There are two assurance questions, and only one is ours. *Are you really the entity you claim* — the French government, Illinois DMV — is the binding, and it's in scope. *How rigorous was the issuance process behind each credential you make* is the issuer's and the certifier's domain, and it's out. Owning only the entry-binding question shrinks "assurance" from an ocean to a gate.

**5. The registry is a place to claim, not to enforce.** It surfaces authority; it doesn't command sovereigns. That single framing dissolves a whole class of hard problems — the registry never has to adjudicate, only to record accurately and let the relying party decide.

## A note on the word "certification"

The word is overloaded, and the overload is why we keep talking past each other. Pull it into three:

- **Recognition** — the registry's own attestation that a listed entity meets *the registry's* bar. AAMVA confers this implicitly by admitting an issuer to VICAL. In substance it *is* a certification, scoped to "meets our requirements to be listed." **In scope for Track 1.**
- **Backing certifications** — formal, external, standards-based attestations (ISO 27001, SOC 2, ISO 18013 conformance) that an entity presents as evidence to earn recognition. The registry may require or reference them. Inputs at the door, not the registry's own act.
- **Standing audit** — continuous, independent auditing of an issuer's operations as an ongoing service. **Out of scope for Track 1**; certification bodies own it.

Recommendation: reserve "certification" for the backing attestations, and call the registry's admission act "recognition." It's already the group's word — Steve Capell's W3C Recognized Entities — and it separates "the registry says you meet its bar" from "a third party audited your operations." The registry recognizes; it may rely on certifications; it does not run a standing audit. (Swap the label if the group prefers "attestation" or "endorsement" — the three-way distinction is the point, not the specific word.)

## What we can cut — and why each still stands alone

Each of these is real and important. None of them has to be in the v0.1 for the v0.1 to be coherent.

- **Standing audit of issuer operations.** Out. Continuous, independent auditing as an ongoing service is a certifier's job, attached later as a feed on top of the registry's own recognition. Keep the distinction sharp: VICAL's application, self-assertion, conformance questions, and committee approval *are* the registry's recognition act, and they stay in. What's out is the track standing up an audit regime behind them.
- **Global standardization of assurance-level meanings.** Out. Unachievable and unnecessary. The field can carry a value and a pointer to the defining authority without the track ever saying what "level 3" means.
- **Assurance of issuance processes** (credential assurance, breeder-document rigor). Out. That's what a certifier or the registry's own membership rules evaluate, not Track 1.
- **Relying-party / verifier onboarding.** Out of *this* track. Issuer onboarding stands on its own; RP onboarding is the mirror problem and can be built against the same registry once it exists.
- **Holder-to-relying-party trust** (can the holder trust the verifier?). Out. Different direction, later phase.
- **Non-identity-document credentials** (business, officer, device, supply chain). Deferred. The abstraction already anticipates them; the initial delivery doesn't carry them.

## What must stay, or it can't stand on its own

This is the irreducible core. Remove any one of these and you no longer have a trust registry — you have a phone book, or a claim no one can trace, or a design that can't grow.

- **The binding.** Cryptographic material tied to a real legal or government entity. Without it there's nothing to trust.
- **The gate.** How an entity gets into the registry and how it keeps its status — active, suspended, revoked. A registry with no entry discipline is just a list. This is where the identity-assurance-of-entry question lives — and it's what makes membership itself a trust signal. The bar an issuer cleared to get in, and the certifications it had to show at the door, are exactly what a relying party leans on when it treats "on the list" as good enough.
- **Claim distribution.** The registry publishes the issuer's self-declared claims to relying parties. Without this, RPs get nothing usable.
- **The assurance slot and the authority pointer.** A structured field (even if blank today) plus a pointer to the governing authority/framework. Drop it and the registry can never carry the governance value it exists for.
- **The recognition linkage.** A relying party can trace credential → issuer → registry authority. The chain of trust is the whole point; a registry that can't be recognized from the outside coordinates nothing.

## Two risks to guard against

**Audit creep.** The pull to answer "but how do we *know* the issuer is telling the truth?" will be constant. Hold the line in the right place: recognition is in — the registry attests you meet its bar and can require evidence, even existing certifications, to let you in and keep you in. What's out is the registry becoming the standing third-party auditor of everyone's operations. Recognition confers real assurance; audit-as-an-ongoing-service is the separate layer for later. Answering the second one now swallows the six weeks.

**Assurance-definition creep.** The pull to standardize what levels mean will be just as strong, especially with sophisticated members in the room who each have a view. Hold the line: make room for the field, defer the meaning to the ecosystem. The moment the track starts defining levels, it's telling sovereigns what to do — which it can't, and which will stall it.

## Proposed six-week deliverable

An **issuer onboarding and governance model** that specifies:

1. How an entity proves it is who it claims and binds to its cryptographic material (identity assurance of entry).
2. How the entity's self-declared claims are captured and published to relying parties.
3. How entry status is maintained — the lifecycle from active through suspension and revocation.
4. A structured, ecosystem-defined assurance-level slot plus a pointer to the governing authority, with no track-level opinion on meaning.
5. The recognition linkage that lets a relying party trace authority from a presented credential back to the registry.

Bounded to identity documents as the proving ground, abstracted so it generalizes, built on existing governance (AAMVA, ICAO PKD, IATA, IAF) rather than replacing it. Small enough to ship. Whole enough to stand on its own.

This is a draft to argue with. If a cut is wrong — if something I've moved out of scope is load-bearing after all — say so before we commit the boundary.
