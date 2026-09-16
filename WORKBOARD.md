<!-- Copy of WORKBOARD.md from flowency-live/bndy-ops, taken 16/09/2026. Change the contract there, then copy it here. -->

# BNDY workboard: agent contract

GitHub Issues in the public repo `flowency-live/bndy-work` plus the "@bndy-work" GitHub Project are the only BNDY workboard and backlog. This contract is kept in `flowency-live/bndy-ops`, with a copy in `flowency-live/bndy-work`. This file is for Claude and ChatGPT agents that read or change the board with gh or the GitHub API. Jason ruled the move on 15/09/2026 (`docs/d0/DECISIONS-2026-09-15.md`, M26 as amended that day).

## Where the board lives

| Thing | Where |
| --- | --- |
| Issues | `flowency-live/bndy-work` (public) |
| Project | "@bndy-work" (https://github.com/users/flowency-live/projects/1), owned by `flowency-live` and linked to `flowency-live/bndy-work` |
| A lane | One issue labelled `initiative` and `lane:<laneId>`. Its body holds the objective, the target state, the lane's repos as plain text, a `## Now` task list and a `## Next` task list. |
| A backlog item | A sub-issue of its lane's initiative, labelled `lane:<laneId>`, with a Rank. |
| Done cards from the website board, and what triage closed | `docs/workboard/ARCHIVE.md`. They are not issues. |

## Lanes

| Lane id | Initiative |
| --- | --- |
| `add-claim` | Add, Claim & Ownership |
| `festivals` | Festivals |
| `bndy-ops` | bndy-ops (Godmode replacement) |
| `curator-experience` | Curator experience on bndy.live |
| `rhythm` | BNDY Rhythm / Curator rewards |
| `capture` | Send to bndy / Capture transport |
| `backline` | BNDY Backline |
| `editions` | Editions & partner views |
| `security` | Security |
| `website` | Public website & proposition |
| `core-discovery` | No initiative. One low-priority backlog item, "Core live discovery", holds this lane's items as its sub-issues. |

Labels:

- `initiative` marks a lane issue.
- `lane:<laneId>` names the lane, for example `lane:festivals`.
- `triage` marks an imported issue Jason has not reviewed. Only imported issues carry it. None does today, because Jason triaged every item before it was created. Work added after the import never does.
- `source:bugs-features` and `source:cto-backlog` name the tracker an intake issue came from.

Project fields:

| Field | Type | Values | Set on |
| --- | --- | --- | --- |
| Status | single select | Backlog, Next, Now, Done | every item |
| Delivery state | single select | live, building, planned, legacy, decommissioned | initiatives |
| Health | single select | green, amber, red, blue, grey | initiatives |
| Lane | single select | the lane ids | initiatives and backlog items |
| Rank | number | 1 is the highest priority | backlog items |

Now is active work. Next is committed upcoming work. Backlog is approved but unscheduled work. Done is finished work that evidence proves.

An initiative's Status is Now while its lane has active work. It is Next while the lane has only committed upcoming work. Otherwise it is Backlog.

An initiative's Health is its lane's health. Triage set it from the website board, or by Jason's ruling for a new initiative. Target state stays a line of text in the initiative body.

Every issue created from the website board or the intake trackers ends with an `ops-import:<kind>:<id>` marker. Do not remove it. It ties the issue to its triage ruling and stops a second copy being created.

The website board (`public/workboard.json` in `flowency-live/bndy-website`, shown at www.bndy.co.uk/workboard) is retired now the board has moved. Do not edit it. Nothing is exported back to JSON. No snapshot of the board is committed or kept anywhere.

The Ops Work view (`/work`) reads the board through bndy-ops's own reader function (`server/work-reader`, served at `/ops-api/work` on ops.bndy.live), which holds a read-only GitHub token in AWS Secrets Manager. Never put a token in the Ops bundle.

## Token scopes

The token needs the `repo` and `project` scopes. Add the project scope with `gh auth refresh -s project`. Check the scopes with `gh auth status`.

## Setup for the commands below

```sh
OWNER=flowency-live
REPO=flowency-live/bndy-work
PROJECT=$(gh project list --owner "$OWNER" --format json --jq '.projects[] | select(.title == "@bndy-work") | .number')
PROJECT_ID=$(gh project view "$PROJECT" --owner "$OWNER" --format json --jq '.id')
gh project field-list "$PROJECT" --owner "$OWNER" --format json
```

The field list gives each field id and each option id. `gh project item-list` names a field's value after the field, with its first letter in lower case: `status`, `lane`, `rank`, `health` and `delivery state`.

## Reading work

Now:

```sh
gh project item-list "$PROJECT" --owner "$OWNER" --format json --limit 1000 \
  --jq '.items[] | select(.status == "Now") | [.content.number, .lane, .content.title] | @tsv'
```

Next:

```sh
gh project item-list "$PROJECT" --owner "$OWNER" --format json --limit 1000 \
  --jq '.items[] | select(.status == "Next") | [.content.number, .lane, .content.title] | @tsv'
```

Backlog, in rank order:

```sh
gh project item-list "$PROJECT" --owner "$OWNER" --format json --limit 1000 \
  --jq '[.items[] | select(.status == "Backlog" and .rank != null)] | sort_by(.rank) | .[] | [.rank, .content.number, .lane, .content.title] | @tsv'
```

Initiatives by health:

```sh
gh project item-list "$PROJECT" --owner "$OWNER" --format json --limit 1000 \
  --jq '.items[] | select(.health != null) | [.health, .content.number, .lane, .content.title] | @tsv'
```

Triage:

```sh
gh issue list --repo "$REPO" --label triage --state open --limit 200
```

One lane, its Now and Next task lists, and its backlog:

```sh
gh issue list --repo "$REPO" --label initiative --label lane:festivals --state all
gh issue view <number> --repo "$REPO"
gh api "repos/$REPO/issues/<number>/sub_issues?per_page=100" --jq '.[] | [.number, .state, .title] | @tsv'
```

## Promoting work

Promote work by setting its Status. Never create a second issue or a second task item for work that already exists.

```sh
ITEM=$(gh project item-list "$PROJECT" --owner "$OWNER" --format json --limit 1000 --jq '.items[] | select(.content.number == <number>) | .id')
gh project item-edit --id "$ITEM" --project-id "$PROJECT_ID" --field-id <Status field id> --single-select-option-id <Now option id>
```

- A backlog item stays a sub-issue of its initiative when its Status moves to Next or Now.
- A task item in an initiative body moves between `## Next` and `## Now` by editing the body. Move the line. Do not copy it.
- Set the initiative's Status to Now when its lane has active work.
- Change an initiative's Health by setting its Health field, with the Health field id and option id from the field list.

## Recording progress

- Record progress as a comment that links the evidence: a PR, a commit, a test run or a deployment.

  ```sh
  gh issue comment <number> --repo "$REPO" --body "<what changed>. Evidence: <links>"
  ```

- Set Status to Done and close the issue only when evidence proves the work is done. A production claim needs production evidence.

  ```sh
  gh issue close <number> --repo "$REPO" --reason completed --comment "Done. Evidence: <links>"
  ```

- Tick a task item in an initiative body only after a comment on that issue links its evidence.

## Adding work

Search first, and reuse an existing issue rather than add a duplicate:

```sh
gh issue list --repo "$REPO" --state all --search "<words>"
```

Work an agent adds after the import goes straight to the backlog. It is a sub-issue under its lane's initiative, with the lane label, Status Backlog, Lane and a Rank. It never carries the `triage` label.

```sh
URL=$(gh issue create --repo "$REPO" --title "<title>" --body "<detail and evidence>" --label lane:festivals)
NUMBER=${URL##*/}
PARENT=$(gh issue list --repo "$REPO" --label initiative --label lane:festivals --state all --json number --jq '.[0].number')
CHILD_ID=$(gh api "repos/$REPO/issues/$NUMBER" --jq .id)
gh api --method POST "repos/$REPO/issues/$PARENT/sub_issues" -F sub_issue_id="$CHILD_ID"
ITEM=$(gh project item-add "$PROJECT" --owner "$OWNER" --url "$URL" --format json --jq .id)
gh project item-edit --id "$ITEM" --project-id "$PROJECT_ID" --field-id <Status field id> --single-select-option-id <Backlog option id>
gh project item-edit --id "$ITEM" --project-id "$PROJECT_ID" --field-id <Lane field id> --single-select-option-id <lane option id>
gh project item-edit --id "$ITEM" --project-id "$PROJECT_ID" --field-id <Rank field id> --number <rank>
```

- The sub-issue API takes the child's numeric id, not its issue number.
- The `triage` label is for imported issues only. Do not add it to new work.
- Reuse an existing lane whenever the work belongs to its stream. Do not create a parallel lane just because a new agent or session starts.
- Rank 1 is the highest priority within the unscheduled backlog. It is not a commitment to build that item next.
- Keep ranks unique. When a new Rank collides, move the lower-priority items down by one.

## Triage

Jason triaged every website board item before it was created, so no issue started with the `triage` label. If an issue ever carries it, triage it in one of three ways.

- Keep it. Move it under the right lane initiative, add the lane label, set Lane and Rank, then clear the label.

  ```sh
  gh api --method POST "repos/$REPO/issues/<initiative number>/sub_issues" -F sub_issue_id=<child id> -F replace_parent=true
  gh issue edit <number> --repo "$REPO" --add-label lane:<laneId> --remove-label triage
  ```

- Close it as a duplicate, naming the issue it duplicates.

  ```sh
  gh issue comment <number> --repo "$REPO" --body "Duplicate of #<other>"
  gh api --method PATCH "repos/$REPO/issues/<number>" -f state=closed -f state_reason=duplicate
  ```

- Close it as not planned, with the reason.

  ```sh
  gh issue close <number> --repo "$REPO" --reason "not planned" --comment "<why>"
  ```

## Rules carried from the website contract

The first five rules are carried verbatim from the bndy-website `WORKBOARD.md` (blob `b7a0cb0abb474d9d1e5ac55553dc11b04a4ccae4`). The last rule carries that contract's rule on private runtime identifiers, which Jason widened on 15/09/2026 to cover issues and comments. They all still hold.

- Never mark something `done` purely because code exists. Production/deployment claims need production evidence.
- The architectural source of truth is: transport -> Capture -> Enrichment/evidence/claims -> projection -> canonical BNDY APIs.
- `bndy-frontstage` is decommissioned. Do not add new work there.
- `bndy-signals` is legacy. New intelligence work belongs in `bndy-enrichment`; migrate useful concepts rather than extending the old runtime.
- Known reliable venue listing websites belong in the Source Registry as scheduled venue sources. Do not build a parallel venue-worker database or direct writer.
- flowency-live/bndy-work is public. Never put secrets, personal data or details of unfixed security weaknesses in its issues or comments.
- Keep private runtime identifiers and receipts, such as account ids, ARNs, secret names and request receipts, out of issues and comments.

## How the board was built

On 16/09/2026 Jason triaged the website board one item at a time: 19 initiatives and 39 backlog items. The rulings are in `docs/workboard/TRIAGE.md`. The issues were created from those rulings, not copied from the board.

- Merged initiatives are one issue. Its body names the website board lanes it came from.
- Kept backlog items are sub-issues of their initiative, ranked in the triaged order. Their bodies record the ruling.
- Done cards, closed items and dropped cards are in `docs/workboard/ARCHIVE.md`.
- The intake items in `BUGS-FEATURES.md` and `cto/CTO-BACKLOG.md` are triaged the same way. Each is created or discarded as Jason rules, checked against the code first.
- Later on 16/09/2026 Jason moved the cards to the public repo `flowency-live/bndy-work`. GitHub cannot transfer issues from a private repo to a public one, so they were recreated there with the same `ops-import` markers. The originals in bndy-ops are closed with a link to their copy, and their old Project cards are archived.
- Nothing is exported back to the website board, and no board JSON is kept.
