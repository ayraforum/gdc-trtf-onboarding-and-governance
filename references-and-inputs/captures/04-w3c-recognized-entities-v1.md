---
title: "W3C Recognized Entities v1.0"
type: external-reference
authors: [Manu Sporny (ed.), Isaac Henderson Johnson Jeyakumar, David Chadwick, Oskar van Deventer, Shigeya Suzuki, Konstantin Tsabolov, Line Kofoed, Rieks Joosten]
origin: W3C Verifiable Credentials Working Group
status: First Public Working Draft (12 May 2026) — experimental, not for production
source_url: https://www.w3.org/TR/vc-recognized-entities-1.0/
captured: 2026-06-15
tags: [external, w3c, verifiable-credentials, trust-lists, recognized-entities]
---

# W3C Recognized Entities v1.0

> Proposed for the TR-TF list by **Steve Capell (UN/CEFACT)** as "a standard mechanism to publish trust lists or single trust links" — with the note that **discovery of trust links** is still an open item. Captured from the spec. See [[SYNTHESIS]] for the Ayra read.

**Full title:** *Recognized Entities v1.0: VCs for recognized entities and the actions they perform.*

## Purpose

Lets "one or more recognized entities (persons and/or organizations) be **described as known to perform specific actions**, such as issuing or verifying a verifiable credential." It provides cryptographic verifiability and some privacy preservation for showing that entities meet recognized standards. It deliberately supports **both** centralized trust infrastructure (X.509 CA lists, ETSI Trust Service Lists) **and** decentralized ecosystems where any entity can publish recognition information **without central gatekeeping**.

## Data model

### RecognizedEntity
Any entity recognized by an issuer of a `VerifiableRecognitionCredential` to perform a specific action.
- **Required:** `id` (global URL), `type` = `RecognizedEntity`, `recognizedTo` (one or more `RecognizedAction`s), `recognizedIn` (the document containing this entity and its actions).
- **Optional:** name, legalName, image, url, sameAs, description, digestMultibase.

### RecognizedAction
An action a recognized entity is expected to perform.
- **Required:** `type` = `RecognizedAction`, `action` (string, e.g., "issue" / "verify"), `recognizedBy` (URL or object identifying the recognizing entity).
- **Optional:** `outputValidation` (references data schemas — integrity-protected via `digestMultibase` — that verifiers use to validate credential conformance).

### VerifiableRecognitionCredential
A VC (conforming to VC Data Model v2.0) carrying recognized entities.
- **Required:** `type` includes `VerifiableRecognitionCredential`; `credentialSubject` = one or more `RecognizedEntity`.
- **Optional:** id, issuer, validFrom, validUntil.

## Use cases
1. **Publishing recognized educational institutions** — a learning commission lists universities authorized to grant degrees, with metadata + validity periods.
2. **Recognizing credential issuers** — an accreditation body lists orgs recognized to issue specific credential types, including validation schemas per type.
3. **Interoperability with existing trust infrastructure** — recognition credentials can reference **ETSI Trust Service Lists** or **X.509 CA lists** via `recognizedIn`, bridging to established regulatory frameworks.

## Privacy considerations (open issues)
1. **Surveillance risk** — public listing of named individuals/orgs (ids, legal names, URLs, images) enables aggregation/profiling; escaping a private group is a risk.
2. **Holder-provided recognition** — sharing the credential directly with verifiers ("certificate stapling") preserves holder privacy better than verifier-initiated registry lookups.
3. **Harms by association** — publishing sensitive ecosystem membership (healthcare, financial) exposes structures and creates targeting risk.

## Security considerations (mostly open issues)
1. **Validate before sharing** — peer acceptance is insufficient; verify cryptographically and against authoritative roots. *"A malicious or negligent actor could craft a VerifiableRecognitionCredential that lists fraudulent or compromised entities as recognized issuers or verifiers."*
2. **Issuer impersonation** — lookalike identifiers/names can deceive verifiers lacking independent validation.
3. **Validity-period selection** — long periods keep compromised entities in circulation; short periods add operational burden.
4. **External-resource tampering** — `outputValidation` schemas referenced by URL need integrity protection (`digestMultibase`).
5. **Verification of recognition chains** — `recognizedIn` enables chaining to other registries; compromised lower-level entries create transitive trust risk unless verifiers enforce depth limits.
6. **Action-value governance** — free-form action strings without ecosystem governance risk over-permissive interpretation.

## How it compares to existing trust infrastructure

| | Recognized Entities v1.0 | ETSI Trust Service Lists | X.509 CA lists | ISO/IEC 18013-5 mDL VICAL |
|--|--|--|--|--|
| **Format** | JSON-LD | Signed XML | Binary ASN.1 | CBOR/COSE |
| **Governance** | Decentralized supported | Hierarchical (EU member states) | Strict hierarchical chains | Designated providers |
| **Scope** | Domain-agnostic | eIDAS-regulated services | Cryptographic operations | mDL-specific |
| **Distribution** | Well-known URLs + holder "certificate stapling" | Well-known URLs | Central gatekeeper approval | Designated providers |
| **Actions** | Arbitrary domain-specific, scoped | — | Crypto ops | Records CAs |

## Status caveat
First Public Working Draft, **experimental, not for production**. Multiple privacy/security sections carry unresolved issues ("Issue 1"–"Issue 8") pending WG discussion.

> Relevance to Ayra: this is a candidate **wire format for a single "trust link" or trust list** — complementary to, not a substitute for, a registry-of-registries coordination layer. See [[SYNTHESIS#Where the W3C Recognized Entities spec fits]].
