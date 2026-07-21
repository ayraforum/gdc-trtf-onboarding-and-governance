---
title: "Synthesis — GDC TR-TF Documents & Ayra's Position"
type: analysis
audience: internal (Ayra)
captured: 2026-06-15
tags: [synthesis, gdc, trust-registries, ayra-strategy, ethos]
---

# Synthesis — GDC TR-TF Documents & Ayra's Position

> Internal analysis of the documents captured in this folder ([[README]]). Covers: what the corpus is really saying, where **Ayra can add value**, where Ayra **differs or should push back**, and the **so-what** for our Track 1 role. Sources are external; the positions here are Ayra's.

**Track structure changed since this was written (captured 2026-06-15).** Track 3 was folded into Track 1; there is no Track 3. Darrell is a co-lead of **Track 1 — Policy, Taxonomy & Scope; Onboarding & Governance**, with Apple and France. Separately, the deliverable moved from **RP/verifier onboarding to issuer onboarding and governance**. References below to a Track 3 RP-onboarding deliverable record the June framing, not current scope — see [track1-simplifications-and-scope-v0.1.md](../../track1-simplifications-and-scope-v0.1.md).

## TL;DR

The TR-TF corpus is **strong on vocabulary and decision frameworks, thin on the cross-ecosystem coordination layer** — which is precisely Ayra's gap. The SIDI Hub "Trust Management" series gives the field a shared language (Trust Vectors / Mechanisms / Conventions) and a builder's decision matrix; the W3C Recognized Entities spec offers a candidate wire format for a single trust list/link; eduGAIN proves federated trust works at internet scale. **None of them owns the registry-of-registries problem** — how one ecosystem's trust registry is discovered and honored by another. That is Ayra's lane, and the documents repeatedly back into it without naming it (Steve Capell's open "discovery of trust links" item; the SIDI "cross-ecosystem considerations"; eduGAIN's inter-federation discovery).

**Recommended posture for Track 1 (Policy, Taxonomy & Scope; Onboarding & Governance):** adopt their vocabulary, contribute the coordination layer they're missing, and gently challenge two framings — the "single Ecosystem Builder" assumption and the "interoperability may be less necessary than pilots advertise" claim.

## What the corpus actually is

| Document | What it gives the field | What it is missing |
|----------|------------------------|--------------------|
| [[01-trust-management-defining-the-challenge\|Defining the Challenge]] | A shared frame: **Trust Vectors** (6 directional risks), **Mechanisms** (artifacts), **Conventions** (policies that give mechanisms meaning) | Treats cross-ecosystem trust as an extension, not the core; no coordination layer |
| [[02-trust-management-developing-conventions-trust-vectors\|Developing Conventions]] | A **builder's decision matrix** (governance models, sustainability, legal backing, social/business/legal considerations) | Assumes a single Ecosystem Builder/Operator per ecosystem; downplays interoperability |
| [[03-trust-management-mechanisms-to-convey-trust\|Mechanisms to Convey Trust]] | A **technical catalogue** of trust elements/mechanisms; names ToIP Trust Spanning, OpenID Federation, smart contracts | Explicitly unfinished; discoverability section largely empty |
| [[04-w3c-recognized-entities-v1\|W3C Recognized Entities]] | A **wire format** to publish a trust list or single "trust link" as a VC; bridges to ETSI TSL / X.509 | First draft; **discovery of trust links unsolved**; open privacy/security issues |
| [[05-gdc-trtf-work-tracks-and-champions\|Work Tracks]] | The TF's operating structure as of June 2026; **since superseded** — Track 3 folded into Track 1, Ayra co-leads Track 1 | — |
| [[06-edugain-and-gtr-logical-model\|eduGAIN OIDF Pilot]] | Proof that federated, discoverable trust scales (84 federations, >10k entities, ~30M users) and is migrating SAML → real-time OpenID Federation | A login federation, not a cross-*ecosystem* / cross-protocol fabric |
| [[08-un-cefact-global-trust-registry-gtr\|UN/CEFACT GTR / GRID]] | A **UN-hosted registry-of-registries** — directory of authoritative registrars; validates the model and the coordinate-not-operate boundary | Scoped to supply-chain / legal-entity registers, not credential/identity ecosystems |

## Where the corpus and Ayra strongly agree

These are open doors — lead with agreement, then extend.

- **Two types of trust.** The SIDI docs separate cryptographic validation (Mechanisms) from policy/governance meaning (Conventions). This is Ayra's **[[Two Types of Trust]]**: technological trust (is the credential valid?) vs human trust (is the issuer legitimate?). Their "a Trust List becomes a form of trust anchor" is our "trust registries are the bridge between the two." **Use their language; it's ours in different words.**
- **Conventions = governance of "conformant."** Their insight that a Mechanism is meaningless without the Convention that says how you join it and what membership *means* is exactly Ayra's **governance-of-conformant** role and the **Conformance Test Suite**. "Look for this seal… creates human trust" (doc #3 on Trust Marks) is the **Ayra TrustMark** thesis almost verbatim — and they explicitly say trust marks **need not come from a central authority**, which is structurally compatible with Ayra-as-neutral-issuer.
- **A perfectly signed lie.** The W3C spec's own security note — *"a malicious or negligent actor could craft a VerifiableRecognitionCredential that lists fraudulent or compromised entities as recognized issuers"* — is **[[A perfectly signed lie]]** stated by the standards body itself. Validation against an authoritative root is unsolved in the spec; that root-of-trust coordination is what Ayra provides.
- **Coordination is the missing layer (and the TF agrees).** Steve Capell flagged that W3C can publish a trust link but **discovery of trust links** is unsolved. eduGAIN's value is inter-federation **discoverability**. The SIDI docs call real-time discoverability "a critical part of making interoperability work" — then leave the section blank. This is Ayra's **[[Coordination is the missing layer]]** thesis with a flashing arrow pointing at it.
- **Human-centricity / motive trust.** Doc #2's "Expertise Trust vs Motive Trust" and its insistence on making the invisible visible aligns with Ayra's **human flourishing over efficiency** and "trust is relational, not attributional."

## Where Ayra adds value (the contributions to make)

1. **The registry-of-registries / cross-ecosystem layer.** Every document stops at the edge of a single ecosystem. Ayra's **Ayra Trust Network** is the connective tissue that lets one ecosystem's registry be understood and honored across ecosystems. *Concrete Track-3 contribution:* an **RP onboarding model that works across ecosystems** — how a bank or airline relying party verifies a credential whose issuer is governed by a registry in another jurisdiction. That is the unsolved "discovery of trust links" problem, scoped to RPs.
2. **Structural neutrality as the answer to "who runs the registry-of-registries."** The corpus debates governance models (open/permissioned/federated) but never asks who can neutrally coordinate **across** competitors and sovereigns. Ayra's **[[The Three-Option Trap]]** answers it: a for-profit platform can't be neutral by design; a competitor consortium can't be neutral by incentive; only a structurally neutral nonprofit can. The TF is co-led by **France + Apple** — a government and a platform — which makes the neutrality question live and concrete, not abstract.
3. **The conformance + TrustMark machinery.** The docs want Trust Marks, conformance, and "what membership means" but have no shared definition of conformant or a neutral issuer of the mark. Ayra runs the **CTS**, the **governance of conformant**, and issues the **Ayra TrustMark** (Intergraf-style, behind the scenes). Offer this as the missing shared surface — without Ayra operating anyone's registry.
4. **Mapping the catalogue to a coordination protocol.** Doc #3 lists candidate mechanisms (ToIP Trust Spanning Protocol, OpenID Federation, Recognized Entities, VICAL, DID-key) and asks whether the ToIP Trust Registry Protocol enables discovery across all of them. Ayra can contribute the **interoperability map**: the Ayra Protocol as the coordination layer that sits above these heterogeneous mechanisms rather than competing with any one of them.

## Where Ayra differs or should push back

1. **The "single Ecosystem Builder" assumption is too clean.** Both SIDI policy docs model trust as something *one* Ecosystem Builder/Operator sets across all six vectors within *its* ecosystem. The real world is **mixed-model federations of sovereigns** (which doc #2 even concedes at the end). Ayra's frame: the interesting, unsolved problem isn't governing one ecosystem — it's coordinating **across** many that will never share a single builder. Push the TF to treat cross-ecosystem coordination as the *core* case, not an annex.
2. **"Interoperability may be less necessary than pilots advertise."** Doc #2 argues many national IDs never cross borders, so don't over-invest in interoperability. **Ayra disagrees on the framing.** True for the *document*, false for the *person*: people, workers, and credentials move even when the issuing document was scoped locally — and **earned trust should travel with the person** ([[You earn trust. You should keep it.]]). The right design target is portability of *earned trust*, not portability of every document. This is the most important framing difference to surface in Track 1 (taxonomy/scope).
3. **"The target customer is the Verifier."** Doc #2's sharpest line optimizes ecosystem design for verifier acceptance. Ayra's ethos is **person-first**: verifier acceptance is necessary but is a *means*, not the terminal value. Risk: a verifier-optimized ecosystem drifts toward surveillance and lock-in — the very harms the same doc catalogues (profiling, ad-tech replication). Ayra should hold the line that the **person who earned the trust controls its portable form**, and that verifier convenience cannot override it.
4. **Registry-of-registries must not become an operator.** As the corpus matures it will be tempting to propose a central operator. Ayra's **[[Ayra Role Boundary — Coordinate Not Operate]]** is load-bearing: Ayra coordinates (registry-of-registries, CTS, governance-of-conformant, issues the TrustMark) and **does not operate** registries or run certification labs. When the TF discusses "who runs this," Ayra's answer is *members operate; Ayra coordinates* — and we must say so explicitly, or risk being read as just another would-be platform.
5. **Member neutrality in a co-led-by-Apple room.** With Apple and Mastercard/Visa/Google/Samsung all at the table, Ayra must not appear to favor any member's wallet/platform. Keep contributions at the **neutral-infrastructure** altitude; don't name member products.

## Where the W3C Recognized Entities spec fits

Treat it as a **candidate wire format**, not a competitor and not a strategy. It can express "entity X is recognized to do action Y" as a VC and bridge to ETSI TSL / X.509. But on its own admission it leaves **discovery, root-of-trust validation, recognition-chain depth, and action-value governance unsolved**. Those are coordination-and-governance problems — Ayra's layer. Good outcome: Ayra-coordinated ecosystems can *emit* Recognized-Entities credentials as one supported format, with Ayra supplying the discovery + governance the spec lacks.

## The UN GTR is a registry-of-registries — alignment and contrast

The [[08-un-cefact-global-trust-registry-gtr|UN/CEFACT Global Trust Registry (GRID)]] is the single most important external item in this folder for Ayra, because it is **another organization building a registry-of-registries** — UN-hosted, approved April 2025, now in public review. How Ayra should read it:

**Striking alignment (use it as validation, not threat):**
- **Directory, not operator.** GRID explicitly "will NOT create another central registry," "will NOT issue secondary credentials," and "will NOT disrupt existing registry business models." That is **Ayra's coordinate-not-operate boundary** stated by the UN. Strong external proof that the registry-of-registries pattern is real and that the neutral-coordinator posture is the correct one.
- **Self-service, ICAO-PKD model.** "Registrars should be empowered (and incentivised) to maintain their own data." Same operating philosophy Ayra uses for the Trust Network.
- **Loosely coupled / not queried per transaction.** Periodic harvest + local verification — a sane architecture pattern Ayra can point to.

**The contrast that defines Ayra's space:**
- **Scope.** GRID covers **legal-entity / supply-chain registers** (corporate, land, IP, trademark) for **trade** under the UNTP umbrella. It is **not** about digital-identity credential ecosystems, wallets, or cross-protocol login/credential trust. Ayra's lane — coordinating **digital-trust ecosystems** across protocols (OpenID Federation, ToIP, mDL/VICAL, VCs), with **conformance + the TrustMark** — is wide open and largely orthogonal.
- **Governance model.** GRID is "**curated and governed by the UN**" at the strategic level — a single intergovernmental anchor. Ayra's **[[The Three-Option Trap|structural neutrality]]** is a *non-governmental* neutral coordinator able to span competitors, platforms, *and* sovereigns who won't all defer to one UN body. These are complementary, not competing: GRID for legal-entity registers; Ayra for credential-ecosystem coordination.
- **DIAs vs Ayra.** GRID's Digital Identity Anchor "is not a new identifier" — a thin VC wrapper on existing registration numbers. Conceptually adjacent to how Ayra honors existing trust registries rather than replacing them ([[You Already Have a Trust Registry]]).

**Action:** treat GRID as a **reference architecture and an ally to name**, not a competitor. In Track 1, citing GRID ("the UN is building exactly this pattern for trade registries") lends Ayra's registry-of-registries argument instant credibility, while drawing the clean line that **credential-ecosystem coordination + conformance is the unserved layer Ayra occupies.** Worth a direct conversation with Steve Capell (who bridges UN/CEFACT GTR and the TR-TF and is championing Track 1).

## Ayra's lane in the task force

> Current scoping in [track1-simplifications-and-scope-v0.1.md](../../track1-simplifications-and-scope-v0.1.md). The earlier RP framing is preserved in [[07-track3-rp-onboarding-scope-gdc2026]] — superseded, retained for the IATA/DTC example.

- **Track 1 (Policy, Taxonomy & Scope; Onboarding & Governance) — Darrell co-leading with Apple and France.** The **GDC 2026 (Geneva, September 2026) deliverable is narrow and deliberate: the bare minimum for an issuer registry for government-issued identity documents.** That's the wedge. The real value Ayra adds here is **scope discipline** — name the out-of-scope items (standing audit of issuer operations; global assurance-level meanings; RP/verifier onboarding; cross-ecosystem registry-of-registries), acknowledge them, and **lead toward** them without letting them swallow the Geneva v0.1. Owning that scope line — disciplined on Geneva, credible on the destination — is what positions **Darrell/Ayra as the leaders who can move the bigger coordination problem forward**, inside the coordinate-not-operate boundary.
- **Canonical example — IATA (Gabriel Marquié), with Jason/Apple and Philippe/France on the sub-group.** IATA is *both* an RP (airlines verifying ID) *and* an issuer of **DTCs (Digital Travel Credentials)** in the old-school issuer/IDP mode, with a source of truth (bona fide airline members). Their burning question — "how is *our* trust registry onboarded and our issuer governance recognized?" — **is now the in-scope question**, not the lead-toward. (Under the earlier RP framing this polarity was reversed; the scope move to issuer onboarding inverted it.) Engage IATA on issuer onboarding and registry recognition now; their RP/verifier side is what sequences to a later phase.
- **Watch the glossary.** Track 1 is where the "interoperability isn't that necessary" and "target customer is the verifier" framings get baked into the shared vocabulary. Contest both early — the co-lead seat makes this materially easier than it was in June.
- **Track 2 (Architecture).** OIDF is championing; Ayra coordinates above the mechanism layer. Position the Ayra Protocol as the layer that maps across OpenID Federation, ToIP, Recognized Entities — not as a competing spec.

## One-paragraph summary

The GDC Trust Registries Task Force has assembled a credible shared vocabulary (SIDI Hub's Trust Vectors / Mechanisms / Conventions), a builder's decision matrix, a candidate VC wire format (W3C Recognized Entities), a proven at-scale federation example (eduGAIN, migrating SAML → real-time OpenID Federation), and — via the UN/CEFACT GTR/GRID — an actual **UN-hosted registry-of-registries** that validates both Ayra's pattern and its coordinate-not-operate boundary while staying scoped to trade/legal-entity registers. The corpus validates Ayra's worldview almost point for point — two types of trust, the perfectly-signed-lie risk, trust marks as human trust, conformance as governance — but it consistently **stops at the edge of a single ecosystem and leaves the cross-ecosystem coordination layer (discovery of trust links, root-of-trust across sovereigns, who-coordinates-the-coordinators) unsolved.** That gap is Ayra's reason to exist. The move is to adopt their language, contribute the registry-of-registries + conformance + TrustMark layer from within our coordinate-not-operate boundary, and push back on two framings — that one ecosystem builder governs trust, and that interoperability is optional — because earned trust belongs to the person and should travel with them.

> Linked ethos: [[Coordination is the missing layer]] · [[The Three-Option Trap]] · [[Two Types of Trust]] · [[A perfectly signed lie]] · [[You earn trust. You should keep it.]] · [[Ayra Role Boundary — Coordinate Not Operate]]
