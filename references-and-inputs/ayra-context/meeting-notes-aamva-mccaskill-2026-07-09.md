---
title: "Meeting Capture — AAMVA (Mike McCaskill), 2026-07-09"
type: meeting-notes
audience: internal (co-leads)
captured: 2026-07-09
source: Notion meeting notes (AAMVA w/ Mike McCaskill)
tags: [gdc, trust-registries, aamva, mdl, assurance-levels, vical, input]
---

# Meeting Capture — AAMVA (Mike McCaskill), 2026-07-09

Internal capture of an intro call between Darrell O'Donnell (Ayra/IIRA) and Mike McCaskill (AAMVA). Both sit on the GDC Trust Registry Task Force. This is preparation context, not group material. It is the input that drove the assurance-levels discussion piece: [Assurance Levels: A Value That Points Somewhere](../../assurance-levels-a-value-that-points-somewhere-v0.1.md).

## Who Mike is

- Long-time AAMVA figure. Prior ~19 years at Florida DMV (driver license work, then non-sworn law enforcement).
- Was on AAMVA's digital ID subcommittee (~2011–2012), the precursor to the mDL effort. That group wrote the white paper defining what a digital identity meant in the driver-licensing space, gathered member state/province input, and fed requirements to ISO (WG10 / ISO 18013).
- Strongly pro-mDL for identity documents, and explicit about why: AAMVA knows how it was developed. Open to better standards if they emerge in a couple of years — wants continuous improvement, not lock-in.

## What AAMVA operates

- **VICAL** (Vehicle/Verified Issuer Certificate Authority List) and **DTS** (Document Trust Service). Used in NIST NCCoE testing — AAMVA's VICAL/DTS provided the certificates for the testing authorities.
- In active talks with **AusRoads** (Australia's sister org) on sharing between their two trust services. The resonant point Mike keeps getting asked about: the two registries are constructed the same way and do things the same way — structural standardization between registries.
- Mike is adamant about staying scoped to **identity documents**. Step outside that domain and questions arrive that you didn't need to answer.

## Assurance levels — the core of the conversation

This is the meat, and the reason for the discussion piece.

- NIST IAL/AAL levels 1–3 were **not designed with driver licensing in mind** — very technical definitions. Driver license wasn't contemplated.
- Every US state issuing under **REAL ID** is **at least IAL2**. Good aligning force AAMVA didn't have to fight for.
- **An mDL is a level-3 credential.** But the backing matters: if the identity proofing was done at a lower level, the effective assurance is lower. **You can bump down, never up.** CAL (credential assurance level) can be 3 while the identity is 2, depending on process. The limiting factor is breeder documents and how they're authenticated.
- AAMVA **flags the assurance difference in its registry**, so a relying party can distinguish an mDL issued after real document verification from one issued on someone's word — same standard, same keys, same registry, different assurance behind them.
- Relying parties are increasingly scrutinizing **how** a credential was issued, not just **that** it was issued.
- Real-world gating: **Canada's passport office** analyzed provincial digital identity credentials and declined some due to process flaws — offered to re-evaluate and "level up" once fixed. Assurance level as a live gate.

## IIRA / Ayra positioning (as Darrell framed it)

- Ayra/IIRA is a **connector of sources of truth, not a source of truth**. Registry of registries. That's all it does.
- **Trust Registry Query Protocol** answers two things: (1) is this entity authorized to do what it did? (2) do you recognize another registry?
- IIRA extends this with **action/resource listings** (e.g. `issue_driverslicense.illinois`) and an **assurance level field**. IIRA defines the *structure*; it **defers the meaning** of levels to governance frameworks (e.g. "authorized at level 3 — see AAMVA governance for what 3 means").
- Key insight Darrell landed: **assurance levels are a proxy for value** (and liability). Technical implementers don't need them; business and governance stakeholders very much do. High assurance isn't always wanted — e.g. age assurance may deliberately avoid it to not constrict audience or take on liability.

## Relying-party trust vs holder trust

- Near-term tractable problem: help **relying parties trust issuers** and understand issuance quality. Start there.
- Holder-side trust (can the holder trust the relying party?) is real but can't be solved at the same time. Apple's terminal-registration model for Apple Pay was the analogy — works in the bounded payments world, doesn't scale to identity where endpoints are unbounded. Apple backed off that registry approach for mDL outside its SDK.

## Proposed collaboration

- Build a **working demonstration** using AAMVA's VICAL as an example trust registry inside the IIRA framework — a hack-grade demo, not production, to show the community what a trust decision looks like end to end.
- Concrete use case: **cross-border recognition of mDLs** with cached VICAL data for offline / low-connectivity scenarios (the Canadian fishing-camp-with-no-comms case; Canada/US vs Australia, Japan, Thailand).
- Cited real-world example: **BC Gov's lawyer credential** — government ID paired with a Law Society credential (matched on name + DOB) without merging them into one credential. Origin story: fake lawyers visiting inmates; also Airbnb/building permits; the trigger that made BC Gov concede they needed a registry was **mining certificates tied to UN frameworks** ("we're not in charge, we need to register").

## Logistics / action items

- Darrell to prepare and present an assurance-levels topic for the Trust Registry Task Force. (This capture + the discussion piece are that prep.)
- Mike to email the secretary (Ruth) to be added to the Trust Registry Task Force series. Darrell to share Track 1 coordinates as a fallback. Mike has a 9:00 conflict on the next call day.
- Track 2 (architecture & tech specs) participants noted: Hesham, Jason, Karen Mulberry, P Raj (IEEE), Gail (OpenID), Anthony (France), Jay Bradley (Yubico), Leif (Zeros), Philippe (France), Gabriel (IATA), David (Apple). Google notably absent (they lead age assurance elsewhere).

## So-what for our Track 1 work

The assurance-level thread is a clean wedge. AAMVA already does in practice what the task force is circling in theory: carry the value in the registry, defer the meaning to the governance framework, cross-recognize at a level. Use AAMVA/VICAL as the concrete example. Keep Ayra in the coordinate-not-operate lane — we make room for the field and carry the pointer; the authority defines the meaning and runs the operational processes.
