# Issuer Registry Data Model Notes (Parked for Later Phases)

Status: Parked working material. Not part of the v0.1 framework.

This material was moved out of the main [Track 3 Issuer Onboarding & Governance Framework v0.1](../track3-issuer-onboarding-and-governance-v0.1.md) so the v0.1 document stays focused on principles and the operating loop, not on data-model design. It is retained here so the thinking is not lost and can be picked up in a later phase, ideally with whichever technical track owns the machine-readable expression of issuer authorization.

Treat everything below as a starting list to discuss and revise, not as a settled schema.

## Candidate fields for an issuer trust registry entry

An issuer trust registry entry should likely be able to express:

- Issuer legal name.
- Issuer identifier.
- Registrar or approving authority.
- Registry governance authority or trust framework.
- Governance rules or policy version used for approval.
- Status.
- Authorized issuer identifiers, keys, certificates, DIDs, endpoints, or metadata.
- Credential types or schemas covered.
- Authorized claims or attributes for each credential type.
- Disallowed claims or limits where useful.
- Subject population, jurisdiction, or ecosystem scope.
- Assurance level or evidence basis.
- Effective date.
- Expiry or renewal date.
- Suspension or revocation status.
- Location of credential status information.
- Location of policy, terms, audit, or conformance evidence where appropriate.
- Appeal or review path for registry decisions.

This list can later be mapped into a specific technical format. The first task is to agree that this information must exist and be checkable.

## Open tension to carry forward: sovereign issuers

This field list was drafted before the framework drew its line between recognition-and-binding (sovereign and public-authority issuers) and delegated vetting. Several fields assume the vetting case — "registrar or approving authority," "governance rules or policy version used for approval," "appeal or review path for registry decisions" — and read awkwardly, or wrongly, for a sovereign whose authority is declared and self-governed rather than approved.

Before this becomes a schema, the group needs to work through how the data expresses a self-declared, discoverable authority source without implying the registry approved, graded, or can revoke the sovereign's underlying right to issue. This connects directly to the open discussion item in the main document about whether a registry entry should signal recognized versus vetted at all, and if so how, without ranking or second-guessing sovereign issuers. See [Respecting Sovereign Authority](../track3-issuer-onboarding-and-governance-v0.1.md#respecting-sovereign-authority).
