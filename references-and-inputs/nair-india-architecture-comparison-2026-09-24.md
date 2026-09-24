# Nair's India proposal — comparison with current Track 1 work

## Document control

- Date: 2026-09-24
- Status: Internal co-lead preparation; not submitted, adopted, or agreed by the task force
- Source: Madhavan Unnikrishnan Nair, [Building a National Digital Trust Architecture for India](https://zenodo.org/records/22840405), version 1.0, September 19, 2026
- Scope authority: [Track 1 scope](../../gdc-trust-registries-tf/Track1/SCOPE-Track1.md)
- Comparison target: [Issuer Trust Registry Governance Framework](../../gdc-trust-registries-tf/Track1/governance-framework/issuer-trust-registry-governance-framework.md)
- Context: Global Digital Collaboration (GDC) trust registry work. This external paper was identified by Darrell; no claim is made that it was circulated through the task force.

## Comparison and disposition

| Source sections | Topic | Current treatment | Disposition |
| --- | --- | --- | --- |
| 3, 7 | Authority differs from signature verification; consumer owns the trust decision. | Framework sections 3 and 7 already state the distinction. | Already covered. Retain terminology; no rewrite needed. |
| 9 | Federate existing directories while authorities retain their mandate. | Scope already supports authority-operated registries, shared services, and scoped recognition. | Already covered. National federation is an informative example, not a universal hierarchy. |
| 7, 10, 13 | Authority and status at the relevant time; unavailable versus negative. | Framework's point-in-time model and bright-line requirement 4 address these. | Useful exercise input. Separate issuance time, reliance time, and information freshness without prescribing fields. |
| 9, 13 | Suspension reasons, stale information, correction. | Discussion D-04 asks what additional status or reason information is needed. | Useful discussion input. Distinguish externally meaningful answers from internal lifecycle procedures. |
| 8, 12–13 | Query correlation and retention. | Discussion D-06 already asks about privacy and security disclosures. | Useful addition: examine what a registry query exposes and who can observe it. No mandated holder-mediated delivery model. |
| 7, 11 | Consumer decision record, purpose, liability, and redress. | Consumer decision rights are established; full consumer governance is deferred. | Later-phase guidance only. No new consumer onboarding requirements in v0.1. |
| 9 | Notice, time-bound review, appeals, public change logs, signed entries, outage policy. | Internal lifecycle operations are excluded; wire formats and mechanisms belong elsewhere. | Defer procedures; refer technical options to the appropriate technical work. Do not add them as Track 1 requirements. |
| 14–16 | Education pilots, agent extension, and national programme. | Current examples concern government-issued personal identity documents. | Outside the current deliverable. Preserve as external context. |

## Questions ready for co-lead consideration

1. For D-04, can a consumer distinguish a negative authorization at the requested time from information too old or unavailable to evaluate that question? The baseline already separates no answer from a negative; the question is whether additional explanation is useful.
2. For D-06, what query-access, logging, retention, and correlation information helps another party decide whether and how to use a registry?
3. Can a worked example show authorization at issuance and at reliance without implying that the registry decides whether a previously issued credential must be accepted?

These are discussion prompts, not settled additions. Ayra's own principles-based participation commitment is not proposed as a requirement for non-Ayra registries or the task force.

## Related preparation

- [Later-phase reliance and correction questions](../later-phases/reliance-records-and-correction-2026-09-24.md)
- [Ayra source dossier](../../kb/ayra-common-kb/reference-material/EXTERNAL/india-national-digital-trust-architecture-2026/README.md)
