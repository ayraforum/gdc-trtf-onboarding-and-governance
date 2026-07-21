# Two Ideas for Track 1: Focused Ecosystems and Assurance Levels

Darrell O'Donnell — for the Track 1 discussion, 2026-07-09

Two versions below. Use the **short version** for a verbal drop or a single chat message. Use the **full version** for screen-share or pasting into the meeting doc.

## Short version (verbal / one chat message)

Two ideas for Track 1.

**One — narrow ecosystems integrate better.** The instinct is that interoperability comes from bigness: one master list, one credential, everyone under one tent. It's backwards. An all-encompassing registry is legible to no one. A registry that knows exactly what it is — driver licenses, issued under these processes, at these assurance levels — is trivial to recognize from the outside. Bounding scope isn't a retreat; keeping a thing narrow is what lets it travel.

**Two — an assurance level is a value that points somewhere.** "Level 3" isn't three stars out of five. It's an address: it points to a governance framework that defines the processes and backing behind it. The registry carries the pointer; the authority owns the meaning. And watch the two levels people collapse — identity assurance (how well was the person proven?) vs credential assurance (how strong is the instrument?). An mDL is a level-3 credential, but if the identity proofing was level 2, the effective level is 2. You can bump down, never up.

The two connect: keep the assurance field bounded, and that discipline is exactly what makes it recognizable across ecosystems later. Focus is the enabler, not the limit.

## Full version (screen-share / meeting doc)

### 1. Narrow ecosystems integrate better

The instinct is that interoperability comes from bigness — one master list, one credential, everyone under one tent. It's backwards. An all-encompassing registry is legible to no one; it can't state plainly what it is because it stands behind too much.

A registry that knows exactly what it is — driver licenses, issued under these processes, at these assurance levels — is trivial to recognize from the outside. Cross-ecosystem trust doesn't come from registries meeting in the middle. It comes from sharp, well-bounded ones that each say clearly what they are and what backs them.

So bounding scope isn't a retreat. Keep a thing narrow, and that's exactly what lets it travel.

### 2. An assurance level is a value that points somewhere

A relying party in the middle of nowhere gets handed a credential from anywhere on the planet. Cryptography tells them it's valid. It doesn't tell them whether it was issued in a way they can rely on. That's the assurance level — and it's where the governance value lives. Skip it and we ship a registry that says who signed a thing but not whether to trust how it was made.

"Level 3" is not three stars out of five. It's an address. On its own it means nothing; it points to a governance framework that defines the operational processes and backing behind it. The registry carries the pointer. The authority — AAMVA, a passport office — owns the meaning. That split is what keeps a registry-of-registries neutral instead of operating everyone's governance.

Two things people keep collapsing:

- **Identity assurance** — how well was the person proven before any credential existed?
- **Credential assurance** — how strong is the credential as a technical instrument?

An mDL is a level-3 credential. But if the identity proofing behind it was level 2, the effective assurance is level 2. **You can bump down. You can never bump up.** Two mDLs in the same registry, same keys — one issued after real document checks, one on someone's word — pass the same technical checks. Only an assurance flag tells them apart.

### Where the two ideas meet

Keep the assurance-level field bounded — to identity documents, to what the authority actually backs — and that discipline is exactly what makes it recognizable across ecosystems later. Focus is the enabler, not the limit.

The ask for Track 1: make room for a structured assurance field, keep its meaning with the issuing authority, carry both assurances and honor bump-down, and express cross-recognition at a level. We're not asking the registry to decide who's trustworthy — just to carry an honest pointer to where that decision's evidence lives.
