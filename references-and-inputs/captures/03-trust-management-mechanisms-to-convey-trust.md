---
title: "Trust Management: Mechanisms to Convey Trust (in progress)"
type: external-reference
authors: [David Kelts (decipher.id), Debora Comparin (Secure Identity Alliance)]
origin: SIDI Hub
status: DRAFT / in-progress (author note "needs a lot of work")
license: CC BY 4.0 (© 2025-26 SIDI Hub Community)
source_url: https://docs.google.com/document/d/1_qkjOt7J7s_WS8LgaUlueiwHUXHgv7VtAcn2xGUMk94/edit
captured: 2026-06-15
tags: [external, sidi-hub, trust-management, mechanisms, technical]
---

# Trust Management: Mechanisms to Convey Trust (in progress)

> Captured from the live Google Doc shared in the [[00-source-thread|GDC TR-TF thread]]. Document #3 in the SIDI Hub series — the **technical catalogue**. The author explicitly flagged it as incomplete ("Wait on this one… still needs a lot of work to become a survey of the mechanisms in use"). Captured for completeness; expect change.

The technical companion to [[02-trust-management-developing-conventions-trust-vectors]]. Where doc #2 guides the **policy** process, this guides the **technical** process: selecting standardized **Trust Elements** and the **Mechanisms** that convey them along each [[01-trust-management-defining-the-challenge#The Six Trust Vectors (wallet-based architecture)|Trust Vector]].

## The three lists

The document separates policy/governance, mechanism categories, and verifiable elements into:
1. **Trust Statements** (typically policy, incl. Conventions)
2. **Trust Elements**
3. **Mechanisms** for conveying and inspecting Trust Elements

## 1. Trust Statements the ecosystem makes

- **Trust Framework** — foundational expectations, rules, guidelines, conventions, mechanisms.
- **Trust / Assurance Policies** — often non-cryptographic rules governing how trust is evaluated.
- **Trust Evaluation Conventions** — how to use a mechanism and what it means in a role.
- **Governance Framework Artifacts** — formal rules, standards, legal agreements (documents or verifiable statements).
- **Rules & Guidelines** — enforceable principles per role.

## 2. Trust Elements that convey assurances

### Trust Marks / Seals
Visible seals/logos/icons; a visual shorthand for a formal, verifiable policy-conformance check. Examples: security seals (padlock / "Secured by X"), **electronic seals** (bearer-certificate version), compliance/privacy logos (BBB, privacy certs), **ecosystem membership** marks (wallet/reader passed conformance; issuer is an audited registry member), crowd-sourced reputation.

> Strategic note in the source: Trust Marks overcome the risk of **brand/reputation being the deciding factor**; they "level the playing field for competition." *"Look for this seal…" creates human trust.* They **do not have to come from a central authority** — independent certification schemes can and should exist, especially in free-market ecosystems.

### Public Keys (and their containers)
Public-key lists/directories/repositories/ledgers; Issuer Public Keys; **DID-Key** mechanisms; **PKD** directories; **distributed ledgers**. (Explains asymmetric crypto: signature integrity + authenticity.)

> The draft lists named projects/efforts to survey here: **Radium, Verana, Aria.bar, Trust Registry Query Protocol (Spanning), DTI Data Trust (Lisa), Distributed Proof-of-Possession extension to OAuth, TCR (SMS sender verification), FindiNet (Finland).**

### Certificates and Attestations
X.509 certificates, Wallet Attestations, Reader ID Certificates, cryptographic digital signatures, **Verifiable Credentials (VCs)**. Functions: **binding** (key ↔ identity info), **validation/attestation** (signed by a trusted third party), **trust conveyance**. Attestations always come with a description of how to inspect/introspect them — those descriptions are **Trust Mechanisms**.

### Smart Contracts (as trust anchors)
Code/state/history immutably on a ledger → transparent, auditable. Software can query the contract to **confirm a rule/policy**, **check a status/state** (reputation, ownership, revocation), or **validate a claim**. Becomes a "real-time, impartial source of truth."

## 3. Mechanisms for working with Trust Elements

> Open question flagged in the draft: whether the **ToIP Trust Registry Protocol** enables discovery across all mechanisms.

**Operating models** (how trust is orchestrated):
- **Centralized Authority** (single anchor, e.g., a CA)
- **Hierarchical — Deputized Intermediates**
- **Federated Trust — Voluntary Intermediates**
- **Decentralized Trust** (anchors kept consistent by the Trust Framework, e.g., smart contracts — "centralized pre-thinking")

**Categories of mechanisms:**
- **Membership in a Managed Trust List** (a Registrar may manage it)
- **Verifiable Credentials (VCs)**
- **Certificates and Attestations**
- **Proof of Control / Possession** (e.g., PoP of a DID's private key)
- **Revocation and Suspension** mechanisms
- **Trusted and Secure Endpoints** (membership / revocation / suspension checks)

**Certificate introspection / inspection:** digital-signature validation, public-key binding, public-key lookup (lists/directories/ledgers), proof of control/possession.

**Trust & policy conformance checks:** Issuer Trust List, Reader Trust List, **Trust Registries or Lists** (for dispensing anchors), Issuer Registries, Reader Registries, **OpenID Federation endpoints**. Includes revocation-status checks, trust-list/registry checks, managed-list membership, and policy-conformance evaluation against the ecosystem's Trust/Assurance Policies and Conventions.

**Securing connections to trusted endpoints:**
- Endpoints carry positive-case elements (membership) or negative-case (revocation/suspension).
- Problem statement: when you receive an endpoint at transaction time from an unverified source or an unfamiliar ecosystem, how do you establish trust to use it?
- Tools: Secure Connections, **OpenID Provider Discovery Endpoints**, **TLS lock icons** on registered endpoints, and the **ToIP Trust Spanning Protocol** (lets a recipient of a URL establish a trusted, private, secure connection to reliably obtain Trust Elements). Plus introspectable/resolvable elements (smart contracts, PoP, revocation/suspension).

## Discoverability

**Real-time discoverability of mechanisms is "a critical part of making interoperability work"** — it stitches together new participants in your own ecosystem and enables cross-border/cross-ecosystem discovery so a partner ecosystem can find your Trust Elements and Mechanisms. *(Section largely unwritten in the draft.)*

## Architect's model of thinking (applying the framework)

The recommended cycle for a software/ecosystem architect:
1. **Start with the Trust Vectors** — identify the risk to mitigate in each ("who trusts whom").
2. **Define Ecosystem Considerations** — use the decision matrix to set requirements ("why we do it").
3. **Select Mechanisms & Elements** — choose tools that technically satisfy the requirements ("what we use").
4. **Establish Conventions** — define the participation rules for each Mechanism ("how we do it").

Architectural considerations grid (decision criteria): Governance & Legal (compliance/enforceability, cross-ecosystem alignment), User & Social (human-centricity/privacy, inclusivity/usability, conveying **expertise** and **motive** trust), Operational & Cost (ecosystem type & sustainability, mechanism complexity), Technical (revocation/suspension, binding & attestation at required assurance levels).

## Unwritten sections (placeholders in the draft)
Issuer Registries (public keys / trust list), Reader Registries (Reader ID certs / trust list), Wallet Registries (wallet attestation mechanism, consumer choice of wallet), and "Known Examples Today" (to be merged from a Literature Review document).

> Companion captures: [[01-trust-management-defining-the-challenge]], [[02-trust-management-developing-conventions-trust-vectors]].
