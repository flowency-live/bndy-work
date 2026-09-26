# Backline V1 working tasklist and session handover

Updated 26 September 2026. Accountable technical owner: current ChatGPT session, programme [#7](https://github.com/flowency-live/bndy-work/issues/7).

## Owner instructions, 26 September

- Implementation ownership is exclusively bndy-enrichment, on main. No new branches, PRs or worktrees.
- All bndy-serverless-api changes go into explicit bndy-work work orders for the VSCode agent with AWS CLI. Coordinate with the ongoing API refactor (#87); do not edit that repository from this lane.
- Keep this document current at meaningful checkpoints and before ending a session. Link evidence and exact next steps on #7. Never imply an inactive worker is running.
- V1 enables a stable curator rollout. Urgency must not produce bypasses, name-specific exceptions or weaker safety gates.
- No graph database is proposed. Assemble connected evidence, scoped authority, identity, history and human decisions using the existing stores.
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
| V1-01 | Partial — next | Canonical lookup correctness: conflict-aware identity; rename/delete invalidation; bounded retry of incomplete writes; human corrections precede cached matches. Positive and negative regression cases must prove the decision. | Backline-owned. Inspect current code before design; preserve canonical API resolution where context cannot decide. |
| V1-02 | Pending | Billing and title interpretation: one decision per bill; preserve real composite acts and evidenced lineups; no invented fragment acts; stamp source on creation. | Existing billing containment policy; any model activation remains separately bounded/approved. |
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
- Additional claimed files: src/knowledge/stores/clients.ts (transaction command type), src/cli/canonical-lookup-backfill.ts (retire obsolete unversioned writes), test/projection-bndy-api.test.ts (test-token isolation), test/canonical-context-integrity.test.ts (new integration regressions), and entry/status/plan documents.
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

## Exact next session

1. Confirm enrichment main remains 204e043 or inspect subsequent commits before editing. Read latest #7/#80/#37 comments. The completed code checkpoint is durable; do not redo its audit or create a new branch.
2. Finish V1-01 Artist human-decision precedence in `src/projection/engine.ts` with existing engine tests: a remembered one-act mapping currently bypasses `verificationEvidence`; `humanConfirmedNew` is evaluated after automatic context; a stale resolvesTo can outrank a later confirmed-new decision. Current human name/identity decisions must precede cache and context without relaxing source creation policy.
3. Test corrections against an existing mapping, contradictory automatic context, superseded human decisions, missing/deleted canonical targets, retry/idempotency and additive-only protections. Keep canonical validation authoritative; inspect existing API contracts before asking for an API addition.
4. Check whether event-candidate human decisions can be pushed outside the bounded 300-claim materialisation window. Do not declare persistent human memory solved merely because the latest small fixture passes.
5. Continue V1-02/03 and #82 producer work in order, claiming exact additional files on #7 before expanding scope. Coordinate the #37 feedback payload with the VSCode agent's refactored boundary; do not implement API changes here.
6. Update this file and #7 at the next meaningful checkpoint. No background coding worker remains active when this session ends.

## Deployment and acceptance dependencies

- Existing unversioned lookup rows intentionally cannot supply authoritative context. Until reviewed revision-aware hydration/current stream evidence covers them, canonical resolver calls or holds may increase. Absence of a local hit is not evidence of a new entity.
- Design and qualify a bounded migration/readiness plan before requesting deployment; the old unversioned backfill is not usable. Do not bulk reindex or replay from this coding checkpoint.
- Qualify stream/projection worker compatibility together, transaction IAM support, existing sync-state shape, ambiguous ordering, large alias sets, read/write cost, and rollback consequences. New observation identities include stream identity/event ID; do not assume old receipt identities are unchanged.
- Reported R1/R2 live pins above remain historical. This commit does not supersede #80 with a deployment order. Obtain exact managed release review against current live state before execution.
- Curator route completeness/authority/feedback (#37), remaining identity/billing defects, reporting reconciliation (#82), <=24h supported freshness and seven complete daily acceptance cycles still gate V1.
