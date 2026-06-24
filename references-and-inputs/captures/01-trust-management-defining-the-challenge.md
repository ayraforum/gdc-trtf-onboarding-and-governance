---
title: "Trust Management: Defining the Challenge for Ecosystem Builders"
type: external-reference
authors: [David Kelts (decipher.id), Debora Comparin (Secure Identity Alliance)]
origin: SIDI Hub → ITU-T SG17 Technical Report on Digital Identity Trust Management
license: CC BY 4.0 (© 2025-26 SIDI Hub Community)
source_url: https://docs.google.com/document/d/1OPCxgF5ZsoJkk3bkBKchm2pby6CuCBac/edit
captured: 2026-06-15
tags: [external, sidi-hub, trust-management, trust-vectors, itu-t]
---

# Trust Management: Defining the Challenge for Ecosystem Builders

> Captured from the live Google Doc shared in the [[00-source-thread|GDC TR-TF thread]]. Document #1 in the SIDI Hub "Trust Management" series. This is a faithful condensation of the source, not an Ayra position. For Ayra's read, see [[SYNTHESIS]].

A conceptual analysis for **Ecosystem Builders, policy-makers, and standards contributors** working on wallet or login Digital ID ecosystems. It proposes a structured way to understand Trust Management through **Trust Vectors, Mechanisms, and Conventions**. The goal is to inform ecosystem design, governance models, and future standardization — **not** to prescribe an architecture or technology.

## Core definitions

- **Trust = assurances that mitigate risk.** Each participant in an identity transaction carries risk; other participants provide assurances that mitigate it. "Trust" expresses that participants are meeting their obligations per ecosystem expectations (a **Trust Framework**).
- **Trust Management** — the rules, guidelines, conventions, and mechanisms that let any participant discover in advance (or determine in real time) that another participant has met their obligations and therefore mitigates risk.
- **Trust Evaluation Mechanisms ("Mechanisms")** — often-standardized methods for inspecting that a participant is a verifiable, conformant member of the ecosystem. *Example: the ICAO Public Key Directory (PKD) for passports.*
- **Trust Evaluation Conventions ("Conventions")** — policies that customize/configure how a Mechanism is used for a role; a Convention "explains how to take part in the Mechanism and therefore expresses the meaning of the Mechanism for others." *Example: the policies for how a country joins and uploads certificates to the ICAO PKD.*

> Key relationship: **Mechanisms** are the technical artifacts (Trust Lists, Wallet Attestations, federation discovery endpoints); **Conventions** are the policies governing participation, approval, configuration, and meaning of those Mechanisms.

## Categories of trust mechanisms

1. **Centralized Authority** — one trust anchor (a CA granting certificates).
2. **Hierarchical CA** — common trust anchor + deputy authorities.
3. **Federated** — multiple trust anchors recognized by the trust model; Federation Trust List dispenses anchors for inspection; possibly a conformance-query mechanism.
4. **Decentralized Trust Anchors** — cooperating entities retain sovereignty over their anchors and specify trust elements in a common place; possibly smart contracts as discoverable policy; interoperability mapped/coordinated by a Trust Framework.
5. **Organic / Free Market** — lack of conventions/mechanisms creates reliance on reputational trust only, until participants solve trust problems themselves; reputational or sector-specific registries are likely to emerge.

## The Six Trust Vectors (wallet-based architecture)

The "complete view" of directional trust relationships that must each be sufficiently satisfied:

1. **Issuer Trusts Wallet** — to approve provisioning credentials into that wallet (and that the wallet will authenticate the user; conversely the wallet should not report transactions back to the issuer).
2. **Reader Trusts Wallet** — to establish that credential protection and user authentication were adequately performed.
3. **User Trusts Verifier** — for informed consent to share attributes (e.g., the checkout reader is the store's, not a rogue reader).
4. **Reader Trusts Issuer** — the reader validates the credential using the issuer's procedures/keys.
5. **Ecosystem Trusts Reader** (Reader can identify itself) — the reader properly identifies itself to users; sometimes registered with a Registrar; sometimes scoped by **Verifier Attribute Policies** the wallet can enforce.
6. **User Trusts Wallet** — that the wallet won't profile, leak receipts, report to authorities, or monetize ID/transaction data. *("Companies involved in surveillance capitalism on the internet will enter the wallet space.")*

> The same Trust Vectors apply in **login/federation** ecosystems; only the Mechanisms and Conventions differ.

## Ecosystem roles

- **Issuers** endorse Digital ID credentials for Users (cryptographic signature attesting accuracy/provenance at provisioning); they use a **Wallet Connector** and must trust the wallet before provisioning.
- **Users** store credentials in cloud or mobile **Wallets** run by a **Wallet Provider**.
- **Verifiers** read and validate credentials via a **Reader** (physical, app, or web service).
- **Trust List Providers** distribute certificates for conformant good actors.
- **Ecosystem Builder** — the decision-making entity for ecosystem policy; authorizes Trust List Providers. Becomes an **Ecosystem Operator** when it adds enforcement/operational duties.

## Observed patterns of trust (and their shortcomings)

**Patterns:**
- **Single-Provider (Homogeneous) Trust** — same entity issues wallet, connector, and reader (e.g., US mDLs). Convenient but not necessarily interoperable; risks the appearance of collusion.
- **Multiple Bilateral Contracts** — out-of-band agreements (e.g., TSA must establish a bilateral agreement per Wallet-Connector-Issuer combination). Doesn't scale.
- **Federation of Issuers or IDPs** — single agreements per role, enforceable by the federation; reduces the explosion of bilateral agreements. Common in login; extends to wallets without changing the Trust Vector map.
- **Regulated Participation.**

**Shortcomings:**
- **Lack of user choice** — without Mechanisms (discoverability) and Conventions (approval policy), user choice of components (critical for privacy) and innovation are constrained.
- **Reputational / implicit trust** — RPs picking only their issuer's readers; users picking brand-name wallets over state wallets; defaults to reputational/fear-of-non-compliance decisions.
- **Receipt storage & profiling** — privacy-preserving, user-controlled, portable receipt storage hasn't become standardized (despite Kantara/ISO consent-receipt standards). Builders should set requirements against profiling and for secure, portable, unidirectional receipt storage.

## Trust (List) Providers

With many issuers and verifiers, **mechanisms must distribute public keys/certificates**, with controls on inclusion. A Trust List indicates which credential types its issuers are authorized to provision; membership means the issuer met the provider's (or federation's) requirements. **The Trust List itself becomes a form of trust anchor** — the verifier needs only one relationship (with the list provider) instead of many.

- **Issuer List Provider** — the best-known list mechanism. Multiple are expected (AAMVA in the US, AustRoads in Australia, eReg in Europe). Global businesses may need conventions to **harmonize lists from multiple providers**; builders may approve issuer lists from other ecosystems.
- **Reader List Provider** — lets the wallet confirm a reader belongs to a verifier and is operated per policy (not a rogue). Builders can appoint **Registrars** to inspect verifiers for inclusion in a Reader List.
- **Wallet Attestations** — a wallet attests its instance, build, builder, authorizer, and permitted operations. Essential for a reader to trust dynamic transaction-time info (e.g., user authentication). *(Note: as of 2025, EU and US implementations do **not** send Wallet Attestations to readers, relying on assumptions about how user authentication is performed.)*

## Federation login ecosystems

Using OpenID Provider (OP) as IDP: Verifier chooses the OP ahead of time (1:1 coupling or a reputable IDP). The verifier's site obtains trust info from the OP's **Well-Known / Discovery endpoints**; **OpenID Federation** endpoints add list-like mechanisms. Three OP deployment pairings will co-exist with **different meaning** behind each: **Verifier/RP-operated**, **Wallet-Provider-operated**, and **Issuer-operated** (incl. government). "When you query the Federation endpoint mechanism, what conventions were followed that are providing you your result?"

## Overlaying login + wallet ecosystems

A **"Federation + Wallet Hybrid"** (e.g., a government login provider overlaid with a government Digital ID issuer) doesn't change the Trust Vectors but increases the number of Mechanisms and lets the builder handle more use cases. Claims can be delivered to web RPs (signed JWTs after login or 18013-7 device engagement) and to in-person verifiers (via OpenID4VP after an 18013-5 exchange) through equivalent mechanisms. The challenge: establish **conventions for omni-channel delivery** that are efficient, accurate, and support revocation — possibly reusing one ecosystem's mechanisms across the other.

## Worked example

AAMVA publishes its **mDL Implementation Guidelines** (the Conventions) that it enforces before an issuer's public key goes into AAMVA's **Digital Trust Service** Trust List (in VICAL format). Verifiers load that list into readers to verify mDL signatures; users gain assurances about issuer behavior.

## Bottom line

The Ecosystem Builder's core job is to **establish clear Conventions for using Mechanisms** — reducing complexity, enabling user choice, and overcoming reliance on reputational trust, opaque operations, and subversive actors. Trust Vectors stay constant across wallet and login worlds; Mechanisms and Conventions vary.

> Related captures: [[02-trust-management-developing-conventions-trust-vectors]] (the policy decision matrix), [[03-trust-management-mechanisms-to-convey-trust]] (the technical catalogue).
