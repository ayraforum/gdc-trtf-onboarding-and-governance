---
title: "UN/CEFACT Global Trust Registry (GTR / GRID)"
type: external-reference
origin: UN/CEFACT (project approved April 2025); shared into TR-TF by Steve Capell
status: Stage 4 — Public Review
source_url: https://un.opensource.unicc.org/unece/uncefact/gtr/docs/draft/About/
captured: 2026-06-15
tags: [external, gdc, trust-registries, un-cefact, gtr, grid, dia, untp, registry-of-registries]
---

# UN/CEFACT Global Trust Registry (GTR / GRID)

> Captured from the authoritative UN/CEFACT source (supplied by the user). This is the project behind Steve Capell's `GTR-Logical-Model.png`. Strategically the most important external item in this folder for Ayra — it is, in effect, a **UN-hosted registry-of-registries**. For the Ayra read, see [[SYNTHESIS#The UN GTR is a registry-of-registries — alignment and contrast]].

## What it is

The **Global Trust Registry (GTR) Project** (approved by UN/CEFACT, **April 2025**) creates the **Global Registry Information Directory (GRID)** — *"a digital directory, publicly accessible and hosted by the United Nations, that will list authoritative registrars."* It lets organizations verify whether credentials issued by a registrar are **legitimate and authorized**.

Core problem: global supply chains carry "trillions of dollars of value" exposed to fraud, counterfeiting, and impersonation because registry systems are **fragmented**. GRID gives a trustworthy reference point for which registrars are authoritative in participating UN Member States.

## GRID — what it is and is NOT

**Is:** a **directory** (not a central registry) cataloguing participating registrars and their registers, holding *"a small amount of data about each participating register"* in **cryptographically signed** formats, while register contents stay under registrar control.

**Is NOT (explicit design constraints):**
- Not another central registry of all entities
- Does **not** issue secondary credentials on behalf of registries
- Does **not** disrupt existing national registry business models
- Does **not** dictate governance to nation states
- Does **not** define new identifier standards for registrars

> This "directory of authoritative registrars, not an operator of registries" stance is **structurally identical to Ayra's coordinate-not-operate boundary** and registry-of-registries role. Note it carefully.

## Architecture & logical model

- **Loosely coupled**: balances centralized governance with decentralized operation. **Not queried for every transaction** — emphasis on **periodic data harvesting + local verification** via distributed credentials. Verification matters most when establishing a **new** trade partnership or entering unfamiliar territory.
- **Self-service data management**, explicitly **inspired by the ICAO Public Key Directory (PKD)** model: *"Registrars should be empowered (and incentivised) to maintain their own data."*
- **The 11-step logical model** (what `GTR-Logical-Model.png` depicts): supply chains → participants in UN Member State jurisdictions → registration with authoritative registrars → many registrars per type (land, trademark, corporate…) → chains span states → trade involves product + documentation + value → verifying documentation requires checking registrar authority → regulators also verify → trust in the **registrars themselves** needs external validation → **GRID confirms which registrars are legitimate.**

## Digital Identity Anchors (DIAs)

- A *"light-weight, open-standards based, cryptographically protected trust wrapper"* around **existing** registrar identifiers. **A DIA is not a new identifier** — it wraps existing registration numbers in verifiable-credential structures.
- Issuance by registrars is **encouraged, not mandatory** for GRID membership; registrars sit at varying digital-maturity levels. DIAs are an **"and"** alongside paper/PDF/websites, not a replacement.
- Value: builds on registrars' existing value propositions; provides the foundational **UNTP** credential for supply-chain ecosystem participation.

## Participation & governance

- **Voluntary** for UN Member States and their registrars; applicants meet eligibility in governance docs.
- **Cost target ≈ ICAO PKD parity — ~US$20k/year per member state.**
- **Governance split:** *curated and governed by the UN* at the strategic level; **self-maintained by Member State registrars** operationally; cryptographically trustworthy via signed data; supports existing legal frameworks without imposing new ones.
- Three interaction patterns: (1) GRID membership application; (2) DIA issuance to supply-chain participants; (3) trustworthy trade execution (buyer verifies supplier docs/credentials before payment).
- Sustainability principle: if GRID *"delivers more value to participants than the cost of participating, it should be welcomed"* (ICAO PKD model).

## Scope

Registries that issue/certify identifiers for **rights, ownership, legal personality, or public status** under national/international law: commercial & corporate registers, land & property, movable assets & secured transactions, IP & trademarks. The framework confirms institutional legitimacy, legal reliability, operational integrity, and alignment with recognized registration principles.

## Place in the UNTP ecosystem

GRID sits inside the **UN Transparency Protocol (UNTP)** alongside **Digital Product Passports** (product attributes), **Digital Conformance Credentials** (quality/process claims), and **DIAs** (organization identity/registration). Aligns to **UN SDGs 9, 12, 16** and the Global Digital Compact.

## Key terminology

| Term | Definition |
|------|------------|
| **GRID** | Global Registry Information Directory — UN-hosted directory of participating registrars |
| **DIA** | Digital Identity Anchor — VC wrapping an existing registrar identifier (not a new identifier) |
| **Authoritative Registrar** | Org recognized by a UN Member State's law as having registration authority |
| **Registrar / Register** | Org maintaining an official register / the specific list it maintains |
| **GTR Project** | Global Trust Registry Project (approved April 2025) |
| **UNTP** | UN Transparency Protocol — the broader ecosystem GRID lives in |

Status: **Stage 4 — Public Review** (prior Stage 3 Draft Development).

## Why this matters to Ayra (pointer)

The GTR/GRID is a **second, UN-backed instantiation of the registry-of-registries idea** — but scoped to **supply-chain / legal-entity registers for trade**, not digital-identity credential ecosystems or wallets. It strongly **validates** Ayra's thesis and even its operating boundary (directory not operator; ICAO-PKD self-service; loosely coupled), while leaving Ayra's actual lane — **cross-protocol digital-trust coordination, conformance, and the TrustMark for credential ecosystems** — open. Full analysis in [[SYNTHESIS#The UN GTR is a registry-of-registries — alignment and contrast]].
