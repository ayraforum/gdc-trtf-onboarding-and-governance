# The Unfunded Obligation: A Design Risk for Track 1

Darrell O'Donnell — Track 1 co-leads working note, 2026-10-13

Track 1 is asking the right question: where is the global registry of registries, and how is it funded? This note is about the trap inside that question.

Two versions below. Use the **short version** for a verbal drop or a single chat message. Use the **full version** for screen-share or pasting into the meeting doc.

## Short version (verbal / one chat message)

A governance framework can create an obligation without creating the means to meet it. That is the biggest risk in front of us, and it is easy to write by accident.

**The expensive part of a registry is the promise, not the software.** The index is small, slow-changing and cheap to run. What costs money is carrying a promise other people rely on: formal assurance, insurance priced on reliance exposure, a funded successor operator, legal maintenance, and above all key management. Every "shall be available" we draft is somebody's permanent budget line. If we don't name who, we've written an unfunded obligation.

**Naming a single global root without funding it fails three ways.** Nobody does it. Or a volunteer does it thinly and reliance builds on something fragile. Or a commercial party does it and the neutrality the framework existed for is gone. All three are worse than designing for plurality from the start.

**So separate the level from the service.** What has to be singular is the *level* — recognition semantics, conformance criteria, and what conformant, recognised and authoritative mean. That is cheap, carries no availability obligation, and is exactly what this task force is uniquely able to produce. *Serving* the data can be plural, distributed and cached, and it should be.

**The ask:** make every "shall" name its obligated party, separate non-binding operating targets from contractual commitments, design for interoperable plurality rather than a single root, and let a participant declare honestly what is not funded without being non-conformant.

## Full version (screen-share / meeting doc)

### 1. Frameworks create obligations silently

Every requirement of the form "shall be available", "shall respond within", "shall be authoritative", "shall be continuously maintained" is an operational commitment that somebody funds forever. Drafted in a governance framework, those words look like quality. In an operating budget they look like staff, on-call rotations, insurance premiums and audit fees.

The failure is not that frameworks are too demanding. It is that they routinely assign obligations without naming the obligated party or asking what the obligation costs. The framework ships, everyone agrees it is sound, and then nobody can implement the parts that assume a funded operator.

**Discipline to adopt: for every obligation we write, name who holds it.** If the answer is "the global registry of registries" and no such funded entity exists, we have written an unfunded obligation and should either fund it, scope it down, or distribute it.

### 2. The expensive part is the promise, not the software

This is the part most easily missed by people who have not costed it.

A registry of registries is a small dataset. Thousands of records, not billions. It changes slowly. It federates to authoritative sources rather than mastering their data. The software and hosting to serve it are genuinely cheap.

What is expensive is **reliance**. Once organizations depend on an answer in a business decision, the operator needs: formal security assurance that participants will actually accept; insurance priced on reliance exposure rather than headcount; a funded successor operator, so the obligation does not end with the organization carrying it; participation agreements and liability review; and continuous governance of admission, correction and withdrawal.

In every costing exercise I have run, that reliance layer dominates. The database is a rounding error.

This matters for drafting because **the cheapest version of the framework is not the one with fewer features. It is the one with fewer promises.** We can require a great deal about governance, provenance, scope and recognition semantics at almost no operating cost. The moment we require availability, we have priced in everything above.

### 3. The single-global-root trap

The instinct behind "where is the global registry of registries?" is reasonable: people want one place to look. But designating a single global root, in a framework, without funding attached, fails in three predictable ways.

| Failure mode | What happens |
|---|---|
| Nobody steps up | The framework names a component that does not exist. Implementers route around it, and the gap the task force identified stays open |
| A volunteer steps up thinly | Someone operates it on goodwill or a grant. Reliance accumulates on infrastructure with no funded backup, no assurance and no reserve. The failure arrives later and larger, while participants are depending on it |
| A commercial party steps up | It gets operated well and the operator eventually competes with its own participants. The structural neutrality that justified the framework is gone |

There is a fourth and worse variant: an organization accepts the designation *because* it is reputationally attractive, and discovers it has taken on a permanent reliance-bearing obligation it cannot fund. Designation without funding is not a win for whoever receives it. It is a liability transfer dressed as an honour.

**If the task force wants a designated global operation, the funding has to arrive with the designation.** That is a legitimate thing to recommend — but it is a recommendation about money and mandate, and it should be written as one rather than smuggled in as an architectural assumption.

### 4. Separate the level from the service

The resolution is to notice that two different things are being asked for under one name.

| | The level | The service |
|---|---|---|
| What it is | Recognition semantics, conformance criteria, and the agreed meaning of conformant, recognised and authoritative | Query surfaces that organizations depend on in real time |
| Must it be singular? | **Yes.** Shared meaning is the entire point. Two incompatible definitions of "recognised" defeat the exercise | **No.** Many operators can serve the same governed data |
| Who can produce it | A neutral, multi-stakeholder body. This task force is well positioned | Operators with infrastructure capability and a commercial or institutional reason |
| Operating obligation | None. Definitions do not have uptime | Full reliance cost base |
| Cost | Modest, and mostly convening and drafting | Substantial and permanent |

Write the level. Let the service be plural. This also matches how the field is actually developing: multiple registries of registries and trust networks, able to coexist and interoperate, rather than one root everyone is obliged to query.

### 5. What DNS actually teaches, and where the analogy stops

The Domain Name System comes up constantly in this conversation, usually as an argument for a global root. Read more carefully, it argues for the opposite.

| DNS fact | What it suggests here |
|---|---|
| The root zone is a small, slow-changing, signed file | Thin signed data with wide distribution is the right shape. Not a large live service |
| Almost nobody queries the root directly; resolvers cache aggressively | Availability comes from distribution and caching, not from one operator's uptime |
| The authoritative function and the serving function are separate institutions | Governing the record and serving it need not be the same party |
| Root operation is funded by mandate plus fees on parties with standing in the namespace | Permanent obligations get funded by beneficiaries or by mandate. Not by goodwill |
| The most ceremonious, most assured and most expensive activity is key management | Keys, not uptime, are where the real assurance burden sits |

And the boundary, which matters: **DNS is a single hierarchical namespace whose authority derives from a unique historical position.** Trust registries are many-to-many across independently governed ecosystems, each authority retaining its own domain, with the relying party making the final decision. Borrow the operational shape — thin, signed, cached, separately governed. Do not borrow the authority model. No single hierarchy of trust is implied by anything in Track 1, and we should be careful that our diagrams do not imply one either.

### 6. Funding duration has to match obligation duration

A point that applies to every operator the framework will touch.

An operational registry obligation is permanent, non-discretionary and reliance-bearing. Grant funding is episodic and renewable only by persuasion. Project and consulting revenue is contingent on winning work. Funding a permanent obligation from impermanent money does not produce a funded service. It produces a dated cliff that arrives while participants are relying on it.

The matching that works:

- **One-time and capital costs** — initial build, first certification, capitalising a reserve — are the right home for grants and philanthropy.
- **Recurring operations** need recurring money from the parties who rely on the service. Beneficiary-funded income is renewable by construction. Donor-funded income is renewable by persuasion, every year, forever.
- **Project revenue** is cost recovery. It can fund a capability build. It cannot carry a run-rate.

A framework that implicitly assumes grant-funded operations has designed in the cliff. If we say anything about sustainability, this is the useful thing to say.

### 7. Let participants be honest about what is not funded

A framework that only has room for compliant and non-compliant pushes operators to overclaim. That is the opposite of what a trust framework should do.

Make room for an operator to state plainly: this capability is governed and operating; this one is built but not assured; this one is specified and not funded; this one we deliberately do not do. A participant who publishes that is more trustworthy than one who publishes a conformance badge covering gaps nobody can see.

Concretely, this means the framework should require operators to distinguish:

- **Non-binding operating targets** — published intents, revisable, no remedy attached.
- **Contractual commitments** — availability, response and restoration promises with consequences.

Conflating the two is how a best-effort service gets relied on as though it were assured. Keeping them apart lets a thinly funded but honestly described registry participate, which is better for everyone than excluding it and pretending the gap does not exist.

### 8. One more requirement worth writing in

Unrelated to funding, but it belongs in the same section of the framework, because it is the failure that actually hurts people.

**An unavailable answer must never become an authoritative negative.** If a registry cannot be reached, a conforming consumer must be able to distinguish "unavailable", "unknown" and "not authorized". Collapse those and an outage silently turns into a denial of someone's qualification, licence or entitlement. Require the distinction, require that answers carry the time the underlying information was established, and require that consumers be tested against stale and unavailable conditions, not just happy-path queries.

### The ask for Track 1

1. **Name the obligated party for every "shall".** If no funded party exists, scope it down or distribute it rather than publishing it.
2. **Separate the level from the service.** Make the recognition semantics and conformance criteria singular and shared. Leave serving plural.
3. **Do not designate a single global root.** Design for interoperable plurality. If the task force does want a designated global operation, recommend the mandate and the funding together, explicitly, as a funding recommendation.
4. **Require the distinction between non-binding operating targets and contractual commitments.**
5. **Say something useful about sustainability:** match funding duration to obligation duration, and keep grants to capital.
6. **Let operators declare honestly what is not funded** without being non-conformant.
7. **Require that unavailable, unknown and not-authorized remain distinguishable,** and that answers carry an effective time.

None of this makes the framework less ambitious. It makes it implementable by organizations that will still exist in five years.
