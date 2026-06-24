---
title: "Trust Management: Developing Conventions Using Trust Vectors"
type: external-reference
authors: [David Kelts (decipher.id), Debora Comparin (Secure Identity Alliance)]
origin: SIDI Hub → ITU-T SG17
license: CC BY 4.0 (© 2025-26 SIDI Hub Community)
source_url: https://docs.google.com/document/d/1NIIRz8avy1gJwrZbJ_IgmnJk9_ytQzeof1OJ7vW_qxU/edit
captured: 2026-06-15
tags: [external, sidi-hub, trust-management, governance, decision-matrix]
---

# Trust Management: Developing Conventions Using Trust Vectors

> Captured from the live Google Doc shared in the [[00-source-thread|GDC TR-TF thread]]. Document #2 in the SIDI Hub series; also titled "Considerations for Conventions at Each Trust Vector." A faithful condensation, not an Ayra position — see [[SYNTHESIS]].

A **Technology Decision Matrix** for Ecosystem Builders (policy + technology) and Governance Councils. It poses **Considerations** (questions) you answer to satisfy the six [[01-trust-management-defining-the-challenge#The Six Trust Vectors (wallet-based architecture)|Trust Vectors]], then translate into **Conventions** (requirements on participants) that you wrap around **Mechanisms** to encourage and enforce trusted participation.

## Key concepts

- **Trust Management Framework (Decision Matrix)** — navigates the business/legal/operational decisions to shape and secure a Digital ID ecosystem.
- **Trust Vectors** — six directional trust relationships; the *magnitude* of each must reach a level that sufficiently mitigates participant risk. **Risk is perception** and varies by transaction and circumstance.
- **Conventions** — the specific requirements/rules derived from considerations, placed by Ecosystem Operators on wallets, readers, and issuers.
- **Trust Elements & Mechanisms** — attestations, trust marks, smart contracts, badges, public keys, signed bearer certificates. *Trust Mechanisms distribute the meaning of Conventions.*
- **Registrars / Enforcement Registries** — deputized control points (Wallet, Reader, Issuer registries) that evaluate, certify, and revoke against Conventions.

## Trust Elements (artifacts that convey assurance)

- **Attestations** — verifiable artifacts conveying assurances (wallet conformance, key security, privacy safeguards, wallet-provider metadata).
- **Trust Marks** — visual seals of adherence to ecosystem values.
- **Badges (Open Badges)** — verifiable indicators held by users (certification/qualification/achievement).
- **Public Keys** — verify signatures / encrypt to a recipient.
- **Smart Contracts** — self-executing programs in a ledger enforcing rules.
- **Signed Bearer Certificates** — cryptographic data unpacked after receipt granting verified proof of a right/identity/claim.

## Trust Governance — the actors

- **Ecosystem Builder / Operator / Governance Council** — a single entity (government, corporate, foundation, alliance), a consortium, an industry alliance, or a public-private partnership. Sometimes there is **no** builder and governance grows organically — in which case representation for **civil society** matters most (because organic actors least represent the end-user viewpoint).
- An ecosystem must be **sustainable** (a business model, parallel models, charitable structure, or participant-sustaining structure) and ideally have **legislative or policy backing** (or bilateral/multilateral contractual enforceability).
- Two roles within the builder:
  - **Policy Manager** — translates goals into technology-independent requirements attached to Mechanisms; interfaces with legislatures; organizes Registrars; makes policy clear to participants (especially end-users).
  - **Trust Architect** — pairs technical architecture(s) with discoverable Mechanisms that operationalize Trust Elements, maintainable/sustainable by Registrars and able to scale. *"Set aside technical bias. This is technology deployment for collective goals."*

## Governance models (independent of technology)

> Explicit authorial note: **any of these models can work**; the section tries to remove bias. Strict-expectation systems disappoint most when they fail to live up to set expectations; organic systems tolerate change well.

- **Open Governance** — any issuer/holder/verifier can participate (builder may set baselines, sometimes allow untrusted participation).
  - **Organic** — builder is more "influencer" than enforcer.
  - **Free-Market** — no centralized marketplace for equipment/SDKs/keys; spurs innovation but adds risk without guidance.
- **Permissioned Governance** — centralized pre-approval before participation; often **Regulated** (law creates structure); builder is usually the operator.
  - **Restricted** — operator is the sole reader vendor / key authority / CA; goal often that the Digital ID is **not** used outside the ecosystem (many national IDs and healthcare IDs are intentionally non-portable). "Not inherently bad" and often used in pilots.
- **Federations** — coordinated consistency across participants via agreements. A **Loose Federation** supports independently developed requirement sets per group reputation/values. A federation can mix governance models. *"In the end, if we achieve global interoperability, there will be a Federation of sovereign mixed models."*

**Adding controls:** guidance can be **Regulated** (law), **Managed** (policy), or **organic** (need + reputation). **Registrars** can be deputized (or self-deputize on reputation) to operate Mechanisms and onboard participants. **Self-Sovereign Identity is a Managed Ecosystem** — "somebody designed that guidance communication." **Unmanaged Ecosystems** carry the most risk (retroactive legislation after users are harmed; brand-over-innovation; monopolistic Registrar capture; value drift) and tend to become "Organically Managed out of necessity."

**Mixed-model reality:** because wallets hold multiple credentials from different issuers at different assurance levels, **all ecosystems are mixed-model from the end-user perspective**. Mandated trust vectors tend to become operational before voluntary ones.

## Tier 1 — Ecosystem Considerations (the glue)

- **Governance Circle** — Which ecosystem type fits your population? What entity operates it? Are you influence or actual governance? Can you dictate/mandate/legislate or only suggest? Who are your allies (PPP)?
- **Sustainability Model** — Business model or supported free market? Who funds/maintains? Self-sustaining? Charitable? Built to last 3–5+ years.
- **Legal or Policy Backing** — Can you place enforceable mandates on verifiers/issuers? Do users expect anti-surveillance built into policy? What enforcement mechanisms exist or must be built?
- **Existing Infrastructure** — Build on national infrastructure? Leverage adjacent momentum (**AI, stablecoins, open banking, digital signing**). "Solving other ecosystems' problems creates in-kind payback."

## Tier 2 — Participant Considerations (viewpoints)

**Consumers (cardholders)** trust the system when it is: *Accepted Everywhere · Makes Life Easier · Protects Privacy.* Two kinds of end-user trust:
- **Expertise Trust** — can the provider do the thing well, reliably, scalably; does it do what it says?
- **Motive Trust** (often invisible/obfuscated by marketing) — are incentives/business model aligned with mine; is it consistent; does it weaken safety/security/privacy for its own profit?

> Ecosystem Considerations exist to **make the invisible visible** and possibly enforce adherence to values. "System transparency is always a critical component of privacy."

**Verifiers** trust the system when it is *Always Available · Accurately Identifies the Presenter · Cannot be Spoofed.*

**Issuers** ask: *Are we doing the right thing for cardholders? Usable for verifiers? Interoperable with our physical documents?* Government issuers typically need a legislative mandate; they sit on a continuum between "creating Digital Public Infrastructure" and "enforcing law by identifying residents."

> Notable line: **"The target customer for a Digital ID credential is the Verifier!"** Decisions should drive verifier acceptance, because only that helps the end-user.

## Considerations grid (ValuesMaxxing)

The builder maximizes the values participants care about most while the Governance Council balances perspectives. Considerations span four columns (note: **no Technical column** — "They aren't relevant" to this policy/operational guidance):

| Social | Business | Operational | Legal |
|--------|----------|-------------|-------|
| Human-centric | Rational cost (model) | Transparency | Enforceable |
| Usable — easy to use | Sustainable | Sustainability | Certifications |
| Usable — works in expected contexts | ROI to participants | Environmental impact | Redress mechanisms |
| Privacy (preserving/enhancing/supporting) | Readiness of business & gov't RPs | Measurements / metrics | Reporting |
| Inclusive | | Expertise | |
| Accessible | | Motive | |
| History | | Conscience | |
| | | Competition | |

### Social considerations (highlights)
- **Human-centricity** — references the OIDF "Human-Centric Digital Identity" concepts (13 orgs): prioritize the individual's needs, rights, and control over institutional interests; shift data control to the user.
- **Usability / expected contexts** — design for the workflows users already know; cover in-person, web, and **agentic** contexts.
- **Privacy fears (mDL)** — surveillance/tracking, corporate data mining, replicating ad-tech, normalization of ID checks. (Cited: ACLU, NILC, etc.)
- **Law enforcement / device security** — handing over a phone as a pretext for search; forensic extraction; remote revocation without due process.
- **Inclusivity & digital divide** — exclusion of those without smartphones; immigrant-safety concerns (data sharing with ICE/CBP).
- **Accessibility** — government ID ecosystems have **no "target user" — it's everyone**, raising the bar on software, messaging, education.

### Business / operational / legal (highlights)
- Can each vector be **self-sustaining**? Wallets inherently hold multiple credentials from multiple issuers. Support **wallet innovation** by defining how an issuer trusts a wallet. Define required **assurance levels** (FAL/AAL) and possibly wallet tiers.
- **Cross-ecosystem**: regulatory-alignment / equivalency models, liability & cross-border dispute resolution, data residency & sovereignty. *(This is the target of the SIDI-Hub Policy Workstream.)*
- **Caution on interoperability**: "Consider strongly your goal for cross-ecosystem interoperability. It may be **less necessary** than your participants and cardholders expect or than current pilots are advertising." Many national IDs never cross borders.

## Component-by-component conventions

- **Issuer Endorsement & Provisioning (Wallet Connector)** — scope the credential's use cases; assess existing technical inventory (ecosystem login, candidate wallet apps, mobile/payment adoption stats).
  - Decision table example fields: Credential Protection (FAL 1–3), User Authentication (AAL 1–3), Privacy Protection, Interaction Modes (in-person, to-website, login).
- **Wallet Conventions** — define provider and unit minimum requirements at the ecosystem level: credential protection, comms security (update/revocation), comms flexibility, interoperability functionality, user authentication at regional assurance levels (expressed clearly to the reader), certification/compliance, privacy, secure & portable transaction-receipt management.
- **End-user wallet concerns (weighted)** — #1: "Will the wallet profile my transactions and resell that to advertisers or agents?"

> Companion captures: [[01-trust-management-defining-the-challenge]] (the frame), [[03-trust-management-mechanisms-to-convey-trust]] (the technical mechanisms catalogue).
