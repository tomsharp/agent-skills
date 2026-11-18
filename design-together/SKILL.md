---
name: design-together
description: Collaboratively design software systems by walking through consequential decisions one at a time, explaining tradeoffs, tracking agreed scope, and aligning implementation specifications and tickets. Use when the user asks to design together, go piece by piece, or close open engineering decisions interactively; do not impose this interview on a direct implementation request.
---

# Design Together

Help the user reach a coherent, buildable design through short exchanges. Optimize for understanding and concrete decisions, not an exhaustive architecture questionnaire.

## Establish the starting point

Read supplied references and relevant existing design artifacts. Recover the current goal, accepted decisions, unresolved questions and explicit exclusions before asking anything already answered. Distinguish a source document's claims from verified implementation.

Briefly propose an order for the remaining topics. Choose the next topic by dependency and consequence, not a rigid checklist. For example, ownership boundaries affect authorization and schema; network access affects dashboard and service integration.

Keep an evolving decision record with four categories: agreed, proposed/default, deferred/out of scope, and unresolved. Record rationale and affected artifacts where useful. Maintain it in an existing authorized design document or conversational context; do not create a new file after every answer.

## Run the conversation

For each consequential decision:

1. Explain what is being decided and why it matters in plain language.
2. Give a specific recommendation with the main tradeoff. Show two or three alternatives only when the user has a real choice. Use a compact table for comparisons or a focused Mermaid diagram when topology or event order helps.
3. Ask ONE focused question and wait. Avoid bundling unrelated questions or ending with an entire checklist.
4. Acknowledge the answer briefly, state its practical consequence, update the decision record and move to the next unresolved decision.

Treat short answers such as “yes,” “only one,” and “for now” as answers to the pending question. Do not expand a narrow answer into approval of unstated design choices. If an answer resolves multiple questions, skip those questions. Honor the user's pace; explain a confusing concept with a concrete example, then resume the pending decision rather than advancing past it.

Use judgment for reversible implementation details. Do not ask the user to select every field, instance size or configuration value. Mark reasonable defaults as proposals and surface only choices that materially affect product behavior, complexity, cost, security boundaries or implementation scope. Verify current vendor capabilities or pricing in official sources before making those claims.

Distinguish:
- Public network reachability from permission to use an API.
- Authentication from authorization and ownership boundaries.
- Desired state from background work completion and user-visible behavior.
- Public access revocation from storage deletion and already downloaded copies.
- A manual administrative workflow from automatic enforcement of its results.
- Initial requirements from future extension points.

Use those distinctions only when relevant; do not force every design through them. Never carry over a previous project's vendors, roles, table count or architecture as universal preferences.

## Incorporate changes coherently

When the user changes a decision, identify affected contracts, data structures, background jobs, integrations and tests. Replace superseded requirements rather than leaving contradictory statements. Keep a future extension feasible without implementing it prematurely. Explain when simplification moves responsibility into application code instead of eliminating the requirement.

Clarify essential lifecycle behavior: what the caller sees immediately, what happens asynchronously, what happens on failure/retry, and where ownership or authorization is checked. Do not declare a design complete while an unresolved item prevents its core workflow from operating.

## Close the design and deliver

When the substantive decisions are settled, summarize the agreed scope and remaining implementation parameters. Prepare or update concrete, reviewable specifications within the authorization already given. Do not repeatedly ask permission to perform an already requested update. Discussion alone does not authorize deployment or external ticket creation.

When documents or tickets are requested:
- Preserve existing artifact identities and honor the user's chosen template and ticket granularity.
- Align API contracts, schema, architecture/workflow diagrams, infrastructure and acceptance criteria with the same decisions.
- Separate ownership between implementation tickets and add dependencies. Moving work to a separate ticket must remove or clearly reassign the old ownership.
- Include how failure paths and meaningful concurrency/authorization boundaries will be verified.
- Identify remaining proposals explicitly; do not report unexecuted migrations or undeployed integrations as tested or live.
- Complete authorized file/ticket updates and return direct links with a concise account of what changed.

If the user wants to keep discussing, end with the next useful question. If the authorized deliverables are finished, stop without inventing another decision or approval gate.
