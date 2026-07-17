---
title: "Meeting Capture — GDC TRTF Track 1, 2026-07-17"
type: meeting-notes
audience: internal (co-leads)
captured: 2026-07-17
source: Notion meeting notes (Trust Registries Track 1) + Darrell manual notes (Google Doc)
tags: [gdc, trust-registries, track1, scope, assurance-levels, onboarding, governance, input]
---

# Meeting Capture — GDC TRTF Track 1, 2026-07-17

Internal capture of the Track 1 (Policy, Taxonomy & Scope; Onboarding & Governance) meeting. Combines the Notion transcript/summary with Darrell's manual notes. Feeds the next-session agenda: [Track 1 Next Session Agenda & Proposed Decisions](../../track1-next-session-agenda-and-proposed-decisions.md), companion to [Track 1 Simplifications and Scope](../../track1-simplifications-and-scope-v0.1.md).

Attendees: Darrell O'Donnell, Jason Lim (Apple), Mike McCaskill (AAMVA), Scott (AAMVA), Loffie Jordaan, Anthony (France), Gabrielle, Nishant.

## The big conceptual win — the registry as "carrier"

The group converged on a clean, defensible scope boundary, and Nishant's word **"carrier"** unlocked it: a trust registry **carries** issuer information; it does not normalize or translate it. The relying party makes its own decision. This resolves the assurance-level fight that has eaten weeks — levels of assurance are out of scope for *meaning* (that is ecosystem governance), but the registry "makes room" to convey them. Buy-in from AAMVA, France, and WG10.

## Where the group converged

- **Registry is a carrier, not a translator.** Conveys what an issuer asserts; does not reconcile meaning across issuers.
- **Assurance-level meaning out; conveyance in.** Issuer states scheme + level and a governance pointer; RP requests by scheme + level. Matches WG10's current direction (moved away from a common-mapping approach toward "identify the scheme and the level within it").
- **Distribution of self-declared claims in; certification of claims out.** (Carried from the SCOPE doc.)
- **Focus is issuer onboarding** for government-issued identity documents; RP onboarding deferred. MDL is the working lens.
- **Registries must publish admission criteria** so RPs can see how an issuer got in and decide to accept, ask for more, or reject.
- **Transparency of process, not total transparency.** "Transparency is not a replacement for trust." The Canadian federal/provincial example: the federal government rejected some provincial digital IDs but could not disclose specifics — "none of your business" up to a point, share enough to be trusted.
- **Internal-vs-external model.** Internally the registry holds SOPs, criteria, accepted certifications; externally the RP-facing answer is authorization (yes/no) plus published criteria. Gabrielle endorsed this as the right cutting function; Darrell to document.

## Open questions (carried to next session)

- **Minimum baseline responsibility** (Nishant): must a registry confirm an issuer has *some* assurance level before an RP relies on it? Reframed post-meeting: presence in the registry is itself the **admission floor** — an assurance signal in its own right (CMM-style "Level 0: governance made legible"). The governance already exists (bilaterals, licensing regimes, paper-world practice); the registry surfaces it into a discoverable, consistent, checkable form. Registry guarantees the floor, does not judge a graded level.
- **Per-issuer vs per-credential granularity** (Loffie/Nishant): an issuer with different practices per credential may not be served by a single per-issuer entry. Darrell's model: a registry entry can carry multiple authorizations per issuer.
- **Jason's utility concern:** if the registry won't normalize meaning, what does an RP actually get? Reframed post-meeting into three layers — registry self-describes governance/assurance as metadata; the RP's curated list of TRs is itself the accepted-bar decision; residual cross-scheme translation is a point-of-verification market service, not a registry function.

## Notable exchanges

- **Tiered trust lists** (Mike): AAMVA DTS already does more than list valid issuers — it states what requirements issuers comply with. Future: different trust lists for different audiences (TSA-grade vs. low-risk retail), each conveying a different level of issuer detail.
- **Assurance mapping is "brutal hard"** (Loffie, Darrell): NIST IAL/CAL, Pan-Canadian Trust Framework, eIDAS, NZISM are orthogonal and not directly mappable. IP2+ vs. IAL2 differ by evidence and culture (e.g., centrally-managed student ID as evidence). WG10 abandoned common-mapping for scheme + level self-identification.
- **IDL is a translation, not a derived credential** (Loffie): the international driver's license translates an existing document rather than deriving a new one.
- **AAMVA–Austroads (Australia)**: early conversations about cross-regional VICAL sharing; no clear model yet — "maybe it doesn't look like anything."
- **Market opportunity** (Darrell): the residual liability layer — age/majority, KYC/AML — creates room for a service that stands between the registry and the RP and takes on liability.

## Actions

- **Mike / Scott** — pull together the AAMVA application/ingestion process for the group; **Darrell** to help compile.
- **Darrell** — add document links to the Start Here / SCOPE docs, then send follow-up email to the group.
- **Track leads** (Anthony/France, Jason/Apple) — confirm Geneva session topics and submit speaker names/bios to Ruth before end of month. CBSA outstanding. **Hard deadline: end of July.**
- **Follow up with Mike** about speaking at the Geneva event — he'll be there, bandwidth uncertain.
- **Gabrielle** — first pass at taxonomy and definitions.
- **Darrell** — carry Steve Capell's Recognized Entities input; cross-participate in Track 2 (Hisham); brief Track 1 on the Track 2 overlap and the one flagged concern (ran out of time).

## Geneva session (emerging)

Cross-comparison of **issuer** onboarding: France Identité vs. AAMVA DTS, MDL as the lens, framed around cross-jurisdiction trust ("how do you trust a US MDL in France, or an AAMVA MDL in Australia?"). Mike is the wanted voice but has not committed to presenting.
