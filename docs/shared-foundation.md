# Shared context and discovery foundation (proposal)

Status: design proposal, not an implemented architecture. Canonical draft in n30; n001 references it rather than maintaining a second copy.

## Architectural hypothesis from the owner

The owner's broader vision is that the fitting system being built with the exo ecosystem and ML labs could develop expertise in fitting models of people to each other and to other things, including jobs, opportunities, and investments. This is a strategic hypothesis about transfer of expertise, not evidence that these capabilities already exist or work.

The possible common thread is representation, fit, evaluation, and feedback. Model/runtime fitting and human relevance are different problems; no transfer of accuracy, fairness, consent, or safety should be assumed. Validate each application with its own evidence and human feedback before claiming a shared advantage. This proposal does not establish any technical integration with exo or ML labs.

People retain control of participation and consequential choices. Investment examples are exploratory scope, not authorization to recommend or execute trades; employment examples do not authorize automated hiring determinations. Any later domain-specific implementation needs separate review and applicable safeguards.

## Small common contract

n30 and n001 need a way to turn explicitly selected context into evidence-backed discovery. Share concepts first. Extract reusable code only when both prototypes demonstrate the same need.

Proposed records:
- **Source:** an opaque identifier, source kind, provenance, and ownership information. Raw content stays in a private, local boundary.
- **Permission:** source identifier, product, allowed purpose, allowed derived uses, and revocation state. Collection, matching, and disclosure are separate grants. Missing permission means no access.
- **Context fact:** a claim with evidence references, uncertainty, timestamp, and the permissions inherited from its source. Do not silently turn weak inference into fact.
- **Candidate:** a learning resource in n30; an opted-in participant's approved discoverable information in n001.
- **Recommendation:** candidate, reasons, uncertainty, and provenance. Private supporting evidence is separate from displayable explanation.
- **Feedback:** explicit user responses and corrections scoped to the product and purpose, not permission for unrelated profiling.

These are conceptual records, not final database fields or an API.

## Proposed flow

1. Select a source and grant a product-specific purpose.
2. Import the selected subset and preserve provenance.
3. Derive context locally, respecting exclusions and uncertainty.
4. Apply eligibility and permission checks before ranking candidates.
5. Rank for relevance and interconnectedness; account for novelty in n30 and reciprocal compatibility in n001.
6. Generate an explanation only from evidence permitted for its intended viewer.
7. Gather optional feedback and allow correction or withdrawal.

Do not select a model, vector database, graph database, hosting vendor, or identity service yet. Do not create shared credentials or persistent cross-product access as part of this proposal.

## Data and consent boundaries

The same source can be available to both products only if the person chooses that use for each product. Reusing an adapter must not reuse permission implicitly. Keep third-party content and incidental personal information private. Do not infer protected or sensitive attributes to decide compatibility.

Withdrawal invalidates downstream derived facts, indexes, caches, and recommendations for the withdrawn purpose. Source lineage must make this testable. Deletion and backup-retention guarantees need an explicit implementation policy before real-user ingestion.

For n001, discovery consent and reciprocal connection choice are additional boundaries. A matching score does not authorize showing a profile, disclosing an underlying source, or contacting anyone.

## First acceptance scenarios (synthetic fixtures)

- n30-only permission never allows n001 to consume the source or its derived context.
- A source allowed in both products still does not appear in a public profile.
- A malicious instruction inside imported content cannot alter permissions or trigger actions.
- Removing a source invalidates its derived contributions to subsequent recommendations.
- Already-known feedback reduces repetitive learning recommendations without asserting complete knowledge.
- Missing or incompatible connection-mode consent excludes a candidate before ranking.
- A private fact cannot leak through an explanation, even when it contributed to private reasoning.
- One person's interest never triggers an introduction without the other person's choice.

## Future professional application

The owner requested another application for opportunities (positions, employment, contracts) and candidate discovery. It may reuse the permission and provenance concepts, but requires separate professional-purpose grants and candidate-approved information. Do not transfer romantic or platonic signals to employment use, use sensitive personal data for high-impact hiring decisions, or treat recommendations as automatic eligibility decisions. No new repository, name, or implementation has been selected.

## Next implementation decision

Build one local, synthetic-fixture test of the permission and provenance contract, then one discovery loop per product. Use the results to decide whether a shared package is justified. This proposed sequence is not a delivery commitment.
