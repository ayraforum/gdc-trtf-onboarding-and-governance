# Government-Issued Identity RP Profile Draft

Status: Supporting strawman operational profile for downstream verifier-access discussion

Parent discussion: [Track 3 Issuer Onboarding & Governance Framework v0.1](../track3-issuer-onboarding-and-governance-v0.1.md)

## How to Read This Profile

This profile is a draft example of downstream relying-party and verifier access questions that arise once issuer trust is available. It is not the main Track 3 deliverable, not a GDC decision, not a consensus document, and not an Ayra governance framework.

The purpose is to preserve the useful RP/verifier thinking from the earlier framing. The profile turns downstream access questions into operational choices: who applies, what evidence is required, who approves, what appears in the registry, what the wallet checks, and what happens when a check fails.

This profile should be treated as supporting discussion material. It should be simplified, corrected, and narrowed before any publication or adoption.

## 1. Purpose

The purpose of this profile is to define a minimal operational pattern for onboarding relying parties, verifiers, and readers that request presentations of government-issued identity credentials.

The profile answers one practical question:

How does a relying party or verifier become recognized to request a specific government-issued identity presentation, and how can a wallet check that recognition before releasing holder data?

## 2. Scope

In scope:

- Relying parties and verifiers that request government-issued identity credential presentations.
- Readers, apps, endpoints, certificates, keys, or other request identifiers used by those verifiers.
- Registry entries that state verifier authorization, status, scope, and binding.
- Wallet-side checks that determine whether the verifier is authorized for the request being made.
- Presentation-level authorization, including purpose, credential type, requested attributes, jurisdiction, and operating context.

Out of scope for this supporting profile:

- Issuer authorization, issuer onboarding, or identity-provider governance, except as defined by the parent issuer-onboarding framework.
- Full trust-framework design for every government identity ecosystem.
- Cross-border registry-of-registries governance.
- Technical wire-format selection.
- Certification of wallets, unless the Track 3 group decides wallet authorization belongs in scope.
- Non-government or fully commercial credential ecosystems.

## 3. Design Posture

This profile follows these working assumptions:

- Authorization is scoped: a verifier is authorized for specific requests, not generally trusted for everything.
- Governance is visible: a wallet or ecosystem participant should be able to determine who approved the verifier and under which rules.
- Privacy is a first-order requirement: verifier authorization checks must not create avoidable holder surveillance.
- Requirements may be satisfied by equivalent regimes: legal identity, privacy, security, and assurance evidence may come from national law, sector regulation, existing certification, or other accepted frameworks.
- Conformance is about the checkable surface: internal implementation details do not need to be exposed if the verifier and registry can produce the required evidence and behavior.
- Risk tiers matter: age-only verification should not require the same evidence as full-document access.

## 4. Roles

| Role | Meaning in this profile |
| --- | --- |
| Relying Party (RP) | The legal or organizational entity responsible for the presentation request and its use. |
| Verifier | The party or service performing the verification interaction on behalf of the RP. |
| Reader | The device, app, endpoint, or component that initiates or carries the presentation request. |
| Holder | The person presenting credential data through a wallet or other agent. |
| Wallet | Holder-controlled software or agent that receives a presentation request, checks verifier authorization, and decides what to release. |
| Registrar | The body authorized to assess verifier applications and make approval, renewal, suspension, or revocation decisions. |
| Registry Governance Authority | The body or governance process that authorizes the registrar and defines the rules the registrar applies. |
| Trust Registry | The governed source that publishes verifier authorization, status, scope, and binding information. |

## 5. Recognition Object

The output of onboarding should be a scoped recognition record, registry listing, credential, certificate, or equivalent artifact that answers:

- Who is authorized?
- Who authorized them?
- Under which governance framework or policy?
- For which credential type?
- For which presentation request profile?
- For which purpose?
- For which requested attributes?
- In which jurisdiction or operating context?
- Through which reader, app, endpoint, certificate, key, or other request identifier?
- With which status?
- Until when?
- Where can the wallet check current status?

This profile does not require a specific technical format for the recognition object. It requires that the information be available, current enough for the risk, and machine-checkable by wallets or holder agents.

## 6. Onboarding Lifecycle

1. The RP or verifier identifies the applicable trust registry and onboarding process.
2. The applicant identifies the responsible legal entity, verifier role, readers or endpoints, and operating context.
3. The applicant states each presentation request it wants to make.
4. The applicant provides minimum evidence for each requested scope.
5. The registrar assesses the application against published rules.
6. The registrar approves, conditionally approves, rejects, or requests more information.
7. If approved, the verifier appears in the trust registry with active status and defined authorization scope.
8. The verifier maintains its information, readers, endpoints, keys, contacts, and compliance evidence.
9. The registrar reviews, renews, suspends, revokes, or expires the authorization as required.
10. Wallets check the registry or recognition source before releasing holder data.

## 7. Minimum Entry Evidence

Every verifier should provide:

- Legal identity of the accountable RP.
- Verifier name and operating role.
- Contact information for operational, privacy, and security issues.
- Proof of control over domains, apps, endpoints, certificates, keys, readers, or other request identifiers.
- Intended use cases.
- Requested credential types.
- Requested presentation profiles.
- Requested attributes.
- Purpose and legal or policy basis for each request.
- Data minimization rationale.
- Agreement to registry rules, audit rights, incident reporting, suspension, and revocation.
- Evidence of technical conformance to the request protocol or registry interface required by the ecosystem.

## 8. Risk Tiers

This profile assumes at least three presentation risk tiers.

| Tier | Example request | Possible evidence posture |
| --- | --- | --- |
| Low | Age-over-threshold, residency yes/no, credential-present yes/no | Basic legal identity, reader binding, purpose statement, data minimization rationale, contact path. |
| Medium | Name, address, document class, jurisdiction-specific entitlement | Low-tier evidence plus stronger legal/policy basis, privacy controls, security controls, renewal cadence. |
| High | Full document, document number, date of birth, sensitive attributes, high-impact decisions | Medium-tier evidence plus stronger assurance, incident process, auditability, explicit approval, shorter renewal, and stricter wallet behavior. |

The exact tiers and evidence thresholds should be set by the applicable governance authority. The important principle is proportionality: more sensitive requests require stronger evidence and tighter governance.

## 9. Registry Status Values

A trust registry should represent at least these verifier authorization states:

- Pending: application received but not approved.
- Active: approved and currently authorized.
- Conditional: approved with limits, remediation requirements, or expiry.
- Suspended: temporarily not authorized.
- Revoked: no longer authorized.
- Expired: authorization ended without renewal.

Wallets should treat status as decisioning data, not display-only metadata.

## 10. Wallet-Side Check

Before releasing holder data, the wallet should be able to check:

- Is the verifier listed in a recognized trust registry?
- Is the verifier currently active?
- Was the verifier approved by an authorized registrar?
- Is the registrar still authorized by the registry governance authority?
- Which policy, governance framework, or rule set was used for approval?
- Is the reader, endpoint, app, certificate, key, or request identifier bound to that verifier?
- Is the verifier authorized for this credential type?
- Is the verifier authorized for this presentation profile?
- Is the verifier authorized for this purpose?
- Is the verifier authorized for these requested attributes?
- Is the verifier authorized in this jurisdiction or context, where relevant?
- Is the authorization fresh enough for the request risk?
- What should the wallet do if any check fails?

Wallet-side checking is in scope for this profile. Whether wallets themselves must be approved, certified, authorized, or listed remains an open Track 3 scope question.

## 11. Wallet Failure Behavior

Recommended baseline behavior:

- Unknown verifier: refuse or warn according to ecosystem policy.
- Inactive, suspended, revoked, or expired verifier: do not release data.
- Reader or endpoint not bound to verifier: do not release data.
- Purpose not authorized: do not release data.
- Attribute request exceeds authorization: release only the authorized subset if technically supported, or refuse.
- Registry unavailable: follow ecosystem policy, such as refusal, cached status with freshness limits, or high-salience holder warning.

The exact behavior may vary by jurisdiction, credential type, risk tier, and law. The profile should require the behavior to be defined, not silently left to wallet vendors.

## 12. Presentation Authorization Model

Each verifier authorization should specify:

- Verifier legal name.
- Verifier identifier.
- Responsible RP, where different from the verifier.
- Registrar or approving authority.
- Registry governance authority or trust framework.
- Policy or rule version used for approval.
- Status.
- Authorized readers, apps, endpoints, keys, certificates, or other request identifiers.
- Credential types covered.
- Presentation request profiles.
- Authorized attributes for each profile.
- Disallowed attributes, where useful.
- Purpose for each profile.
- Jurisdiction or ecosystem scope.
- Effective date.
- Expiry or renewal date.
- Status, suspension, and revocation location.
- Appeal or review path.
- Policy, terms, audit, or conformance evidence location where appropriate.

## 13. Discovery

A wallet needs a discovery signal that tells it which trust registry or recognition source to check. Possible discovery inputs include:

- Credential or trust framework metadata.
- Credential type or trust framework identifier.
- Verifier presentation request.
- Registry identifier or trust framework reference in the verifier request.
- Well-known endpoint associated with the verifier.
- Wallet policy bundle or ecosystem configuration.
- Governance framework mapping credential types and jurisdictions to recognized registries.

This profile does not choose a single discovery mechanism. It requires the applicable ecosystem to define how the wallet determines which registry is authoritative for the verifier check.

## 14. Privacy and Non-Correlation Requirements

Verifier authorization checks should not create avoidable surveillance of holder transactions.

The profile should require:

- No phone-home to the issuing authority or government unless explicitly lawful, visible, and justified.
- Data minimization by default.
- Purpose limitation for each authorization.
- Attribute-scope enforcement.
- Reader and endpoint binding.
- Disclosure of material correlation risks in registry query, status, credential, wallet, or business-process design.
- Governance controls for logging, retention, audit, complaint, remedy, and sanctions where correlation is operationally necessary.

## 15. Minimum Registry Entry

A minimal registry entry should include:

```json
{
  "verifier_id": "string",
  "verifier_legal_name": "string",
  "responsible_rp": "string",
  "status": "active | conditional | suspended | revoked | expired",
  "registrar": "string",
  "registry_governance_authority": "string",
  "policy_version": "string",
  "authorized_readers": ["string"],
  "authorized_endpoints": ["string"],
  "authorized_credential_types": ["string"],
  "authorized_presentation_profiles": [
    {
      "profile_id": "string",
      "purpose": "string",
      "authorized_attributes": ["string"],
      "disallowed_attributes": ["string"],
      "jurisdiction_or_context": "string",
      "effective_date": "YYYY-MM-DD",
      "expiry_date": "YYYY-MM-DD"
    }
  ],
  "status_endpoint": "string",
  "evidence_uri": "string",
  "appeal_or_review_uri": "string"
}
```

This JSON shape is illustrative only. It is not a proposed wire format.

## 16. Open Questions

- Are wallets only required to perform verifier checks, or must wallets themselves be approved, certified, or listed?
- What minimum evidence is required for low-risk government-issued identity presentations?
- What additional evidence is required for high-risk presentation requests?
- Who may act as registrar?
- How is registrar authority granted, reviewed, suspended, or revoked?
- What decision records must the registrar retain?
- Which verifier status values must wallets understand?
- How fresh must registry status be?
- How should cached status behave when a registry is unavailable?
- What is the minimum discovery signal that tells a wallet which registry to check?
- Which technical track owns the machine-readable expression of verifier authorization?
- Which parts of this profile should be mandatory, recommended, optional, or left to jurisdictional profiles?
