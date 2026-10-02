# Backline V1 working tasklist and session handover

Updated 2 October 2026. Accountable technical owner: current ChatGPT session, programme [#7](https://github.com/flowency-live/bndy-work/issues/7).

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

## 2 October: API corrections still partial; listing interpreter connected to enrichment worker

**Story:** Backline understands the advertised bill, applies evidence-backed Artist decisions and continues eligible gigs; curators review genuine uncertainty.
**API review:** Exact **68bf257f209a445e18fda0ca73a6be5dedfe3a86**, not deployed. Accept initial replay target/binding validation, failed candidate reads stopping reuse, supplied sibling revision prechecks, conditional Artist Put and corrected array/timestamp fields. Strict location/current-create context, transaction revision/binding guards, common recovery validation and agreed input contract remain incomplete. [Remaining original corrections #81/5951012060](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5951012060).
**Enrichment progress:** Main **97d1c50aa3d44f0b89d1f6de7a1f06e8c974e13e**, parent 215e5a5. Existing queue/publisher/Lambda accept a typed interpret-listing job. Same structured provider and shared budget; cited result and original evidence refs retained before reprojection. Repeated delivery repairs send from retained result without repeating paid reasoning. Unavailable/invalid output is parked as operational work with no curator question or automatic reprojection.
**Impact / remaining:** The interpreter is now executable through the actual worker. Projection still does not automatically submit these jobs or consume interpreted performers. Artist proposal application is also unfinished. This is not intelligence acceptance, live quality proof or hold recovery.

### Latest API evidence

Isolated execution of 68bf257's committed handler with mocked dependencies:
- Empty performing-region evidence with the legacy default log mode still returns 201. New resolvable guard only rejects in enforce mode; the new command must be strict independently.
- Create with a stale compared candidate returns 201 and reads only receipt/binding. The fresh applicable lookup/checks remain absent.
- Static revision plus newer updated_at returns 200 reuse; the transaction checks existence/deleted only.
- Fixed: missing-target replay returns 409 INVALIDATED_CONTEXT; failed candidate read returns 500 SERVICE_ERROR with no transaction.

These are branch checks, not live DynamoDB concurrency proof. Reported API full-suite success was not independently rerun. The only test edit adds a binding fixture to the old replay case. Common validated creation/context, replay/reconciliation and versioned evidence contract remain the same outstanding order, not new requirements. No code, deployment, AWS/model usage or source state changed in this review.

### Next owned work and handover

1. CTO: connect projection admission/consumption before bill/identity rejection, assemble retained listing/profile/current human context, separate pending/technical outcomes from human review, preserve current canonical mappings/source keys and source pause. This is not wholly blocked by the API lane.
2. API agent: finish the existing correction order and return a new SHA/final wire contract/hash vectors/actual verification.
3. CTO: integrate governed Artist application against the accepted API contract, then prove contrasting examples end to end and issue a finite #80 release/recovery order. Provider qualification remains with its existing owner; no repeat paid diagnostic here.
4. Wessex stays reported paused. No deployment, source resume, AWS/model calls, hold clearing or canonical repair executed in this session.

Enrichment validation: required npm run check EXIT 0 (build, 205 Vitest files / 2720 passed / 5 skipped, 56 recovery passed). Eight focused worker-delivery cases use supplied model responses, not live model quality. Exact local/remote tree **7c231efa891b1e281a4042e0a5698a29c065c04b** matches; one main checkout, no branches/PRs/worktrees. Unrelated dirty docs/sources/MLE-001-CTO-INTEGRATION-2026-09-17.md preserved. [Implementation boundary and next steps](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-LISTING-INTERPRETATION.md).

### Retained review of 0589340

**Story:** Supported Artist decisions publish once and their identity is reusable across gigs.
**Review completed:** Exact API **0589340e1cf07f65b00ead2a0e166158ee82e8a1** is now accessible. Read route/tests, entity/region helpers, ordinary write paths and SAM template. [One consolidated correction order #81/5948114377](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5948114377).
**Outcome:** Not accepted for integration/deployment. Wessex stays reported paused. Reported 26 focused / 538 full tests do not cover the demonstrated failures.
**Impact:** Prevents routine reuse becoming another hold and prevents unsafe/invalid canonical creation.

Executed the committed application function in a local isolated Node harness with mocked dependencies, no AWS/model/network:
- Receipt replay with missing canonical target returns 200 success.
- Existing scope binding to the intended Artist returns 409 instead of compatible reuse.
- Failed read of a rejected candidate is swallowed; reuse writes and succeeds.
- Create skips compared candidates entirely.
- Empty performingRegionEvidence permits blank-location creation in the harness.
- Reordered equivalent nested scope properties produce a different fingerprint.
These are branch/contract checks, not a real DynamoDB concurrency test.

Static findings: missing SAM apply-decision route; create writes external_ids as an object rather than canonical array and omits ordinary record/provenance fields; does not require resolvable business uniqueness; reuse lacks revision/lifecycle transaction guards; newly minted revision masks normal updated_at changes; transaction failure reconciliation and real current-context lookup incomplete. Correct via existing API record builder/strict transaction module, not another matcher. Detailed exact correction and test guidance is on #81.

No API code changed by CTO, no extra source/model/AWS execution and no deployment order. Enrichment main stays 215e5a5. Full before-identity semantic queue/projection integration remains owned and incomplete; this API review does not claim intelligence delivered or block all independent enrichment work.

## Historical checkpoint: #81 local completion reported; shared implementation unavailable

**Story:** Apply a supported Artist decision once and reuse its canonical identity across gigs.
**Task:** Review the implementation handback before enrichment integration.
**Finding:** Owner reports 532 tests and handleApplyDecision implemented locally. Exact shared API master **d23595f5baad6e7b93e031bc833322505266328b** lacks the handler/route, decision tests and named decision-store file. Local work may exist; it has not been reviewed or accepted.
**Next:** API agent pushes the existing owned implementation on current master, preserves refactor work and returns exact SHA/final corrected contract. No reimplementation or new design round required merely because it is unpushed.

The supplied summary uses earlier producer-source binding keys, optional claimRefs, bare performingRegion, incomplete candidate revisions and idempotent/fingerprint response semantics. Agent must confirm/correct actual code against #81/5941545767, including strict atomic effects, technical error separation and durable replay. Claimed-profile protection must not ban ordinary identity reuse/gig publication. Tests were reported, not independently rerun.

Wessex remains reported paused. No API/enrichment code, runtime, provider call, source restart or deployment changed in this review. Enrichment still 215e5a5; automatic interpretation/application remains incomplete.

## 1 October evening: Wessex pause reported complete; API contract approved

**User story:** Backline applies a supported Artist decision once and reuses that identity across gigs.
**Task completed:** Reviewed the worker's contract against current API resolution route, unique-gate implementation and SAM template. [Corrected implementation order #81/5941545767](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5941545767) authorises coding now, without another design round trip.
**Done next:** API agent returns strict atomic application, exact wire contract/hash examples and verified retry/conflict behavior; enrichment integrates that actual contract. No deployment in this checkpoint.
**Backline impact:** Enables safe application of reasoning and human memory; the reasoning/publication loop remains incomplete.

- Wessex pause reported 21:32:38.695Z: 12/12 disabled/shadow, schedules removed, 24 writes and 48 reads. The 40-read bound was exceeded by eight; existing-ledger explanation requested, no renewed reads. Post-timeout canonical-outcome check is not supplied and remains unverified.
- Pre-pause enabled roots were authorised by #80/5933397717's later full-sweep order, not evidence of drift. A 47-row catalogue count does not establish the earlier seed write set; only reuse retained command receipts for clarification.
- API decisions/bindings use existing bndy-unique-keys with distinct namespaces and no TTL. Do not put metadata in Artist rows or add a StateTable dependency/new table.
- Stable persisted decision ID plus server-computed fingerprint of the full versioned semantic request; native identity namespace shared across event/profile routes, explicit evidence scopes for sources without native Artist IDs, separate mandatory Claim/observation refs, existing performing-region evidence semantics.
- Critical code finding: current gatedPut can fail open in off/log/missing-table cases. New command needs a dedicated strict atomic path preserving legacy callers, with no plain-put fallback. Artist/sentinels/binding/receipt commit together; reuse checks revisions/lifecycle. Replay never counts as a fresh creation or recreates an invalidated/deleted target.
- Current enrichment main remains 215e5a5, no new code/tests/model/AWS execution this contract review. Interpretation queue/projection integration remains outstanding, not claimed blocked in its entirety on the API. Other CTO provider lane remains separate.

## Historical checkpoint: containment ordered; interpretation preparation committed

**Story:** Routine gigs are interpreted and resolved automatically; curator review is for genuine uncertainty.
**AWS action:** [Execute Wessex pause #80/5934988802](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5934988802). Authorised by owner; execution not yet reported. Disable/shadow exactly twelve sources, preserve evidence and verify in-flight effects separately.
**Implementation:** enrichment main **215e5a5ba94d57024e2dfd80b768a0446aa0aeed**, seven owned files, parent befe888e. Local/remote commit and tree matched; unrelated Music Live edit preserved.
**Done so far:** Wessex original title/description/categories/related native links survive as source-listing-context Claims. Unresolved links stay leads. Identity prompt receives role warnings and bounded context prioritises human/listing evidence. Shared semantic interpretation component uses the existing structured provider and validates cited quotations, performer names and native-profile refs; distinguishes performance/session/festival/excluded/unresolved.
**Not done:** That component is NOT wired to automatic queue/projection; it does not yet fix publication or clear holds. Mock model responses prove contract handling, not semantic quality. Existing Artist proposals remain unresolved awaiting qualification.

- Full npm run check EXIT 0: build, 204 Vitest files, 2712 passed/5 skipped; 56 recovery passed. No paid model calls, AWS mutation, source crawl or deployment here.
- [Implementation boundary/next integration](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-LISTING-INTERPRETATION.md).
- [API implementation order #81/5935057449](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5935057449): existing authenticated resolution route applies supported decisions idempotently, preserves current conflicts/ownership and records reusable canonical identity; coordinate #87/#37. Current confirmNew is manual matching bypass and must not be used as AI authority. The existing refactor moved resolution.js to artists-lambda/routes/resolution.js.
- Next owned integration uses the actual returned API contract and existing provider correction/qualification, then connects listing interpretation before bill/identity failure through the existing budgeted queue with retained results. No assumed API endpoint or unqualified model output may publish. Provider HTTP implementation remains the other CTO lane; no duplicate diagnostic.
- Source keys unchanged. Added evidence can produce updated content on a later observation; no baseline reset or mass replay is authorised. Catalogue repair remains a specific retained-evidence manifest after decision correctness is proven.

## 1 October, owner quality review: 549 holds; decision delivery is the priority

**User story:** As a curator, I want Backline to interpret listings and create or reuse supported Artists, so I review genuine uncertainty rather than routine intake.
**Task now:** Review completed against the constitution, both owner attachments and main befe888e. Implementation plan below; no new runtime change or live repair executed.
**Done when:** A representative retained cohort demonstrates correct publication, exclusion/session routing, remembered identities and explicit remaining questions, followed by controlled recovery and a natural daily cycle.
**Backline impact:** Complete evidence-to-decision-to-canonical application, not further scraper expansion.

### What is established

- Owner reports 549 open gigs. Attachments contain 58 listed Diane gigs in 14 groups and 70 listed Wessex gigs in 57 groups. These are UI rows, not 128 unique events or a census of all holds; inline examples overlap.
- Main source-evidenced Artist creation rejects likely-new whenever candidates.length is nonzero (src/projection/source-evidence-artist.ts). Retrieval alternatives are therefore a hard block even when they may be irrelevant. Do not simply remove the guard and force-create.
- Assessment v3 in src/enrichment/worker.ts retains EVERY model proposal as unresolved / identity-proposal-awaiting-qualification. A successful model response alone cannot currently complete existing-act or different-act publication. Provider success/application remains unproven in reviewed evidence; coordinate with the existing #34 provider lane, not a duplicate diagnostic programme.
- Wessex parse.ts falls back to event title as artistName, attaches native Artist identity only for an exact title/name equality, and parks based on a narrow category/descriptor exclusion. Related Artist pages are fetched but unmatched role links are not supplied as performer assertions. Source profile availability does not prove it influenced the decision.
- Shared billing relies on title/splitting/unnameable rules; source text can become a speculative bill or no-act exception before identity reasoning. Wessex event-level interpretation is inadequate for the supplied promotional, classical and session examples.
- Existing candidate labels such as Jake Ward's Jingle Ball 2026, Halloween Party, Salisbury Chamber programme titles and highway child does blues brothers supported by kingfast suggest catalogue pollution. Origin/creation time is NOT established: do not blame today's release for every candidate or delete by name.
- Repeated Bitter listings across Wessex sites need canonical deduplication, not three independent corroborating votes. Real same-name acts (Roosters), venue postcode conflicts and outdoor-place modelling remain distinct.
- Owner reports befe888 deployed and three roots dispatched. This proves neither source quality nor all canonical outcomes. Handback says 47 sources seeded despite order limiting changes to 12 Wessex CONFIGs: inspect retained before/after receipts for unintended policy changes; no blind registry rollback. Three saved-human retries remain undemonstrated.

### Ordered delivery plan

1. **Contain Wessex risk (#128 / #80).** Recommend temporarily suspending Wessex automatic canonical writes and new discovery while preserving evidence, queued work, current human decisions and existing canonical records. Exact supported controls must be checked for already-queued work; disabling roots alone is not a write fence. This review has NOT paused production. No global stop, queue purge or automatic cleanup.
2. **Interpret evidence before Artist resolution (enrichment CTO / #128, shared #34).** Keep raw title, description, source categories, all role-labelled native/profile links and Facebook facts. Use existing exact structured evidence when sufficient; use the existing bounded model path for genuinely semantic bill/type interpretation. Produce cited performer identities separately from event/promoter title, session, festival or excluded category. Preserve an eligible live act within a mixed fundraiser rather than reject on a keyword. No expanded regex/name exception catalogue.
3. **Complete governed reasoning application (#34 / #81).** Qualify the real existing provider path once its evidenced request defect is fixed. Compare plausible candidates using source facts, canonical history, profiles and human memory. Carry a validated decision through to reuse OR genuinely new Artist creation, with fresh canonical conflict/ownership checks and idempotent writes. Reject irrelevant retrieval hits with an evidence-backed explanation. No website prerequisite; labelled performing region may come from the gig, not invented home. Technical/provider failures go to operational recovery, not curator identity questions. Canonical API changes, if required, go to VSCode via #81; no source-specific resolver duplication.
4. **Remember and reuse (#37).** Bind a successful new-Artist decision to its canonical ID and relevant source identities, preserving human scope and invalidation. Apply to sibling gigs and cross-source evidence only when identity is established. One decision should not create many Artists or repeatedly ask the owner.
5. **Recover quality, then resume (#128 / #80).** Assemble a finite manifest from retained supplied cases and referenced canonical IDs: accepted gig, correct existing Artist, correct new Artist, excluded classical, session/deferred festival, real collision and technical failure. Confirm polluted canonical records and ownership/references before proposing specific repairs; no name-based delete/merge. Re-evaluate the supplied cohort after fix, inspect actual effects and duplicate counts, then expand recovery using existing holds without new full sweeps. Preserve source event keys/baselines or plan any necessary transitions explicitly.

### Acceptance examples and execution discipline

- Blink Daze/Blind Eye, Thunderslug/Thunderhead, Speared Art/Speakeasy: weak name similarity alone cannot force a curator question; decide using actual evidence, not pre-label every case new.
- Seth Lakeman: Freedom Fields and The Rozzers billing: separate performer from programme and use existing identity evidence.
- Open Mic/NYE/Band Night: no invented Artist; route sessions or missing performer detail distinctly. Choir/classical exclusions are retained policy decisions, not identity holds.
- Charity Golf Day with Jake Ward, Wilton festival bill and folk duo: inspect performer roles and event scope; promotional or festival words alone neither prove rejection nor a new Artist.
- Roosters and incomplete venue evidence: genuine conflicts must survive automated processing.
- Existing polluted Artists must not become unquestioned positive identity evidence. Display casing comes from supported identity text, with original billing retained.
- Release acceptance requires actual decisions and canonical outcomes plus contrasting non-match/excluded cases. Parser success, queued work and passing mocks are insufficient. Measure unnecessary holds, wrong creations/merges, reused decisions and provider spend per resolved identity.
- No code or AWS mutation in this review; no model calls or source crawling. The next implementation is the shared interpretation/application outcome above, coordinated with the other CTO's provider/telemetry work. No new infrastructure or graph database proposed.

## Historical checkpoint: Wessex full sweep authorised; human new-Artist routing fixed

**User story:** Complete Wessex gig/profile evidence reaches governed canonical processing; the owner's saved new-Artist decisions reach creation.
**Implemented:** enrichment main **befe888e98bc0c4d6f71b4757f1a8aec0be68f7e**, full npm run check EXIT 0. Explicit Wessex predicate allowlist added; aggregator human-confirmed-new decisions now enter the existing human confirmNew path rather than the source-only resolver.
**Next:** [Execute managed release, full sweep and named verification #80](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5933397717).
**Impact:** Fixes demonstrated delivery/authority routing omissions without new matching rules.

- Owner reports 5e41086 deployed; two initial Wessex events held at missing allowlist. The omission was CTO integration responsibility. Source unchanged repeats do not prove canonical publication.
- Owner now authorises full sweep and canonical writes. Earlier keep-roots-disabled qualification instruction is superseded by the new order: activate three daily roots serially with all nine children and complete directory/month/event/profile graph; preserve policy, state and bounded transport.
- Latest three-Artist trace reports facts saved and retries completed but re-held. Concrete code defect: aggregator source-evidenced branch preceded the human confirmNew flow and rejected likely-new responses with candidates. The correction reuses the existing human-authorised path; ordinary source ambiguity still holds.
- Recovery order retries one exact existing hold per Artist once; reads actual canonical outcomes. #37 durable new-decision-to-created-Artist association remains open, so do not repeatedly create or claim all remaining group gigs recovered. Biography notes are retained, not structured Artist bio facts.
- This session has not deployed or executed AWS. Source docs and #128/#37 contain status. No API code changes or infrastructure changes. Unrelated Music Live document edit preserved.

## 1 October: Wessex family integration complete, initial runtime qualification next

**User story:** Curators need Salisbury, Andover and Winchester gigs with Artist Facebook links and Venue facts available to evidence-based decisions.
**Task completed:** Reviewed c301b226 and integrated the complete twelve-source family on main at **5e41086e307101b6774ec3f7bdf914117f753ae3**. Full npm run check EXIT 0; no AWS execution here.
**Done next:** Execute [#80 initial cohort order](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5932273738), return actual canonical/held/failed/pending results and unchanged repeat. Then size and activate the full discovery graph.
**Backline impact:** Rich attributable identity evidence and maintained gig updates; no new matching heuristics.

- #128 is family implementation index, with #129/#130 for local coverage. Reader retains Facebook profile URLs, addresses, websites and source-native identities; one publisher, not independent corroboration.
- Integrated runtime/catalogue, three daily London roots at 06:30/06:40/06:50 and nine discovery-only children. Corrected additive-only update blockage and one-event gate to the existing four-act maximum. Governed create/update only; explicit cancellation application remains disabled.
- First runtime order installs roots disabled/no schedule and enables only finite named detail/profile work. Complete directories and all advertised months remain required follow-on, not waived; publisher pacing, full volume, cross-site dedup and canonical profile application are not live-proven. No claim of full BAU.
- Source handoff updated; obsolete integration.patch removed. Seven owned files only; unrelated Music Live document edit preserved. Shared files released. No API implementation or new infrastructure.
- Owner reports Diane 9cd8f7c deployed and 489 valid listings ingested; canonical totals remain missing. #119/#80 track the existing outcome read-back. Sources overview HTTP 500 reported separately; [targeted incident #80](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5930966805), API repair #82. Neither incident nor ingestion counts establish source canonical delivery.
- Incoming CTO provider/KLMA/Fizgig work remains separate and must preserve these newer source commits.

## 1 October follow-on: Diane's Gig List launch authorised and integrated

**User story:** As a curator, I want Diane's gigs in bndy and kept current daily.
**Task completed:** Catalogue/runtime integration committed on enrichment main **9cd8f7cd7279f2f853a842b9b816990a63a08828**, atop 9741eaf7. Build/full check EXIT 0; local/remote tree matched. No runtime execution here.
**Done next:** AWSCLI performs [the authorised managed launch](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5929917876), initial/repeat canonical verification and then natural-cycle BAU evidence.
**Backline impact:** Daily static-index evidence and governed gig delivery; no additional directory/profile crawl.

- Owner explicitly requested live ingestion and BAU after the CTO handover. This supersedes Diane's earlier planned/disabled integration status, but is not a claim that live registration/deployment has occurred.
- Code definition: live AWS writer, daily 06:20 Europe/London, registry schedule, 26h freshness; create/update evidence-gated; incremental omission never cancels. One page per run, 4 MiB/20 seconds, no browser or profile fanout; event/action gates 1,000.
- Applied catalogue/runtime patch and removed the patch file. Runtime CONFIG/catalogue installation is exact-source-only through the existing store, not an unfiltered seed. No API change is required for this adapter integration.
- [Source result #119](https://github.com/flowency-live/bndy-work/issues/119#issuecomment-5929930649). Source docs contain rollout. Claimed shared integration files released; unrelated local Music Live document modification preserved. No worker assumed active.
- Reported live enrichment remains fadcb8ae until #80 returns the release receipt. Provider qualification, KLMA/Fizgig reconciliation and other CTO priorities remain open and are not included in this source activation.

## Current checkpoint, 1 October: evidence reviewed and CTO handover ready

**User story:** As a curator, I want explained evidence-based decisions, remembered corrections and reliable daily gig delivery.
**Task completed:** Processed the full diagnostic/source bundle; refreshed source-agent progress and the issue-by-issue handover.
**Done next:** Fix/qualify the provider request and implement identity-preserving source reconciliation, then demonstrate the curator loop and daily telemetry.
**Backline impact:** Precise continuation of the intelligence layer. V1 is not yet accepted; no new deployment or runtime repair.

Read [the current CTO handover](BACKLINE-CTO-HANDOVER-2026-10-01.md) first. It contains the complete current issue map and supersedes older checkpoint status below.

- Actual qualifier at 0b224202 returned HTTP 400 through the real runtime/control store. Full provider body is generic invalid_request; no rejected field, no validated proposal. Original context and prompt reproduced. Diagnostic02 is consumed, no automatic rerun.
- All four source snapshot hashes match. Repository transition logic finds KLMA **55 old rows / 24 bills**, Fizgig **2 / 1**. Worker slug reimplementation omitted four ampersand-name keys.
- Returned candidate evidence covers 53 old expanded keys only; four old keys and 25 replacement keys were not queried. Request lacks ConsistentRead. No canonicalEntityId is not proof nothing published. Publication-state evidence and conditional reconciliation remain outstanding.
- Same billing text survives for 16/24 KLMA bills and the Fizgig bill. Do not label structural normalisation as cancellation or collapse genuine lineups. Keep guard/baselines.
- Source read ledger is six prior plus nine additional = fifteen. Qualifier used four AWS calls. No allowances reset in this review.
- Latest remote enrichment main observed **9741eaf703aedcc9136f62b1fb0c9afb27c0714a** includes KLMA HTML fallback **bbf0f400** and Diane reader **9741eaf7**, both source-reported build/full-check passed and undeployed. Diane still needs CTO registration/scheduling review.
- Reported production remains **fadcb8ae**. Current local checkout is older and has an unrelated Music Live document modification: preserve it. Refresh remote pins before implementation/release.
- No AWS/model call, runtime code edit, new tests, deployment, source reset or canonical mutation in this handover. No worker assumed active. Public issues contain sanitized status; private receipts remain in the owner's bundle.
- Priority: actual reasoning qualification; KLMA/Fizgig recovery; current-human/command-recovery acceptance; #82/#79 daily telemetry; specific Lemonrock/Insangel/venue gaps. #81/#82 API implementation stays with VSCode/#87. All runtime orders go through #80.
- The owner's disposable-test memory decision is settled. No migration, graph infrastructure or per-name matching rules. Every new task begins with user story, precise task, done outcome and Backline impact.

## Previous checkpoint, 30 September: artifacts reviewed; real qualifier ready

**User story:** As a curator, I want Backline to explain Artist matches using bndy's accumulated evidence while source gig identities remain dependable.
**Task completed:** Reviewed all three uploaded files and replaced the improvised diagnostic with a repository-owned qualification command at **0b22420221a59b4180162a4fb2c264b1f2a350df**.
**Done when:** The next AWS execution returns a real proposal/rejection and the actual old/new source rows with stored identities.
**Backline impact:** Removes the execution bypass and enables safe reconciliation. No live AI proposal or restored source delivery is claimed.

### Findings from actual uploads

- diagnostic-originals-01-script-for-review.mjs confirms custom reservation/budget namespaces and direct fetch. It is incomplete (undefined variables, omitted secret/reservation execution), not a full runnable history. Reject as application qualification. Do not fix only its key prefix.
- Its embedded Originals context does reproduce original jobec0af02f... and SHA256110deb5034557933c7af8446b5ab03e0826cc7df266c7b11e140cf84deb6c978; offline prompt2916bytes.
- billing-reconciliation-manifest.json has only inventory rows. KLMA40 of55 reported rows,18 of24 reported native groups; final four-act group truncated at2. Fizgig16 rows/14 unique keys/7 groups; two duplicate keys. Only its Paul Sherry + Band pair is proposed; one speculative part is literally Band. No current whole-bill rows, baseline pointer proof, snapshot hashes, retrieved Candidate records, canonical IDs or supportingClaimIds.
- Do not infer published state from generated candidateKey strings or missing IDs. Do not collapse legitimate source-supplied performers. Uploaded COMPLETE reconciliation label is rejected; guard/baselines remain.
- Upload SHA256s: script cd19ff541f67691d75359a51ac1359cfc69f78111fd893b82b1481ef3b9c87f1; handback789b45a9a1e5b0a63c1ccfe038d56009619a1fd4fdeeb3105956deb16b92c555; manifest1ae4bac8b28ffaef38dab26b384c52f8311c201bfd4e88dd53c9dc0d40235ee3. Do not copy the script's internal configuration identifiers into public issues.

### Implementation and exact next execution

- Seven files; single main checkout, local/remote treebb696607c0ca5bf20f99c903e91b3fc6f698f40c matches. No branch/PR/worktree or infra change. Shared secret loader/daily limits/reasoner factory moved from the Lambda handler without changing its policy/defaults.
- New src/cli/qualify-artist-identity.ts does offline plan by default, checking retained context identity/hash and prompt allowance. Explicit apply requires expected clean repo pin and a new private receipt directory. It uses the actual DynamoEntityEnrichmentControlStore and GeminiStructuredEnrichmentReasoner through the shared reasonArtistIdentity path. Only started permits one call. No alternative HTTP payload/store, Claim, Observation, projection or canonical writer.
- Numbered receipts precede model execution and terminal control outcome; record pin/compiled command hash/ledger/result. Private bounded provider rejection is retained with exact key redacted. No response-loss retry. Existing/custom diagnostic01 records and original results stay untouched.
- Build and required npm run check exited0:200 Vitest files,2638 passed/5 skipped,56 recovery. Six focused cases;28 focused checks passed. Offline CLI plan passed on the actual supplied context, zero AWS/model calls.
- [Executable #80 order5915508216](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5915508216) supplies the exact command for the already-authorised unused diagnostic02. One provider attempt/$0.04 estimated reservation/unchanged token limits. A retains8 AWS attempts/1MiB/5minutes; no SDK retries. No deployment required for local qualification.
- Source order requests full raw old/current snapshots plus effective CONFIG/STATE and actual strong CandidateStore responses, not another shortened summary. B grants at most10 additional exact reads/8MiB/5minutes beyond the previously reported6; cumulative ledger starts6. At most100 derived keys, no bucket list/scan/crawl/automatic retry. Preserve unprocessed/missing keys as incomplete. No source repair authorised before review.
- Await AWSCLI execution, not another owner policy decision. No executor assumed active. No model/AWS/deployment/source mutation performed here. Reported live remains fadcb8a; main is not deployed. #82/#79 reporting remains open; Lemonrock EBUSY root cause is still unproved.

## Earlier blocker, 30 September (files now reviewed above)

**User story:** As a curator, I want Backline's real AI reasoning qualified and existing gig identities preserved.
**Task now:** Review the diagnostic script and billing reconciliation manifest already produced by AWSCLI.
**Done when:** The actual artifacts support an executable corrected qualification and an identity-preserving source repair.
**Backline impact:** Enables the reasoning/ingestion repair without another broad diagnostic or invented matching rule.

- Owner confirms diagnostic01 bypassed the reviewed control store and reasoner, using custom ENRICHMENT_RESERVATION and direct fetch. It is not application qualification. The prior attribution of its400 to execution of fe6e63c is withdrawn; temperature remains a documented request-contract mismatch corrected at7aea0ed, not a proved cause of the original worker failures.
- PartA stopped correctly under the script-discrepancy condition; diagnostic02 is not reported executed.
- PartB reports KLMA332 events/55 billing rows/24 bills/40 candidates and Fizgig278/16/7/16. These are unreviewed inventory counts, not demonstrated reconciliation coverage. Need actual old/new rows, baseline provenance and retrieved candidate/canonical identities. Candidate counts do not establish actual reads.
- Reported ledger:6 AWS calls including S3 listing and2 downloads;5 files generated. Listing diverges from the exact-object/no-list order. Preserve the actual ledger; do not rerun to reconstruct it.
- The named Windows-local script and manifest are not accessible here or attached to#80. [Artifact handoff request](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5914611482) requests existing files, with credentials removed and referenced already-downloaded rows included. No new AWS/model work or cleanup.
- Latest implemented main stays7aea0ed71addfd31e28e55e8b3ee8b24212de41d, tested and undeployed. No application edit/test rerun in this review. No source state, baseline, reservation or canonical mutation authorised. No worker assumed active. Resume with file review; do not treat the summary's COMPLETE label as acceptance.

## Previous task, 30 September: request fix and reconciliation order

**User story:** As a curator, I want Backline to explain ambiguous Artist listings while new gigs keep flowing.
**Task now:** Request compatibility fix is committed/tested at **7aea0ed71addfd31e28e55e8b3ee8b24212de41d**. [Next AWSCLI order](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5912883104) qualifies it locally and retrieves the exact KLMA/Fizgig bill transitions.
**Done when:** One validated proposal or precise provider rejection is retained, plus an old/new bill manifest with existing candidate identities sufficient to plan repair.
**Backline impact:** Enables AI reasoning and safe source reconciliation. Actual proposal quality and restored ingestion remain unproved.

- Handback reports fe6e63c diagnostic01 reached Gemini and received HTTP400; secret/preflight succeeded. No validated proposal or actual usage. The receipt was reportedly deleted. Reported reservation key/code differ from reviewed code; new order checks the actual script before any paid continuation.
- Google's current Interactions GenerationConfig omits temperature; code now removes that field while preserving model, endpoint, evidence/schema, thinking/output limits and application boundary. Model gemini-3.6-flash and /v1beta/interactions remain documented. This is a request-contract fix, not a proven attribution of the specific400.
- Four files changed; one request-field removal, existing contract assertion strengthened, status/investigation docs updated. No new tests or matching rules. Required npm run check exited0: build,199 Vitest files,2632 passed/5 skipped,56 recovery. Local/remote commit/tree29168900d4c55708ea2d6288dd4683db28a9f83b matched, clean main. Not deployed; reported live remains fadcb8a.
- New explicitly bounded diagnostic02 permits one further model attempt after the fix, $0.04 estimated reservation, existing daily provider partition and token/deadline limits. Prior three-attempt allowance is exhausted. Only a verified existing execution path and new started reservation permit the call; keep original jobs and prior reservations unchanged. Retain private script/receipt and provider rejection details rather than discard them. A: at most8 AWS attempts/1 MiB/5minutes.
- KLMA and Fizgig failures correlate to billing-key-transition-requires-reconciliation. The prior shared release qualification omitted these active sources while checking Lemonrock/LBP. CTO owns the gap. Preserve guard and baselines; obtain exact prior/current normalised rows and up to40 derived candidate identities. B: at most12 AWS reads/8 MiB/5minutes, no automatic retries. Source repair implementation depends on these concrete identities, not another general health audit.
- Lemonrock Artist hydration sample is getaddrinfo EBUSY against DynamoDB. It is a DNS lookup failure; root cause and applicability to145 historical failures are unknown. Use existing stack frames first; no speculative concurrency/DNS/IAM change.
- No AWS/model calls, deployment, source reset, canonical mutation or billing repair executed here. Diagnostic reservation/outcome writes must be reported separately from no canonical/source mutations. No external worker assumed active. #82/#79 telemetry remains open.

## Earlier 30 September diagnostic order (completed handback above)

**User story:** As the owner, I want Backline to explain Artist matches using bndy's evidence and keep importing gigs.
**Task now:** AWSCLI execution of [one retained-input reasoning diagnostic and three exact source error windows](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5912305547). This supersedes the earlier wait for input recovery; it does not reopen broad qualification or source audits.
**Done when:** One validated proposal or a safe precise failure diagnostic is retained, together with correlated source exceptions or explicitly bounded-search misses.
**Backline impact:** Enables the actual AI/provider and ingestion repair. Reasoning quality and source recovery are not yet demonstrated.

- Owner's corrected handback confirms both raw Observations retain context, reasoning and assessment. Prompt sizes are 6,858 bytes (Undercovers) and 2,916 (Originals); neither exceeds the 12,000 bound. The separate four-read correction allowance is fully consumed.
- Size is ruled out for those reconstructed prompts. HTTP attempt remains unknown because configuration/secret setup can fail earlier. Original exceptions were discarded.
- Reviewed main remains **fe6e63ca6d3994c065ca907990394d1232032d30**, clean, safe diagnostics implemented/tested but undeployed. Reported live remains fadcb8a.
- #80 now explicitly permits one local direct reasonArtistIdentity diagnostic using unchanged retained Originals context and fixed operation ID **artist-identity-diagnostic-20260930-originals-01**. It uses the existing control store and same identity-provider daily budget partition. Only a new started reservation permits a call; existing/resumed/ambiguous operations never retry. The original cached Claims and investigation IDs remain intact.
- This uses the remaining third model attempt under the original three-attempt envelope, unchanged $0.04 estimated per-job reservation and token/deadline limits. Provider cost remains unknown without actual usage evidence. A has a new explicit cap of six AWS attempts / 1 MiB / five minutes for config/secret/control operations, no automatic retries.
- B has a separate new cap of six AWS reads / 2 MiB / five minutes: exact SourceWorker KLMA 11:54–11:56 UTC, exact BrowserSourceWorker Fizgig 13:10–13:12, exact SourceWorker Lemonrock Artist hydration 03:15–03:18, all30 September. Resolve at most one missing physical resource map; no wildcard/day-wide search. Retained exact failed-report objects may replace log reads within the same allowance.
- Code review shows runner failures attempt to write a failed report. Absence is possible, not universal. Fizgig complete:true/itemCount616 proves capture only for that observation until correlated to the failed run.
- No deployment, original-result deletion, canonical/Claim writes, projection, source activation, model substitution, migration or Insangel clear. Diagnostic control reservation/outcome are the only authorised writes. Do not imply successful local qualification proves the Lambda role.
- Order is posted for the owner's AWSCLI worker; no executor assumed active. This session made no AWS/provider calls. Next technical-owner step is the evidenced fix, then remaining actual proposal-quality acceptance; telemetry work in #82/#79 remains open.

## 30 September implementation checkpoint: failure diagnostics fixed

**User story:** As the owner, I want the reasoning trial to return an explained proposal or a precise technical failure.
**Task completed:** Enrichment main **fe6e63ca6d3994c065ca907990394d1232032d30** retains safe failure stage/code, prompt size/input allowance, HTTP attempt/response state, status and allowlisted provider status. Configuration/secret failures are separated before Gemini HTTP. Arbitrary exception/provider prose and credentials are omitted.
**Verified:** Build and required full check exited0:199 Vitest files,2632 passed/5 skipped and56 recovery passes;40 focused checks passed. Tests prove raw Observation context reconstructs the actual worker prompt, including after unavailable results. No model, matching, budget, retry or infrastructure change. Not deployed and no real provider call made here.
**Backline impact:** Diagnosable reasoning execution; this is supporting work, not completed model-quality qualification or restored source delivery.

The handback's claim that ArtistInvestigation context was never retained conflicts with6632b28: the raw Observation JSON includes top-level context, reasoning and assessment. Follow the existing Claim/Observation evidenceKey; Claim.value alone is insufficient. [Exact retrieval correction](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5911478269) permits at most four keyed/object reads,2 MiB,three minutes, no retry. Reuse existing downloaded evidence first. Use the original pinned prompt to measure the original input. If the raw object does not match the reviewed writer, report that exact discrepancy.

Historical next step, superseded by the current diagnostic order above: AWSCLI was to execute that retained-input check and return the missing original source report errors. [Diagnostic code receipt](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5911531793). Existing failed jobs remain cached and immutable; no new paid call, deletion, fabricated context/version or retry authorised. The original error was discarded and cannot be retroactively recovered by deploying this fix.

Source handback still has no precise exceptions or Insangel terminal correlation. Do not convert suspected rate limiting/site changes/shared deployment into diagnoses. Do not clear Insangel activity fields merely from age; that would not establish restored ingestion. Future-reconcile shadow mode does not explain absent scheduled runs. Existing bounded #80 source error request remains open, with cumulative allowance and no general log audit or runtime mutation.

Single main checkout clean, local/remote tree1f2c2e1c5cf1be8496c44d001c3eb835e39d5489 matched. No executor assumed active. The earlier30 September review below is retained as history.

## 30 September handbacks: qualification failed; source errors need exact causes

**User story:** As the owner, I want Backline to keep importing gigs and explain uncertain Artist matches reliably.
**Task now:** Narrow diagnostic continuation in [#80/5910009404](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5910009404), using retained local execution evidence and existing failed source reports. No further model call or deployment yet.
**Done when:** The precise failing stage/error is available for an evidenced CTO fix and controlled retry. Generic blocker categories are not root causes.
**Backline impact:** Restores source delivery and enables evaluation of actual intelligence proposals.

Owner-reported qualification on worker 6632b28 executed two jobs, Originals and Undercovers. Both retained unresolved/unavailable results, with no proposal; the contrasting case was not tested. The catch currently discards the original error, so configuration/secret retrieval, prompt/cost preflight, HTTP, output parsing and missing usage can all appear as identity-reasoning-unavailable. This is an enrichment-owned diagnostic omission. Reported $0 cost and two provider calls remain unverified without failure-stage/usage evidence. Actual model quality remains unqualified.

Job identities retained in #80. Re-running the same jobs reuses their unavailable results. Do not delete reservations/results, modify factual context to evade caching, or consume the remaining third provider slot blindly. Request exact input/invocation and any retained original exception first; offline prompt-size/configuration inspection needs no model call. No raw error/secret material in public issues.

Owner's source snapshot as of 30 September 11:00 London:
- Recent successful acquisition: Gigs News, Lemonrock gig hydration, LBP, OnTheCase, Scenic Eye and Rigger. Successful runs are not confirmed daily publication totals or complete scheduled-cycle coverage.
- Recent failure cluster: KLMA/Fizgig/Eleven/Sugarmill/Hairy Dog last succeeded around28 September. A common deployment/runtime cause is a hypothesis pending actual error signatures.
- Prolonged failures: Lemonrock Artist/Venue hydration, last success18 September, reported145/157 failures. Diagnose independently of the recent cluster.
- Lemonrock new-gigs/cancellations roots report recent successful shadow acquisition. Shadow root acquisition with live detail children must not be called a publication outage merely from mode.
- Future reconciliation is stale since22 September, even though idle/shadow. Need effective schedule/checkpoint evidence, not a blanket enablement.
- Insangel's active flag with missing last-run/success timestamps is unverified activity, not proof a run is in progress.
- Music Live parked; BandForge origin-restricted/disabled; Fantastic All Library manual-assisted. Historical failures remain separate from expected policy mode.

The supplied23–30 September run-day table records successful activity on eight dates for several sources. Today is incomplete; the summary does not prove every expected hourly/daily run succeeded or establish uninterrupted uptime. New/update/cancellation counts remain unqualified.

Source diagnostic follow-up uses at most8 further keyed/report reads,2 MiB,3 minutes, cumulative maximum18 of the original24 source reads. Reuse the already-collected CONFIG/STATE and report pointers. No scan, broad log search, crawl, provider call, restart, mutation, config change or deployment. #82/#79 telemetry remains prioritised. External worker is not assumed running; this session made no AWS/provider calls or application edits during this review.

## Active user story and task

**User story:** As a curator, I want Backline to interpret ambiguous listings using the evidence bndy has accumulated, so I only answer questions that evidence cannot settle.

**Task now:** Contextual reasoning, failure diagnostics, request compatibility and the real qualification command are implemented on main at **0b22420221a59b4180162a4fb2c264b1f2a350df**, proposal-only and default off. The first two qualification jobs in [#80/5900192251](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5900192251) returned unavailable, with no model proposal. Next is post-fix qualification and the two-source reconciliation manifest under the current task above. No deployment or automatic matching activation is needed for that trial. No executor is assumed running.

**Done when:** The actual reasoning path assembles available canonical candidates, gig/venue history, native identities, source provenance and current human decisions; produces an evidence-referenced existing-act/different-act/unresolved proposal; validates authority, IDs and contradictions before any application; retains the result for reuse. Demonstrate a supported alias, a genuine competing act and insufficient/conflicting evidence. Distinguish real provider output from mocked/offline tests and deployed behaviour.

**Backline impact:** Connected evidence influences an explained decision. Website discovery, test counts and safe holds alone are not acceptance.

**Current checkpoint:** The existing structured provider receives listing/native identity, canonical cards/aliases, referenced gigs and active supporting Claims. It returns a cited existing-act/different-act/unresolved proposal with candidate comparisons and contradictions. Schema/reference checks validate integrity, not prose truth. Results and raw responses/usage are retained and reused; invalid/unavailable attempts do not cause another paid call. Current human decisions run before automatic investigation. Every version-3 proposal remains a hold, with details in its exception/run trace; Ops UI rendering and automatic application are not delivered.

**Verification:** Required `npm run check` exited 0: build, 199 Vitest files, 2625 passed/5 skipped and 56 recovery passes. Ten focused additions exercise the real transport/worker/projection with simulated responses. No actual provider or AWS call was made. Real model quality and the three contrasting acceptance cases remain open.

**Next:** #80 is limited to up to three real-provider attempts ($0.12 total estimated within existing daily caps), named retained inputs, no reprojection/canonical writes and no cloud deployment/configuration change. Review actual explanations before application work. If contrasting evidence is unavailable, retain that gap; do not fabricate histories or add more name/venue rules.

## Mandatory delivery and delegation check

Use this short check inside the existing task/work order, not another document or owner approval process:

1. What user-visible decision/capability improves?
2. What evidence is available, missing, discarded or not used?
3. What belongs in deterministic authority/identifier/write checks, and what needs contextual interpretation?
4. What observable before/after outcome will prove the improvement, including a contrasting case that must not be wrongly accepted?
5. Does each supporting repair remove a demonstrated blocker to that outcome? If not, defer it.

Apply before selecting work, before delegating, and when reviewing the handback. If a worker returns only guards/tests, accept those as support only and keep the outcome open. Do not add new speculative acceptance requirements on each review. Explain a genuine newly discovered blocker and keep its fix bounded. Continue other owned, unblocked outcome work.

Keep updates succinct: implemented / verified / deployed / demonstrated, actual blocker and exact next action. No background-work claims. Owner should not have to detect architectural drift. This check supersedes earlier workflow wording that treated the API fix as blocking all enrichment reasoning.

**API scope:** [#81/5899743194](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5899743194) limits work to reliable bounded evidence, retaining candidates and safe canonical application. Preserve accepted fixes/refactoring; do not expand the name/venue rule set. No deployment authorised.

**Memory unchanged:** Applied disposable-test cutoff 2026-09-28T16:23:54.000Z; later human decisions retained. No migration.

## Owner priority, 29 September: source health and daily delivery

**User story:** As the owner, I want to see which sources operate reliably and how many gigs they add, update and cancel each day, so I can leave Backline running and spot problems.

**Task now:** Prioritise the existing #82 accounting and #79 source overview while the contextual reasoning trial awaits its executor. Do not wait for every source to be enabled and do not activate parked/manual sources for the dashboard.

**Done when:** One family/source view shows effective mode, last attempt/success/next due, first observed run, successful scheduled days versus expected days, current blocker, and daily confirmed Added/Updated/Cancelled gigs with matching records and coverage. Use Europe/London operation dates, not gig dates. Unknown history is not zero or an assumed success streak.

**Backline impact:** Operational visibility and evidence of canonical delivery; supporting work, not a substitute for the intelligence task above.

Ready assignments:
- [#82 API/accounting](https://github.com/flowency-live/bndy-work/issues/82#issuecomment-5900303684): finish bounded complete-window accounting and stable pagination, separate creations/updates/cancellations, correct sampled verified totals and last-publication semantics. VSCode API agent owns implementation under #87; enrichment owns any demonstrated producer dependency.
- [#79 UI](https://github.com/flowency-live/bndy-work/issues/79#issuecomment-5900314166): compact source table and 7/14/30-day delivery view using the existing pages; hourly/manual refresh and lazy drill-down. Claude/Ops implementation lane.
- [#80 read-only snapshot](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5900315655): once, after already-started trial work; effective catalog/CONFIG/STATE and preceding seven London days plus today of bounded retained run evidence. Maximum 24 read attempts / 8 MiB / 10 minutes. No table/log scan, fresh billing audit, provider call, activation, replay or deployment. Return partial at the bound.

Source/code review, not fresh AWS evidence: API backline.js blob 4c3e46a still samples eight projection observations, combines creates/updates in intoBndyByDay, and can call a match-only summary publication. Ops main c30661f retains a six-run embedded sample and an acquisition-row pattern view. Existing acquisition DAY counters can be inflated by repeated report writes; they are not canonical delivery totals. Reuse existing run/operation records, summaries, tables/indexes and cache; no new metrics service/resource, per-gig CloudWatch metric, background job or provider spend is authorised.

Last quantified retained delivery report: 24 hours ending 26 September 12:41 London, Lemonrock 1,019 Events, Scenic Eye 13, Fizgig 10, Gigs News 1. These are dated reported canonical creations, not current daily totals or run-streak proof. LBP has a 28 September retained run in the deployment receipt, without a qualified daily creation total. KLMA/OnTheCase/Insangel current natural-cycle health remains unverified from this review. BandForge unknown-origin restrictions remain; Music Live is deliberately parked; Fantastic All Library is manual-assisted. Current counts/cancellation coverage need the bounded snapshot and completed reporting contract.

No runtime/UI/API change was made by this prioritisation. Assignments are ready, not running in the background. Keep the contextual reasoning trial and current human memory scope unchanged.

## Current state, 28 September

**Reported live implementation: fadcb8ae525afe8d040a2ac90841f5c7cc520dc8.** BndyEnrichmentStack UPDATE_COMPLETE at **18:05:13Z**, eleven code-only Lambda updates. The corrected Stage A predecessor time is **13:10:01Z**, superseding the earlier 14:11:11Z report.

Version-2 owner-test-reset initialized in four calls. Ten verification reads reported health OK, a valid empty current-human read on an unused subject and no observed coverage-unavailable or billing-transition errors. Full private coverage identity/receipt remains with AWSCLI; the owner summary truncates that ID.

Examined baselines: three empty Lemonrock root feeds; lemonrock-gig-hydration run-b71207a9, one single-act event; LBP run-6f5b37a7, one single-act event. No expansion metadata in those examined artifacts. This is not a full historical-import inventory. No additional audit follows from release acceptance.

Accepted handback: [#80/5875912460](https://github.com/flowency-live/bndy-work/issues/80#issuecomment-5875912460). Enrichment main subsequently advanced through 9e6bbef to **6632b28eb0c8f581fd67769b681a878fa697675f**, with contextual proposal reasoning implemented and undeployed. The live pin remains fadcb8a. API 6239ffb was source-reviewed; its removal of the same-venue requirement and retention of candidates are accepted. A narrow response-evidence/assertion gap is recorded in [#81/5899963128](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5899963128), without further resolver-policy expansion. This session has not independently queried AWS.

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
| V1-01 | fadcb8a reported live; fe6e63c proposals off/diagnostics fixed; retained-input and source-error evidence #80 next | Canonical lookup correctness: conflict-aware identity; rename/delete invalidation; bounded retry of incomplete writes; human corrections precede cached matches. Positive and negative regression cases must prove the decision. | Backline-owned. Inspect current code before design; preserve canonical API resolution where context cannot decide. |
| V1-02 | Partial: bill containment and attribution implemented | Billing and title interpretation: one decision per bill; preserve real composite acts and evidenced lineups; no invented fragment acts; stamp source on creation. | Existing billing containment policy; any model activation remains separately bounded/approved. |
| V1-03 | Partial: trace/owner guard; API contract pending | Existing event identity across import keys; explicit traced lookup before creation; preserve distinct performances and bill relationships. | Reuse existing API deduplication, do not duplicate it. API gaps become work orders. |
| V1-04 | Priority: source health/daily delivery contract; API and UI assignments ready; bounded live snapshot requested | P3 accounting: complete entity inventory; existing/new/unknown separate from canonical effects; partial successes retained; retries/pages/parent-child totals reconcile. | #82 backend contract, #79 UI. Backline producer here; API portion via VSCode work order. |
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

## Historical stop and restart (superseded by the current task above)

1. Next owned implementation is the contextual Artist reasoning step above, on enrichment main in the existing checkout. Read current main/AGENTS and inspect the existing structured reasoner before introducing any new component. Claim precise files on #7 before edits.
2. Use the three decision outcomes as acceptance, not another round of identity-rule fixes. Maintain evidence provenance and contradictory/human authority. Model confidence alone is insufficient.
3. API agent follows the superseding [evidence/application support scope](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5899743194); #87 owns auth integration. Enrichment reasoning is not blocked wholesale on that lane.
4. Last verified enrichment main 9e6bbefa8b2fe3d2c8930d29abefba93f069c387, tested but undeployed. Last reviewed API 615138c; no deployment receipt. Reported live enrichment fadcb8a. Refresh pins before edits.
5. No new deployment, model-spend expansion, migration, reset, broad audit or bulk replay. Live provider qualification/application must use the existing authorised controls and a concrete bounded #80 order where needed.
6. This checkpoint records the corrected working method only. Contextual reasoning has not yet been implemented or demonstrated; do not count this documentation as product progress.

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


### 29 September evening: #81 handback reviewed, partial only

- Read exact current API master a2fb8ef6dd2ea5d7156b15e38683d1b3778ecd9d, resolution.js and the five added tests. Commit is test-only (+233 lines); cumulative guards exist in earlier code.
- Core candidate filter remains before history. New long-name assertion accepts containment, so it does not establish history participation. Unique venue-history can return before completeness guard; inner Venue read failure remains swallowed; history pagination remains unlabelled.
- [Specific correction #81/5899010360](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5899010360), [auth integration #87/5899012507](https://github.com/flowency-live/bndy-work/issues/87#issuecomment-5899012507). Revise existing proof cases rather than adding a large test programme. Reported 26 write failures are not independently reproduced or dismissed as unrelated.
- Owner's constitutional correction recorded above: real decision improvement is the acceptance unit; contextual AI reasoning remains ChatGPT-owned enrichment work, not blocked wholesale on API. No new runtime edits, test rerun, AWS calls, deployment or live identity adjudication this review.

### 29 September late evening: 615138c review

Accepted: Backline guard now precedes venue-history decisions; Venue read exceptions mark incomplete; descriptor containment joins the history cohort; tests assert Event reads. Remaining: the new same-venue restriction is an unintended policy; partial is assigned but discarded before scoring/response; a later read-only branch can erase known containment candidates as likely-new. [Finite follow-up #81/5899575531](https://github.com/flowency-live/bndy-work/issues/81#issuecomment-5899575531). Prior counterfactual-test instruction corrected by technical owner. 509 passes reported, command/suite scope and resolution of prior auth failures not yet supplied. No code changes, test rerun, AWS calls or deployment in this review; contextual AI remains owned enrichment work.
