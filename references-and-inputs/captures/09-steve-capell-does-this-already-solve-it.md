---
title: "Steve Capell — \"Don't these already solve the problem?\" (review of Start Here / Framework v0.1)"
type: external-reference
origin: Email from Steve Capell (UN/CEFACT Vice-Chair) reviewing the Track 1 Start Here / Onboarding & Governance Framework v0.1
status: captured
captured: 2026-07-08
tags: [external, gdc, trust-registries, w3c, recognized-entities, un-cefact, gtr, grid, discovery, review-feedback]
---

# Steve Capell — "Don't these already solve the problem?"

> Review feedback on the Track 1 [[start-here-issuer-trust-registries|Start Here]] / [[issuer-onboarding-and-governance-v0.1|Framework v0.1]]. Steve is W3C/UN-centric and bridges UN/CEFACT GRID into the TR-TF. He calls the draft "a good start" and raises two pointers, then asks the sharp question: **don't these basically solve the problem this group aims to address?** The answer is *they solve parts of it — as options, not as the solution.* See [[SYNTHESIS#Where the W3C Recognized Entities spec fits]] and [[SYNTHESIS#The UN GTR is a registry-of-registries — alignment and contrast]].

**Naming:** the UN/CEFACT effort is now referred to as **GRID** (Global Registry Information Directory); "GTR" was the earlier project name and is superseded. This capture uses GRID throughout.

## What Steve said (verbatim points)

1. **Relevant emerging W3C spec** — [Recognized Entities v1.0](https://www.w3.org/TR/vc-recognized-entities-1.0/). And **a PR in the pipeline about discovery** — i.e. *given a credential, how to find the recognition credential.*
2. **For government registers, the logical trust root is the member-organisation-of-governments** — UN/CEFACT: `https://un.opensource.unicc.org/unece/uncefact/gtr/`

> Contact: Steve Capell — mob/WhatsApp +61 410 437854.

## The reframe: each point is an option, not the answer

The track is deliberately **mechanism-neutral** and **root-plural**. The [[SCOPE-Track1|scope]] puts wire formats, protocols, and data models *out of scope* (they belong to the technical track), and the framework's core design principle is **no single root** — a web of mutually-recognizing registries, not one master list. Steve's two items land squarely on the two things the scope holds open on purpose.

### Point 1 — Recognized Entities is *a* mechanism, one of several

Recognized Entities v1.0 is a strong candidate **wire format** for expressing a trust list or a single "trust link" as a VC. It is one option alongside:

- **OpenID Federation** (the eduGAIN / OIDF path)
- **ETSI Trust Service Lists / X.509 CA lists** (eIDAS, existing PKI)
- **ICAO PKD** (travel-sector trust list already in production)
- **ISO/IEC 18013-5 VICAL** (mDL)
- **a bespoke system of record** an authority already runs

The framework's job is the **pattern + policy** that lets *any* of these satisfy the two relying-party questions — not to bless one and strand the sovereigns and ecosystems already standardized on another. Blessing a single wire format is precisely what the scope avoids.

Also: Recognized Entities is **First Public Working Draft — experimental, not for production**, with open privacy/security issues, and on its own admission it leaves **discovery, root-of-trust validation, and recognition-chain governance unsolved**. Which is exactly Steve's second bullet —

### The discovery PR *is* the shared prize, not a solved problem

Steve's own "PR in the pipeline about discovery — given a credential, find the recognition credential" is the framework's **Step 4: find the right registry**. Recognized Entities gives the *link format*; it does not yet give *discovery* or *cross-root traversal*. That unsolved discovery problem is a big part of what this group exists to work — see [[SYNTHESIS#Coordination is the missing layer]].

### Point 2 — UN/CEFACT GRID can only ever be *a* root, never *the* root

GRID is captured in full at [[08-un-cefact-global-trust-registry-gtr]]. It's a genuinely strong option and we cite it as **validation** (directory-not-operator, ICAO-PKD self-service, loosely coupled). But by the framework's own design it can only ever be **a** root — one authoritative directory the web points to — **never the** root. Reasons:

- The framework is explicit that **no single root will be accepted by everyone**, and sovereignty means a government's authority **isn't granted or ratified by any body** — not a registrar, not an industry group, not a UN directory. A single universal root collides with that stance.
- GRID is scoped to **legal-entity / supply-chain / registrar** registers (corporate, land, IP, trademark) for trade under UNTP — *not* government-issued personal identity credentials (passport, national ID, mDL), which is Track 1's September wedge.
- Roots already exist and won't defer to one directory: **ICAO PKD** (passports), **AAMVA** (mDL), **EU Trust List** (eIDAS), plus sovereign-run registries.

So GRID is an excellent authoritative directory the web can **point to** for many government/registrar cases — one node in the web of registries. "A root, never the root; good for many purposes, won't fit all."

## So-what

- **Steve has likely only seen the 2-page [[start-here-issuer-trust-registries|Start Here]], not the fuller [[SCOPE-Track1]] and [[issuer-onboarding-and-governance-v0.1|Framework v0.1]].** Both his points are already worked there — Authority Options + the four-step loop (step 4 = *find the right registry*) + the no-single-root / web-of-registries stance, and the scope's explicit hand-off of wire formats/protocols to the technical track (i.e. mechanism-neutrality). His "doesn't this already solve it?" reads like a reaction to the summary, not the worked docs. The reply's job is to *point him to where each point already lands*, not to re-argue from assumed shared context.
- Steve's points **strengthen** the framework rather than obsolete it: they're two concrete instances of options the pattern is designed to accommodate.
- Worth a **direct conversation with Steve** — he bridges UN/CEFACT GRID and the TR-TF and champions Track 1. Flagged as valuable in [[SYNTHESIS#The UN GTR is a registry-of-registries — alignment and contrast]].
- Action item for the framework: make the **mechanism-neutrality** and **no-single-root** stances explicit enough that a reader as sharp as Steve doesn't read "pattern" as "we haven't noticed the mechanisms exist."
