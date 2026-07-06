# Diagrams — Trust Pattern Visuals

These diagrams illustrate the trust pattern defined in [SCOPE-Track1.md](https://github.com/ayraforum/gdc-trust-registries-tf/blob/main/SCOPE-Track1.md). The PlantUML files are useful for architecture discussion; the storytelling SVGs are more presentation-oriented.

## Storytelling Graphics

| Graphic | Shows |
|---------|-------|
| [storytelling/00-trust-pattern-plain-language.svg](storytelling/00-trust-pattern-plain-language.svg) | A non-technical version of the generic trust pattern: authority, issuer, person, verifier, trust registry, and trust decision |
| [storytelling/01-two-sided-trust-story.svg](storytelling/01-two-sided-trust-story.svg) | The two-sided story: authority exposes trust information; verifier asks for answers; trust decision stays with the verifier or relying party |
| [storytelling/02-question-pattern-flow.svg](storytelling/02-question-pattern-flow.svg) | The repeated question pattern from credential type to issuer, authority basis, registry lookup, registry answer, and trust decision |

## C4 / PlantUML Diagrams

| Diagram | Shows |
|---------|-------|
| [00-trust-pattern.puml](00-trust-pattern.puml) | The generic pattern: credential signed by an issuer, anchoring to a trust registry (Q1), registry-to-registry recognition (Q2), and the trust decision staying with the relying party |
| [01-drivers-license.puml](01-drivers-license.puml) | Mobile driver's license — authority option: *participate in a shared registry service* (AAMVA) |
| [02-national-id.puml](02-national-id.puml) | National ID card — authority option: *operate its own registry*, with Q2 traversal via the EU List of Trusted Lists |
| [03-passport.puml](03-passport.puml) | Passport — the working reference model (ICAO PKD), including why peering beats a single root |
| [04-web-of-registries.puml](04-web-of-registries.puml) | The traversal itself: from any credential, registry to registry, to an authority the relying party trusts — a graph, not a hierarchy |

## Rendering

Any of:

- VS Code: the PlantUML extension (`jebbs.plantuml`) — open a `.puml` file and preview (Option+D).
- CLI: `plantuml -tsvg diags/*.puml` (requires `brew install plantuml`).
- Web: paste into <https://www.plantuml.com/plantuml>.

The C4 macros come from the PlantUML standard library (`!include <C4/C4_Context>`), so no extra files are needed.
