# Link Availability and Reappearance Policy

**Status:** Policy specification; automated checking is not yet deployed.

## Principle

Public listings do not expire merely because time has passed. Their display state follows verified source availability and publication eligibility.

## States

- `AVAILABLE`: the canonical page was successfully retrieved.
- `CHECK_PENDING`: one retrieval failed; keep the listing and retry.
- `UNAVAILABLE_UNCONFIRMED`: repeated checks failed under independent conditions; temporarily hide or label the listing, without deleting its private source record.
- `REMOVED_CONFIRMED`: the creator or authoritative source confirms removal, or reliable evidence establishes intentional withdrawal.
- `RESTORED`: the same source is reachable again; verify identity/version and rights before restoring the listing.

## Required safeguards

A timeout, rate limit, robots restriction, login wall, DNS problem, server outage, or crawler error is not proof of deletion. Use retry/backoff and more than one observation before changing a public listing's state.

If the source returns, verify it is the same work/version and that its rights and public-sharing conditions remain valid. A changed or replaced page must not be silently treated as the original.

The public board contains only the minimum metadata and link needed for discovery. Detailed source history and operational evidence remain in private N.U infrastructure.

## Deletion

When a creator confirms withdrawal, remove the listing from active public discovery promptly. Do not retain a public copy of the work. Apply the private data-retention and deletion rules to any stored payloads. Git commit history is not a short-memory store: removing a listing from the current version does not erase earlier commits, forks, caches, or downloaded copies.

## Automation status

No crawler, scheduled monitor, or automatic restoration service is claimed to be active until implemented, tested, and its failure modes documented.
