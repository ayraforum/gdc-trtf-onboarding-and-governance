# Track 1: Next Session — Agenda, Proposed Decisions & Scope Limitations

- Status: agenda draft v0.1
- Audience: GDC Trust Registry Task Force (Track 1), co-leads
- Author: Darrell O'Donnell
- Origin: Track 1 meeting, 2026-07-17 — see [meeting capture](references-and-inputs/ayra-context/meeting-notes-track1-2026-07-17.md)
- Companion to: [Track 1 — What to Simplify, What to Cut, What Must Stay (v0.1)](track1-simplifications-and-scope-v0.1.md)

Most of the statements below are ratifications of where the room already converged, not fresh debates. The purpose of the session is to lock them so they stop getting re-litigated, and to state the scope limitations explicitly.

## Agenda

1. **Carry-forward actions** (10 min)
2. **Ratify core scope decisions** (20 min)
3. **Ratify scope limitations** (15 min)
4. **Open questions — resolve or defer** (15 min)
5. **September deliverable** (15 min)
6. **Track 2 / Hisham overlap** (10 min)
7. **Geneva session** (5 min)

Detail below.

## 1. Carry-forward actions

- AAMVA ingestion process — Mike/Scott to walk through; Darrell to help compile
- Speaker names to Ruth — **hard deadline end of July**, CBSA outstanding
- Taxonomy first pass — Gabrielle to report status

## 2. Ratify core scope decisions

Each is written as a statement the group can adopt as-is. Rationale in italics.

1. **A trust registry is a carrier of issuer information, not a translator of it.** It conveys what an issuer asserts; it does not normalize, map, or reconcile meaning across issuers. The relying party makes the decision. *This is the "carrier" alignment (Nishant) reached last session — the load-bearing decision everything else hangs off.*
2. **Assurance-level meaning is out of scope; conveyance is in scope.** The registry makes room to carry an issuer's scheme + level and a pointer to the governing authority. It holds no opinion on what a level means. *Meaning is ecosystem governance; conformance is registry operations. Matches the WG10 direction — issuer states scheme + level; RP requests by scheme + level.*
3. **Scope is the distribution of self-declared claims, not the certification of claims.** The registry distributes what an issuer/authority declares about itself. Certifying those declarations is a separate function. *From the SCOPE doc — the cleanest boundary, and it keeps the group out of the certification tar pit.*
4. **The initial focus is issuer onboarding for government-issued identity documents.** Relying-party onboarding is explicitly deferred, not rejected. *Keeps the first deliverable bounded; MDL is the working lens given ecosystem adherence around the table.*
5. **A registry must publish the criteria by which issuers are admitted.** RPs must be able to see *how* an issuer got in, so they can accept, ask for more, or reject. *The published-criteria requirement is what makes the "carrier" model usable rather than opaque.*
6. **Transparency of process, not total transparency.** A registry shares enough for outside parties to understand and trust its admission process; it does not demand or expose every internal detail. Transparency is not a replacement for trust. *The Canadian federal/provincial example and the sovereignty point — sovereigns will not accept "show me everything."*
7. **Adopt an internal-vs-external model of registry information.** Internally the registry holds SOPs, criteria, and accepted certifications; externally the RP-facing answer is authorization ("is this issuer authorized for X: yes/no") plus published criteria. *Darrell to document; Gabrielle endorsed this as the right cutting function.*

## 3. Ratify scope limitations

These are the boundaries the group keeps drifting back across. Naming them stops the re-litigation.

1. **Track 1 will not define, normalize, or map assurance levels across schemes.** NIST IAL, eIDAS, PCTF, NZISM and others are not directly mappable, and solving that is not this group's problem to own.
2. **Track 1 will not perform or design certification of issuers or claims.** The registry conveys certifications an issuer holds; it does not certify.
3. **Track 1 will not dictate how sovereigns run their onboarding.** No global minimum standard that tells jurisdictions how to operate internally. The group defines good standards and SOPs *for admission to a trust list*, not for how a government issues.
4. **Relying-party onboarding is out of scope for this round.**
5. **Cross-jurisdiction equivalence / bilateral recognition is out of scope.** That is a sovereign-to-sovereign decision (the AAMVA–Austroads VICAL conversation is an example, not a deliverable).
6. **The registry does not establish issuer truthfulness, and does not decide its own reliance.** "Is this issuer telling the truth?" is not a registry question — it is answered, if at all, by proofing, verification, liability, and consequence elsewhere in the system. And the decision to rely on a given trust registry is made *outside* it, by the relying party choosing which registries to trust and why. The registry supplies inputs to decisions; it makes none — including the decision to trust the registry. A registry answers one bounded question: is this issuer recognized and authorized under published criteria, and is that current. *This is the root that makes standing audit a red herring — the "how do we know the issuer is honest?" pull is answered by leaving it outside the registry, not by building audit into it.*

## 4. Open questions — resolve or defer

- **Minimum baseline responsibility** (Nishant): must a registry confirm an issuer has *some* assurance level before an RP relies on it? *Resolution: reframe. Presence in the registry is itself the baseline — the **admission floor**. Being listed confirms the issuer cleared the registry's published criteria and that its already-existing governance has been surfaced into a discoverable, consistent, checkable form. That is an assurance signal in its own right, qualitative and unquantified — CMM-style "Level 0: governance made legible," not "governance created." The governance and operating processes usually already exist — in bilaterals, licensing regimes, and paper-world practice; what the registry adds is legibility and consistent availability. The registry's minimum responsibility is to guarantee the floor — published criteria, real admission, surfaced governance — not to attach or judge a graded level. Graded levels, where present, sit above the floor.*
- **Per-issuer vs per-credential granularity** (Loffie/Nishant): *Proposed resolution: adopt Darrell's model — a registry entry can carry multiple authorizations per issuer, so one issuer maps to one entry with credential-level authorizations. Confirm as the working model.*
- **Jason's utility concern:** if the registry won't normalize meaning, what does an RP actually get? *Resolution: normalization moves off the registry, not away. (1) Each registry self-describes its governance and assurance mechanisms as metadata. (2) The RP's curated list of TRs is itself the accepted-bar decision — choosing which registries to trust, and why, does most of the normalization today. (3) Residual cross-scheme translation is a real business need that belongs to a service at the point of verification, not to the registry. The registry stays a carrier.*

## 5. September deliverable

- Confirm outline, section owners, and dates
- **Add an explicit section: "What the relying party gets"** — owner needed. Frame it as three layers: registry self-description (metadata), list curation as the accepted-bar decision, and a point-of-verification mapping service as the market layer. This answers Jason concretely and names the business opportunity sitting on top of the registry.
- **Include the admission floor** as the entry point of the assurance story: presence is an assurance signal in its own right — governance made legible and consistently available — with graded levels sitting above it.
- **Hold the line on the metadata layer:** registry self-description must describe *mechanisms and governance*, not assert cross-scheme equivalence. If registries start signaling assurance in a common vocabulary "to help RPs," the normalization fight comes back through the back door. Worth one explicit sentence in the deliverable.

## 6. Track 2 / Hisham overlap

- Darrell's brief on Track 2 (Recognized Entities, top-down and bottom-up)
- The one scoping-overlap concern flagged last session but not yet detailed

## 7. Geneva session

- Confirm the theme: cross-comparison of **issuer** onboarding (France Identité, AAMVA DTS), MDL as the lens, framed around cross-jurisdiction trust
- Follow up with Mike on speaking — will be in Geneva, bandwidth uncertain

## Terminology to ratify this cycle

### The registry's role

- **Carrier** — the registry's role: it conveys issuer information, it does not translate or normalize meaning.
- **Admission floor** — presence in the registry as an assurance signal in its own right; the qualitative, unquantified baseline an issuer clears by being listed.
- **Governance made legible** — what the admission floor actually adds: existing (often analog, informal) governance surfaced into a discoverable, consistent, checkable form. The registry surfaces governance; it does not create it.

### The four-way split — disentangling "recognition"

"Recognition" is currently overloaded across three different relationships. Split it, and reserve the word for the cross-ecosystem case only.

- **Listing (admission)** — the operational fact of an issuer being in a registry with current status (active, suspended, revoked, expired). The signal weight of being listed at all is the *admission floor*.
- **Authority** — the underlying power behind an issuer. The registry **records and surfaces** it; it never grants it. Three flavors, genuinely different:
  - *Inherent* (sovereign): rests on law — "recorded, not approved."
  - *Delegated*: an authority delegates to a sub-issuer — established by **vetting**.
  - *Mutual / federated*: peers agree to a common bar and the body asserts the shared authority on their behalf. **AAMVA ↔ its states/provinces/territories** — an asserted, mutually-agreed authority, recorded. Not recognition, not mere vetting.
- **Recognition** — reserved for **one ecosystem accepting another's authority across a boundary, for a defined scope**. Scoped and often reciprocal. Example: `recognition: AAMVA → AustRoads, authoritative-for (issue, driverlicense.au.*, driverlicense.nz.*)`. This is the registry-of-registries / cross-ecosystem sense — the piece that makes the web of registries scale.
- **Certification** — reserved for external, standards-based backing attestations (ISO 27001, SOC 2, ISO 18013 conformance) an entity presents as evidence. Referenced by the registry, not the registry's own act.

The line that keeps flavor 3 and recognition distinct: **federation *forms* an ecosystem from its members; recognition *bridges* two ecosystems that already exist.** AAMVA↔states forms one. AAMVA↔AustRoads bridges two.

*Caveat on external vocabulary:* W3C terminology (including "Recognized Entities") tends to oversimplify and reuses terms loosely — treat it as an input to stay aware of so we don't collide, not a framing to adopt. Confirm directly with Steve Capell whether his "recognition" means the cross-ecosystem sense (aligns) or the admission sense (clashes) before standardizing. Flag to Gabrielle for the taxonomy pass.
