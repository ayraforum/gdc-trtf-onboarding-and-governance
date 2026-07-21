---
title: "RP / Verifier Onboarding: Scope for GDC 2026 (Geneva) [ARCHIVED]"
type: analysis
audience: internal (Ayra)
champion: Darrell O'Donnell (Ayra)
event: GDC 2026, Geneva, September 2026
source_url: https://docs.google.com/document/d/18vwwzdyAo0PL7YBRW37zQiFz2oGmZh8ZBbHgczVIAr8/edit?tab=t.0
captured: 2026-06-15
status: superseded
superseded_by: track1-simplifications-and-scope-v0.1.md
tags: [gdc, trust-registries, superseded, rp-onboarding, scope, ayra-strategy, iata, dtc]
---

# RP / Verifier Onboarding: Scope for GDC 2026 (Geneva) [ARCHIVED]

**Archived — the June 2026 framing. Do not work from this scope.** The Geneva deliverable is now the bare minimum for an **issuer** registry for government-issued identity documents; RP/verifier onboarding is out of scope. Current scope: [track1-simplifications-and-scope-v0.1.md](../../track1-simplifications-and-scope-v0.1.md). All of this work now sits in Track 1, which Darrell co-leads with Apple and France. Filename kept so existing links resolve.

Still useful here: the IATA/DTC example and the scope-discipline method — though the IATA polarity has inverted, since their registry-onboarding question is now the in-scope one.

> Working scope note for the track Darrell is championing. Source: the [Track 3 effort doc](https://docs.google.com/document/d/18vwwzdyAo0PL7YBRW37zQiFz2oGmZh8ZBbHgczVIAr8/edit?tab=t.0) (same TR-TF strategy doc captured in [[05-gdc-trtf-work-tracks-and-champions]]). This note states what we are actually delivering in Geneva, what we are deliberately holding out, and how Ayra/Darrell lead the room toward the bigger prize.

## The Geneva 2026 deliverable — keep it sharp

**In scope for GDC 2026 (Geneva, September 2026):**
- **Relying Party / Verifier onboarding** — specifically, onboarding the **verifiers (RPs) that want to consume government-issued identity**.
- The RP Onboarding Framework (v0.1): the principles, privacy/security model, and governance for *how an RP gets recognized and is allowed to verify* government-issued credentials.

That is the spine. Everything we ship in Geneva should serve **"how does a relying party that wants to use government-issued ID get onboarded and trusted?"**

## Scope discipline — the real job of Track 3

The hard, valuable work here is **scoping**, not expanding. The pattern in this corpus (and in every adjacent body — SIDI, W3C, OIDF) is scope creep: every participant has an adjacent problem they want solved. Our job is to **name the out-of-scope items explicitly, acknowledge them, and lead toward them** — without letting them swallow the Geneva deliverable.

| | Item | Handling for GDC 2026 |
|--|------|----------------------|
| **In scope** | RP/verifier onboarding for verifiers consuming **government-issued** identity | Deliver the v0.1 framework |
| **In scope** | Privacy & security model for RP access/verification | Deliver |
| **In scope** | Governance: who recognizes an RP, on what basis | Deliver (principles) |
| **Out of scope** | Issuer authorization, issuer onboarding, or identity-provider governance | Do not solve in Track 3; keep the room focused on RP/verifier authorization |
| **Lead toward (out of scope)** | Cross-ecosystem / cross-border recognition (registry-of-registries) | Acknowledge as the destination; position Ayra as the layer for it |
| **Out of scope** | Non-government / fully commercial credential ecosystems | Note as a later phase |
| **Out of scope** | Technical wire-format selection (Track 2 / OIDF owns the architecture) | Defer to Track 2 |

> The framing to repeat in the room: **"For Geneva we are delivering RP onboarding for government-issued identity. Here is the bigger picture it connects to, and here is how we get there — but that's the next milestone, not this one."** Naming the boundary clearly is what makes Ayra the trusted steward of it.

## Why this positions Darrell & Ayra as leaders

RP onboarding for government-issued ID is the **narrow, deliverable wedge** into the broad coordination problem Ayra exists to solve. By owning the scope line — disciplined on Geneva, credible on the destination — Darrell/Ayra become the people who can **move the bigger thing forward** without spooking the room with over-reach. This is consistent with Ayra's **coordinate-not-operate** boundary: we frame the governance and onboarding model; members and governments operate their registries. See [[SYNTHESIS#Ayra's lane in the task force]].

## Open questions to resolve with co-leads
- Exact boundary of "government-issued identity" for v0.1 (national ID + mDL only, or broader public-sector credentials?).
- Are we working only on relying-party/verifier authorization, or does wallet authorization / wallet approval also belong in Track 3?
- What "onboarded" means concretely for an RP — recognition credential, listing, conformance check, or all three?
