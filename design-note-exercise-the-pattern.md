# Exercise the Pattern, Not the Snapshot

- Status: working design note (co-leads) — not yet shared with the group
- Author: Darrell O'Donnell
- Date: 2026-07-10
- Builds on: the parked Track 2 concern in the [Track 2 capture](references-and-inputs/ayra-context/meeting-notes-track2-2026-07-10.md) ("Private note — not for sharing yet")

## The claim

If you plan, design, or pilot only the static case, you never exercise the pattern. You build something that demos and ships and then falls over on the very next use case — because the mechanism that actually matters was never built or tested. A static list is the *output* of the pattern, not the pattern. Build the pattern; cache the output.

## What the pattern actually is

A verifier answers two questions against a trust registry, and keeps answering them as the world changes:

- **Authorization** — is this issuer authorized to issue what it just issued?
- **Recognition** — do I recognize the registry that vouches for this issuer?

The load-bearing word is *keeps*. Issuers get added, suspended, revoked. Recognition relationships change. The pattern is a live query capability with a freshness and status dimension baked in. That's the whole job — keeping trust current — and it's the part that's hard.

## The static case is a frozen snapshot of that pattern

A static, pre-transaction list is what you get when you run the query once and freeze the result. It's a legitimate and necessary mode — it's fast, and it's the only thing that works offline or in low-connectivity (the cached-VICAL, fishing-camp-with-no-comms case). But it is a *special case*: the degenerate version where the refresh interval is "never" and the answer to an unknown issuer is "not in my list, reject."

Nothing wrong with the snapshot. The problem is mistaking it for the thing.

## Why static-only doesn't exercise the pattern

Design a v0.1 that only does static, and here's the list of things you never build and never test:

- **Refresh.** How the list stays current, how often, what staleness window is tolerable.
- **Status change propagation.** What happens between snapshots when an issuer is suspended or revoked — the revocation-latency question.
- **The live-query path.** What the verifier does when it meets an issuer that isn't in its list.
- **Recognition traversal.** Following from an issuer you don't know to a registry you *do* recognize.
- **Failure behavior.** What the verifier does when the registry is unreachable, or the answer is stale, or two registries disagree.

Every one of those is the actual pattern. A static-only build skips all of them and still looks finished. You've validated the wrapper, not the engine.

## The trap

Static-only produces two failures at once, and they compound.

**False confidence.** The demo works. A known government ID verifies against a frozen list, on stage, every time. It looks like the problem is solved. It isn't — you've proven you can read a snapshot, which proves nothing about keeping trust current.

**A built-in cliff.** Because the static path was designed as an *endpoint* rather than as one mode of the query, the next use case — an issuer not known in advance, a status that changed this morning, an education credential that has to traverse to another registry — doesn't require an extension. It requires a redesign. The narrow delivery becomes a dead end instead of a foundation.

## The design rule

Design the pattern first — the live query, with authorization, recognition, and status — and treat the static/cached list as *one materialization* of it. Then, even a v0.1 deliberately scoped to government identity documents actually exercises the mechanism:

- Run the query. Cache the result. Prove the cache is a *refresh of the same query* you would otherwise run live.
- Make the unknown-issuer path a real code path that returns "unknown," not an assumption baked into a frozen list.
- Give status and staleness a defined behavior, even if the first refresh interval is generous.

This keeps the delivery narrow and the design honest. The before-the-transaction and during-the-transaction modes are the same query at two different times — cache-and-refresh versus live lookup — so building for both from the start costs little, and the dynamic path drops in without a redesign.

## The ask

Don't let "we scoped it down" become "we only built the snapshot." Scope the *delivery* to government identity documents. Do not scope the *design* to static. A pilot that never runs the query live, never handles an unknown issuer, and never ages out a status has not tested the thing we're actually building — it has tested a cache. Exercise the pattern, even small.
