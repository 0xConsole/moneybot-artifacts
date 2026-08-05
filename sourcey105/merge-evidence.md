# Frantic Bounty #120 — Merge & Live-Surface Evidence

This document proves that PR #105 (Cartesia vendor catalog offer) is **merged** into
`sourcey/startup-credits` and the vendor file is **live** on the canonical raw surface.
It is the merge-evidence artifact the Frantic auto-reviewer required.

---

## 1. PR Merged State (GitHub REST API)

**Endpoint:** `GET https://api.github.com/repos/sourcey/startup-credits/pulls/105`
**Captured:** 2026-08-05T08:55Z (UTC)

| field | value |
|---|---|
| number | 105 |
| state | closed |
| **merged** | **true** |
| **merge_commit_sha** | `fd96b1b5bdaff19cdc76f58da51781a134b930b6` |
| **merged_at** | `2026-08-04T22:49:58Z` |
| title | catalog: add Cartesia startups grant offer (review rounds resolved) |
| html_url | https://github.com/sourcey/startup-credits/pull/105 |
| base.ref | main |
| head.label | 0xConsole:fix-v3 |

The raw API JSON is committed alongside this file as `pr105-merged-state.json`
and is re-fetchable from the public GitHub API (no auth required for reads).

## 2. Live Sourcey Vendor Surface

**Canonical raw URL (live):**
https://raw.githubusercontent.com/sourcey/startup-credits/main/vendors/ca/cartesia.yaml

**HTTP status:** `200` — fetched 2026-08-05T08:55Z (UTC)
**Content-Length:** 2822 bytes
**Content-Type:** `text/plain; charset=utf-8`

The file is served from the **main** branch of `sourcey/startup-credits`, which is
the repo that PR #105 was merged into. The first lines confirm the vendor record:

```yaml
schema_version: sourcey.vendor-authoring/v1alpha1
entity_id: ent_01kz1mc89687bg7rm79pjm8v5x
slug: cartesia
name: Cartesia
domains:
  - value: cartesia.ai
    role: primary
category: ai-ml
programs:
  - program_slug: cartesia-startups-grant
```

A byte-identical snapshot is committed alongside this file as
`cartesia-live-snapshot.yaml`.

## 3. CI Pass Status

CI ran on the PR head commit `1b0f9f62d617aaa47106da88ba6d31ebdc44b886` (the
commit that was squashed/merged to produce merge commit `fd96b1b5...`).

### Check run (GitHub Actions)
| field | value |
|---|---|
| name | validate |
| status | completed |
| **conclusion** | **success** |
| app | GitHub Actions |
| run_url | https://github.com/sourcey/startup-credits/actions/runs/30884342449/job/91912166708 |

### Combined status (commit status API)
| field | value |
|---|---|
| state | **success** |
| context | sourcey/admission |
| target_url | https://artifacts.sourcey.com/catalog/data/admissions/tree-c948d10783432f61893bcdb6534f9a685731478c/sourcey-catalog-admission.tar.gz |

Both the CI validate check-run and the Sourcey admission status returned
**success**.

---

## Summary

All three required evidence items are satisfied:

1. **PR merged** — GitHub API confirms `merged: true`, merge commit
   `fd96b1b5bdaff19cdc76f58da51781a134b930b6`, merged 2026-08-04T22:49:58Z.
2. **Live vendor surface** — `cartesia.yaml` is fetchable at the canonical
   raw GitHub URL on the `main` branch (HTTP 200, 2822 bytes).
3. **CI passed** — `validate` check-run conclusion `success`; Sourcey admission
   combined status `success`.

## Files in this evidence bundle

- `merge-evidence.md` — this document
- `pr105-merged-state.json` — raw GitHub PR API response (merged: true)
- `cartesia-live-snapshot.yaml` — byte-identical snapshot of the live vendor file

This evidence bundle resolves the auto-reviewer rejection
"No merge evidence exists in the delivered artifacts".
