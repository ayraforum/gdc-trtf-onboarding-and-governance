# Considerations for Later Phases

Status: Working notes for later-phase discussion

## Purpose

This file holds material that matters for the larger issuer onboarding and governance conversation, but is too broad for the initial v0.1 framework. The starting framework should remain focused on five questions: how an issuer gets in, how it stays in, how a verifier or wallet checks the issuer trust registry, how the verifier or wallet knows which registry to check, and which credential types or claims are authorized for that issuer.

## Broader Question

The larger Track 3 question is: how does a credential issuer get recognized, onboarded, and trusted, how can verifiers and wallets check that the issuer has been verified before relying on a credential or claim, and how does that issuer recognition travel across ecosystems?

The first document handles the local issuer-governance loop. This considerations file holds material for later expansion.

## Shared Vocabulary

The framework should align with vocabulary already emerging across GDC, SIDI, W3C, OpenID Foundation, ToIP, and other adjacent communities rather than inventing a parallel language.

- Issuer: The organization or authority that issues a credential or claim.
- Issuer trust registry: A governed source that lists recognized issuers and can express the authority behind the issuers it represents.
- Issuer authorization: A scoped statement that either grants authority or expresses authority from another competent source for a defined credential type, schema, claim set, assurance level, jurisdiction, or subject category.
- Holder: The person or organization controlling and presenting a credential through a wallet or other agent.
- Wallet: Holder-controlled software or agent that stores, receives, or presents credentials and may check issuer authority.
- Relying Party (RP): The legal or organizational entity that wants to rely on a credential presentation.
- Verifier: The role performed when a party requests, receives, and checks a credential presentation.
- Reader: The software, device, or component used to perform a verification interaction.
- Wallet-side issuer check: The wallet or holder agent's runtime check that an issuer is registered, currently recognized, bound to the presented credential metadata, and either authorized by the registry or represented by the registry as having authority for the credential or claim being presented.
- Wallet-side verifier check: A downstream check that the verifier is registered, currently recognized, bound to the presented reader or endpoint, and authorized for the requested purpose and data scope.
- Government-issued identity: The v0.1 scope boundary, including national ID, mobile driver's licenses, passports or passport-derived credentials, and equivalent public-sector identity credentials.
- Trust registry: A governed source that states which issuers, relying parties, verifiers, readers, registrars, or other in-scope actors are recognized, and for what.
- Registrar: The body authorized to assess and recognize issuers or other in-scope actors under a defined governance framework.
- Recognition: A verifiable statement that a party is recognized to perform a defined action under defined conditions.
- Conformance: Evidence that a party meets the requirements of a trust framework, ecosystem convention, technical profile, or policy.
- Scope: The specific credential type, schema, claim, purpose, presentation type, jurisdiction, and operating context for which recognition applies.
- Registry-of-registries: A coordination layer that lets one ecosystem's trust registry be discovered, evaluated, and honored by another.

## Trust Relationships

Issuer onboarding is not only an administrative admission process. It establishes trust before a credential is relied upon and gives participants a way to check that trust at runtime.

The broader framework is concerned first with issuer trust, and then with downstream verifier and wallet behavior:

- Reader trusts issuer: The verifier can determine that the credential came from an authoritative issuer for the credential type or claim being relied upon.
- Wallet trusts issuer: The wallet can determine whether a credential it stores or presents came from an issuer whose authority for that credential or claim is granted or expressed by a recognized registry.
- User trusts verifier: The holder knows the RP is legitimate, understands what is being requested, and can make an informed choice before sharing.
- Ecosystem trusts reader: The ecosystem can identify the RP or reader and determine whether it is authorized to request the relevant scope.

The Track 3 starting point is now: have we verified the issuer? Before a credential is relied upon, verifiers and wallets should be able to ask whether this issuer is registered, whether its authority evidence has been verified by an authorized registrar, whether it is still in good standing, and whether this exact credential or claim is within the issuer's recognized scope.

Verifier authorization remains important downstream: once issuer trust is established, wallets may still need to ask whether a verifier is authorized to request a particular presentation.

## Issuer Onboarding and Governance Considerations

The broader framework should describe who can recognize issuers and on what basis.

Issuer-governance topics include:

- Issuer registry governance authority: Who governs the issuer trust registry itself?
- Issuer registrar authority: Who is authorized to assess and recognize issuers?
- Issuer authority evidence: Is the registry itself authoritative for the issuer, or is it expressing authority from a statute, ministry, state or provincial agency, professional regulator, corporate register, sector body, or other competent source? A registry of banks run by a financial regulator may be authoritative; a registry of banks run by an industry group may only express authority granted elsewhere.
- Credential scope: Which credential types, schemas, claims, assurance levels, subject categories, and jurisdictions is the issuer authorized for?
- Issuer metadata and binding: Which keys, certificates, DIDs, endpoints, metadata, or other identifiers are bound to the issuer?
- Issuer lifecycle: How are issuance authority, status, key rotation, suspension, revocation, expiry, correction, and appeal handled?
- Conformance evidence: What technical, operational, security, privacy, and governance evidence is required before issuer listing?
- Verifier and wallet checks: What machine-readable evidence lets a verifier or wallet answer "what authority is granted or expressed for this issuer, credential, or claim?"
- Decision records: What record is kept of issuer approval, rejection, conditions, suspension, revocation, renewal, and appeal?
- Ecosystem accountability: How are incidents, misuse, audit findings, disputes, and governance changes handled?

The issuer registrar role may live in different places depending on the ecosystem. It could be a public authority, ecosystem operator, national trust-list operator, sector body, accredited assessment body, or federation. The framework does not need to choose one universal model, but it should define what any acceptable model must make visible and checkable.

## Recognition as a Scoped Governance Statement

Recognition should never be treated as a vague badge of legitimacy. It should be a scoped governance statement.

A useful issuer recognition statement answers:

- Who is recognized?
- Who recognized them?
- Under which governance framework?
- For which credential type or schema?
- For which claims or attributes?
- For which assurance level?
- For which subject population?
- For which jurisdiction, context, or ecosystem?
- For which issuer identifiers, keys, certificates, DIDs, endpoints, or metadata?
- For what time period?
- Under what technical and policy conditions?
- Where can the recognition and status be checked?
- What must the verifier or wallet do if the issuer is unknown, inactive, suspended, revoked, not bound to the credential metadata, or issuing beyond its recognized scope?
- How are suspension, revocation, correction, and appeal handled?

This matters because the same issuer may be authoritative for one credential or claim and not another. A registry that grants or expresses authority for an age-over-threshold claim is not automatically granting or expressing authority for a full identity document, passport number, driver's licence number, national ID number, or address claim. Same organization, different claim, different authority, different risk, and therefore a different recognition scope.

## Relationships to the Governance System

The trust registry has multiple users, and they relate to governance in different ways.

The issuer is the first applicant. It applies to be admitted, gets assessed against published conventions, and is recognized or rejected for specific credential and claim scopes. Governance acts on the issuer. Its defining relationship to this framework is that it had to apply for recognition before its credentials are relied upon.

The verifier or RP may be a later applicant in a downstream verifier-access model. It applies to be admitted, gets assessed against published conventions, and is recognized or rejected for specific presentation-request scopes.

The holder, through the wallet or agent, is the protected party. The holder does not apply to the governance system. The holder relies on it. Before presenting data, the wallet may need to ask both whether the issuer is authorized for the credential or claim and whether the verifier is authorized to request the presentation.

Issuer authorization, verifier authorization, and holder protection are different relationships. The v0.1 framework should start with issuer onboarding, while preserving the downstream verifier and wallet questions.

## Governance of the Registry Itself

Issuer governance depends on registry governance. An issuer can keep its information current and follow the rules, but the ecosystem still needs to know who created those rules, who applies them, and who holds the registrar accountable.

The governance model should distinguish at least four layers:

- Registry governance authority: The body or process responsible for the registry's rules, scope, accountability, and change control.
- Registry operator: The party operating the technical registry service.
- Registrar or assessor: The party that vets issuers and decides whether they enter, remain, are suspended, or are removed.
- Issuer: The party being assessed and listed.

Those layers may be performed by the same organization in a small ecosystem, but the roles should still be named separately. If the same organization governs, operates, and admits issuers, the conflict-of-interest and accountability model needs to be explicit.

Registry governance should answer:

- Who has authority to create or recognize the issuer trust registry?
- What is the registry's scope: credential types, schemas, jurisdictions, ecosystems, issuer categories, and claim types?
- Who can act as registrar or assessor?
- What qualifies a registrar to vet issuers?
- What requirements must the registrar apply consistently?
- What evidence must be collected and retained for each issuer decision?
- What decision records are public, private, or audit-only?
- What appeal path exists for a rejected, suspended, or revoked issuer?
- What complaint path exists for holders, wallets, verifiers, issuers, and ecosystem participants?
- How are conflicts of interest managed?
- How are registry rule changes approved, versioned, and published?
- How are registrar mistakes corrected?
- How can the registrar be audited, suspended, replaced, or removed?
- What happens to listed issuers if the registrar loses authority?
- What minimum information do wallets and verifiers need about registrar authority to trust registry entries?

The verifier or wallet does not need to understand every governance detail at runtime, but it does need a reliable signal that the issuer's authority was granted or expressed through an authorized registrar under a recognized governance framework. The ecosystem needs the deeper governance records so that this signal is not just another unsigned claim of trust.

## Can I Trust the Wallet?

The initial issuer framework asks how a verifier or wallet can check whether an issuer is registered and authorized. A later phase may need to ask whether the ecosystem can trust the wallet that is performing or mediating the check.

This is different from asking whether the holder has a wallet. It asks whether the wallet is capable of enforcing the governance model: checking the right issuer registry, interpreting issuer scope correctly, handling failed checks, minimizing disclosure, protecting holder data, and presenting credential or verifier information accurately to the holder.

The approved-wallet question should be treated as an open governance question, not an assumption. Ecosystems may land in different places:

- Open wallet model: Any wallet can participate, but verifiers and ecosystems rely on protocol conformance and market accountability.
- Conformant wallet model: Wallets must demonstrate technical conformance to a profile before participating.
- Approved wallet model: Wallets must be listed, certified, accredited, or otherwise approved by a governance authority.
- Tiered wallet model: Some presentations work with any conformant wallet, while higher-risk presentations require an approved wallet.
- Policy-bound wallet model: Wallets consume a policy bundle or trust framework configuration that tells them how to handle issuer checks, verifier checks, data minimization, and failure cases.

The core question is not only "is this wallet software legitimate?" It is "can this wallet be trusted to perform the trust decision the ecosystem is relying on?"

Wallet governance may need to answer:

- Who is allowed to determine that a wallet is conformant or approved?
- What wallet behaviors must be tested?
- Does the wallet correctly discover the applicable issuer trust registry?
- Does the wallet correctly validate issuer registration, registrar authority, status, metadata binding, credential type, schema, claim scope, and jurisdiction?
- Does the wallet correctly validate verifier registration, status, reader binding, purpose, credential type, and attribute scope when verifier checks are in scope?
- Does the wallet refuse or warn when an issuer or verifier is unknown, suspended, revoked, out of scope, or asking for too much?
- Does the wallet minimize disclosure when a credential supports more attributes than the verifier is authorized to receive?
- Does the wallet present issuer identity, verifier identity, purpose, requested attributes, and authorization status accurately to the holder?
- Does the wallet prevent silent escalation from age-only to full document or high-risk attribute requests?
- Does the wallet protect holder data and avoid creating new tracking channels?
- How are wallet conformance failures reported, remediated, suspended, or revoked?

## Privacy and Security Considerations

Government-issued identity raises the stakes. The framework should take a clear privacy and security position rather than treating those concerns as implementation details.

Privacy and security topics include:

- Issuer authority limitation: Issuers are recognized for specific credentials and claims and may not silently expand that scope.
- Data minimization: The default should be minimum necessary disclosure.
- Holder consent and transparency: The holder should understand who issued the credential, who is asking for it, what is being asked, why, and under whose authority.
- Wallet-side issuer verification: Wallets should be able to check that the issuer is registered, recognized, active, and authorized for the credential or claim before presenting holder data.
- Clear failure behavior: If the issuer cannot be verified, is suspended, is unknown, or is out of scope, the wallet or verifier should follow defined policy.
- No phone-home: Verifying a credential should not report the transaction back to the issuing authority or government unless an explicit, lawful, and visible exception applies.
- Anti-surveillance posture: Registry checks and status mechanisms must not become transaction tracking mechanisms.
- Issuer binding: Recognition should bind to issuer identifiers, keys, certificates, DIDs, endpoints, metadata, or other operational identifiers where appropriate.
- Suspension and revocation: Wallets, verifiers, and relying ecosystems need fresh enough status information to avoid relying on suspended or revoked issuer authority.
- Auditability: Governance decisions and operational events should be auditable without exposing holder transaction data.

## Recognition Across Ecosystem Boundaries

A later version should name the cross-ecosystem requirement without forcing a premature mechanism choice.

A relying ecosystem may need to discover whether another ecosystem's registry is authoritative for a given issuer, registrar, credential type, claim, or domain. That creates the registry-of-registries problem: how does one governed trust registry become discoverable and acceptable to another without collapsing everything into a single centralized authority?

Any technical mechanism should satisfy:

- Discoverability: Participants can find the relevant issuer trust registry or registrar for a domain.
- Authority: Participants can understand why that registry or registrar is authoritative.
- Scope: Participants can determine what the registry is authoritative for, and what it is not authoritative for.
- Integrity: Registry data and recognition statements are tamper-evident and verifiable.
- Freshness: Status, suspension, and revocation information can be checked.
- Privacy: Discovery and verification mechanisms do not create avoidable transaction surveillance.
- Governance transparency: Criteria, roles, delegations, and dispute processes are visible enough to support reliance.
- Interoperability: The mechanism can work across multiple standards, credential formats, and jurisdictional models.

Candidate mechanisms may include W3C recognized entities patterns, OpenID Federation, ToIP-style governance layers, trust lists, governance registries, issuer lists, or other registry-of-registries approaches. The initial framework should focus on requirements and defer mechanism selection to architecture and technical specifications work.

## Organization and Business Identity

Organization and business identity should be treated as a first-class consideration, not as a footnote to person identity. Many issuer-governance questions depend on knowing which legal entity is responsible for issuing a credential, which authority registered that entity, and whether the claimed business identity maps to an authoritative source.

This matters in at least three directions:

- Issuer identity: The issuer trust registry needs to know the legal entity or public authority responsible for an issuer, not just a domain name, app name, certificate, DID, or brand.
- Verifier identity: Downstream verifier registries may need to know the legal entity responsible for a verifier.
- Cross-ecosystem recognition: An issuer, verifier, registrar, or registry operator may need to be recognized across jurisdictions using business, corporate, supply-chain, or public-status registries.

The Legal Entity Identifier (LEI) should be considered as one important organization identity anchor. It may help identify legal entities in financial, regulatory, or cross-border contexts, but it should not be assumed to solve every organization identity problem by itself. The framework should consider how LEIs relate to national company numbers, tax identifiers, business registration numbers, beneficial ownership registers, trade registers, professional licensing registers, and other authoritative sources.

UN/CEFACT's Global Trust Registry work is especially relevant here. The Global Registry Information Directory (GRID) pattern is principally about registries and registrars for business, trade, legal personality, ownership, rights, and public status. It is not a central registry of all organizations. It is a directory of authoritative registrars and registers, designed so participants can determine which registrar is legitimate for a given business or supply-chain context.

For Track 3, the lesson is not that issuer onboarding should become a business-registry project. The lesson is that organization identity and registrar authority are inseparable. If an issuer claims to be a government agency, bank, airline, university, employer, government contractor, licensed professional body, or other organization, the issuer trust registry may need to know which authoritative business, public, or institutional registry supports that claim.

Later-phase questions include:

- What organization identity evidence is required before an issuer can enter the registry?
- When is a legal entity identifier enough, and when is a national or sector-specific business registry required?
- How should the framework distinguish legal entity identity from authorization to issue a specific credential or claim?
- How should LEIs, company registration numbers, tax identifiers, and sector-specific identifiers be represented or linked?
- How should beneficial ownership, delegated authority, brands, subsidiaries, branches, franchises, and operating names be handled?
- Can a trust registry rely on UN/CEFACT GRID-style registrar discovery to determine which business registry is authoritative?
- What business-registry evidence should wallets or verifiers see at runtime, and what should remain governance or audit evidence?
- How does organization identity interact with issuer metadata, keys, certificates, DIDs, endpoints, and domain binding?

## Downstream RP/Verifier Access

RP/verifier access should be treated as downstream of issuer trust rather than the main Track 3 deliverable.

Later phases may still need to answer:

- How does a verifier get recognized to request a credential presentation?
- What are the minimum governance requirements for that verifier to remain listed?
- How does a wallet check a verifier or reader registry?
- How does a wallet know which verifier or reader registry to check?
- Which presentation requests are authorized for that verifier?
- How does verifier authorization interact with issuer authorization?
- What should happen if the issuer is authorized but the verifier is not, or the verifier is authorized but the issuer is not?

## Future Work Beyond Government ID

Although v0.1 is scoped to issuer trust for government-issued identity, the same onboarding pattern will need to extend to other authoritative registries.

Future phases should address:

- Organizations and business registries: Company registers, beneficial ownership registers, and other authoritative organization identity sources.
- Education registries: Recognized institutions, programs, and credentials.
- Travel and border contexts: Passport-derived presentations and other public-sector identity use cases where issuer authorization, verifier authorization, purpose limitation, and cross-border reliance are central.
- Professional and occupational licensing: Registries of licensed, accredited, or otherwise authorized professionals.
- Healthcare and finance: High-assurance domains where authorization, purpose limitation, and liability are central.
- Cross-border and cross-ecosystem recognition: Registry-of-registries models that allow trust established in one domain to be discovered and evaluated in another.

The goal is not to solve all of this in Geneva. The goal is to make the first issuer-governance pattern clear enough that it can grow.

## Later-Phase Open Questions

- What is the exact boundary of government-issued identity for v0.1?
- Does v0.1 include only national ID and mobile driver's licenses, or also passports, passport-derived credentials, public-sector benefits credentials, immigration credentials, and other public-sector identity credentials?
- What does issuer onboarding concretely produce: a recognition credential, a registry listing, a conformance result, a certificate, a trust mark, or some combination?
- Where does the issuer registrar role live in the first version?
- Are domain-specific issuer registrars included in v0.1, or named as a later phase?
- What must a verifier or wallet check before relying on a credential: issuer registration, recognition status, registrar authority, metadata binding, credential type, schema, claims, assurance level, jurisdiction, or all of these?
- What should verifier or wallet behavior be when the issuer is not registered, cannot be verified, is suspended or revoked, or is issuing beyond its recognized scope?
- Can the ecosystem trust any wallet to perform these checks, or does the wallet itself need to be conformant, approved, certified, accredited, or listed?
- Are wallet requirements the same for low-risk and high-risk credentials?
- What organization or business identity evidence is required for issuer onboarding?
- How should LEIs, national business identifiers, and UN/CEFACT GRID-style authoritative registrar discovery relate to issuer recognition?
- How should downstream verifier presentation authorizations be expressed and enforced?
- How should suspension, revocation, and incident response be represented in a way wallets and verifiers can use?
- Which technical track owns the machine-readable expression of issuer authorization?
