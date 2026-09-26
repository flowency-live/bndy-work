# Backline technical handover: single entry point

Updated 26 September 2026, 13:15 London, by the Backline CTO session. Every link is to remote main or to an issue; nothing here depends on a local checkout. Read the four documents in "Start here" in order, then the rest as needed.

## Start here

1. [Status](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-STATUS.md): what is live, the measured 24-hour canonical adds by source, open holds by family, queue depths, pending owner decisions, next CTO work. Rewritten 26/09.
2. [Handover of 24 September, updated 26/09](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-CTO-HANDOVER-2026-09-24.md): the finding that changed the plan, what is live, the technical section "how the intelligence path works now", what went wrong this week, decisions pending, next work with owners.
3. [Intelligence implementation plan](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-INTELLIGENCE-EXECUTION-PLAN.md): packages P0 to P6, acceptance cases, release protocol, and the progress record before section 9.
4. [CTO ledger](https://github.com/flowency-live/bndy-ops/blob/main/audit/2026-09-24-cto-ledger.md): part A records to delete, part B design defects (B1 to B14), part E lessons from the owner's hold actions, the 24-hour adds table.

## Governing documents

- [Constitution](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-CONSTITUTION.md): the decision chain (source evidence proposes, context decides, a person settles doubt).
- [Runbook](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-RUNBOOK.md) and [Enrichment contract](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-ENRICHMENT.md).
- [Golden cases G1 to G17](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-GOLDEN-CASES.md) and the [billing containment rule](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-P0-BILLING-CONTAINMENT.md) (approved 24/09, live in R1).
- [Documentation index](https://github.com/flowency-live/bndy-enrichment/blob/main/docs/BACKLINE-DOCUMENTATION-INDEX.md) for everything older.
- [Source-agent contract](SOURCE-AGENT-COORDINATION-2026-09-17.md) in this repo.

## Issues that carry the live record

- [#7 Programme](https://github.com/flowency-live/bndy-work/issues/7): progress posts after each delivery gate.
- [#80 Deployment queue](https://github.com/flowency-live/bndy-work/issues/80): the only place a deploy is ordered or reported. R1 (59d9083) is live; R2 (5974843) is ordered and waits for the owner's go.
- [#82 Accounting contract](https://github.com/flowency-live/bndy-work/issues/82) for [#79 Ops dashboard](https://github.com/flowency-live/bndy-work/issues/79).
- [#59 Lemonrock](https://github.com/flowency-live/bndy-work/issues/59), the acceptance source; [#70 Fizgig](https://github.com/flowency-live/bndy-work/issues/70), [#83 source identity out of the API](https://github.com/flowency-live/bndy-work/issues/83), [#81 profile application](https://github.com/flowency-live/bndy-work/issues/81).
- Evidence folders in bndy-ops: [hold register 24/09](https://github.com/flowency-live/bndy-ops/tree/main/audit/2026-09-24-hold-register), [Lemonrock reconcile 22/09](https://github.com/flowency-live/bndy-ops/tree/main/audit/2026-09-22-lemonrock-reconcile).

## Code map (bndy-enrichment, remote main)

| Concern | Where | What it does |
| --- | --- | --- |
| Canonical copy and lookup index | [src/bndy-baseline/lookup.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/bndy-baseline/lookup.ts), [change-store.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/bndy-baseline/change-store.ts) | `LOOKUP#name|core|external|place|postcode|facebook|gig#...` rows in the state table, written per stream change; backfill CLI `canonical:lookup-backfill` |
| Change stream worker | [src/handlers/canonical-change-stream-worker.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/handlers/canonical-change-stream-worker.ts), wired in [lib/bndy-enrichment-stack.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/lib/bndy-enrichment-stack.ts) behind CDK context `canonicalChangeStreamsEnabled` | reads bndy-artists, bndy-venues, bndy-events streams (ARNs in SSM `/bndy/canonical/<table>/stream-arn`) |
| Context before API | [src/projection/context.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/projection/context.ts) | `CanonicalLookupContext`: artist by native id, facebook, exact name, core name; venue by native id, place, postcode+name, name+town, unique name |
| Projection engine | [src/projection/engine.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/projection/engine.ts) | `resolveBill` asks context first; `ProposedActError` holds a bill as `bill-needs-confirmation`; `confirmNew` on human new-act; `humanVenue()` facts; `nothing-to-cancel` |
| Hold actions and lessons | [hold-actions.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/projection/hold-actions.ts), [hold-retry.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/projection/hold-retry.ts), [hold-lessons.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/projection/hold-lessons.ts), [exception-sink.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/projection/exception-sink.ts) | tell/retry/ignore, venue facts `same-venue` and `venue-address`, monthly `HOLD_ACTION#YYYY-MM` index |
| Billing | [src/sources/billing/](https://github.com/flowency-live/bndy-enrichment/tree/main/src/sources/billing) | `splitLineup`, guest-after-feat, genre and first-name lists, `proposed` parts, session and no-act patterns |
| Lemonrock | [src/sources/adapters/lemonrock/](https://github.com/flowency-live/bndy-enrichment/tree/main/src/sources/adapters/lemonrock), [runner/lemonrock-future-refresh.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/sources/runner/lemonrock-future-refresh.ts) | gig page JSON-LD venue name and address; nightly future refresh, bounded by newly queued gigs |
| Live Band Photos | [src/sources/adapters/livebandphotos/](https://github.com/flowency-live/bndy-enrichment/tree/main/src/sources/adapters/livebandphotos) | town taken from the place name after the comma when no address row exists |
| Shared AWS clients | [src/knowledge/stores/clients.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/knowledge/stores/clients.ts) | one DynamoDB and S3 client per process (R2, on main, not deployed) |
| Canonical API caller | [src/projection/bndy-api.ts](https://github.com/flowency-live/bndy-enrichment/blob/main/src/projection/bndy-api.ts) | sends `venuePostcode`, `confirmNew`; does not yet stamp `source` on creations (ledger B14) |

Canonical side (bndy-serverless-api, master; owned by the owner's cleanup lane since 25/09): artists-lambda `lib/identity.js` region from postcode and the ONS gazetteer (`lib/gazetteer.json`, built by `scripts/build-gazetteer.mjs`), `lib/resolution.js` containment and name history, `wrapResponse` resolution contract on 422s, data-quality gate at creation only; venues lambda `venue-deduplication.js` stores a postcode found in the address.

## Operator commands (tools, not authorisation)

```
npm run holds:retry -- --reason <regex> --actor <email> --note <why> [--source] [--since] [--limit] [--apply]
npm run holds:lessons -- --month YYYY-MM [--all]
npm run projection:replay -- --keys-file <keys> --error <regex> [--apply]
npm run lemonrock:trace -- <id|url>
npm run lemonrock:reconcile
npm run lemonrock:rehydrate -- <ids>
npm run canonical:lookup-backfill -- --apply
```

Mutating runs need the owner's word. Deploys only by the AWS worker from the `_ops` clones, with `git log --oneline -1` of the clone pasted on #80.

## AWS names

Account 771551874768, eu-west-2. Stack `BndyEnrichmentStack`. State table `BndyEnrichmentStack-StateTable9728C7E5-14HR6N3NEWGLM` (GSIs `ObservationClaimsIndex` on `GSI1PK`, `SubjectClaimsIndex` on `GSI2PK`). Queues `ProjectionQueue84CD9FA9-MNRzvzNKh5Vg`, `SourceScanQueue1C378650-2ik6EDD7UUyd` and their DLQs. Canonical tables `bndy-events`, `bndy-artists`, `bndy-venues`.

## Rules that stand

Main and master only; no branches, worktrees or pull requests. Tests first; commit gate is tsc plus the full suite by exit code. No claim about system behaviour without the query or trace. Postcode is fact, a town name is a guess. DJ, karaoke, quiz and disco are never listed; sessions are captured and held with their pattern. Purges, redrives, hold changes and canonical deletions only on the owner's word. Questions to the owner one at a time, in plain English.
