# Backline source-agent coordination and handovers

17 September 2026. Authorised by Jason in the Backline CTO conversation. This is an execution/ownership contract, not a board snapshot, runtime configuration change or claim that an agent has started.

## 1. Ownership and priority

Source-to-canonical delivery comes first. Jason now explicitly delegates source implementation to two specialist coding agents. This supersedes older instructions saying ChatGPT must personally write every source adapter. It does **not** delegate coding to the existing AWSCLI deployment/evidence helper.

| Role | Owns | Work issue |
| --- | --- | --- |
| Backline CTO, current ChatGPT conversation | Architecture, shared engine/identity/policy changes, existing-source completion, cross-team dependencies, integration, cost envelope and release review | #7; #34 shared intelligence; #40 reporting |
| Source agent A | Lemonrock source implementation and end-to-end source qualification | #59 |
| Source agent B | Music Live East, then Live Band Photos, then BandForge; separate adapters and provenance, one coordinated lane | #32, #22, #33 |
| API implementation agent | Agreed canonical/read-facade changes; not source engines | #58 by request ID |
| Ops UI agent | Display and interaction only | #3 |
| Existing AWSCLI helper | Specifically requested runtime evidence and deployment/verification of exact reviewed packages | Linked release/evidence request |
| Jason | Product, real identity/merge decisions, explicit access/spend exceptions; notes on holds | Relevant existing case |

The two source agents use isolated branches/worktrees and can build concurrently. Production integration and deployments are serial because they share SourceWorker and other existing functions. No parallel main pushes, stack hotswaps, ad hoc canonical MCP writes or competing Cowork writer for the same source.

## 2. How work is claimed and reviewed

Before editing, read the issue and latest comments, then post `Claimed | agent/session | branch | base SHA | exact files | next deliverable`. No claim is fabricated on behalf of an unstarted worker. Agent A works below `src/sources/adapters/lemonrock/` and its own named fixtures/tests/docs. Agent B works below its three new adapter directories and its own named fixtures/tests/docs; check for existing work before creating directories.

Shared files remain CTO-controlled: source/adapter registration, shared runner/fanout/schedules, projection engine/store, knowledge schemas, identity/ownership/authority, canonical feedback, deployment/CDK/SAM and common fixtures. Propose an exact shared-file patch and focused proof; the CTO integrates it or grants a named file lease. Do not duplicate a shared selector in a source folder to evade this boundary. Source-local policy definitions may be proposed in the agent's branch; activation needs CTO release review.

All code commits use `[skip ci]`. Run focused affected-path tests, not the full suite or unrelated parity cleanup. Do not dispatch Actions or assume opening a PR cannot consume Actions. Branch commits and diffs are sufficient for review. Preserve other work, no reset/force push.

Update the source issue at each material result/blocker/commit/handback and at least every 30 minutes **while actively executing**. A stopped session leaves a final resumable checkpoint, not a claim to continue in the background. Each update: result, user impact, branch/SHA, test evidence, cost implications, exact blocker/owner if any, next action. Keep technical details in linked private-repo docs and confidential fixtures out of this public board.

At handback use `Review needed | source | commit | changed files | focused tests | proposed runtime scope | request/write/storage estimate | remaining gaps`. The CTO reads code/evidence, resolves shared changes via #58, and records `Reviewed` or concrete corrections. No response is not approval. Deployment helper receives a separate exact-function request; returns hashes/scope/time and natural outcomes. `Implemented`, `Deployed`, `Accepted on a real run` and `Complete source coverage` are different states.

The CTO reviews issue updates in active coordination turns and before integration/releases. This contract does not create a background agent scheduler or continuous surveillance of other sessions. Workers can complete independent source-local work while a review waits.

## 3. Lane A: Lemonrock handover

**Issue #59. Target:** all supported Lemonrock gig coverage plus daily discovery/intake of new and changed Artists and Venues, with useful canonical publication. Not merely collection into shadow.

Jason's new policy explicitly supersedes the blanket requirement for both canonical Artist and Venue to pre-exist. Implement governed new-entity creation from sufficient source identity/evidence. Do not simply turn `match-only` into `curator-trusted` or remove ownership/duplicate/conflict checks. A source's authority is scoped; a missing entity is not by itself a reason to skip forever.

Read in `flowency-live/bndy-enrichment`: AGENTS.md; docs/BACKLINE-STATUS.md; docs/BACKLINE-CONSTITUTION.md; docs/BACKLINE-RUNBOOK.md; docs/BACKLINE-ENRICHMENT.md; docs/LEMONROCK-RECOVERY-2026-09-16.md; docs/BACKLINE-EVENT-POLICY-2026-09-17.md; src/sources/adapters/lemonrock/ including sources.ts; current shared runner/fanout and projection code for integration context. Read #40 comments 5713148936 and 5713604743 as reported evidence and its corrections, not proof of full publication.

First working session: identify actual source-local gaps, current policy dependencies and amplification risk; post a short plan and start implementation rather than stop at another inventory. Use already-retained raw fixtures, bootstrap state and report artifacts. The overnight report's 22,733 jobs, 181 canonical-addition inference and parent/child example are not verified acceptance. Correct from retained artifacts first; missing AWS evidence is a precise CTO request, not permission for a fresh estate audit.

Deliver incrementally:
- A source/job inventory with acquisition, policy and publication states separate, and an explicit event-date/coverage horizon.
- Bounded resumable completion of previously collected coverage; preserve source identities/checkpoints. No restart of the national import.
- Daily new/changed Artist and Venue detection, including identities not yet in bndy, not limited to already-known or gig-referenced records as an undisclosed scope cut. Read details only for new/changed/stale work. Work that cannot fit headroom is an explicit queued/coverage gap and escalation, not a success claim.
- Actual entity-creation and gig-publication path through Backline's governed canonical API. Profile acquisition alone is not creation. Where shared entity application is missing, submit the smallest exact CTO/API dependency and source-side patch; continue independent work.
- Regular gig diffs and explicit cancellation/re-observation handling. Preserve safe destructive authority; a partial or rolling omission is not cancellation. Do not increase cadence or activate parked mass reconciliations blindly.
- Resilience and duplicate/retry proofs, including new Artist/new Venue, existing identities, conflicting matches, changed event, Karaoke rejection, time default, human correction and unchanged repeat.

Names/home locations are source facts, not inferred from gig geography. Claimed Artist profiles remain owner-managed; automated Venue enrichment is links-only. This does not bar legitimate source-provided Venue identity/address facts used for creation. No mandatory paid model/Places step may appear unnoticed in the creation path; bring such a dependency to the CTO.

## 4. Lane B: new publisher handover

**Issues #32, #22, #33. Sequence:** Music Live East -> Live Band Photos -> BandForge. These are distinct sources with overlapping/upstream data, not three interchangeable independent corroborators. Same-day delivery is the target, not an assertion that all code/access/coverage already exists.

Read the same architecture/status files as Lane A, current source adapter interfaces/catalogue/shared runner, the three issues and their linked research. If a research file/fixture is not in your checkout, use its repository/Library reference or state the precise missing input; do not invent its content. Claim each next source as it becomes active, using separate incremental commits so a ready source is not held for the entire trio.

- **Music Live East #32:** stable source identity from evidenced native IDs/slugs; distinguish doors from start time; preserve multi-act billing, original event links and source dependence; dedupe across pagination. The 232-event/20-venue estimate is dated 7 September, not current coverage. Do not copy biographies/images without a permitted basis.
- **Live Band Photos #22:** preserve/reuse prior canonical import lineage and existing identities. Link relevant retained imports/Backline evidence before re-creating anything; no wholesale canonical-hydration scan as a hidden prerequisite. Prove query-string detail pages and rolling versus complete snapshots. Establish ongoing deltas without duplicate imports or false cancellations.
- **BandForge #33:** preserve upstream attribution to Music Live East/Live Band Photos/Lemonrock; overlapping rows are neither extra Events nor independent corroboration. Confirm the permitted access route. Unknown missing-time cases use current defaults, not holds; invalid dates and actual ambiguity remain distinct. External access/permission is an explicit blocker if not established, never bypassed.

For each source: implement acquisition/normalisation/evidence integration using existing machinery; provide focused fixture and unchanged-repeat tests; supply registration/policy patches for CTO integration; demonstrate at least the normal new/existing/ambiguous/excluded/missing-time paths. Target governed canonical publication, not permanent shadow. Bring cross-source creation/identity dependencies to the CTO in #58 rather than building an independent canonical writer.

## 5. One source report, usable now

Use #40 for the common reporting contract and each source issue for its actual checkpoint. A report is sufficient while Ops is being rebuilt. Do not wait for INT-001 or repair old Godmode as part of source work.

One family row, child jobs underneath, plus every known watched Venue and planned source: `build state | coverage horizon | last successful ingestion | ingestion health | publication policy/health | source gigs assessed | Claims written | Artists/Venues/Events created or updated | already present | held/rejected | failed/pending | unknown coverage | asOf | next action`.

Use the same candidate/time population for reconciliation. Distinguish distinct source gigs from operations and distinct canonical IDs; multiple source listings can map to one Event. Preserve original attempt/decision history; separately report current open holds and newly held decisions in the window. Missing joins are unknown, not zero. Do not relabel source-diff `added` as canonical creations, acquisition success as publication success, or shadow as ingestion failure. Do not claim the old dashboard's zero/failing badge establishes whole-family current health.

Completion proof includes named canonical IDs and real outcome references, a genuine new Artist/Venue where relevant, a repeat that does not duplicate them, and disclosed incomplete coverage. A few successful examples prove that path, not full ingestion of the source.

## 6. Human notes, cost and release controls

Jason is working through holds. Use the current case/action history and evidence on re-evaluation; never overwrite a new human note using a stale cohort. CTO owns shared re-evaluation plumbing. Source agents fix source-local causes; only actual remaining identities/merges go back to Jason. Karaoke is rejected globally; a missing time uses Fri/Sat 21:00, Sun 19:00, other weekdays 20:00, explicitly afternoon 14:00. Preserve explicit/existing canonical times and policy-derived provenance.

No blanket hold purge, source-history reset or blindly replaying completed keys. Re-evaluate a named, bounded cohort from retained evidence with current guards after the applicable release. Changes must produce recorded decisions, not merely remove rows from an index.

There is **one shared AWS free-tier envelope**, not a budget per worker. Reuse existing account usage evidence; before live expansion publish expected discovery/detail volume, changed-versus-unchanged Claim writes, fanout/retry/concurrency bounds, Lambda/database/storage/log/trace implications and remaining-month allowance impact. A daily scan is not a daily full detail crawl. Unknown headroom or expected excess requires a specific Jason decision. No new AWS resources/indexes/alarms/custom metrics, paid providers, broad permissions or unrestricted probes are authorised here.

Offline coding/tests and review may proceed now. Use retained source material first; small public-source fixture retrieval may use the existing permitted acquisition method, with declared page/byte/timeout/redirect limits and no rate-limit/authentication bypass. AWS calls and live source activation are separate, scoped CTO instructions. CLI pagination/retries count as actual service attempts, not one shell command. Prior report/release budgets do not reset for the new agents.

CTO serialises reviewed code and policy/configuration activation, preserving current release hashes and rollback. Scope each release to its exact functions/assets and compare against live baseline to avoid overwriting the other agent's work. No blanket deploy from main. Source agents do not self-deploy; the CLI helper does not fix a build.

## 7. Durable handoff

This public contract and source issues hold role/scope/acceptance. `bndy-enrichment/docs/BACKLINE-STATUS.md` holds the operational checkpoint; source-local docs hold reproducible technical evidence. CTO edits shared Status and cross-source entry documents to avoid concurrent overwrites. Each agent updates its issue and own technical checkpoint with base/commit, tests, coverage, cost, unresolved items and exact next command at session end.

Use current bndy-work issues. Project fields and sub-issue links require distinct verified operations; no claim of setting Status/Health/Rank follows from a comment. The board contract still contains an older Project URL: resolve the current @bndy-work Project rather than mutate two projects. The source agents are ready to be started by Jason; posting these assignments alone does not launch them.
