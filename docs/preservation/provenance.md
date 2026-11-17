# Source provenance and checks

The local source archive is `openswarm-14120a43f7e43cbe5a1263fe379b8dfe0a195fb0.zip`. Its SHA-256 is `d526d01c001e5bb830b21a8e4337f1457dbf7d89812509e1b5b0db233348b91c`.

| Record | Value |
| --- | --- |
| Original project | OpenSwarm, `openswarm-ai/openswarm` |
| Upstream revision | [14120a43f7e43cbe5a1263fe379b8dfe0a195fb0](https://github.com/openswarm-ai/openswarm/tree/14120a43f7e43cbe5a1263fe379b8dfe0a195fb0) |
| Upstream commit author | `ciregenz`, per [GitHub commit metadata](https://github.com/openswarm-ai/openswarm/commit/14120a43f7e43cbe5a1263fe379b8dfe0a195fb0) |
| Upstream commit date | 2026-08-12 UTC, per the same commit |
| Application version | 1.7.7 in [Electron](../../electron/package.json) and [backend release notes](../../backend/apps/help/changelog.py) |
| Independent root | `d2c3e0ff057f4a6c47fea7c8ce826a56646b6972` |
| Git tree | `be8f2cb4c073f5f4bfe2ecdf0e27d8fce704e4b8` |
| Source imported | 2,024 files and 33 executable file modes |

## What the checks establish

On 2026-11-17, archive inspection rejected unsafe Windows path forms, Git metadata, links, encrypted entries, and case collisions. The 2,024 file reads passed the ZIP integrity check. Each extracted file matched its archive SHA-256. The file paths, Git blob IDs, and modes matched the complete [pinned GitHub tree response](https://api.github.com/repos/openswarm-ai/openswarm/git/trees/14120a43f7e43cbe5a1263fe379b8dfe0a195fb0?recursive=1). A fresh repository recorded the same bytes and modes in a parentless commit.

The source scan covered all file paths and applied credential, personal-data, and endpoint patterns to text. The static check parsed 703 Python files and nine package manifests without errors. Test strings, examples, and a credential-handling docstring produced candidate matches. This was a bounded scan and does not certify bundled code or media as free of private material. See [third-party notices](third-party-notices.md) for the independent redistribution check.

The checkout audit checked Git object integrity and the source inventory. Dependency installation, desktop startup, account flows, end-to-end tests, and packaged builds remain unverified. The required local untrusted-code sandbox was unavailable during preparation.

To inspect the original README and tree from this repository:

```sh
git show d2c3e0ff057f4a6c47fea7c8ce826a56646b6972:README.md
git ls-tree -r d2c3e0ff057f4a6c47fea7c8ce826a56646b6972
```

The ZIP does not carry the upstream Git history, signatures, or release artifacts. Those can be checked independently using the pinned [upstream revision](https://github.com/openswarm-ai/openswarm/tree/14120a43f7e43cbe5a1263fe379b8dfe0a195fb0).
