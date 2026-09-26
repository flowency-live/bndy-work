# Backline V1 working tasklist and session handover

Updated 26 September 2026. Accountable technical owner: current ChatGPT session, programme [#7](https://github.com/flowency-live/bndy-work/issues/7).

## Owner instructions, 26 September

- Implementation ownership is exclusively bndy-enrichment, on main. No new branches, PRs or worktrees.
- All bndy-serverless-api changes go into explicit bndy-work work orders for the VSCode agent with AWS CLI. Coordinate with the ongoing API refactor (#87); do not edit that repository from this lane.
- Keep this document current at meaningful checkpoints and before ending a session. Link evidence and exact next steps on #7. Never imply an inactive worker is running.
- V1 enables a stable curator rollout. Urgency must not produce bypasses, name-specific exceptions or weaker safety gates.
- No graph database is proposed. Assemble connected evidence, scoped authority, identity, history and human decisions using the existing stores.
- A commit checkpoint is not a deployment dependency. Continue unblocked enrichment implementation; distinguish coding, API integration and live acceptance gates explicitly.
- Current deployment queue is #80. Production deployments and data recovery remain separately scoped; no cleanup, redrive or replay follows from coding authority.

## Start/resume here

1. Read this file, the latest #7 and #80 comments, and bndy-enrichment AGENTS.md.
2. Read [constitution](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-CONSTITUTION.md), [implementation plan](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-INTELLIGENCE-EXECUTION-PLAN.md) and [status](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-STATUS.md).
3. Check remote main and any local uncommitted work. Preserve existing edits; use one main checkout.
4. Resume the first In progress task below. Do not restart old source audits, stale deployment orders or the API refactor.
5. Behavioural commits require TypeScript/build and the full repository test command passing by exit code. Use [skip ci]. Keep implemented, deployed and live-verified separate.

## Baseline and evidence limits

- Remote main inspected at session start: 1b515fb59f1b443b8b5ced6bc8e74d7ae0370926.
- Reported production baseline: R1 59d9083, from #80's 26 September 12:45 London checkpoint. Not independently reread from AWS by this session.
- R2 5974843 is recorded as pending owner go, with no concurrent API cleanup deployment.
- API #87 reports local successful build at 132e02d, not deployment. PR111 profile integration remains draft/unmerged.
- Review reproduced context/index defects offline against R1 code. This is not proof of specific production corruption.
- No current production count or remaining monthly budget has been independently measured by this session.

## Working tasklist

| ID | State | Work and acceptance | Dependency / evidence |
| --- | --- | --- | --- |
| V1-01 | Partial — reader integration next | Canonical lookup correctness: conflict-aware identity; rename/delete invalidation; bounded retry of incomplete writes; human corrections precede cached matches. Positive and negative regression cases must prove the decision. | Backline-owned. Inspect current code before design; preserve canonical API resolution where context cannot decide. |
| V1-02 | Partial: source attribution implemented | Billing and title interpretation: one decision per bill; preserve real composite acts and evidenced lineups; no invented fragment acts; stamp source on creation. | Existing billing containment policy; any model activation remains separately bounded/approved. |
| V1-03 | Pending | Existing event identity across import keys; explicit traced lookup before creation; preserve distinct performances and bill relationships. | Reuse existing API deduplication, do not duplicate it. API gaps become work orders. |
| V1-04 | Pending | P3 accounting: complete entity inventory; existing/new/unknown separate from canonical effects; partial successes retained; retries/pages/parent-child totals reconcile. | #82 backend contract, #79 UI. Backline producer here; API portion via VSCode work order. |
| V1-05 | API work order issued; implementation pending | Curator V1: authorised immediate canonical edits, durable actor/scope/provenance, feedback convergence, stable human memory, delete/ownership protection. | [#37 API work order](https://github.com/flowency-live/bndy-work/issues/37#issuecomment-5846352119), coordinated with #87. No API worker is assumed active. |
| V1-06 | Pending | Profile facts and governed application: close historical/current feedback gaps; reuse PR111; claimed Artist exclusion, Venue links only. | #81/API work order. Optional profiles never block valid gigs. |
| V1-07 | Pending | Lemonrock supported discovery/change/cancellation scope and <=24h freshness with measured budget and bounded recovery. | #59; weekly known-ID refresh is not daily coverage. No new live crawl allowance implied. |
| V1-08 | Pending | Named hold recovery and exact cleanup proposals after defects are stopped; preserve current human decisions and uncertain writes. | #80 executes approved scope; destructive cleanup needs exact owner approval. |
| V1-09 | Pending | Seven complete daily acceptance cycles with reconciled counts, no unexplained invalid/duplicate writes, stable curator corrections, freshness and cost inside limits. | Starts after prerequisite gates; actual daily evidence, not code/test completion. |
| V1-10 | Pending | Apply accepted shared capability to LBP, then remaining sources. Preserve normal schedules; Music Live parked, Fantastic All Library manual-assisted. | Existing source issues. No all-source relaunch or extra infrastructure. |

## Current implementation claim

- V1-01: src/projection/context.ts; src/projection/engine.ts as necessary for evidence/human precedence; src/bndy-baseline/lookup.ts, change.ts and change-store.ts; their existing tests; minimal related handover/status documentation.
- This continuation also claimed src/projection/bndy-api.ts, its existing tests, and test/bandforge.test.ts, test/livebandphotos.test.ts and test/music-live-east.test.ts for read-port fixture typing only.
- Additional claimed files: src/knowledge/stores/clients.ts (transaction command type), src/cli/canonical-lookup-backfill.ts (retire obsolete unversioned writes), test/projection-bndy-api.test.ts (test-token isolation), test/canonical-context-integrity.test.ts (new integration regressions), and entry/status/plan documents.
- Current human persistence checkpoint additionally claims src/knowledge/stores/current-human-claims.ts, src/knowledge/stores/claim-store.ts, test/current-human-claims.test.ts, docs/adr/ADR-124-current-human-claims.md and docs/BACKLINE-STATUS.md.
- Whole-action publication additionally claims src/projection/hold-actions.ts, src/handlers/backline-admin-api.ts, test/hold-actions.test.ts, test/hold-retry.test.ts and test/backline-explorer.test.ts; it extends the existing current-human store and tests.
- No API files claimed. No source worker launched.
- Before expanding scope, record exact additional files and why on #7.

## Checkpoints

### 26 September: ownership and V1 start
- Reviewed all 29 Backline-labelled issues and related API/Ops/Capture issues, governing documents and decision/index code.
- Offline review found: unique venue name can override conflicting town/postcode; artist name/core match lacks geography; rename then delete leaves an old live name lookup; unprocessed lookup writes return success.
- Published this restart document before behavioural changes.
- Next: establish a verified main checkout, add failing regressions, implement V1-01, run required gates and commit on main.
- No production change, API edit, deployment, redrive, cleanup or new graph infrastructure.


### 26 September: first implementation checkpoint committed

- Enrichment main: [204e0430924b47e7f2489fbfb8e90683ec886cef](https://github.com/flowency-live/bndy-enrichment/commit/204e0430924b47e7f2489fbfb8e90683ec886cef), parent 1b515fb. One direct main commit, 16 files; no new branch, PR or worktree. Remote ref and changed-file list verified. Local checkout is clean at the same actual commit/tree; it has shallow history at the reviewed parent.
- Implemented atomic lookup/self-resolution/sync-state publication and an idempotency marker on the existing observation. Rename/delete invalidates old keys; replay and concurrent publication cannot partially rewind the accepted context. Same-second ordering uses predecessor evidence, not a globally compared stream sequence.
- Strongly consistent lookup/revision reads reject stale/unversioned rows. Incomplete reads/writes retry within explicit bounds and then fail. Transactions exceeding 97 lookup keys and unprovable same-second ordering fail explicitly.
- Artist name/core-name alone no longer bypasses canonical contextual resolution. Venue name-only/substring matches no longer override premises evidence. Conflicting asserted identities become reviewable holds.
- A current human Venue selection precedes cached mapping, automatic context and creation-only town validation. Missing/deleted human-selected Venue is held rather than replaced automatically.
- Retired `canonical:lookup-backfill --apply`: it exits before data reads/writes. Inventory mode remains a full scan and has NOT been run or authorised here.
- Build plus full `npm run check` exited 0: **195 Vitest files, 2517 passed, 5 skipped; 56 recovery tests passed**. Added regressions include rename/delete, stale replay, name cycles, decreasing sequence values, concurrent transaction conflict, failed atomic publication, incomplete reads/writes, identity/premises conflicts and Venue human precedence.
- Existing API tests had two missing-token isolation failures at baseline. The test hook now covers both describe groups and restores environment state; no production credential or access behaviour changed.
- CLI guard checked using the compiled entry point: expected exit 1 with the retirement message, no data calls. The tsx wrapper itself could not start its local IPC socket in this workspace; that is not a production CLI qualification.
- Source entry points now link this tasklist and explicitly record exclusive enrichment ownership and the API work-order boundary.
- [Curator feedback API work order](https://github.com/flowency-live/bndy-work/issues/37#issuecomment-5846352119) issued for the VSCode agent under #87. Reuses the existing issue and requires route coverage, server-authenticated actor/scope, durable versioned feedback, outage/retry/ordering proofs and echo suppression. This is an assignment, not a claim of execution.
- **Not deployed. No AWS mutation, API edit, redrive, cleanup or graph infrastructure. V1 acceptance remains open.**

### 26 September: Artist corrections and creation attribution committed

- Enrichment main: [a97af880b78f31a0eab906ad536da1f784fd41cf](https://github.com/flowency-live/bndy-enrichment/commit/a97af880b78f31a0eab906ad536da1f784fd41cf), parent 204e043. Remote ref/files verified and local main clean at the same actual commit/tree. Eight changed files, no new branch/PR/worktree.
- Human Artist evidence is read before remembered mappings and automatic context. Identity decisions supersede across same-act/new-act predicates; contradictory same-time decisions hold instead of depending on query order. Latest withdrawn decisions do not revive older facts, including in source-evidenced creation.
- A human-selected Artist is checked through the existing canonical GET endpoint. Missing, hidden or deleted targets hold without an automatic replacement. Human location/link facts outrank newer automated testimony. Match-only and dry-run protections remain.
- Each performer carries its own asserted native identity; support acts no longer inherit the headliner's identity in the canonical candidate.
- Permitted Artist and Venue creation requests now carry `source: candidate.sourceId` on both HTTP paths. Read-only requests retain their write-free contract. No canonical API implementation changed.
- New-Artist instructions do not silently accept a contradictory ordinary canonical match. They do not bypass a match-only source policy. **Per-decision creation idempotency is NOT solved**: reviewed API code uses ordinary identity uniqueness, not a retained association between a human decision and its result. The [specific #37 API work order](https://github.com/flowency-live/bndy-work/issues/37#issuecomment-5847071704) covers concurrent calls, timeout/retry, later gigs, changed region and explicit supersession. VSCode agent owns this under #87.
- Existing HTTP port tests and three source test fixtures gained the required GET Artist stub. No production source adapter changed.
- Verification: focused engine/HTTP/source-evidence tests during development; **one full `npm run check` gate** before commit, exit 0. Build passed; 195 Vitest files, 2530 tests passed, 5 skipped; 56 recovery tests passed. Vitest wall time 11.56 seconds. Thirteen new cases cover the changed behaviour; the thousands are the existing repository suite. No paid CI dispatch or AWS operation.
- Persistent human history remains open. Reading evidence before a cached Artist mapping increases history-read demand. The Artist bound fails explicitly; the event-candidate 300-claim window can silently omit older human facts. Do not mark V1-01 complete or release this as full Curator readiness.
- No deployment, bulk hydration, replay, cleanup or API mutation.

### 26 September: atomic current-human storage committed

- Enrichment main: [9fca094e6bc7e3a99d9916d305a09f38f72593a0](https://github.com/flowency-live/bndy-enrichment/commit/9fca094e6bc7e3a99d9916d305a09f38f72593a0), parent a97af88. Five files; remote ref/files verified and local main clean at the identical actual commit/tree.
- Existing godmode:human Claim writes now publish immutable evidence and current subject references atomically in the existing table. Scope groups retain latest decisions, withdrawals and two representatives of tied conflicts; older replay cannot rewind them. CAS contention retries are bounded to three transactions. Existing immutable Claim retries verify and condition-check content rather than overwrite history.
- Added a strong, bounded current-human read method. It requires explicit complete legacy coverage before returning decisions or certified absence, validates each retained reference, and fails on missing/corrupt evidence. Ordinary writes never create the coverage assertion.
- Focused persistence/hold tests passed (78 cases across three files). Final npm run check exited 0: build passed; 196 Vitest files, 2543 passed and 5 skipped; 56 recovery tests passed. Vitest duration 12.26 seconds. Thirteen focused storage cases were added. One earlier build attempt caught a test-fixture optional-key typing error, corrected before the full suite ran.
- The old-correction read-port test retains a Venue decision after 10,000 automatic Claims using three strong keyed reads. Concurrency, atomic failure, lost-response retry, ID conflict, missing/partial coverage and explicit retry/size bounds are covered with an in-memory transaction model. This is not AWS integration evidence.
- [ADR-124](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/adr/ADR-124-current-human-claims.md) records the implemented storage contract and precise remaining migration, coverage, mixed-writer rollback and cost obligations.
- **Staged storage only:** projection has NOT switched to this read method. No legacy coverage assertion has been written and no migration tool/execution is included. The existing 300-Claim Venue gap and Artist automatic-verification bound remain open. Whole-action/alias atomicity, human trace provenance and reader integration are also still required.
- No API implementation, new infrastructure, deployment, AWS mutation, bulk migration, replay or cleanup.

### 26 September: complete curator fact actions committed

- Enrichment main [1eb1b7ee69fed81414d0d8399ad5997ed474429c](https://github.com/flowency-live/bndy-enrichment/commit/1eb1b7ee69fed81414d0d8399ad5997ed474429c), parent 9fca094. Ten files; remote ref and file list verified, local main clean at the same real commit/tree. No branches/PRs/worktrees added.
- A tell action now collects all facts and all selected act aliases and atomically publishes their immutable Claims/current references in one transaction. Publication failure queues no retry; a new fact subset cannot leak from a failed action. Existing single-Claim writes delegate to the same store logic.
- Batches deduplicate identical Claim IDs, reject conflicting reused IDs, respect 100 transaction items and a conservative 3 MiB serialized request budget, and never split one action into partial commits. Strong reads run with at most eight requests concurrently; CAS retries remain bounded.
- Conflicting facts within a request are rejected before changes. Venue corrections require the individual gig route; an act-group action cannot silently apply a Venue fact to only its first gig. Venue holds cannot become Artist identity/ignore rules. Group act facts cover every selected alias, not only the first hold's spelling.
- Different decisions in the same millisecond now retain different observation and retry identities. This is not stable HTTP retry identity across later requests.
- Focused tests: 69 passed across four files. Full npm run check exited 0: build, 196 Vitest files (2552 passed, 5 skipped), 56 recovery tests. Vitest 11.85 seconds. Nine new behavioural cases; existing admin HTTP error checks extended.
- **Remaining:** accepted facts followed by failed/partial queue publication still need durable recovery and stable request identity. S3 Observation persistence, hold action audit append and queue sends are outside the Claim transaction. Projection's durable-human reader and bounded migration are not activated. No claim of complete Curator V1 readiness.
- Updated ADR-124 and Status. No deployment, AWS mutation, API repository edit, new infrastructure, migration, replay or cleanup.
- Deployment is not blocking further owned implementation. Remaining coding, API coordination and live qualification are separate gates.

## Exact next session

1. Confirm enrichment main remains 1eb1b7e or inspect subsequent commits. Read latest #7/#80/#37 comments, this handover and ADR-124. Preserve the single main checkout.
2. Continue V1-01 reader integration and legacy coverage from the implemented current-human storage. Do not recreate the store or assume a newly written current record proves complete historical coverage. Claim exact additional files before editing.
3. Design and implement a finite, resumable legacy inventory/hydration proposal with explicit requests/pages/bytes/retries, manifest reconciliation and checkpoints. Settle the writer fence and completeness proof before supplying coverage-publication tooling. A partial/cohort inventory cannot certify the current global coverage contract. No migration execution is authorised.
4. Whole-action/alias Claim publication is now implemented. Continue stable request identity and recovery for the remaining evidence/queue/audit boundaries: facts can commit before queue publication fails, and group queue sends can be partial. Retain actor/Observation provenance and avoid relabelling a transport retry as a newer human decision. Coordinate the canonical new-Artist once-only dependency with the existing #37 API work order, not an enrichment workaround.
5. Integrate current human reads separately from bounded automatic evidence. Missing coverage must fail explicitly. Preserve withdrawals, tied-conflict handling for both Artist and Venue, mapping invalidation and canonical target validation. Include the actual human Claim/Observation references in resolution traces. Consider corrections arriving between decision read and canonical mutation.
6. Resolve the separate Artist automatic-verification history bound without a silent smaller window or unbounded per-gig scan. Storage read-port tests do not close this requirement. Acceptance must demonstrate end-to-end old corrections survive repeated source observations and incomplete coverage cannot create false absence.
7. Integrate the VSCode agent's new-Artist decision contract only after request/response and idempotency tests exist. Do not enable force-creation or interpret an unrelated uniqueness collision as human acceptance.
8. Continue remaining billing/title interpretation, per-bill admission, event identity and #82 producer accounting. Source attribution is implemented; billing admission is not complete. API implementation remains work orders.
9. Use focused checks during development; AGENTS still requires build and the full suite before each behavioural commit. Update this file/#7 at material checkpoints. No background worker remains active when this session ends.

## Deployment and acceptance dependencies

- Existing unversioned lookup rows intentionally cannot supply authoritative context. Until reviewed revision-aware hydration/current stream evidence covers them, canonical resolver calls or holds may increase. Absence of a local hit is not evidence of a new entity.
- Design and qualify a bounded migration/readiness plan before requesting deployment; the old unversioned backfill is not usable. Do not bulk reindex or replay from this coding checkpoint.
- Qualify stream/projection worker compatibility together, transaction IAM support, existing sync-state shape, ambiguous ordering, large alias sets, read/write cost, and rollback consequences. New observation identities include stream identity/event ID; do not assume old receipt identities are unchanged.
- Reported R1/R2 live pins above remain historical. This commit does not supersede #80 with a deployment order. Obtain exact managed release review against current live state before execution.
- Curator route completeness/authority/feedback (#37), remaining identity/billing defects, reporting reconciliation (#82), <=24h supported freshness and seven complete daily acceptance cycles still gate V1.
