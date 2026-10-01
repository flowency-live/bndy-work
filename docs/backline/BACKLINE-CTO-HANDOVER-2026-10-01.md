# Backline CTO handover, 1 October 2026

## Outcome and working method

**User story:** As a curator, I want Backline to use bndy's accumulated evidence to resolve gigs, remember corrections and show dependable source delivery.
**Task now:** Restore the real reasoning call and blocked source delivery, then demonstrate the decision loop and daily telemetry.
**Done when:** Named supported and conflicting cases produce explained governed outcomes; a fresh human correction survives repeat processing; active sources show attributable daily additions, updates and cancellations with honest coverage.
**Backline impact:** A stable V1 for initial curator onboarding. Successful deployment, test volume and an enabled source are not that outcome.

The owner repeatedly corrected mechanistic drift. Before any implementation or delegation, state the user story, exact task, observable done condition and Backline impact in four short lines. Use AI to reason over canonical history, aliases, source identities and scoped human decisions where ambiguity needs interpretation. Deterministic code should carry evidence, budgets, authority, integrity and application boundaries. Do not solve each hold with another special name/region/venue rule. A website or history at the exact venue is not a prerequisite. Model confidence is not authority. No graph database is needed for this increment.

## Ownership and constraints

- Work in bndy-enrichment, one main checkout. No new branches, PRs or worktrees. Preserve other agents' changes.
- API edits belong to the owner's VSCode agent through bndy-work issues, coordinated with #87. Ops UI belongs to #79. Source-local work stays on its source issue.
- AWS execution is #80, explicit reviewed scope, managed CDK/SAM/CloudFormation only. No direct Lambda updates/hotswap. Do not imply a worker is running merely because an order exists.
- Continue unblocked owned work; stop only on concrete evidence/access, owner policy or execution dependencies.
- Human test history was declared disposable. Version-2 owner-test-reset was initialized at the agreed 28 September cutoff. Do not reopen migration or reset.
- No blanket replay, source-history reset, table scans, broad crawl, automatic provider retry, guessed canonical aliases or removal of the bill-transition guard.
- Every behaviour commit: build and required full check by exit code, [skip ci]. No paid CI. Documentation review does not require another runtime test campaign.
- Public bndy-work must contain only sanitized status and instructions, no private receipts, runtime identifiers, credentials or raw candidate records.
- September's $500 ceiling and dated gross-spend evidence are not proof of October headroom. This handover authorises no runtime expansion.
- Read enrichment AGENTS.md, Constitution, Status, intelligence execution plan, runbook and current V1 tasklist. This dated checkpoint supersedes older incompatible status/stop/deployment instructions, not later owner decisions.

## Code versus production

| Item | State |
| --- | --- |
| Last reported enrichment production release | fadcb8ae525afe8d040a2ac90841f5c7cc520dc8, 28 September; memory initialization included |
| Contextual Artist reasoning | 6632b28 and descendants, implemented; no successful live model proposal demonstrated |
| Safe diagnostic failures | fe6e63c, implemented |
| Request field correction | 7aea0ed, removed temperature; this did not establish the cause or resolve the later 400 |
| Real qualification command | 0b22420221a59b4180162a4fb2c264b1f2a350df, tested; actually executed locally and returned provider rejection |
| KLMA HTML fallback | bbf0f400d43715bb65d70f0e2aab02622637cf8f, source agent reports required full gate passed; undeployed |
| Latest remote enrichment main observed | 9741eaf703aedcc9136f62b1fb0c9afb27c0714a, Diane's Gig List reader; source agent reports required full gate passed; undeployed |
| API evidence integration | Last reviewed #81 pin 6239ffb; narrow response coverage/assertion follow-up outstanding; do not assume API master or live pin |
| This review | Offline evidence processing and documentation only; no runtime code change, AWS/provider call or deployment |

Refresh remote main before implementation. The current local checkout remains at the qualification-era code and has an unrelated modification to docs/sources/MLE-001-CTO-INTEGRATION-2026-09-17.md. Preserve it; do not reset/overwrite to sync. Current remote includes two subsequent source increments. Never deploy 0b224202 as though it were current main.

## Evidence bundle processed

Owner attachment: diagnostic-evidence-80-20261001.zip, 19 files. Raw evidence remains private in the attachment/worker's retained files. The review verified all four source snapshot SHA256 values against the supplied handback, reproduced the original context hash and ran the repository's own venueSlug/transition logic offline. No need to request this bundle again while available.

### A. Actual reasoning failure

Numbered receipts show the real qualifier reserved work, invoked the actual reasoner once, received HTTP 400, and recorded the terminal failure. Prompt size is 2,916 bytes, below the conservative 12,000 bound. The complete 86-byte provider error body is generic: “Request contains an invalid argument.” Code is invalid_request; no rejected field is supplied. It was not truncated.

This is now application-path failure evidence, unlike the earlier custom diagnostic script. It is not model-quality qualification. Secret/preflight succeeded for this execution. There is no proposal or usage response, so do not claim $0 actual cost solely from the absence of usage.

The response-format shape and low thinking setting matched the official contract inspected in the preceding review. That is not proof every model/schema/request combination is valid. Next CTO must inspect the complete serialized request and schema against the official supported model/API contract, keeping this private input unchanged. Do not guess that model name, endpoint, temperature or token size caused this rejection. Fix a demonstrated mismatch; if an actual compatibility probe remains necessary, first write its concrete one-attempt order. Diagnostic02 is spent and must not be rerun or renamed casually.

References to verify when working on the provider: https://ai.google.dev/static/api/interactions.openapi.json and https://ai.google.dev/api/interactions-api .
Real implementation: src/enrichment/providers/gemini-structured-reasoner.ts, artist-identity-reasoning.ts, runtime.ts, identity-qualification.ts, cli/qualify-artist-identity.ts.

### B. Source reconciliation findings

| Source | Baseline rows | Failed-current rows | Actual affected old rows | Whole bills |
| --- | ---: | ---: | ---: | ---: |
| KLMA | 332 | 425 | 55 | 24 |
| Fizgig | 278 | 343 | 2 | 1 |

The worker reported KLMA 51, not 55. Its standalone detect-transitions.mjs reimplemented venueSlug and removes ampersands; the repository maps them to “and”. Four old KLMA keys were therefore omitted. Use the repository function, not another hand-maintained slugger.

The candidate request contains only 53 old expanded keys. All 53 were returned; no unprocessed keys. It omitted four affected old KLMA keys and all 25 whole-bill replacement keys. Complete affected candidate scope is 82 distinct keys; 29 were not queried. The request does not set ConsistentRead, so do not describe these reads as strong. A future mutation needs fresh conditional checks regardless of this historical snapshot.

Returned rows have supporting Claim references and projected Observation markers, without canonicalEntityId. That does NOT prove nothing reached canonical. Inspect the existing projection outcomes/operations and Claims before deciding whether a binding, supersession, cancellation or canonical repair is needed. Do not delete or merge from these candidate fields alone.

CONFIG/STATE snapshots establish delta + complete-snapshot mode and the retained complete baseline pointers. Both sources are additive-only/create-only in the supplied configuration. Repairing the structural guard does not establish update/cancellation delivery.

The “listing changed from multi-act to single-act” explanation is not supported as a general diagnosis: 16 of 24 KLMA bills retain exactly the same billing text, and the Fizgig bill text is identical. This is substantially a normalisation transition; retain bill testimony and legitimate support acts. Remaining spelling/content differences require normal source comparison, not blanket consolidation.

Root code: src/sources/runner/diff.ts detects old expanded keys absent from current while the original key is present. Capture/current normalised evidence exists before that failure. Whole-run guard stays until identity-preserving reconciliation is implemented. The prior rollout's compatibility scope missed KLMA/Fizgig; CTO owns that release gap.

### C. Exact next evidence boundary, not a fresh audit

No new AWS order is executed or authorised by this handover. Prepare a single narrow #80 follow-up only after reviewing the existing stores:
- derive the exact complete 82-key cohort with repository logic; retain the 29 previously unread keys explicitly;
- request strong complete candidate evidence and only the existing per-candidate outcome/Claim keys needed to settle publication state, within an explicit finite envelope;
- reuse the four verified snapshots, configuration and error receipts; no new bucket listing, source crawl or broad logs;
- then implement reviewed conditional, resumable reconciliation preserving human decisions, genuine lineups and canonical identities; qualify an unchanged repeat before any live repair.

Previous accounting: qualifier four AWS calls; source pass nine additional reads. Source cumulative total is six prior plus nine = fifteen, not a reset to nine. No allowance silently renews. The earlier “all diagnostic tasks complete” label does not establish safe repair readiness.

## Priority tasklist for the incoming CTO

1. **Reasoning works:** inspect/fix the actual provider contract, then one reviewed real-path qualification. Evaluate explanation and evidence references, not merely JSON validity. Follow with the still-missing conflicting/insufficient-evidence case, within a separately stated allowance.
2. **Imports recover:** complete publication-state evidence for the exact KLMA/Fizgig cohort and implement identity-preserving reconciliation. Keep valid bills, avoid false cancellations, and show a successful subsequent natural cycle.
3. **Curator loop completes:** finish #81's response evidence contract and #37's authenticated command-id/recovery dependency. Prove fresh correction -> durable scoped memory -> repeat decision. Do not ask the owner to process technical failures as identity questions.
4. **Owner can see delivery:** #82/#79 daily per-source health and actual Added/Updated/Cancelled, success days against cadence, human holds separate from technical failure, completeness/unknown visible. Existing tables/summaries, lazy drill-down, hourly/manual refresh.
5. **Source follow-through:** Lemonrock technical/profile/scheduling/cancellation gaps first; Insangel conditional orphan recovery and exact venue exceptions. Reuse retained successful-source evidence. Integrate KLMA fallback in the eventual cumulative managed release. Review Diane's source integration without delaying the first four outcomes.
6. **V1 acceptance:** named intelligence outcomes, post-cutoff human-memory demonstration, stable natural source cycles and affordable truthful telemetry before calling curator onboarding ready. Open-mic/recurring-session classification is a separate product path, not another artist-name matcher.

## Issue-by-issue status and next owner action

Dates matter: source health statements below are the 30 September snapshot unless the new bundle or later source comment is explicitly named. They are not a fresh live-health certification. Assignment is not evidence of an active agent.

| Issue | Scope | Progress / current status | Next task |
| --- | --- | --- | --- |
| [#7](https://github.com/flowency-live/bndy-work/issues/7) | Programme | V1 incomplete. Contextual reasoning implemented; no successful real model proposal demonstrated. Source delivery and visibility remain uneven. | Own the priorities below and keep the tasklist current. |
| [#80](https://github.com/flowency-live/bndy-work/issues/80) | AWS execution | Evidence bundle reviewed offline. Qualification returned HTTP 400. Source repair has incomplete candidate coverage. | No repeat of diagnostic02. Receive a reviewed request fix or a narrowly specified missing-evidence order from CTO before execution. |
| [#34](https://github.com/flowency-live/bndy-work/issues/34) | Intelligence | Canonical context, human memory and contextual Artist proposal path implemented. Provider qualification failed. | Fix provider integration, then demonstrate supported match, conflicting/insufficient evidence, and governed application. September freeze is superseded. |
| [#81](https://github.com/flowency-live/bndy-work/issues/81) | API integration | Last reviewed Artist resolution change 6239ffb. History and coverage support partly accepted; response-contract assertions still outstanding. | Tighten existing unresolved-response assertions and scored coverage propagation; finish profile/application dependencies. No further name/region policy expansion. |
| [#83](https://github.com/flowency-live/bndy-work/issues/83) | Native identity | Adapter-asserted identity and API exact-key changes reported implemented; Lemonrock index/profile parity remains explicitly incomplete. | Reconcile existing release evidence, then complete sourceIdentity parity when profile intake is enabled; no synthetic/name-derived identity binding. |
| [#82](https://github.com/flowency-live/bndy-work/issues/82) | Telemetry API/producer | Per-run work exists; daily source health and Added/Updated/Cancelled overview remains open. | Use bounded existing summaries with London operation dates, distinct outcomes, completeness and drill-down. API agent implements; CTO owns producer gaps. |
| [#79](https://github.com/flowency-live/bndy-work/issues/79) | Ops UI | Daily source delivery view requested; no completion handback found for the latest scope. | Consume #82; distinguish acquisition/publication, technical errors/human decisions, shadow/manual/parked and unknown history. Hourly/manual refresh. |
| [#40](https://github.com/flowency-live/bndy-work/issues/40) | Source visibility | Historical counting defects and earlier releases are recorded; complete current daily outcome coverage is not established. | Use #82/#79 as implementation lanes, not a second reporting system. |
| [#59](https://github.com/flowency-live/bndy-work/issues/59) | Lemonrock | 30 September report: gig hydration operating; artist/venue hydration prolonged failures; discovery/cancellations shadow; reconcile stale. One artist sample proves DynamoDB DNS EBUSY only. | Separate sampled technical failure from policy/scheduling gaps; prove new/changed gigs and cancellations. Existing client reuse fix is already in code. |
| [#72](https://github.com/flowency-live/bndy-work/issues/72) | KLMA | Bundle confirms billing transition blocker. Actual shared logic finds 55 old rows across 24 bills. HTML fallback bbf0f400 implemented, source tests/full gate reported passing, undeployed. | CTO owns identity-preserving bill reconciliation. Include fallback in cumulative release; do not treat acquisition resilience as fixing the guard. |
| [#70](https://github.com/flowency-live/bndy-work/issues/70) | Fizgig | Bundle confirms 2 old rows into 1 bill; historical split includes a placeholder performer. 48 consecutive failures in supplied state. | CTO reconciles existing Claims/publication safely. Do not remove guard or infer cancellation from normalisation changes; preserve valid other multi-act lineups. |
| [#75](https://github.com/flowency-live/bndy-work/issues/75) | Insangel | 30 September report shows acquisition active since 20 September; no correlated terminal evidence or repair receipt. | Correlate retained run/terminal outcome and design conditional recovery. Do not blindly clear active fields or restart ingestion. |
| [#23](https://github.com/flowency-live/bndy-work/issues/23) | Venue readers | 30 September snapshot: Rigger operating; Flowerpot shadow; Eleven/Sugarmill failing, Hairy Dog failing in shadow. | Obtain exact retained exceptions for each affected reader before assigning a cause. KLMA/Fizgig correlation does not prove a shared cause here. |
| [#22](https://github.com/flowency-live/bndy-work/issues/22) | Live Band Photos | 30 September snapshot reports successful runs; earlier source capture/location coverage acceptance remains open. | Use retained captures and bindings to close specific omissions and prove next root/band cycle. No invented locality or broad recrawl. |
| [#71](https://github.com/flowency-live/bndy-work/issues/71) | Gigs News | 30 September snapshot reports daily success; legacy binding/update-policy acceptance remains open. | Preserve lineage, verify attributable new/changed/repeat outcomes. Do not equate a successful source run with canonical delivery. |
| [#73](https://github.com/flowency-live/bndy-work/issues/73) | OnTheCase | 30 September snapshot reports operating hourly; earlier parser work and lineage tasks retained. | Qualify named canonical delivery/repeat from retained evidence; avoid optional directory/profile fanout. |
| [#74](https://github.com/flowency-live/bndy-work/issues/74) | Scenic Eye | Continuation/coverage work integrated historically; 30 September snapshot reports daily success. | Qualify current eligible natural-cycle canonical outcomes; do not recreate completed adapter work. |
| [#33](https://github.com/flowency-live/bndy-work/issues/33) | BandForge | Origin-restricted/disabled in 30 September snapshot; source continuation previously implemented. | Complete per-row upstream attribution before activation. Preserve parked Music Live policy and identities. |
| [#30](https://github.com/flowency-live/bndy-work/issues/30) | Fantastic All Library | Manual-assisted by policy; last reported success 8 September and later failed attempts. | Keep permitted manual intake and explicit coverage; no unattended Facebook crawler or misleading automated-health status. |
| [#32](https://github.com/flowency-live/bndy-work/issues/32) | Music Live | Parked by owner; historical hold-suppression acceptance remains separate. | Do not activate, publish, recrawl or repeat old launch orders. Preserve evidence and mixed-source support. |
| [#76](https://github.com/flowency-live/bndy-work/issues/76) | Music Live bridge | Parked with #32. | No competing direct writer or restart. |
| [#119](https://github.com/flowency-live/bndy-work/issues/119) | Diane's Gig List | Source reader 9741eaf7 implemented and tested; 479 pre-policy records from retained index, 284 profile IDs. Not registered/deployed/activated. | Review supplied shared integration patch, bounded scheduling/profile refresh and venue-directory gap. Preserve disabled/shadow planning state until reviewed rollout. |
| [#37](https://github.com/flowency-live/bndy-work/issues/37) | Human authority | Atomic current-human Claims and version-2 test-memory start deployed; full human-command recovery/actor feedback contract remains open. | Agree stable command identity at authenticated action boundary, then retained idempotent recovery. Do not repeat disposable-test migration. |
| [#47](https://github.com/flowency-live/bndy-work/issues/47) | Learned decisions | Current-human memory implemented; general cross-scope learning is not demonstrated. | Reuse scoped Claims, provenance and supersession. Prove a fresh correction is remembered; do not turn every resolution into a global name rule. |
| [#39](https://github.com/flowency-live/bndy-work/issues/39) | Curator questions | Curator enrichment queue remains a product dependency; this handover does not establish delivery. | Expose useful scoped missing/conflicting facts, answer/skip/not-known, and accepted contribution outcomes. Keep technical failures out of curator identity work. |
| [#50](https://github.com/flowency-live/bndy-work/issues/50) | Legacy lineage | Existing source-ID reconciliation contracts retained; no new backfill performed. | Use exact existing Artist/Venue/Event bindings in a named cohort; no name-only matches, scans or recreated imported events. |
| [#77](https://github.com/flowency-live/bndy-work/issues/77) | Venue ignore | Shared global venue-ignore specification remains open; no new implementation evidence. | One scoped authoritative control, enforced before publication with history retained; reconcile #46 and Ops UI. |
| [#46](https://github.com/flowency-live/bndy-work/issues/46) | Excluded venues | Overlaps #77. | Deliver through the shared #77 contract, not separate source lists; no new completion claim. |
| [#69](https://github.com/flowency-live/bndy-work/issues/69) | Checkpoint reads | Repair implemented/integrated historically; final issue-specific live acceptance not reconciled. | Link retained managed-release evidence before closure. Do not rebuild or run an audit just to fill the checkbox. |
| [#68](https://github.com/flowency-live/bndy-work/issues/68) | Cost/architecture | Historical global freeze superseded. September budget/spend is dated, not October headroom. | Keep bounded economical BAU and reuse retained evidence. Establish current envelope only when a concrete new runtime expansion needs it; no general audit restart. |
| [#78](https://github.com/flowency-live/bndy-work/issues/78) | Publication policy | Existing owner policy remains in force; shared admissions work has progressed through later releases. | Preserve scoped authority, permitted venue verification, optional artist websites, inferred performing region not home. No blanket activation. |
| [#6](https://github.com/flowency-live/bndy-work/issues/6) | Capture | Evidence delivery reported deployed historically; full route convergence not proven by that receipt. | Preserve evidence-only recovery and immediate authorised human publication; reconcile actor/revision feedback with #37. |
| [#21](https://github.com/flowency-live/bndy-work/issues/21) | Festival monitoring | Broader BAU/progressive programme monitoring remains backlog; no new delivery evidence in this bundle. | Preserve bill and cancellation semantics; do not expand this into the immediate V1 repair. |
| [#85](https://github.com/flowency-live/bndy-work/issues/85) | Recurring sessions | Venue-owner creation has a separate API work order; no completion comment found here. | Keep imported open-mic/recurring listing classification distinct from Artist resolution and from owner creation permission. Route API implementation through its existing owner. |
| [#105](https://github.com/flowency-live/bndy-work/issues/105) | Curator verification | Issue comment reports API/app shipped and closed. | Preserve shipped work; use #37 to verify attributable feedback into Backline, not a new publication gate. |
| [#106](https://github.com/flowency-live/bndy-work/issues/106) | Curator flags | Issue comment reports API/app shipped and closed. | Preserve current routing; no reopening or rebuild from this diagnostic handover. |
| [#107](https://github.com/flowency-live/bndy-work/issues/107) | Public verification | Issue comment reports live route checked and closed; legacy absent verification intentionally reads unchecked. | Preserve response contract and privacy. No blanket backfill. |
| [#87](https://github.com/flowency-live/bndy-work/issues/87) | API refactor | Separate API build/auth consolidation remains a coordination constraint. Later #81 suite reportedly passed, but current integrated runtime not independently qualified here. | API agent owns code. Preserve concurrent changes; #81/#82 carry Backline requirements, #80 carries reviewed runtime execution. |
| [#58](https://github.com/flowency-live/bndy-work/issues/58) | API routing | Standing wider API work log remains active for other product lanes. | Backline runtime is #80; Backline implementation dependencies #81/#82, coordinated with #87. Do not resurrect old Backline release pins. |
| [#19](https://github.com/flowency-live/bndy-work/issues/19) | Performance variants | Approved backlog; no new implementation or merge evidence in this handover. | Preserve billed-name testimony and distinguish variants from separate acts. Reuse existing identity foundation; no blanket Artist merge. |
| [#20](https://github.com/flowency-live/bndy-work/issues/20) | Artist lifecycle | Approved lifecycle/discovery backlog; no new delivery evidence in this handover. | Retain canonical historical/dormant identities for reasoning. Separate discovery visibility from existence; do not delete useful evidence-backed artists. |

## Resume without repeating work

- Keep BACKLINE-V1-TASKLIST.md and #7 current at each material checkpoint.
- Read the latest comments on the specific issue before claiming files; do not activate all source agents.
- Existing upload is the starting evidence. If it is unavailable in a new session, request that one bundle, not another AWS collection.
- Do not resubmit the rejected custom diagnostic, repeat memory migration, recreate source adapters, or rerun the full test suite just to read this handover.
- A local successful model call will still not prove the Lambda's role/configuration. A deployment will still not automatically replay held records.
- No source/API code was changed in this handover. Issue status updates do not mutate native Project fields, close unresolved work or start workers.
