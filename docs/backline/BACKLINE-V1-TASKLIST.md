# Backline V1 working tasklist and session handover

Updated 28 September 2026. Accountable technical owner: current ChatGPT session, programme [#7](https://github.com/flowency-live/bndy-work/issues/7).

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
- 28 September: owner supplied an AWS qualification report (~6 GB / 6.85 million StateTable items; 32 attempts). This session has not inspected raw AWS receipts. Claimed live 5974843 conflicts with the earlier R1/R2 release record; exact live revision, gross pre-credit headroom and human-writer coverage remain unverified. See the correction checkpoint below.

## Working tasklist

| ID | State | Work and acceptance | Dependency / evidence |
| --- | --- | --- | --- |
| V1-01 | Partial — reader/migration implemented | Canonical lookup correctness: conflict-aware identity; rename/delete invalidation; bounded retry of incomplete writes; human corrections precede cached matches. Positive and negative regression cases must prove the decision. | Backline-owned. Inspect current code before design; preserve canonical API resolution where context cannot decide. |
| V1-02 | Partial: bill containment and attribution implemented | Billing and title interpretation: one decision per bill; preserve real composite acts and evidenced lineups; no invented fragment acts; stamp source on creation. | Existing billing containment policy; any model activation remains separately bounded/approved. |
| V1-03 | Partial: trace/owner guard; API contract pending | Existing event identity across import keys; explicit traced lookup before creation; preserve distinct performances and bill relationships. | Reuse existing API deduplication, do not duplicate it. API gaps become work orders. |
| V1-04 | Partial: producer attribution/retry repair; API work order issued | P3 accounting: complete entity inventory; existing/new/unknown separate from canonical effects; partial successes retained; retries/pages/parent-child totals reconcile. | #82 backend contract, #79 UI. Backline producer here; API portion via VSCode work order. |
| V1-05 | API work orders issued; implementation pending | Curator V1: authorised immediate canonical edits, durable actor/scope/provenance, feedback convergence, stable human memory, delete/ownership protection. | [#37 API work order](https://github.com/flowency-live/bndy-work/issues/37#issuecomment-5846352119), coordinated with #87. No API worker is assumed active. |
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

### 26 September: staged human-memory writer and reader committed

- Stage A writer/migration pin: [c36ce685efd984ebf9695f625a08c4bd92bbe871](https://github.com/flowency-live/bndy-enrichment/commit/c36ce685efd984ebf9695f625a08c4bd92bbe871). Existing-table transactional human-write fence; bounded resumable inventory/hydration/verification/certification/release/abort CLI. Two requests reserved for safe abort; SDK retries disabled; unknown cost retained. Maintenance reads serialize checkpoints. No AWS operations performed.
- Stage B reader pin: [956fc0c62a30d658a5f587825d89148db627df3c](https://github.com/flowency-live/bndy-enrichment/commit/956fc0c62a30d658a5f587825d89148db627df3c). Human decisions read separately from automatic history; missing global coverage fails explicitly. Venue withdrawal invalidates remembered choices, tied choices hold, selected Artist avoids automatic-history exhaustion; human revision/coverage/evidence retained in trace.
- **Order is mandatory: deploy A, verify all writers, complete and certify migration, then deploy B. Never deploy latest main directly without coverage.** [Rollout guide](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-HUMAN-MEMORY-ROLLOUT.md). Managed releases remain #80; no live execution authorized.
- Each exact pin passed npm run check by exit code: A 197 files / 2560 Vitest passed / 5 skipped / 56 recovery passed; B 197 / 2566 / 5 / 56. Vitest ~12 seconds. Compiled CLI help and offline plan checked, zero AWS calls.
- Same main checkout, two sequential commits; no branches/PRs/worktrees. Reader WIP was backed up while checking exact A, then restored and committed as B.
- Still open: whole HTTP action identity/outbox recovery, automatic verification history, cross-system human update race, canonical new-Artist once-only #37, billing/accounting and live qualification. This is not Curator V1 acceptance.
- Continuing immediately into V1-02 shared billing containment and V1-04 producer accounting under [file claim](https://github.com/flowency-live/bndy-work/issues/7#issuecomment-5848566096). No deployment needed to code these changes.

### 26 September: bill integrity, Event trace and partial accounting committed

- Enrichment main: [ffe3b7112d8e8554ff8288eedebc3350185eafe8](https://github.com/flowency-live/bndy-enrichment/commit/ffe3b7112d8e8554ff8288eedebc3350185eafe8), parent 956fc0c. Fourteen files. Remote commit/file list verified; local main clean at the exact real commit/tree. No branches, PRs or worktrees.
- Uncertain separator-derived bill parts remain one source Event/decision. Asserted native composite profiles stay whole, without giving the source identity to guessed fragments. Actual adapter-supplied lineups retain per-act expansion. Proposed parts are checked before any Artist create.
- Expanded Events retain original bill-key lineage. A transition from historical generated fragment keys to a whole source key fails before Claims/projection/withdrawal publication and before baseline advancement. Existing retained keys require named reconciliation; never reset history or infer a cancellation from parser representation changes.
- Per-source-key entity decisions prevent compressed Artist ID arrays from being assigned to the wrong performer. Ignored acts retain their own disposition; known/created Venue and earlier Artist outcomes survive a later hold. Legacy multi-act attribution without evidence stays Unknown.
- Existing/New/Unknown now partition distinct source identities per run. New survives later reuse; conflicting canonical bindings stay Unknown. Retry merging preserves completed entity work and creation attribution while retaining the latest gig terminal outcome. This does not establish full window or parent/child P3 acceptance.
- Event traces retain external lookup, canonical read and ensure results. Owner-managed Events require matching date/Venue/bill before a protected match is reported; a different identity becomes a hold instead of false success.
- Focused checks: 334 cases across five relevant files. Final npm run check exited 0: build, 197 Vitest files, 2576 passed / 5 skipped, 56 recovery passed. Vitest 12.22 seconds. One earlier full gate exposed the old runner fixture expecting per-proposed-part Events; updated to the intended one-bill contract and final gate passed. No unrelated parity cleanup.
- API read-only review at 9699aa0 confirmed ordinary Event uniqueness ignores startTime (Venue/Artist/date); source-runs/backline.js still has the eight-observation and within-page distinctness contracts. No API edits.
- Work orders: [Event identity #81](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5848686201), [complete reporting #82](https://github.com/flowency-live/bndy-work/issues/82#issuecomment-5848625317), [stable human command identity #37](https://github.com/flowency-live/bndy-work/issues/37#issuecomment-5848687116). Earlier actor/scope and new-Artist once-only orders still stand. API work belongs to the owner's VSCode agent under #87; none is assumed running.
- **Deployment-readiness handoff published:** [#80 request 5848715123](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5848715123). Owner must activate the AWS agent. First scope is bounded read-only qualification: 60 total AWS attempts, 32 MiB total bytes, ten minutes, retries disabled, existing resources only. No deploy/migration/scan/replay/cleanup follows from the request.
- Next critical release sequence: A c36ce68 writer → verified finite human-history migration/certification → B 956fc0c reader → C ffe3b71 only after retained billing-key qualification. Latest main cannot replace old R2. Full managed delta, live writer population, IAM/cost and rollback must be reviewed first.
- No production change, API implementation, paid CI dispatch, new resources, graph service, source crawl, migration or cleanup. **V1 remains unaccepted.**

### 28 September: read-only qualification reviewed; corrections issued

- Reviewed the owner's pasted #80 report against current source, rollout requirements, issue history and latest API #87 activity. Remote enrichment main and local clean checkout remain ffe3b7112d8e8554ff8288eedebc3350185eafe8. No code edits or test reruns were needed for this evidence review.
- **Stage A is not cleared.** The report assumes R2 5974843 live without proving the change from recorded R1; gives truncated hashes; and places some evidence after its stated completion time. Require full artifact/configuration identity and corrected observation timestamps.
- CONTROL#PROJECTION/GLOBAL is not the human writer fence or coverage key. Require strong keyed presence/absence evidence for CONTROL#HUMAN_CLAIMS/GLOBAL and CURRENT_HUMAN_COVERAGE/VERSION#1, deployed/alternative writer population and existing transaction permissions. Global TTL metadata does not establish immutable/no-TTL human Claim history.
- Gross spend remains unknown: credits-offset ~$0 cannot qualify the pre-credit $500 ceiling/BAU reserve. The report's scan price calculation is unsupported. Approximate item count implies at least ~6,853 inventory pages at the implemented 1,000-item limit, plus one fence read/page, before hydration/verification. Migration needs a separate finite budget and maintenance plan.
- No-CDK-source-change does not prove a complete managed deployment delta. Require A synthesis/configuration/asset comparison against verified live resources and retained live rollback artifacts. Reverting only c36ce68 does not undo the cumulative A package. API #87 Lambda-name separation alone is insufficient release coordination; latest source-runs fix 1ee95d7 has no verified deployment receipt here.
- Empty shadow parity/diff evidence does not qualify C's retained billing keys. Four artifacts claimed/three listed and missing LBP remain C evidence gaps, **not independent prerequisites for A**. B still requires complete certified human history after separately approved migration.
- [Targeted #80 correction order](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5867210518) published. Use retained receipts first; explicitly permits up to ten additional minutes read-only execution, at most residual 28 AWS attempts and a cumulative 32 MiB across both qualification passes, with exact ledger reconciliation, retries disabled and per-call <=60 seconds. No scan/deployment/migration/mutation, implicit renewal, source crawl or API implementation authorized.
- No AWS agent is assumed running. Next action is the AWS agent returning the corrected Stage A evidence under this order. Technical owner reviews before an exact managed A release order; B/C gates stay separate. V1 remains unaccepted.

## Current stop and exact restart

The current implementation package is retained. The owner's first AWS qualification report was reviewed on 28 September and is partial evidence, not release clearance. The next critical-path action is the VSCode/AWS agent completing [#80's targeted correction order](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5867210518), plus the existing API work orders. This ChatGPT session has no AWS execution connection and must not impersonate an active deployment agent. This is a deployment/integration handoff, not a claim that all V1 coding is finished.

1. Confirm main ffe3b7112d8e8554ff8288eedebc3350185eafe8 or inspect subsequent commits. Read this tasklist, latest #7/#80/#37/#81/#82 and enrichment AGENTS.md. Use the same main checkout and preserve any newer work.
2. Obtain the corrected #80 response, preserving the cumulative request/byte ledger. Resolve actual deployed pins/timestamps, managed delta, correct human control/coverage keys, writer population, permissions, gross budget, rollback and #87 coordination. Use existing receipts first; do not restart a broad audit. Do not deploy latest main blindly or write coverage from a sample. Do not run old backfill apply, reset snapshots or replay holds.
3. Issue an exact managed A release order only after reviewing that evidence and coordinating with API refactor #87. Migration approval is separate, finite and based on measured table size/headroom; B requires completed global coverage. C additionally requires retained billing-key compatibility/reconciliation.
4. Review the API command-identity/actor/new-Artist contract (#37) before implementing the remaining whole-action recovery/outbox boundary in enrichment. Current action Claim publication is atomic; S3 Observation, audit append and queue sends are not. Never deduplicate a transport retry by inventing a newer human decision or a body/time heuristic.
5. Other owned work remains explicit: non-human automatic verification history bounds, field-clear semantics, complete early-source entity inventory and run-counter failure/concurrency accounting, profile application integration, daily discovery/cancellation coverage and bounded recovery. Current fixes are partial gates, not proof these are solved.
6. Event distinct-performance behavior and complete API window/pagination depend on #81/#82 response contracts. Preserve canonical uniqueness; do not add an enrichment matcher or bypass the one-day sentinel.
7. Live qualification/recovery and seven complete daily acceptance cycles follow the relevant safety, provenance, accounting, freshness and budget gates. Never substitute test counts or decreased holds for verified canonical outcomes.
