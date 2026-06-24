---
title: "eduGAIN OpenID Federation Pilot (deck) + GTR pointer"
type: external-reference
origin: Gail Hodges (OIDF) shared the deck; Steve Capell (UN/CEFACT) shared the GTR
deck_authors: [Niels van Dijk (SURF), Davide Vaghetti (GARR)]
deck_event: EIC 2026, Berlin, May 2026
captured: 2026-06-15
tags: [external, gdc, trust-registries, edugain, openid-federation, saml]
---

# eduGAIN OpenID Federation Pilot (deck) + GTR pointer

> The `eduGAIN Federation.pptx` deck is now in this folder; its text is extracted below. The **GTR** ("Global Trust Registry") that Steve Capell attached as a logical model has its own dedicated capture: [[08-un-cefact-global-trust-registry-gtr]].

## eduGAIN OpenID Federation Pilot — deck contents

Source file: `eduGAIN Federation.pptx` (in this folder). Presented at **EIC 2026, Berlin, May 2026** by **Niels van Dijk (SURF)** and **Davide Vaghetti (GARR)**. Shared into the TR-TF by Gail Hodges (OIDF) as real-world prior art on federated trust at scale.

**What eduGAIN is:** *"eduGAIN interfederation service connects identity federations around the world, simplifying access to content, services and resources for the global research and education community."*

**Global coverage (slide 3):**
- **84 federations**
- **>10,000 entities**
- **6,333 Identity Providers**
- **3,998 Service Providers**
- Refs: https://edugain.org & https://technical.edugain.org/

**eduGAIN + OpenID Federation — the "why" (slide 5):**
- **OpenID Federation** is a **protocol-independent** way of describing trust, already supporting **OAuth 2.0, OpenID Connect 1.0, and Wallets**.
- R&E federations and eduGAIN are based on **SAML 2.0 — a legacy protocol**.
- OpenID Federation is **real-time and dynamic**, which is "essential for scalable and secure establishment of trust."
- **"Research and Education needs a global trust infrastructure which can span country, sector (and protocol) borders."** ← the core thesis, and the line most relevant to Ayra.

**Pilot specifics:**
- Slide 7 — intermediate results, via the OpenID Federation browser: https://italia.github.io/openid-federation-browser/main/
- Slide 8 — OpenID Federation & Wallets: DIIP (https://fidescommunity.github.io/DIIP/), eduwallet.nl (https://eduwallet.nl/en), and the [OpenID Federation Wallet spec](https://openid.net/specs/openid-federation-wallet-1_0.html).

> Scale context added in the TR-TF thread: eduGAIN serves on the order of **~30M users** on SAML infra; its cousin **eduroam** (network login) does ~**1Bn logins/year**; eduGAIN likely does an order of magnitude more transactions across a wider range of applications.

**Why it matters to Ayra:** eduGAIN is a working, multi-decade, internet-scale example of **cross-federation trust that spans country, sector, and protocol borders** — and it is actively migrating SAML → OpenID Federation to get **real-time, dynamic** trust establishment. It is the closest deployed analogue to the coordination problem Ayra is chartered around, and a useful baseline for the OIDF discussion in Track 2. See [[SYNTHESIS#Coordination is the missing layer (and the TF agrees)]].

## GTR (Global Trust Registry)

Steve Capell's `GTR-Logical-Model.png` attachment refers to the **UN/CEFACT Global Trust Registry** project. The user supplied the authoritative source — captured in full at **[[08-un-cefact-global-trust-registry-gtr]]**.
