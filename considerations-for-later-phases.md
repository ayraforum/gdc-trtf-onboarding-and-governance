# Considerations for Later Phases

Status: Working notes preserved from the broader Track 3 draft

## Preamble

These working notes have been consolidated from material shared within the GDC Trust Registry Task Force group, with deliberate AI assistance. They also draw on the Ayra knowledge base and on experience from Ayra's membership and related trust-registry work.

The ideas here are prompts for discussion, not decisions. They are intended to elicit more detail about what belongs in later phases and what must stay out of the initial framework. Before any of this material is published externally, it will need to be compressed, simplified, checked against the group's shared intent, and rewritten for a broader audience.

This file holds material that matters for the larger RP onboarding and governance conversation, but is too broad for the initial v0.1 framework. The starting framework should remain focused on five questions: how a verifier gets in, how it stays in, how a wallet checks the trust registry, how the wallet knows which registry to check, and which presentation requests are authorized for that verifier.

## Broader Question

The larger Track 3 question remains: how does a relying party that wants to consume government-issued identity get recognized, onboarded, and trusted, how can wallets check that the verifier has been verified before a holder shares data, and how does that recognition travel across ecosystems?

The first document handles the local operating loop. This considerations file holds material for later expansion.

## Shared Vocabulary

The framework should align with vocabulary already emerging across GDC, SIDI, W3C, OpenID Foundation, ToIP, and other adjacent communities rather than inventing a parallel language.

- Relying Party (RP): The legal or organizational entity that wants to rely on a credential presentation.
- Verifier: The role performed when a party requests, receives, and checks a credential presentation.
- Reader: The software, device, or component used to perform a verification interaction.
- Registered relying party verifier: An RP, verifier, or reader that appears in a recognized trust registry with an active, scoped authorization to request a defined presentation.
- Holder: The person or organization presenting a credential through a wallet or other agent.
- Wallet-side verifier check: The wallet or holder agent's runtime check that the verifier is registered, currently recognized, bound to the presented reader or endpoint, and authorized for the requested purpose and data scope.
- Government-issued identity: The v0.1 scope boundary, including national ID, mobile driver's licenses, passports or passport-derived credentials, and equivalent public-sector identity credentials.
- Trust registry: A governed source that states which relying parties, verifiers, readers, registrars, or other in-scope actors are recognized, and for what.
- Registrar: The body authorized to assess and recognize RPs under a defined governance framework.
- Recognition: A verifiable statement that a party is recognized to perform a defined action under defined conditions.
- Conformance: Evidence that a party meets the requirements of a trust framework, ecosystem convention, technical profile, or policy.
- Scope: The specific data, purpose, presentation type, credential type, jurisdiction, and operating context for which recognition applies.
- Registry-of-registries: A coordination layer that lets one ecosystem's trust registry be discovered, evaluated, and honored by another.

## Trust Relationships

RP onboarding is not only an administrative admission process. It establishes trust before a transaction happens and gives participants a way to check that trust at runtime.

The broader framework is concerned with two trust relationships:

- User trusts verifier: The holder knows the RP is legitimate, understands what is being requested, and can make an informed choice before sharing.
- Ecosystem trusts reader: The ecosystem can identify the RP or reader and determine whether it is authorized to request the relevant scope.

The wallet is the point where these relationships meet. In shorthand, the wallet check asks: have we verified the verifier? Before releasing holder data, the wallet should be able to ask whether this verifier is registered, whether it has been verified by an authorized registrar, whether it is still in good standing, and whether this exact request is within the verifier's recognized scope.

## Recognition as a Scoped Governance Statement

Recognition should never be treated as a vague badge of legitimacy. It should be a scoped governance statement.

A useful recognition statement answers:

- Who is recognized?
- Who recognized them?
- Under which governance framework?
- For which credential type?
- For which purpose?
- For which data attributes or presentation type?
- For which jurisdiction, context, or ecosystem?
- For which readers, systems, or endpoints?
- For what time period?
- Under what technical and policy conditions?
- Where can the recognition be checked?
- What must the wallet do if the verifier is unknown, inactive, suspended, revoked, not bound to the presented reader, or asking beyond its recognized scope?
- How are suspension, revocation, and appeal handled?

This matters because the same credential can support very different presentations. Reading a driver's license for age-only verification is not the same authorization as reading the full driver's license. Same credential, different purpose, different data, different risk, and therefore a different recognition scope.

## Two Relationships to the Governance System

The trust registry has at least two different users, and they relate to governance in different ways.

The verifier or RP is the applicant. It applies to be admitted, gets assessed against published conventions, and is recognized or rejected for specific scopes. Governance acts on the RP. Its defining relationship to this framework is that it had to apply for recognition before requesting government-issued credential presentations.

The holder, through the wallet or agent, is the protected party. The holder does not apply to the governance system. The holder relies on it. Before presenting data, the wallet should be able to ask whether this verifier is registered, whether the verifier has been verified by an authorized registrar, whether it is still active, whether the presented reader or endpoint belongs to the recognized verifier, whether it is recognized for the requested purpose, and whether the requested data exceeds the recognized scope.

Both relationships must be first-class. Admitting an RP is one process. Protecting the holder's right to check the verifier before presenting is another. A complete onboarding and governance framework must serve both.

## Governance Model Considerations

The broader framework should describe who can recognize RPs and on what basis.

Governance topics include:

- Registry governance authority: Who governs the trust registry itself?
- Registrar authority: Who is authorized to assess and recognize RPs?
- Delegation model: Can an ecosystem operator delegate assessment to accredited or domain-specific registrars?
- Requirements publication: Where are eligibility rules, policies, technical profiles, privacy requirements, and assessment criteria published?
- Neutrality: Are recognition criteria transparent, evidence-based, and applied consistently?
- Purpose limitation: How is the RP's requested purpose evaluated and limited?
- Scope control: How are authorized attributes, presentations, credential types, jurisdictions, and readers represented?
- Conformance evidence: What technical, operational, security, and privacy evidence is required?
- Wallet-check requirements: What machine-readable evidence does the wallet need to answer "is this a registered relying party verifier?" and "has this verifier been verified for this request?"
- Decision records: What record is kept of approval, rejection, conditions, suspension, revocation, renewal, and appeal?
- Holder protection: What does the wallet or holder-facing interface need to know before a presentation?
- Ecosystem accountability: How are incidents, misuse, audit findings, disputes, and governance changes handled?

The registrar role may live in different places depending on the ecosystem. It could be an ecosystem operator, a public authority, an accredited assessment body, a domain-specific registrar, or a federated set of recognized registrars. The framework does not need to choose one universal model, but it should define what any acceptable model must make visible and checkable.

## Governance of the Registry Itself

Verifier governance depends on registry governance. A verifier can keep its information current and follow the rules, but the ecosystem still needs to know who created those rules, who applies them, and who holds the registrar accountable.

The governance model should distinguish at least four layers:

- Registry governance authority: The body or process responsible for the registry's rules, scope, accountability, and change control.
- Registry operator: The party operating the technical registry service.
- Registrar or assessor: The party that vets verifiers and decides whether they enter, remain, are suspended, or are removed.
- Verifier: The party being assessed and listed.

Those layers may be performed by the same organization in a small ecosystem, but the roles should still be named separately. If the same organization governs, operates, and admits verifiers, the conflict-of-interest and accountability model needs to be explicit.

Registry governance should answer:

- Who has authority to create or recognize the trust registry?
- What is the registry's scope: credential types, jurisdictions, ecosystems, verifier categories, and presentation types?
- Who can act as registrar or assessor?
- What qualifies a registrar to vet verifiers?
- What requirements must the registrar apply consistently?
- What evidence must be collected and retained for each verifier decision?
- What decision records are public, private, or audit-only?
- What appeal path exists for a rejected, suspended, or revoked verifier?
- What complaint path exists for holders, wallets, verifiers, and ecosystem participants?
- How are conflicts of interest managed?
- How are registry rule changes approved, versioned, and published?
- How are registrar mistakes corrected?
- How can the registrar be audited, suspended, replaced, or removed?
- What happens to listed verifiers if the registrar loses authority?
- What minimum information do wallets need about registrar authority to trust registry entries?

The wallet does not need to understand every governance detail at runtime, but it does need a reliable signal that the verifier was admitted by an authorized registrar under a recognized governance framework. The ecosystem needs the deeper governance records so that this signal is not just another unsigned claim of trust.

## Can I Trust the Wallet?

The initial v0.1 framework asks how a wallet can check whether a verifier is registered and authorized. An early scope decision is whether Track 3 is only about relying-party/verifier authorization, or whether wallet authorization or wallet approval also belongs in the track.

This is different from asking whether the holder has a wallet. It asks whether the wallet is capable of enforcing the governance model: checking the right registry, interpreting verifier scope correctly, refusing or warning on failed checks, minimizing disclosure, protecting holder data, and presenting the verifier request accurately to the holder.

The approved-wallet question should be treated as an open governance question, not an assumption. Ecosystems may land in different places:

- Open wallet model: Any wallet can participate, but verifiers and ecosystems rely on protocol conformance and market accountability.
- Conformant wallet model: Wallets must demonstrate technical conformance to a profile before participating.
- Approved wallet model: Wallets must be listed, certified, accredited, or otherwise approved by a governance authority.
- Tiered wallet model: Some presentations work with any conformant wallet, while higher-risk presentations require an approved wallet.
- Policy-bound wallet model: Wallets consume a policy bundle or trust framework configuration that tells them how to handle verifier checks, data minimization, and failure cases.

The core question is not only "is this wallet software legitimate?" It is "can this wallet be trusted to perform the trust decision the ecosystem is relying on?"

Wallet governance may need to answer:

- Who is allowed to determine that a wallet is conformant or approved?
- What wallet behaviors must be tested?
- Does the wallet correctly discover the applicable trust registry?
- Does the wallet correctly validate verifier registration, registrar authority, status, reader binding, purpose, credential type, and attribute scope?
- Does the wallet refuse or warn when a verifier is unknown, suspended, revoked, out of scope, or asking for too much?
- Does the wallet minimize disclosure when a credential supports more attributes than the verifier is authorized to receive?
- Does the wallet present verifier identity, purpose, requested attributes, and authorization status accurately to the holder?
- Does the wallet prevent silent escalation from age-only to full document or high-risk attribute requests?
- Does the wallet protect holder data and avoid creating new tracking channels?
- How are wallet conformance failures reported, remediated, suspended, or revoked?
- What happens if an otherwise valid verifier request comes from or interacts with a non-conformant wallet?

This topic is adjacent to Track 3 because the verifier onboarding framework depends on wallet-side enforcement. If wallets cannot be trusted to check and enforce verifier scope, the registry may still exist, but its protections will not reliably reach the holder.

## Privacy and Security Considerations

Government-issued identity raises the stakes. The framework should take a clear privacy and security position rather than treating those concerns as implementation details.

Privacy and security topics include:

- Purpose limitation: RPs are recognized for specific purposes and may not silently expand those purposes.
- Scope enforcement: Recognition should be tied to specific attributes or presentation types, not only to organization identity.
- Data minimization: The default should be minimum necessary disclosure.
- Holder consent and transparency: The holder should understand who is asking, what is being asked, why, and under whose authority.
- Wallet-side verifier verification: Wallets should check that the verifier is registered, recognized, active, and authorized for the requested scope before releasing holder data.
- Clear failure behavior: If the verifier cannot be verified, is suspended, is unknown, or asks beyond its recognized scope, the wallet should refuse the request or present a clear, high-salience warning according to the governing policy.
- No phone-home: Verifying a credential should not report the transaction back to the issuing authority or government unless an explicit, lawful, and visible exception applies.
- Anti-surveillance posture: Recognition mechanisms must not become transaction tracking mechanisms.
- RP authentication: The holder or wallet should be able to confirm that the reader belongs to the recognized RP.
- Reader binding: Recognition should be able to bind to systems, readers, certificates, endpoints, keys, or other operational identifiers where appropriate.
- Suspension and revocation: Wallets, verifiers, and relying ecosystems need fresh enough status information to avoid relying on suspended or revoked recognition.
- Auditability: Governance decisions and operational events should be auditable without exposing holder transaction data.

## Recognition Across Ecosystem Boundaries

A later version should name the cross-ecosystem requirement without forcing a premature mechanism choice.

A relying ecosystem may need to discover whether another ecosystem's registry is authoritative for a given RP, verifier, registrar, credential type, or domain. That creates the registry-of-registries problem: how does one governed trust registry become discoverable and acceptable to another without collapsing everything into a single centralized authority?

Any technical mechanism should satisfy:

- Discoverability: Participants can find the relevant trust registry or registrar for a domain.
- Authority: Participants can understand why that registry or registrar is authoritative.
- Scope: Participants can determine what the registry is authoritative for, and what it is not authoritative for.
- Integrity: Registry data and recognition statements are tamper-evident and verifiable.
- Freshness: Status, suspension, and revocation information can be checked.
- Privacy: Discovery and verification mechanisms do not create avoidable transaction surveillance.
- Governance transparency: Criteria, roles, delegations, and dispute processes are visible enough to support reliance.
- Interoperability: The mechanism can work across multiple standards, credential formats, and jurisdictional models.

Candidate mechanisms may include W3C recognized entities patterns, OpenID Federation, ToIP-style governance layers, trust lists, governance registries, or other registry-of-registries approaches. The initial framework should focus on requirements and defer mechanism selection to architecture and technical specifications work.

## Organization and Business Identity

Organization and business identity should be treated as a first-class consideration, not as a footnote to person identity. Many verifier-governance questions depend on knowing which legal entity is responsible for a request, which authority registered that entity, and whether the claimed business identity maps to an authoritative source.

This matters in two directions:

- Verifier identity: The trust registry needs to know the legal entity responsible for a verifier, not just a domain name, app name, certificate, or brand.
- Cross-ecosystem recognition: A verifier, registrar, or registry operator may need to be recognized across jurisdictions using business, corporate, supply-chain, or public-status registries.

The Legal Entity Identifier (LEI) should be considered as one important organization identity anchor. It may help identify legal entities in financial, regulatory, or cross-border contexts, but it should not be assumed to solve every organization identity problem by itself. The framework should consider how LEIs relate to national company numbers, tax identifiers, business registration numbers, beneficial ownership registers, trade registers, professional licensing registers, and other authoritative sources.

UN/CEFACT's Global Trust Registry work is especially relevant here. The Global Registry Information Directory (GRID) pattern is principally about registries and registrars for business, trade, legal personality, ownership, rights, and public status. It is not a central registry of all organizations. It is a directory of authoritative registrars and registers, designed so participants can determine which registrar is legitimate for a given business or supply-chain context.

For Track 3, the lesson is not that verifier onboarding should become a business-registry project. The lesson is that organization identity and registrar authority are inseparable. If a verifier claims to be a bank, airline, university, employer, government contractor, licensed professional body, or other organization, the trust registry may need to know which authoritative business or institutional registry supports that claim.

Later-phase questions include:

- What organization identity evidence is required before a verifier can enter the registry?
- When is a legal entity identifier enough, and when is a national or sector-specific business registry required?
- How should the framework distinguish legal entity identity from authorization to perform a specific verifier role?
- How should LEIs, company registration numbers, tax identifiers, and sector-specific identifiers be represented or linked?
- How should beneficial ownership, delegated authority, brands, subsidiaries, branches, franchises, and operating names be handled?
- Can a trust registry rely on UN/CEFACT GRID-style registrar discovery to determine which business registry is authoritative?
- What business-registry evidence should wallets or verifiers see at runtime, and what should remain governance or audit evidence?
- How does organization identity interact with reader, endpoint, key, certificate, and domain binding?

## Future Work Beyond Government ID

Although v0.1 is scoped to government-issued identity, the same onboarding pattern will need to extend to other authoritative registries.

Future phases should address:

- **Organizations and business registries:** Company registers, beneficial ownership registers, and other authoritative organization identity sources.
- **Education registries:** Recognized institutions, programs, and credentials.
- **Travel and border contexts:** Passport-derived presentations and other public-sector identity use cases where verifier authorization, purpose limitation, and cross-border reliance are central.
- **Professional and occupational licensing:** Registries of licensed, accredited, or otherwise authorized professionals.
- **Healthcare and finance:** High-assurance domains where authorization, purpose limitation, and liability are central.
- **Cross-border and cross-ecosystem recognition:** Registry-of-registries models that allow trust established in one domain to be discovered and evaluated in another.

The goal is not to solve all of this in Geneva. The goal is to make the first pattern clear enough that it can grow.

## Later-Phase Open Questions

- What is the exact boundary of government-issued identity for v0.1?
- Does v0.1 include only national ID and mobile driver's licenses, or also passports, passport-derived credentials, public-sector benefits credentials, immigration credentials, and other public-sector identity credentials?
- What does onboarded concretely produce: a recognition credential, a registry listing, a conformance result, a certificate, a trust mark, or some combination?
- Where does the registrar role live in the first version?
- Are domain-specific registrars included in v0.1, or named as Phase 2?
- What must a wallet check before releasing holder data: registration, recognition status, registrar authority, reader binding, requested purpose, data scope, credential type, jurisdiction, or all of these?
- What should wallet behavior be when the verifier is not registered, cannot be verified, is suspended or revoked, or asks beyond its recognized scope?
- Can the ecosystem trust any wallet to perform these checks, or does the wallet itself need to be conformant, approved, certified, accredited, or listed?
- Are wallet requirements the same for low-risk and high-risk presentation requests?
- What organization or business identity evidence is required for verifier onboarding?
- How should LEIs, national business identifiers, and UN/CEFACT GRID-style authoritative registrar discovery relate to verifier recognition?
- How are presentation-level authorizations expressed and enforced, such as age-only versus full driver's-license reads?
- How should suspension, revocation, and incident response be represented in a way wallets and verifiers can use?
- Which technical track owns the machine-readable expression of recognition?
