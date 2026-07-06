# Issuer Trust Registry Operational Detail

Status: Later-phase working notes moved out of the v0.1 issuer onboarding and governance paper

This note preserves operational detail that may be useful later, but should not carry the first collaboration paper. It is intentionally more granular than the main framework document.

The language in this note follows the corrected trust-registry model: issuers establish and control their identifiers, keys, endpoints, metadata, and status services. A trust registry records, exposes, references, or verifies those relationships depending on the registry model. Where a registrar model applies, the registrar may verify proof of control.

## Detailed Recognition Or Representation Path

For delegated or registry-governed issuers, appearing in an issuer trust registry may reflect a governance decision, not merely possession of a signing key.

For a sovereign or public-authority issuer, the path is recognition and discoverability, not approval. The process establishes what the issuer is, lists or exposes issuer-controlled technical material, and records the scope and governance the issuer declares. It does not put the registrar in the position of granting or judging the issuer's underlying authority.

One candidate path is:

1. Discover the applicable issuer trust registry and recognition process.
2. Engage the registry operator or registrar.
3. Where a registrar model is used, confirm that the registrar is authorized by the registry governance authority to assess and list issuer authority evidence.
4. Identify the issuer's legal identity, public authority or business authority, issuing roles, operating jurisdictions, systems, keys, endpoints, and responsible contacts.
5. State the credential types, schemas, claims, assurance levels, and issuing contexts the issuer wants to be recognized for.
6. Identify the authority source for those credentials or claims. For a delegated issuer, provide evidence of authority from the relevant competent source. For a sovereign or public-authority issuer, declare the authority source and make it discoverable; this is recorded, not adjudicated.
7. Provide evidence, declarations, or other agreed assurances that the issuer can meet the technical, privacy, security, operational, and lifecycle requirements relevant to that registry model.
8. Receive a scoped recognition, approval, rejection, or request for more information, depending on the issuer type and registry model.
9. If recognized or approved, appear in the issuer trust registry with active status and defined credential scope.

## Candidate Evidence Or Declaration Set

The initial evidence or declaration set should be modest but real. A candidate baseline is that an issuer provides or declares:

- Legal identity of the issuing organization.
- Evidence of public authority, statutory authority, regulatory authority, institutional authority, business authority, or other recognized basis for issuance.
- Credential types, schemas, claims, assurance levels, and jurisdictions requested.
- Proof of control over issuer identifiers, domains, endpoints, signing keys, certificates, DIDs, or other issuance infrastructure.
- Governance and operating policies for issuance, renewal, suspension, revocation, correction, and appeal.
- Privacy contact and holder-support path.
- Security contact and incident-response path.
- Lifecycle and status-management process for issued credentials.
- Agreement to the registry rules that apply to that issuer type, including any audit, suspension, and revocation rules for the registry listing or listed technical material.
- Technical conformance evidence for the credential format, issuer metadata, trust registry interface, and status mechanism used by the ecosystem.

The registrar may require more for higher-risk credentials. An issuer of low-risk membership attestations should not need the same evidentiary burden as an issuer of national identity, travel, immigration, health, financial, or legal-status credentials.

For a sovereign or public-authority issuer, this list is read in recognition mode. The authority basis is declared and made discoverable rather than proven to an industry registrar's satisfaction. Audit, suspension, and revocation rules apply to the registry listing and affected technical material, not to the sovereign's underlying right to issue.

## Keeping Registry Information Current

Registration or recognition is not a one-time event. A listed issuer remains useful to relying parties only while its registry information, status, and listed technical material remain current.

A candidate baseline for continued listing is that a listed issuer is expected to:

- Keep organization, authority, contact, endpoint, key, certificate, metadata, and status-service information current.
- Issue only the credential types, schemas, claims, assurance levels, and jurisdictions for which it is authorized.
- Maintain required technical conformance.
- Maintain required privacy and security controls.
- Maintain accurate credential status, suspension, revocation, and correction processes.
- Support holder inquiries, verifier inquiries, and correction or dispute processes.
- Report material security, privacy, operational, legal-authority, or governance incidents.
- Participate in renewal, review, audit, or reassessment when required by the applicable registry model.
- Stop using suspended or revoked keys, endpoints, identifiers, or authorizations.
- Accept suspension or removal of the registry listing or affected technical material if it no longer meets the applicable requirements.

## Candidate Status Values

A candidate status model would represent at least these states:

- Pending: Application, recognition request, or technical-material update received but not yet active.
- Active: Recognized or approved and currently in scope.
- Conditional: Recognized or approved with limits, remediation requirements, or expiry.
- Suspended: Temporarily not active for the affected credential, claim, registry listing, identifier, key, endpoint, metadata, or status service.
- Revoked: No longer active for the affected credential, claim, registry listing, identifier, key, endpoint, metadata, or status service.
- Expired: Authorization ended without renewal.

The working assumption is that verifiers and wallets should not treat these states as display-only metadata. Status affects whether a credential or claim can be relied upon.

## Candidate Verifier Or Wallet Checks

The check is meant to answer: have we verified the issuer?

Before relying on a credential or claim, the verifier or wallet should be able to check:

- Is the issuer listed in a recognized issuer trust registry?
- Is the issuer currently active?
- Where a registrar model is used, was the issuer listed by an authorized registrar?
- Where a registrar model is used, is the registrar still authorized by the registry governance authority?
- Which governance rules, trust framework, or authority source is the listing connected to?
- Is the presented issuer identifier, key, certificate, DID, endpoint, or metadata listed for that issuer, and is control established or verified under the registry model?
- Does the registry express authority for this issuer to issue this credential type or schema?
- Does the registry express authority for this issuer to issue these claims or attributes?
- Does the registry express authority for this assurance level or issuing context?
- Does the registry express authority for this jurisdiction or ecosystem context, if that matters?
- Is the authorization still fresh, not suspended, not revoked, and not expired?
- What should the verifier or wallet do if any check fails?

These checks are about authenticity, scope, currency, and discoverability, not about adjudicating a sovereign's legitimacy. Where the issuer is a sovereign or public authority, "Which governance rules or trust framework was the issuer assessed against?" should be read as "Which governance or authority source does the issuer declare, and where can it be found?"

## Candidate Failure Behavior

The framework should help the group decide what failed issuer checks mean. A verifier may still decide to accept something under its own policy, but the shared work should identify candidate baseline recommendations and any cases that the relevant ecosystem treats as mandatory refusal rules.

One candidate baseline is:

- Unknown issuer: Treat the credential as not reliable unless the governing policy explicitly allows override.
- Inactive, suspended, revoked, or expired issuer: Treat credentials issued under the affected authorization as not reliable.
- Key, certificate, DID, endpoint, metadata, or status service not listed for the issuer, or proof of control not established where required: Treat the credential as not reliable.
- Credential type not authorized: Treat the credential as not reliable for that credential type.
- Claim or attribute exceeds issuer authorization: Treat the unsupported claim as not reliable.
- Registry unavailable: Follow ecosystem policy, which may require refusal, cached status with freshness limits, or a high-salience warning.

The warning text and user experience are implementation details outside the v0.1 document. The issuer framework can define the issuer-status and authority information that downstream consumers need in order to apply their own policy.

## Discovery Inputs

The verifier or wallet needs a discovery signal. It can only check the right issuer trust registry if the credential, issuer metadata, trust framework, or ecosystem configuration tells it where issuer authority is represented.

Possible discovery inputs include:

- Credential metadata.
- Credential type or trust framework identifier.
- Issuer metadata or issuer well-known endpoint.
- Issuer identifier, DID document, certificate chain, federation metadata, or trust-list reference.
- Registry identifier or trust framework reference embedded in the credential or issuer metadata.
- Consumer policy bundle.
- Ecosystem configuration that maps credential types and jurisdictions to recognized issuer trust registries.

The discovery signal is expected to let the verifier or wallet answer:

- Which issuer registry is authoritative for this credential or claim?
- Where a registrar model is used, which registrar or governance framework recognized or authorized the issuer?
- What credential type, schema, claim scope, assurance level, and jurisdiction does that authority cover?
- How does the relying consumer validate integrity, freshness, and status?
- What happens if multiple registries claim authority?

## Credential And Claim Scope Examples

An issuer trust registry needs to do more than list issuers. It needs to express what authority each issuer has for the credentials and claims it issues.

Expressed authority should be credential- and claim-specific. Examples:

- National identity credential: The issuer may issue a defined national ID credential under a stated public authority.
- Mobile driver's license: The issuer may issue an mDL or driver entitlement credential for a defined jurisdiction.
- Passport-derived credential: The issuer may issue passport-derived claims under a defined issuing or relying framework.
- Age or age-over-threshold claim: The issuer may issue only an age-related claim, not full identity data.
- Address or residency claim: The issuer may issue address, residency, or jurisdictional presence claims.
- Business or organization identity: The issuer may issue organization identity or registration claims based on a company register, LEI, professional register, or other authoritative source.
- Professional, education, health, financial, or licence credential: The issuer may issue defined claims only where its authority for that domain is established.

One candidate listing model would specify:

- Issuer identity.
- Issuer identifiers, keys, certificates, DIDs, endpoints, metadata, and status services.
- Credential types or schemas.
- Authorized claims or attributes.
- Disallowed claims, if useful for clarity.
- Subject population or eligibility boundary.
- Assurance level or evidence basis.
- Jurisdiction or ecosystem context.
- Legal, regulatory, institutional, business, or other competent authority source.
- Time limit or renewal date.
- Status and revocation information.
- Registrar, registry operator, or authority responsible for the recognition, approval, or listing decision.

If a registry expresses authority for an issuer only for age-over-threshold claims, the working assumption is that verifiers should not treat that issuer as authoritative for full first name, last name, address, passport number, driver's licence number, national ID number, or full document data. If a registry expresses authority for high-risk identity or legal-status credentials, that authority should be explicit, visible to the verifier or wallet, and supported by governance evidence appropriate to the issuer type and registry model.

## Data Model Notes

Data-model design is deliberately out of scope for the main v0.1 paper. The machine-readable expression of an issuer registry entry is later-phase work, ideally owned by whichever technical track handles issuer authorization. Early field-level thinking has been parked, not discarded: see [Issuer Registry Data Model Notes](issuer-registry-data-model-notes.md).

## Longer Open Questions

- What issuer categories are in scope for Geneva v0.1?
- How does the framework distinguish recognition and discoverability for sovereign and public-authority issuers from delegated vetting, in process and in the data model?
- For a sovereign or public-authority issuer, what is the minimum it declares, and what must the registry never require it to "prove" to an industry registrar?
- How does a relying party authenticate a sovereign-operated or sovereign-designated registry and trace its governance without that becoming a challenge to sovereign authority?
- How does the data model record an authority source as declared and discoverable versus assessed by registrar?
- Should a registry entry signal, in some form, whether the listed authority is recognized or vetted? This needs discussion before it is settled. A consumer arguably benefits from knowing which kind of answer it is reading, but encoding it carelessly risks the opposite of this framework's intent: letting industry tooling treat "recognized" as a lesser or unverified tier, or implying the registry is grading sovereign authority.
- What is the minimum evidence required for a low-risk issuer?
- What additional evidence is required for high-risk public-sector, travel, health, finance, or legal-status credentials?
- Who is authorized to act as issuer registrar, and how is that authority granted?
- What governance authority holds the issuer registrar accountable?
- What decision records must the issuer registrar keep?
- What audit, appeal, conflict-of-interest, and registrar-removal processes are required?
- Which issuer registry status values must relying consumers understand?
- Should failed issuer checks be mandatory refusals, warnings, or ecosystem-specific policy decisions?
- How fresh must issuer registry status be?
- How should cached issuer registry data behave when the registry is unavailable?
- What is the minimum viable discovery signal that tells a relying consumer which issuer trust registry to check?
- How should expressed issuer authority be scoped to credential types, schemas, claims, assurance levels, and jurisdictions?
- Which technical track owns the machine-readable expression of issuer authorization?
