# Upstream and maintenance review

This package maintains `vfile-statistics@2.0.1` under the independent `@stackline/vfile-statistics` name.

- Source: https://github.com/vfile/vfile-statistics/tree/89e02204e340f99347cb4c2d8d2cfe57214a9cb7
- Public npm artifact integrity: `sha512-W6dkECZmP32EG/l+dp2jCLdYzmnDBIw6jwiLZSER81oR5AHRcVqL+k3Z+pfH1R73le6ayDkJRMk0sutj1bMVeg==`.
- Upstream issue evidence checked: 2026-09-29T00:22:21.287727+00:00.
- Original license and author notices are retained.
- The upstream published runtime files and declarations are hash-checked in `.stackline/upstream.json`. Any runtime fix is explicitly listed there.
- Functional upstream suites run against the source and extracted final package. Development tools were reduced to those used by validation; full source and runtime audits must pass.
- Only direct dependencies of the original Stackline portfolio are in this migration. This is not a claim that all transitive projects are maintained by Stackline.

## Issue triage

The queried open-issue list contained no issue entries. This does not establish that the upstream is abandoned or bug-free. No runtime bug fix is claimed for this initial maintenance release.

The evidence query fetched the latest 100 open and 30 closed issue/PR entries and removed PRs. Closed entries were collected for context; this report does not claim an exhaustive historic review.

## Release discipline

The source commit, passing CI and CodeQL, reviewed CI tarball hash, npm provenance, normal and aliased installs, and immutable GitHub release are checked before a release is complete. Published versions and tags are never replaced.
