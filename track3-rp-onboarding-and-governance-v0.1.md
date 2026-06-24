# Track 3 RP Onboarding and Governance Framework v0.1

Status: Working draft for GDC Trust Registry Task Force discussion

Event target: GDC 2026, Geneva, September 2026

Track: Track 3, RP Onboarding and Governance

Champion input: Darrell O'Donnell, Ayra

## Preamble

This working draft has been consolidated from multiple pieces of material shared within the GDC Trust Registry Task Force group, with deliberate AI assistance. It also draws on the Ayra knowledge base and on experience from Ayra's membership and related trust-registry work.

The ideas here are intended to spark thinking and elicit more detail from co-leads and contributors. They should not be read as hard decisions, settled scope, or final language. Before anything is published externally, this material will need to be compressed, simplified, checked against the group's shared intent, and rewritten into a form that is easier for a broader audience to use.

## Source Materials Consulted

The externally shared materials consulted for this draft were gathered primarily from the GDC Trust Registries Task Force email thread titled `REMINDER: Trust Registries Meeting Today @ 16:30 CET`, shared through the TR-TF Google Group between June 10 and June 15, 2026. Local copies of the consulted materials are gathered in `references-and-inputs/`.

Group-shared resources consulted:

- GDC Trust Registries Task Force page and meeting thread provenance.
- GDC Secretariat work tracks / champion allocation document, shared by Ruth Puente, including the Track 3 RP Onboarding & Governance assignment.
- `Trust Management: Defining the Challenge for Ecosystem Builders`, by David Kelts and Debora Comparin, from the SIDI Hub / ITU-T SG17 trust-management work.
- `Trust Management: Developing Conventions Using Trust Vectors`, by David Kelts and Debora Comparin, from the SIDI Hub / ITU-T SG17 trust-management work.
- `{In-progress} Trust Management: Mechanisms to Convey Trust`, by David Kelts and Debora Comparin, shared as an incomplete technical catalogue of trust mechanisms.
- `W3C Recognized Entities v1.0`, a W3C Verifiable Credentials Working Group First Public Working Draft dated May 12, 2026, proposed to the list by Steve Capell.
- `eduGAIN OpenID Federation Pilot` presentation, by Niels van Dijk and Davide Vaghetti, shared by Gail Hodges as prior art on federated trust at scale.
- UN/CEFACT Global Trust Registry / Global Registry Information Directory material, including the GTR logical model shared by Steve Capell.

Ayra context and synthesis consulted:

- Ayra's internal synthesis of the GDC TR-TF corpus, included in `references-and-inputs/ayra-context/SYNTHESIS.md`, especially where the shared materials align with or diverge from Ayra's trust-registry work.
- Ayra's Track 3 scope notes for GDC 2026, including the current boundary that Track 3 is about RP/verifier authorization for government-issued identity, while issuer authorization is out of scope.
- Ayra meeting notes and knowledge-base material on trust registries, verifier authorization, wallet-side checks, registry-of-registries patterns, and member experience with trust infrastructure.

## Design Posture

This draft is intentionally operational, but it should remain implementation-neutral and ecosystem-neutral. It is not intended to require one governance model, one technology stack, or one operator.

The working posture is:

- Scoped authorization, not blanket trust: registration should say what a verifier is allowed to request, for which purpose, under which conditions.
- Transparency over hidden governance: participants should be able to understand who admitted a verifier, under what rules, and how status can change.
- Privacy and non-correlation by design: verifier checks should not become a transaction-surveillance layer or hidden phone-home mechanism.
- Ecosystem sovereignty: different ecosystems may satisfy requirements through their own laws, policies, standards, or governance frameworks, provided the result is visible and checkable.
- Conformance and evidence over self-asserted legitimacy: technical ability to make a request is not enough; the verifier needs a governance basis for making that request.
- Implementation neutrality: this framework should define the questions and minimum surfaces, while leaving wire formats, APIs, and certification machinery to the appropriate technical and governance work.

## Relationship to Operational Profiles

This framework defines the questions a relying-party / verifier onboarding model should answer. It does not need to contain every operational answer for every credential type or jurisdiction.

A separate operational profile can make the framework concrete for a specific use case. For example, [Government-Issued Identity RP Profile Draft](government-issued-identity-rp-profile-draft.md) sketches one possible profile for relying parties and verifiers that want to consume government-issued identity credentials. That profile is a strawman example, not a GDC decision and not an Ayra governance framework. Its purpose is to make the discussion more concrete so the group can decide what to keep, remove, simplify, or defer.

## Starting Point

This v0.1 framework starts small. It does not try to solve every cross-ecosystem trust registry problem. It defines the minimum pattern for onboarding a verifier, keeping that verifier in good standing, and letting a wallet check whether the verifier is allowed to make a specific presentation request.

The first version answers five questions:

- How does a verifier get in?
- What are the minimum governance requirements for that verifier to continue to be in the trust registry?
- How does a wallet check a trust registry? Includes: How does a wallet know to check a trust registry?
- Which presentation requests are authorized for that particular verifier?

Early open question for co-leads: Are we working only on relying-party/verifier authorization, or **does wallet authorization or wallet approval also belong in this track**? The current draft treats wallet-side checking as in scope, because the verifier governance model only matters if wallets can act on it. Whether wallets themselves must be authorized, approved, certified, or otherwise governed is unresolved and should be decided explicitly.

Additional material that informed this draft is preserved in [Considerations for Later Phases](considerations-for-later-phases.md).

## Scope for v0.1

In scope:

- Verifier onboarding into a trust registry for government-issued identity credentials.
- Governance of the trust registry and registrar: who is authorized to vet verifiers, what rules they apply, and how they are held accountable.
- Minimum ongoing governance requirements for a verifier to remain listed.
- Wallet-side checks against the trust registry before holder data is released.
- Discovery signals that tell a wallet which trust registry to check.
- Presentation-level authorization: which credential type, attribute set, purpose, and context a verifier is allowed to request.

Out of scope for this first document:

- Cross-border registry-of-registries governance.
- Full trust framework design for every credential ecosystem.
- Technical wire-format selection.
- Issuer authorization, issuer onboarding, or identity-provider governance.
- Non-government or fully commercial credential ecosystems.

Those topics matter, but they should not obscure the initial operating loop: admit the verifier, govern the verifier, let the wallet check the verifier, and constrain the verifier's request to its authorized scope.

## Core Roles

- Verifier: The party asking the holder to present credential data.
- Relying Party (RP): The legal or organizational entity responsible for the verification request.
- Reader: The device, endpoint, app, service, or component making the request on behalf of the verifier.
- Wallet: The holder-controlled software or agent that receives a presentation request and decides what, if anything, to release.
- Holder: The person presenting credential data through the wallet.
- Trust registry: The governed source that lists recognized verifiers and what each verifier is authorized to request.
- Registrar: The body authorized to assess, approve, maintain, suspend, or revoke verifier registration.
- Registry governance authority: The body or governance process that authorizes the registrar, publishes the rules the registrar must apply, reviews registrar performance, and can suspend or replace registrar authority.
- Presentation request: The verifier's request for a credential presentation, including purpose, credential type, requested attributes, data minimization constraints, and reader or endpoint identity.

## Registry Governance

The trust registry is only as trustworthy as the governance behind it. A verifier keeping its information up to date is necessary, but not sufficient. The framework also needs to say who is allowed to vet verifiers, what criteria they use, how their decisions are reviewed, and what happens if the registrar fails.

At minimum, the registry governance authority should define:

- Who is authorized to operate the trust registry.
- Who is authorized to act as registrar or assessor.
- What eligibility, privacy, security, technical, and operational requirements the registrar must apply.
- What evidence the registrar must collect before admitting a verifier.
- What decision record the registrar must keep for approval, conditional approval, rejection, suspension, revocation, and appeal.
- How conflicts of interest are declared and managed.
- How registrar decisions can be appealed or reviewed.
- How registrar performance is audited.
- How the registrar's own authority can be suspended, revoked, transferred, or renewed.
- How changes to registry rules are published and made visible to wallets, verifiers, holders, and ecosystem participants.

The registrar should not be a black box. If a wallet is expected to trust that a verifier has been vetted, then the wallet and the ecosystem need a basis for trusting the vetting function itself.

## 1. How a Verifier Gets In

A verifier should not appear in the trust registry merely because it can make a technically valid request. Entry into the registry requires a governance decision.

The minimum onboarding path is:

1. Discover the applicable trust registry and onboarding process.
2. Apply to the registrar.
3. Confirm that the registrar is authorized by the registry governance authority to make this decision.
4. Identify the RP, verifier role, readers or endpoints, operating jurisdictions, and responsible contacts.
5. State the verifier's intended use cases.
6. State the exact presentation requests the verifier wants to make.
7. Provide evidence that the verifier is legitimate and accountable.
8. Provide evidence that the verifier can meet the technical, privacy, security, and operational requirements.
9. Receive a scoped approval, rejection, or request for more information.
10. If approved, appear in the trust registry with active status and defined authorization scope.

The application should be specific enough that the registrar can answer: should this verifier be allowed to ask this holder for this data, for this purpose, in this context?

## Minimum Entry Evidence

The initial evidence bar should be modest but real. A verifier should provide:

- Legal identity of the responsible organization.
- Control of the domain, app, service, reader, endpoint, certificate, key, or other identifier used in the presentation request.
- Business or public-service purpose for each requested presentation.
- Legal or policy basis for requesting the data.
- Data minimization rationale.
- Security contact and incident-response path.
- Privacy contact and holder-support path.
- Agreement to registry rules, audit rights, suspension rules, and revocation rules.
- Technical conformance evidence for the request protocol or trust registry interface.

The registrar may require more for higher-risk requests. A verifier requesting proof of age should not need the same evidentiary burden as a verifier requesting a full identity document with address and document number.

## 2. Minimum Governance Requirements to Stay In

Registration is not a one-time event. A verifier remains in the trust registry only while it continues to meet the requirements under which it was approved.

At minimum, a listed verifier must:

- Keep organization, contact, reader, endpoint, key, and certificate information current.
- Request only the credential types and attributes for which it is authorized.
- Use each authorized presentation only for the approved purpose.
- Maintain required technical conformance.
- Maintain required privacy and security controls.
- Support holder inquiries and complaints.
- Report material security, privacy, operational, or governance incidents.
- Submit to renewal, review, audit, or reassessment when required.
- Stop using suspended or revoked readers, endpoints, keys, or authorizations.
- Accept suspension or removal if it no longer meets the requirements.

The trust registry should represent at least these states:

- Pending: Application received but not approved.
- Active: Approved and currently authorized.
- Conditional: Approved with limits, remediation requirements, or expiry.
- Suspended: Temporarily not authorized.
- Revoked: No longer authorized.
- Expired: Authorization ended without renewal.

Wallets should not treat these states as display-only metadata. Status affects whether holder data can be released.

## 3. How a Wallet Checks a Trust Registry

The wallet check asks: have we verified the verifier?

Before releasing holder data, the wallet should be able to check:

- Is the verifier listed in a recognized trust registry?
- Is the verifier currently active?
- Was the verifier approved by an authorized registrar?
- Is the registrar still authorized by the registry governance authority?
- Which governance rules or trust framework was the verifier assessed against?
- Is the reader, endpoint, app, certificate, key, or other request identifier bound to that verifier?
- Is the verifier authorized for this credential type/presentation?
- Is the verifier authorized for this purpose?
- Is the verifier authorized for these requested attributes?
- Is the verifier authorized in this jurisdiction or ecosystem context, if that matters?
- Is the authorization still fresh, not suspended, not revoked, and not expired?
- What should the wallet do if any check fails?

The trust registry or recognition artifact therefore needs to expose enough machine-readable information for the wallet to make a runtime decision. It is not enough for the registry to say that an organization is generally legitimate. The wallet must know whether this particular request is allowed.

## Wallet Failure Behavior

The framework should define clear wallet behavior for failed checks. NOTE: a wallet may allow sharing anything - but recommendations for the concerns below would be to, at minimum, warn the Holder. Regulation may disallow sharing with unregistered/unauthorized parties.

At minimum:

- Unknown verifier: Do not release data unless the governing policy explicitly allows user override.
- Inactive, suspended, revoked, or expired verifier: Do not release data.
- Reader or endpoint not bound to verifier: Do not release data.
- Purpose not authorized: Do not release data.
- Attribute request exceeds authorization: Release only the authorized subset if the protocol supports it, or refuse the request.
- Registry unavailable: Follow ecosystem policy, which may require refusal, cached status with freshness limits, or high-salience holder warning.

The warning text and user experience are implementation details, but the policy choice is governance. The trust framework must say what the wallet is expected to do.

## 4. How a Wallet Knows to Check a Trust Registry

The wallet needs a discovery signal. A wallet cannot check the right trust registry unless the presentation flow tells it where the verifier claims recognition, or the wallet already knows which registry applies to the credential type, trust framework, ecosystem, or jurisdiction.

Possible discovery inputs include:

- Credential or trust framework metadata.
- The credential type or trust framework identifier.
- The verifier's presentation request.
- A registry identifier or trust framework reference in the verifier's request.
- A well-known endpoint associated with the verifier.
- A wallet policy bundle or ecosystem configuration.
- A governance framework that maps credential types and jurisdictions to recognized trust registries.

The v0.1 requirement is not to choose a single discovery mechanism. The requirement is that the wallet can determine which trust registry or recognition source to check before it decides whether to release data.

The discovery signal should let the wallet answer:

- Which registry is authoritative for this verifier check?
- Which registrar or governance framework authorized the verifier?
- What credential type and presentation scope does that authority cover?
- How does the wallet validate integrity, freshness, and status?
- What happens if multiple registries claim authority?

## 5. Which Presentation Requests Are Authorized

The trust registry must not only list verifiers. It must list what each verifier is authorized to ask for.

Authorization should be presentation-specific. Examples:

- Age only: The verifier may ask whether the holder is over a threshold, such as over 18 or over 21, without receiving name, address, document number, or full date of birth.
- Full name: The verifier may ask for first name and last name.
- Address: The verifier may ask for current residential address.
- Document number: The verifier may ask for a passport number, driver's licence number, national ID number, or other document identifier.
- Full document presentation: The verifier may ask for the full credential or a broad attribute set.
- Jurisdiction-specific entitlement: The verifier may ask for attributes only where a law, policy, or ecosystem rule allows it.

Each authorization should specify:

- Verifier identity.
- Reader, app, endpoint, key, or certificate binding.
- Credential type.
- Authorized purpose.
- Authorized attribute set.
- Disallowed attributes, if useful for clarity.
- Jurisdiction or ecosystem context.
- Time limit or renewal date.
- Status and revocation information.
- Registrar or authority responsible for the decision.

If a verifier is approved only for age checking, the wallet should not release full first name, last name, address, passport number, driver's licence number, national ID number, or full document data. If a verifier needs a full document or high-risk attribute set, that authorization needs to be explicit, visible to the wallet, and supported by stronger governance evidence.

## Minimum Data Model

A v0.1 trust registry entry should be able to express:

- Verifier legal name.
- Verifier identifier.
- Registrar or approving authority.
- Registry governance authority or trust framework.
- Governance rules or policy version used for approval.
- Status.
- Authorized readers or endpoints.
- Credential types covered.
- Authorized presentation request profiles.
- Authorized attributes for each profile.
- Purpose for each profile.
- Jurisdiction or ecosystem scope.
- Effective date.
- Expiry or renewal date.
- Suspension or revocation status.
- Location of policy, terms, audit, or conformance evidence where appropriate.
- Appeal or review path for registry decisions.

This data model can later be mapped into a specific technical format. The first task is to agree that this information must exist and be checkable.

## v0.1 Deliverables

- Minimal verifier onboarding lifecycle.
- Registry governance requirements for who may vet and admit verifiers.
- Minimum governance requirements for continued registry listing.
- Wallet-side trust registry check requirements.
- Trust registry discovery requirements.
- Presentation-request authorization model.
- Open questions list for co-leads and contributors.

## Open Questions

- What is the minimum evidence required for a low-risk verifier?
- What additional evidence is required for high-risk presentation requests?
- Who is authorized to act as registrar, and how is that authority granted?
- What governance authority holds the registrar accountable?
- What decision records must the registrar keep?
- What audit, appeal, conflict-of-interest, and registrar-removal processes are required?
- Which registry status values must wallets understand?
- Should wallet refusal rules be mandatory, recommended, or ecosystem-specific?
- How fresh must registry status be for wallet-side checks?
- How should cached registry data behave when the registry is unavailable?
- How should a verifier request only an authorized subset when a holder credential supports more data than the verifier is allowed to receive?
- What is the minimum viable discovery signal that tells a wallet which trust registry to check?
- Which technical track owns the machine-readable expression of verifier authorization?
