# Discovery, And How Global Registries Get Established

Darrell O'Donnell — Track 1 co-leads working note, 2026-10-14, for the monthly meeting

Two topics have moved to the front since Geneva in September: **discovery**, and **how one or several global registries of registries actually get established**. Both are live inside Ayra as well, so take what is useful and discard the rest — but the findings below are offered because they are inconvenient as often as they are convenient, and the group should have them either way.

Two versions. Use the **short version** to speak from. The **full version** is for the meeting doc.

## Short version (to speak from)

**One — discovery, authorization and recognition are three questions, and TRQP already answers two of them.** Authorization asks *is this entity permitted, under that authority's rules, to do this thing?* Recognition asks *does this ecosystem treat that one as authoritative, and for what?* The Trust Registry Query Protocol (TRQP) carries both, and that is further along than it often gets credit for. **Discovery is the one it does not answer** — *can I find the authority in the first place?* You cannot query an authority you cannot locate, which is why discoverability is the right next piece of work. One distinction worth keeping: TRQP transports a recognition answer; a governance decision about what recognition means across a boundary is what creates it.

**Two — design discovery so that nobody has to watch it happen.** If discovery means calling a central service, that service sees who is asking about whom, continuously. That is a surveillance surface we would be designing in, and it is also a single point of failure and a metering chokepoint. Publish signed, time-stamped records that anyone can mirror and serve, and discovery becomes a lookup against a local copy. The privacy property and the resilience property come from the same design decision.

**Three — on global registries, the expensive part is the promise, not the software.** The index is small and cheap. What costs money is carrying an obligation other people rely on: assurance, key management, insurance priced on reliance, and succession — a second organisation able to take the whole thing on. We modelled this properly and the result surprised us — the costly step is *publishing* authentically, not offering a service level on top. The service level is nearly free once you are publishing well. That is inconvenient for anyone hoping a premium tier pays for the base.

**Four — so plan for several, not one.** Naming a single global root without funding it fails three ways: nobody does it, or a volunteer does it thinly and reliance accumulates on something fragile, or a commercial party does it and the neutrality we convened for is gone. What has to be singular is the *level* — recognition semantics and conformance criteria. Serving the data can and should be plural.

**A caveat worth saying out loud:** this comes out of Ayra's situation, and Ayra's situation is not necessarily yours. We are a membership nonprofit coordinating across competitors, so neutrality and a decentralised default are not choices, they are constraints. Where authority is derived differently — a state, a treaty body, a regulator — a single authoritative root may be right rather than fragile, and our cost shape may not be your cost shape. Take the method, test it against your own situation.

**The ask:** keep discovery, authorization and recognition as three questions; prefer published, mirrorable records over mandatory live calls; make every "shall be available" name its obligated party; and let a participant say honestly what is not funded without being non-conformant.

## Full version (meeting doc)

### 1. Discovery, authorization and recognition are three questions

**Discovery:** given a credential, an assertion, or a counterparty, can I find the authority or registry that can speak to it?

**Authorization:** having found it, is this entity permitted under that authority's rules to do this particular thing — issue this credential, act in this role, at this scope?

**Recognition:** should I honour that authority at all, when it sits on the other side of an ecosystem boundary from me?

The second and third questions already have a working protocol answer. The Trust Registry Query Protocol (TRQP) carries both authorisation queries and recognition queries, and it is worth stating plainly that the task force has that in hand, because it changes what the remaining work is.

**Discovery is the question TRQP does not answer.** It sits upstream of the protocol: you cannot query an authority you cannot locate, and nothing in TRQP tells you where to look. That is the gap, and it is why discoverability is the right next piece of work.

One distinction is worth holding onto on the recognition side. TRQP *transports* a recognition answer — it can report that this ecosystem treats that one as authoritative, for this scope. What *creates* that answer is a governance decision about what recognition means across an ecosystem boundary, and about what conformant and authoritative mean. The protocol carries the answer; the governance populates it. So the work remaining divides cleanly in two: discovery, and the governance that gives recognition its content.

These three are routinely treated as one step, and the merge is not harmless. Whatever component performs discovery starts to accrete judgement — it becomes the thing that decides which authorities are findable, and therefore which are usable. That is an enormous amount of power to acquire by accident, and it is acquired by accident, through convenience rather than intent. The same happens in the other direction when an authorisation answer is read as though it settled recognition, which the protocol does not do on its own.

Keeping them apart has a practical consequence for the framework. A discovery result should be a *pointer*, not a verdict: here is the authority, here is its scope, here is the governance framework behind it. TRQP then answers the authorisation and recognition questions against that authority. What the framework has to supply is the governance behind the recognition answer — a stated level, and agreed meanings for conformant, recognised and authoritative. This is the same split we discussed for assurance levels: the registry carries the pointer, the authority owns the meaning.

### 2. Discovery should not require anyone to watch it

This is the part worth the most discussion tonight.

If discovery is designed as a live query to a central service, that service necessarily observes the pattern of who is asking about whom, and how often. Even with no logging policy and good intentions, the capability exists, and capability tends to get used — by the operator, by whoever acquires the operator, or by whoever compels it.

It is also operationally fragile. A central discovery service is a single point of failure for every transaction that depends on it, and it is a natural metering point, which invites a commercial model built on counting other people's lookups.

The alternative is well understood and unglamorous: publish the record, sign it, time-stamp it, and let anyone mirror and serve it. Discovery then happens against a copy close to the relying party. Nobody has to be trusted not to look, because nobody is positioned to look. Freshness becomes a stated property — "current as of this time" — rather than an availability promise.

The design choice that buys privacy is the same one that buys resilience. That is rare and worth taking.

A caution against over-correcting: this does not mean live services are forbidden. It means the framework should not *require* one, and conformance should not depend on calling a particular endpoint.

### 3. What it actually costs to establish a global registry

A registry of registries is a small, slow-changing index. The software is not the problem and never was.

The cost is in carrying a promise other people rely on. Formal security assurance. Key management and custody, which is where the hardest risk sits. Insurance priced on reliance exposure rather than headcount. Succession: a second organisation contractually able, and funded, to take the service on, so the obligation outlives whoever is carrying it today. Legal maintenance. These are permanent budget lines, and every "shall be available" drafted into a framework is somebody's.

Ayra has now modelled this in detail, and the shape of the answer was not what we expected. We costed three levels: a governed record with no availability claim; publishing signed snapshots that others serve; and operating a live service under a commitment. **The expensive step is the second one — moving from a governed record to authentic, signed, current publication.** Adding a service level on top of that is comparatively cheap.

That cuts against the intuition that a premium service tier can subsidise the public base. It mostly cannot, because the base is where the money goes. Anyone planning to fund a global registry from enterprise service revenue should test that assumption early.

We are sharing the shape rather than our figures, because the figures are ours and the shape is what transfers.

### 4. Plan for several registries, not one

The previous note set out why naming a single global root without funding it fails three ways — nobody does it, a volunteer does it thinly and reliance builds on something fragile, or a commercial party does it and neutrality is lost. That argument stands, and the costing above sharpens it: the funded obligation is larger than most volunteers can carry and larger than most conveners expect.

The resolution is to be precise about what must be singular. **The level must be singular** — what "conformant", "recognised" and "authoritative" mean across ecosystem boundaries, and the criteria behind them. That is cheap to maintain, carries no availability obligation, and is exactly what a task force can produce.

**Serving the data should be plural.** Multiple registries, mirrors, caches, regional operators, commercial providers — all publishing and serving against the same level. Plurality is not a compromise forced by lack of funding; it is the more robust design, and it removes the question of who gets to be the root.

### 5. Where Ayra sits, stated plainly

Ayra's mission runs directly through this, so treat everything above as interested testimony and weigh it accordingly.

Ayra convenes and stewards cross-ecosystem governance — the definitions of conformant, recognised and authoritative — and intends to operate a recognition-scoped registry of registries. We have not funded that service, we are not asking this group to designate anyone, and we are not proposing Ayra as the global root. We think "the global root" is the wrong shape for the framework regardless of who would hold it.

What we can offer the task force is the work itself: the cost structure, the nine components we broke the problem into, and what we learned about which obligations are affordable and which are not. If that is useful as an input, it is available.

### 6. What may not transfer from our context

Everything above comes out of Ayra's situation. Four places where it may not carry to this group.

**Authority is derived differently in different rooms.** Ayra is a membership nonprofit coordinating across competitors, so structural neutrality and a decentralised default are not choices, they are constraints. A state, a treaty body or a regulator derives authority from a different source. Where a participant legitimately can claim authority over the others, a single authoritative root may be the right answer rather than a fragile one. The plurality argument in section 4 is strongest precisely where nobody can make that claim — which is Ayra's room, and not every room.

**Regulated contexts may require the live endpoint we argue against.** The privacy case for publish-and-mirror assumes nobody is obliged to produce a verifiable record of who asked what. Where a regulator requires exactly that, the calculus inverts and a logged authoritative service may be the compliant design. Read our argument narrowly: conformance should not *depend* on calling a live endpoint. It is not a claim that live endpoints are wrong.

**Our cost shape is conditioned on our assurance path.** The finding that publishing is the expensive step comes from a model carrying commercial certification, market-rate staff, commercially priced insurance and an outsourced operations provider. A body with existing accreditation machinery, seconded staff or state backing has a different curve, and may well find the service level is the expensive part rather than the base. Take the method, test the shape against your own cost drivers, and do not inherit our conclusion.

**Our funding problem may not be yours.** Ayra needs a recurring instrument because membership dues cannot carry a standing obligation. An appropriated or treaty-funded body does not have that problem in the same form — though it has the political equivalent, which is that an appropriation can lapse while the reliance does not.

What we would defend as general, in any context: the three questions are distinct and should stay distinct; every continuing obligation needs a named party who carries it; and honesty about what is unfunded should never make a participant non-conformant.

### The ask for Track 1

1. **Separate discovery, authorization and recognition** in the framework text. TRQP answers authorization and recognition; discovery is the open one, and discovery results should be pointers, not verdicts. Recognition answers still need a governance source that defines what recognition means across a boundary.
2. **Require published, mirrorable, signed records** with a stated freshness property, and do not make conformance *depend* on calling a live endpoint. Conditional, see section 6: where a regulator requires an auditable query record, a live authoritative service may be the compliant design and the framework should permit it.
3. **Make every "shall be available" name its obligated party**, and separate non-binding operating targets from contractual commitments.
4. **Design for interoperable plurality** rather than a single root, and keep singular only what must be — the level. Conditional, see section 6: where authority derives from a state or a treaty rather than from agreement among competitors, a single authoritative root may be appropriate.
5. **Let a participant declare honestly what is not funded** without being non-conformant. A framework that makes honesty non-conformant will be answered with optimism.

### Related notes

- [The Unfunded Obligation: A Design Risk for Track 1](track1-unfunded-obligation-risk.md)
- [Two Ideas for Track 1: Focused Ecosystems and Assurance Levels](track1-share-focus-and-assurance.md)
