# Backline V1 working tasklist and session handover

Updated 29 September 2026. Accountable technical owner: current ChatGPT session, programme [#7](https://github.com/flowency-live/bndy-work/issues/7).

## Owner instructions, 26 September

- Implementation ownership is exclusively bndy-enrichment, on main. No new branches, PRs or worktrees.
- All bndy-serverless-api changes go into explicit bndy-work work orders for the VSCode agent with AWS CLI. Coordinate with the ongoing API refactor (#87); do not edit that repository from this lane.
- Keep this document current at meaningful checkpoints and before ending a session. Link evidence and exact next steps on #7. Never imply an inactive worker is running.
- V1 enables a stable curator rollout. Urgency must not produce bypasses, name-specific exceptions or weaker safety gates.
- No graph database is proposed. Assemble connected evidence, scoped authority, identity, history and human decisions using the existing stores.
- A commit checkpoint is not a deployment dependency. Continue unblocked enrichment implementation; distinguish coding, API integration and live acceptance gates explicitly.
- Current deployment queue is #80. Production deployments and data recovery remain separately scoped; no cleanup, redrive or replay follows from coding authority.

## Task communication, owner instruction 28 September 2026

For every task, including AWS/API work orders and handoffs, tell the owner briefly:
- **User story:** As a [user], I want [capability], so that [benefit].
- **Task now:** The precise work being done, including whether it is coding, deployment, verification or preparation.
- **Done when:** The observable result that completes this task.
- **Backline impact:** How it improves evidence, memory, reasoning, decisions or curator experience. Label supporting infrastructure work honestly; do not present it as delivered intelligence.

Use clean, succinct language, normally four short lines. At completion or a blocker, report against that same outcome and state the next step. Distinguish implemented, deployed and demonstrated behaviour. Keep the active story and outcome in the shared tasklist so a new session can resume it.

Tie technical subtasks to an existing user outcome. If a task cannot explain that connection, reconsider its scope before expanding it. Tests, code volume, audits and deployments are evidence or means, not the product outcome. This communication rule creates no new approval gate or document workflow.

## Active user story and task

**User story:** As a curator, I want Backline to recognise an existing act from bndy's established gig history without requiring a website.

**Task now:** Enrichment portion committed and checked at **9e6bbefa8b2fe3d2c8930d29abefba93f069c387**. The primary resolver correction is in the API repository and has an executable [VSCode work order #81/5889481419](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5889481419), coordinated with #87. No API worker is assumed active.

**Done when:** The API considers history before excluding plausible full/short names, explains supported matches/contradictions, and the integrated release demonstrates that behaviour on named holds.

**Backline impact:** Uses accumulated bndy knowledge in identity decisions. This enrichment patch alone does not complete history-based matching; it preserves useful evidence, accepts supported names in the external fallback and removes the website-demand question.

**Owner correction, 29 September:** Canonical gig history is admissible identity evidence. Public web searches did not adjudicate Undercovers and must not displace existing bndy knowledge by default. No owner correction has yet been reported submitted; the separate current-human memory demonstration remains open.

**Memory decision unchanged:** Earlier holds are disposable tests. Applied cutoff **2026-09-28T16:23:54.000Z**; later decisions retained. No migration.

## Current state, 28 September

**Reported live implementation: fadcb8ae525afe8d040a2ac90841f5c7cc520dc8.** BndyEnrichmentStack UPDATE_COMPLETE at **18:05:13Z**, eleven code-only Lambda updates. The corrected Stage A predecessor time is **13:10:01Z**, superseding the earlier 14:11:11Z report.

Version-2 owner-test-reset initialized in four calls. Ten verification reads reported health OK, a valid empty current-human read on an unused subject and no observed coverage-unavailable or billing-transition errors. Full private coverage identity/receipt remains with AWSCLI; the owner summary truncates that ID.

Examined baselines: three empty Lemonrock root feeds; lemonrock-gig-hydration run-b71207a9, one single-act event; LBP run-6f5b37a7, one single-act event. No expansion metadata in those examined artifacts. This is not a full historical-import inventory. No additional audit follows from release acceptance.

Accepted handback: [#80/5875912460](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5875912460). Enrichment main subsequently advanced to **9e6bbefa8b2fe3d2c8930d29abefba93f069c387**, an undeployed behavioural change. The live pin remains fadcb8a; see the current API dependency above. This session has not independently queried AWS.

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
| V1-01 | fadcb8a live; 9e6bbef enrichment correction ready; API history correction #81 pending | Canonical lookup correctness: conflict-aware identity; rename/delete invalidation; bounded retry of incomplete writes; human corrections precede cached matches. Positive and negative regression cases must prove the decision. | Backline-owned. Inspect current code before design; preserve canonical API resolution where context cannot decide. |
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

### 28 September: second qualification review and exact resource resolution

- Owner supplied corrected report: 48 cumulative AWS attempts, ~100 KB, absent human fence/coverage keys, and claimed R1 live. Accept reported key absence as valid pre-migration state; retain strong-read receipts. Timestamp ordering still does not prove R1's deployed package. Code hashes must map to retained managed assets for every affected worker, including BacklineAdminApi.
- **Stage A remains NOT CLEARED.** No synthesized managed delta/live configuration comparison or transaction-permission evidence was supplied. No-CDK-source-change is insufficient. Rollback must retain verified live assets/template/parameters; rebuilding a presumed Git revision alone is not qualification.
- Read-only API review at ab5763d4720274042eda23aa4eed2b674a919f8e, template blob bbb648f59aa162afd1151cad20aa18e0d944cb1c, resolves the source-runs naming issue: logical ID **SourceRunsFunc** in template.yaml. It references the Backline table with CRUD permissions and proxies hold actions to the Backline admin API. ArtistsFunction also writes Backline evidence, and enrichment consumes canonical streams. The “separate stacks/no shared resources” readiness conclusion is invalid. These source facts do not establish the deployed API pin.
- Reviewed Artist and Venue API evidence writers use frontstage-user-created-artist and join-user-created-venue, respectively; they are not godmode:human publishers in those files. Do not expand this migration's source scope or infer complete deployed writer coverage.
- [Exact final evidence order](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5869472472) supplies the keyed CloudFormation SourceRunsFunc lookup and an UnblendedCost query excluding Credit/Refund. Requests three packages: retained live assets/rollback mapping; synthesized A managed delta/IAM/API coordination; gross headroom with billing lag and BAU reserve. No broad regional search or billing-console detour unless a concrete access gap remains.
- Report ledger needs reconciliation: 11:52–12:05 is 13 minutes against the previous ten-minute correction bound; cumulative ~18 minutes conflicts with the earlier ~8-minute pass. 32 MiB minus ~100 KB is ~31.9 MiB, not 32.8 MiB. New order explicitly allows one final <=10-minute read-only collection with **at most the residual 12 attempts and cumulative 33,554,432 bytes**, only after exact reconciliation; reduce bounds for any additional consumption. No implicit renewal.
- Migration lifecycle/TTL proof remains a maintenance prerequisite; C billing artifacts remain a later gate. No AWS mutation, deployment, scan, migration, API edits, enrichment edits or test reruns by this session. Enrichment main remains verified clean at ffe3b7112d8e8554ff8288eedebc3350185eafe8.
- Next: AWS agent returns the concrete evidence packages or identifies missing artifact/access and stops. Technical owner reviews before release; no agent is assumed active.

### 28 September: owner authorises Stage A deployment

- Owner explicitly directed “We can just deploy as is” after discussion of the missing historical manifest/backup. [Deployment order issued on #80](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5870249194); earlier readiness blocks on recovering the historical package are superseded.
- Deploy only A c36ce685efd984ebf9695f625a08c4bd92bbe871 using normal CDK/CloudFormation, with normal rollback enabled, existing configuration preserved and the complete managed change set reviewed. No additional permission is required if the intended A delta is clean. Stop only for an actual unexpected destructive/IAM/configuration/dependency change or execution failure.
- Latest main includes the B reader and must not be deployed before migration. No migration, fence acquisition, coverage marker, replay, cleanup, API edit or source activation accompanies A.
- Final AWS report supplied by owner: 54 cumulative qualification calls/~110 KB; live function identities retained but no historical commit mapping; SourceRunsFunc's Backline dependency confirmed; estimated gross September spend $130.30, $369.70 headroom, proposed $150 BAU reserve. Claimed API fix identity remains a report, not independent proof from timestamps.
- End the historical-manifest search and repeated cost/source qualification. New authorisation covers one normal managed release attempt and limited verification, separately from the exhausted qualification time windows. Retain the new A release assets/commit/results.
- Enrichment implementation is unchanged. No deployment has been executed by this ChatGPT session and no AWS agent is assumed active. Await actual release completion before claiming A is live.

### 28 September: Stage A deployment reported successful

- AWSCLI handback supplied by owner reports A c36ce68 deployed via the managed workflow in 194.12 seconds, with all 11 listed Lambda updates complete. Current A asset manifest retained. This session has not independently read AWS; no migration or coverage publication has been reported.
- Supplied completion time 14:11:11Z needs a UTC/BST correction from the retained CloudFormation receipt; this is recording housekeeping, not a reopened deployment gate.
- [Next #80 task](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5870631793): complete the existing limited smoke check, verify fence-aware deployed writers/lifecycle/permissions, and return a concrete finite migration plan with cost and maintenance duration. Use existing receipts and offline plan mode first; at most 12 additional keyed/configuration read attempts / 32 MiB / ten minutes if needed. No scan, fence acquisition or migration under this preparation order.
- Product outcome remains dependable curator memory: migrate historical godmode:human decisions, verify complete coverage, then deploy B's reader. A alone does not complete this story or V1 acceptance. Keep source billing C and API work orders separate.

### 28 September: Artist investigation implemented and checked

- Enrichment main [b333b4788b52f774350de106957be5e13562daf4](https://github.com/flowency-live/bndy-enrichment/commit/b333b4788b52f774350de106957be5e13562daf4), parent 5202e99. Ten files; exact local/remote commit tree matched, clean main checkout. No branch, PR or worktree.
- Extends the existing queue/worker with verify-identity. Candidate context, source/native identity and partial Venue history are retained with grounded discovery evidence. Supported official profile facts require an exact booking cited on that profile's own pages, independently of supplied publisher hosts. Separate same-name pages are insufficient.
- Canonical resolution remains responsible, with no creation/external lookup for the evidence result and no selection outside the reviewed candidates. Human decisions and existing native bindings precede discovery. Incomplete lookup stays a technical gap. No broad Artist/name Claim or profile mutation.
- Retained scoped result prevents unchanged paid investigation repeats; queue-send failure is repaired from that result. Provider outage is retained as uncertainty. Interrupted reservations without a result require targeted technical recovery and never silently repeat provider work.
- Validation: npm run check exited 0; build, 198 Vitest files / 2606 passed / 5 skipped, plus 56 recovery passes. Thirty added behavioural cases, Vitest 13.83 seconds. Retained cases and synthetic collision checks are offline evidence, not proof of live provider citation quality.
- File claim/result: #7/5872530212 and checkpoint #7/5872801535. Source implementation and limits documented in BACKLINE-ARTIST-INVESTIGATION.md; Status updated. No AWS/API changes, live model calls, paid CI, deployment, migration or replay.
- The new commit inherits B's current-human coverage prerequisite and C's retained billing-key transition. A remains the reported live pin. Broad migration preparation stays paused; no new execution order is implied.

### 28 September: owner-approved disposable-test memory transition

- Owner clarification: previous holds were disposable tests; cutoff 2026-09-28T16:23:54Z. Decision/file claim [#7/5874185210](https://github.com/flowency-live/bndy-work/issues/7#issuecomment-5874185210).
- Enrichment main [fadcb8ae525afe8d040a2ac90841f5c7cc520dc8](https://github.com/flowency-live/bndy-enrichment/commit/fadcb8ae525afe8d040a2ac90841f5c7cc520dc8), parent b333b47. Six files, one main checkout, exact local/remote commit/tree matched; no branch/PR/worktree.
- Reader accepts explicit version-2 owner-test-reset coverage, separate from version-1 migrated history. Filters current references at/before the cutoff; later atomic writes, withdrawals and tied conflicts remain available. Historical Claims stay stored. No canonical edits, mappings, holds or ignore rules are undone.
- New human-memory-start CLI: offline plan; apply uses at most four strong keyed/conditional transaction calls, no SDK retries, ten-second per-call timeout. Refuses different existing coverage and maintenance; same-plan rerun reconciles lost response. Requires retained proof that all human publishers had the atomic writer before the cutoff. No marker was applied in this session.
- Build/focused checks passed (204 cases across three files). Required npm run check exited 0: 198 Vitest files, 2611 passed / 5 skipped, 56 recovery passed, Vitest 13.45 seconds. Five targeted additions. Compiled help/offline plan passed, zero network calls.
- Rollout and Status updated. Broad migration is unnecessary for this owner choice. Do not deploy the older B/C reader against the version-2 marker. Next release must use a compatible descendant and cover the cumulative managed delta.
- Remaining specific input: saved multi-act gig baseline compatibility. [One AWSCLI read/offline order](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5874307544): retained evidence first, at most 20 exact read attempts / 16 MiB / five minutes collection if needed; no scans, fresh source crawl, mutation or deployment.

### 28 September: baseline handback reviewed; exact conditional release ordered

- Owner supplied the worker's 20-call handback: lemonrock-new-gigs, lemonrock-future-reconcile and lemonrock-cancellations baselines empty; livebandphotos-gig-listing one single-act event. A receipt reiterated c36ce68 at 14:11:11Z, eleven updates.
- Code review corrected its interpretation: billSize/billOrdinal and per-act expansion were already present at A; target prevents speculative expansion and preserves one native composite identity. Root discovery rows do not qualify actual Lemonrock gig history. lemonrock-gig-hydration is the missing concrete entry. One LBP page also does not prove complete historical coverage.
- Main verified unchanged/clean at fadcb8ae525afe8d040a2ac90841f5c7cc520dc8. A-to-target cumulative delta: 29 files, +1355/-130; no CDK/dependency source change found. No source code changed or tests rerun for this evidence review.
- [Release order #80/5875121025](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5875121025) folds that gap into preflight so AWSCLI proceeds without another owner round trip when clear. Retained inventory/receipts first; at most four exact additional reads / 8 MiB / two minutes for the named Lemonrock CONFIG/STATE and referenced baseline objects. Missing/affected scope stops before mutation; no global audit or baseline edits.
- After complete managed-diff review and preflight, initialize the exact cutoff with human-memory-start (four calls normal path, six total including the specifically bounded lost-response reconciliation), then one normal CDK/CloudFormation release of fadcb8a. Existing configuration, API dependencies and caps preserved; no intermediate B/C or direct Lambda update.
- Post-release application smoke: at most twelve reads / 8 MiB / ten minutes. Normal managed deployment polling is separately covered. No replay, provider allowance increase, new crawl or fabricated canonical test data. Natural investigation absence is reported as not demonstrated.
- Previous missing historical-manifest gate remains waived. Owner test-memory disposition is settled. Stage A remains the reported live pin until an actual completion handback.

### 28 September: fadcb8a deployment accepted from AWSCLI handback

- Owner reports exact fadcb8ae525afe8d040a2ac90841f5c7cc520dc8 live, stack UPDATE_COMPLETE 18:05:13Z, eleven code-only updates. Corrected predecessor Stage A time 13:10:01Z. No actual deployment was performed by this ChatGPT session.
- Missing Lemonrock gig-source entry supplied: run-b71207a9, one single-act event with no expansion metadata. Other examined artifacts: three empty Lemonrock roots and LBP run-6f5b37a7, one single-act event. Preserve the stated scope; no claim of universal historical compatibility.
- Memory initialization completed in four calls, version 2, status owner-test-reset, cutoff 16:23:54.000Z. No test-history migration. Ten smoke reads passed health/current-human read and found no specified recent errors.
- No BAU Artist investigation observed. Release completion accepted; intelligence-quality and seven-day V1 acceptance are not implied. A genuine post-cutoff human correction also remains to be demonstrated.
- [Accepted handback and next task](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5875912460). Status updated at doc-only main 833ab8455896ea1b014e9dcbf3f864422c9ba213; local/remote tree matched. No runtime code change, test rerun, new AWS order or audit.

## Current stop and exact restart

1. **Activate the owner's VSCode API implementation agent on [#81/5889481419](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5889481419).** Coordinate files with #87 and use current master. This is the actual implementation dependency, not an owner decision about the band and not an AWS audit.
2. Review its code/test handback. Preserve the existing canonical resolver; no second matcher or name rewrite in enrichment. Ask for existing bndy history/provenance on the named cases, without broad scans.
3. Enrichment main/local checkout are clean at 9e6bbefa8b2fe3d2c8930d29abefba93f069c387. Required check passed; no need to rerun unless changed. Implementation details in [#7/5889585025](https://github.com/flowency-live/bndy-work/issues/7#issuecomment-5889585025).
4. Issue exact managed release order through #80 once the API delta is reviewed. [Dependency handoff #80/5889587941](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5889587941) is not permission to deploy an unreviewed API pin or replay holds. No AWS worker is assumed active.
5. Current live remains reported fadcb8a. No migration, test reset, historic-manifest search or new compatibility audit. Named-case investigation/canonical receipts are still needed before claiming live intelligence quality.
6. Current-human correction demonstration and other V1 API/accounting/profile/freshness/acceptance work remain open. No further owner hold processing is needed to implement this fix.

### 29 September — owner hold examples: diagnosis checkpoint

**User story:** As a curator, I want Backline to distinguish a shortened artist name from a different act, so I only answer genuine identity questions.
**Task now:** Read-only code/evidence review of The Originals (Marple Conservative Club, 2026-10-03) and Undercovers (Cove Ivy Leaf Club 2026-10-10; Knaphill WMC 2026-11-28; Odiham & Greywell Cricket Club 2026-12-18).
**Done when:** Identify supported identity evidence and the actual reason investigation did not resolve each case.
**Backline impact:** Evidence-based identity reasoning; avoid both unnecessary holds and incorrect merges.

Findings:
- Originals: owner identifies The Originals Sixties Band as the local existing act. Plausible shortened-name case; this session has not independently verified the exact booking/profile link.
- Undercovers: do NOT treat Sussex Undercover Band as a confirmed match. Official https://www.undercovers.me.uk/ describes a Hartley Wintney act established 2007, working Hampshire/Surrey/Berkshire. Its band description matches the retrieved Lemonrock Cove listing. https://undercoverband.live/ describes a different four-piece formed 2018, with different members; its gig list is Sussex-based. Strong evidence of separate acts, but exact held dates/current canonical profiles still need linking. Official booking source: https://www.undercovers.band/index.php/home/gigs/ .
- Code at live fadcb8a / main 833ab84: src/enrichment/artist-investigation.ts rejects artist and booking names unless they exactly equal the incoming normalized name. This can discard official full-name evidence for a shortened listing. It is a general limitation, NOT yet proven to be the executed cause of these holds.
- Knaphill wording comes from the investigation-pending path. It shows an investigation was requested, not that it completed or remains active. Other two retain generic canonical-review text; deployment does not itself replay old holds.
- Resolver only accepts initial canonical candidates. A discovery identifying a different band cannot silently select/create it. Preserve this safety boundary while making the evidence and next decision useful.
- No owner correction has been reported submitted; current-human memory demonstration remains pending.

Next: obtain the existing Knaphill investigation result/reprojection receipt for this exact booking, then address any evidenced general alias/evidence gap. Do not merge these acts on name/region, add artist-specific exceptions, replay all holds or expand crawls. No AWS calls, code changes, test rerun, canonical writes or deployment this session. Main remains clean at 833ab8455896ea1b014e9dcbf3f864422c9ba213.

### 29 September — canonical history correction implemented in enrichment; API dependency issued

**User story:** As a curator, I want Backline to recognise an existing act using established bndy gig history without needing a website.
**Task now:** Enrichment portion committed on main at 9e6bbefa8b2fe3d2c8930d29abefba93f069c387; API resolver correction assigned to the owner's VSCode agent.
**Done when:** The API uses that history for plausible full/short names and returns an explained match or remaining contradiction; combined release and named-case evidence then demonstrate it.
**Backline impact:** Canonical knowledge participates in identity. External-profile evidence remains a fallback, not the only admissible evidence.

- Ten files, one main checkout; exact local/remote tree b4aa9f355b235d77a2b72cf20700f57c51e164ee matched, local clean. No branches, PRs or worktrees.
- HTTP reader preserves canonical Event IDs and venue names/localities. Investigation carries up to eight referenced gigs across venues, plus existing exact-venue dates, and records partial coverage/Event IDs in its trace.
- Supported full canonical names/recorded aliases can pass external-profile assessment when linked through a unique already-known cited profile. Text resemblance alone and conflicting/shared profiles do not establish the alias. Assessment v2 is fingerprinted; outstanding v1 jobs keep their original policy and ID. Existing caps/reservation/reuse remain.
- Removed the curator-facing demand for an official profile. Constitution and investigation docs now state canonical history is positive identity evidence and a website is not required.
- Main cause needs API code: similarity filtering precedes footprint assessment; later containment candidates can miss history, and footprint read errors silently become empty evidence. API source reviewed at 907330bf861ab59de083f620dafbc18927168066, not claimed live.
- Exact executable implementation order: [#81/5889481419](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5889481419); refactor coordination [#87/5889564970](https://github.com/flowency-live/bndy-work/issues/87#issuecomment-5889564970). No API file edited here. Do not add a second enrichment matcher or force full-name substitutions into the resolver.
- Three read-only BNDY searches confirmed Originals 0574ef35-82c5-40a9-98f3-22b7628a8698 and Sussex Undercover Band a25b2473-1190-4132-a94b-6c5cd1390377. Exact Undercovers search returned no matches, which is not identity disproof. Tools do not expose history; actual held identities/pending Knaphill result remain unverified. Earlier public-web comparison did not supersede bndy's own evidence.
- Focused three-file checks passed. Required npm run check exited 0: build, 198 Vitest files, 2615 passed /5 skipped, 56 recovery passed. Four new focused regressions; existing projection/HTTP tests extended. No paid CI or live model discovery; no direct AWS calls.
- Enrichment alone does NOT deliver history-based matching. Stop on the API implementation boundary, not on owner hold review. Activate the API agent with the linked work order; after handback technical owner reviews exact integrated pins and issues #80 managed release/limited named-case checks. No new audit, migration, bulk replay or deployment has been ordered.

