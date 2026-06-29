# Global Digital Collaboration Trust Registry Task Force

## Track 3 Issuer Onboarding & Governance Framework v0.1

Status: Working draft for GDC Trust Registry Task Force discussion

Event target: GDC 2026, Geneva, September 2026

Track: Track 3, Issuer Onboarding & Governance

Co-leads:

- Philippe Nieto, France, Ministère de l’Intérieur
- Darrell O'Donnell, Ayra Association
- Gabriel Marquie, IATA

New to this? Start with [Start Here: Issuer Trust Registries](start-here-issuer-trust-registries.md). This document is the v0.1 detail behind it.

## Purpose

This paper is an early draft that explores the structure of a governance framework that will be derived from. It is still a shared starting point, not a specification and not a finished answer. Its job is to give the Track 3 group enough common language to test the model together.

The question is simple: when someone sees a digital credential, how can they check who issued it, what that issuer is recognized to issue, and whether the answer is still current?

For v0.1, we are starting deliberately with government-issued identity credentials and public-authority issuers. Other issuer types, relying-party governance, wallet governance, registry-of-registries governance, and detailed data-model work are parked in [Later Phases](later-phases/README.md). They matter, but they are not where this first collaboration starts.

## Core Model

A trust registry does not create an issuer's authority. It also does not create the signing keys, identifiers, endpoints, or status services behind a credential. Those remain under the issuer's control. The registry makes the relevant parts discoverable and keeps them usable for people who need to rely on a credential.

The basic loop has four parts:

1. **Get in.** An issuer is recognized in the registry. For a government, that means declaring what it issues, while its signing keys or other trust signals are listed or made discoverable. Recorded, not approved.
2. **Stay current.** The registry keeps the issuer's information current, including whether the issuer, key, credential type, or status service is active, suspended, revoked, expired, or otherwise no longer usable.
3. **Check.** Before relying on a credential, a relying party can confirm that the issuer is recognized, the credential or claim is in scope, the technical signal belongs to that issuer, and the answer is current.
4. **Find the right registry.** The relying party needs a dependable signal for which registry or authority source to check in the first place.

This is the same pattern people already know from trust lists such as ICAO PKD. The v0.1 work is about making the pattern clear enough to test across government-issued identity credentials, not about solving every registry model at once.

## Sovereignty Boundary

This boundary is critical.

A government's authority to issue passports, national IDs, civil-status documents, or similar credentials comes from that country's own law. Nothing — no registry, registrar, industry body, trust framework, or cross-ecosystem layer — grants it, ratifies it, or sits in judgment of it.

The registry's job is narrower. It can help answer whether this is really the government authority, what that authority says it issues, where the governance basis can be found, and whether the relevant information is current. It must not become a verdict on whether a sovereign is allowed to issue under its own law.

Put simply: a government is recognized and made discoverable through the registry. It is never vetted or approved by it.

For delegated or registrar-governed issuers, the process can be different. A registrar may assess evidence and approve or reject participation under published rules. The same registry data may support both models, but the governance meaning is not the same.

## What A Registry Answer Should Make Clear

A registry answer should be useful to anyone who has a stake in the credential: a verifier, a wallet, the holder receiving it, or another party that needs to understand whether the issuer can be relied on.

At this stage, the answer should make five things clear:

- **Who is the issuer?** Identify it clearly enough that a relying party is not guessing.
- **What can this issuer issue?** Show the credential types, claims, or jurisdictions that are in scope.
- **Which technical signals belong to it?** List or point to the signing keys, identifiers, endpoints, or status services under the issuer's control.
- **Is the answer current?** Make clear whether the relevant issuer, key, credential type, claim, or status service is active and usable.
- **Who is accountable for the registry answer?** Say whether the registry is authoritative itself, points to another authority source, or uses a registrar model.

These checks are about authenticity, scope, currency, and discoverability. They are not a place to adjudicate sovereign legitimacy. A relying party can still apply its own policy about which authorities it honors, but that policy decision belongs to the relying party, not to the registry.

## Registry Governance

Governance is not only about listing an issuer. It is about who operates the registry, what claim the listing makes, and who keeps the answer current.

For v0.1, the governance model should make a few things visible:

- Who operates the registry or is responsible for it.
- Whether the registry is authoritative in its own right or points to another authority source.
- Whether a registrar or assessor is involved.
- How entries are added, updated, suspended, revoked, or removed.
- How issuer-controlled technical signals are recorded, referenced, or verified.
- How relying parties discover the registry and read its answer.

For sovereign-operated or sovereign-designated registries, the governance answer may simply be the sovereign and its law. For industry, professional, commercial, or delegated registries, the governance evidence may need to be more explicit.

## Decisions To Make Together

This is the small set of questions the v0.1 paper exists to work through together. None of them is settled. The starting points below are just a place to begin, so the group has something concrete to test and improve.

1. **Where to start.** *Starting point:* begin with government-issued identity credentials and public-authority issuers, including passports, national IDs, and mobile driver's licenses. *Still open:* is that the right first slice for Geneva, or should v0.1 narrow further?
2. **Recognized vs. vetted.** *Starting point:* keep sovereign recognition and delegated registrar vetting clearly distinct in process. *Still open:* should the registry data also distinguish the two, and if so, how do we do that without ranking or second-guessing sovereign issuers?
3. **Who runs the registry, and who's accountable.** *Starting point:* a sovereign can operate or designate its own registry; industry or delegated models can also exist; the cross-ecosystem layer should discover and point to those sources rather than govern them. *Still open:* when is a registry authoritative, when is it expressing authority from somewhere else, and who is responsible for its operation?
4. **What happens when a check fails.** *Starting point:* agree baseline handling for a few clear failures, such as unknown issuer, suspended issuer, or credential out of scope. *Still open:* which failures should mean refusal, a warning, cached reliance, or an ecosystem-specific policy call?
5. **Freshness and outages.** *Starting point:* the ecosystem sets the freshness requirement, with cached data allowed within limits when a registry is briefly unavailable. *Still open:* how current must issuer, credential, claim, key, endpoint, and status-service information be for real border, travel, and relying-party workflows?
6. **How precisely authority is scoped.** *Starting point:* express authority by credential type, by claim, and by jurisdiction. *Still open:* is that enough for v0.1, or does the first version also need schemas, assurance levels, subject populations, technical signals, and registry discovery signals?

## What Is Deferred

This v0.1 paper stays small on purpose. Detailed evidence lists, candidate status values, failure behavior, discovery inputs, claim-scope examples, data-model notes, and the longer open-question list live in [Issuer Trust Registry Operational Detail](later-phases/issuer-trust-registry-operational-detail.md).


