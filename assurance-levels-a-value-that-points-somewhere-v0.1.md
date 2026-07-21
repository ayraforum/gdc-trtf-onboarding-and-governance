# Assurance Levels: A Value That Points Somewhere

- Status: discussion draft v0.1
- Audience: GDC Trust Registry Task Force (Track 1)
- Author: Darrell O'Donnell
- Date: 2026-07-09
- Origin: conversation with Mike McCaskill (AAMVA), 2026-07-09 — see [meeting capture](references-and-inputs/ayra-context/meeting-notes-aamva-mccaskill-2026-07-09.md)

## Why this matters

A relying party sitting in the middle of nowhere gets handed a credential from somewhere on the planet. They have to decide, right then, whether they can act on it. Not "is it valid?" — cryptography answers that. The real question is "was this issued in a way I can rely on for *my* transaction?"

That question has an answer. The answer is an assurance level. And most people building trust registries want to skip it, because the technical people don't need it and it's hard to pin down. That's the mistake. Assurance level is where the governance value lives. Punt it, and we ship a registry that tells a relying party who signed a thing but not whether they should trust how it was made.

## An assurance level is a pointer, not a score

"Level 3" is not three stars out of five. It's an address.

On its own the number means nothing. What it means is: *go look at this governance framework, and it will tell you the operational processes, the identity proofing, and the backing that stand behind a credential issued at this level.* The number is a handle on a body of work. Strip away the framework it points to and you've got a digit.

So the registry's job is narrow. It carries "authorized at level 3 — see the AAMVA framework for what 3 means." It defines the *structure* of the field. It deliberately does not define the *meaning*. The meaning belongs to the authority that runs the processes — AAMVA for driver licenses, a passport office for passports. A registry that tried to own the meaning of "level 3" across all of them would be operating everyone's governance, and the neutrality that makes it useful collapses.

The chain is simple: the relying party reads a value (level 3), the value points to a framework (AAMVA, REAL ID, an EU scheme), the framework points to real operational processes, and the relying party makes their own call. That last step never moves to us.

## Two assurances, and people keep collapsing them

The most useful thing we can teach the task force: "assurance level" is not one number. It's two.

**Identity assurance** — how well was the person proven before any credential existed? Verified breeder documents, or a name and a birthday told to a clerk?

**Credential assurance** — how strong is the credential itself as a technical instrument?

Mike McCaskill put it cleanly. An mDL is a level-3 *credential*. But if the identity proofing behind it was level 2, the effective assurance is level 2. **You can bump down. You can never bump up.** A strong credential wrapped around a weak identity is a weak result — and the credential's own strength will hide that unless the registry surfaces it.

Picture two mDLs: same standard, same keys, same registry — one issued after real document verification, one issued on someone's word. Same technical checks pass for both. Without an assurance flag pointing to how each was issued, the relying party can't tell them apart. Same signature, different truth behind it.

## Where this stops

Bounding the topic matters as much as making the case. Assurance level is a small, sharp thing. It gets useless the moment we let it swallow everything nearby.

In scope for the task force:

- Making room for a structured, machine-readable assurance field on the authorization.
- Carrying **both** identity and credential assurance, and honoring bump-down (effective level is the floor).
- Pointing accurately to the governance framework that defines the meaning.
- Expressing **cross-recognition at a level** — "we recognize AusRoads at level 3; we recognize this other authority at level 1, meaning they have a pulse but we don't understand their process." Recognition is scoped, not yes/no.

Out of scope — and we should say so out loud:

- **Defining what the levels mean.** That's each authority's governance, not the registry's.
- **The acceptance decision.** Whether level 2 is good enough for a car rental or a border crossing is the relying party's call, every time.
- **Equivalence and conversion.** Whether a Canadian license "equals" a Thai one for licensing purposes is a different animal. We can say it was issued as a driver's license with these classes. We cannot decide equivalence.
- **Holder-to-relying-party trust.** Can the holder trust the verifier? Real problem, later problem. It can't be solved in the same motion.
- **Anything past identity documents.** Step outside that domain and questions arrive that we don't need to answer. Stay bounded.

None of the out-of-scope items are unimportant. They're just not *this*. Naming them is how we keep the assurance-level field from turning into a governance-of-everything project that never ships.

And this is the part that gets missed: the narrow boundary is not a limitation on cross-ecosystem work — it's what makes cross-ecosystem work possible. The more focused an ecosystem is, the better it integrates with others. A registry that knows exactly what it is — driver licenses, issued under these processes, at these assurance levels — is trivial to recognize from the outside. A registry trying to cover everything is legible to no one. Cross-ecosystem trust doesn't come from big, all-encompassing registries meeting in the middle. It comes from sharp, well-bounded ones that each state plainly what they are and what they stand behind. Assurance level is exactly that kind of plain statement. Keeping it narrow here is how it travels later.

## The ask

Don't punt assurance levels. Four moves:

1. **Make room for the value** — a structured assurance field, not prose. The technical track owns how it's expressed, not whether it exists.
2. **Keep the meaning with the authority** — the registry points; the framework defines.
3. **Carry both assurances and honor bump-down** — build it in now, or spend years explaining why a "level 3 credential" isn't level 3.
4. **Cross-recognize at a level** — scoped, not binary.

None of this asks the registry to decide who's trustworthy. It asks the registry to carry an honest pointer to where that decision's evidence lives. The whole game is making the trust question answerable — not answering it for anyone.

This is a draft to argue with. If there's a sharper way to say "the number is an address, not a score," or a scope line I've drawn wrong, reach out before it goes in front of the full task force.
