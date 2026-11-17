# Licence and third-party notices

The original [LICENSE](../../LICENSE) is GNU Affero General Public License version 3. The [Electron](../../electron/package.json) and [frontend](../../frontend/package.json) manifests identify the licensing choice as `AGPL-3.0-only`. The original README in the root commit labels the project MIT. That statement conflicts with both manifests and the licence text. The archived files preserve the original evidence. The Free Software Foundation copyright line in `LICENSE` applies to the licence document. The Electron authorship field credits `openswarm-ai`. A separate project copyright statement was not located in the archive.

## Preserved and recovered notices

| Component | Evidence |
| --- | --- |
| Tool UI | MIT, Copyright (c) 2025 AgentbaseAI Inc. The source carries a notice in the [main frontend](../../frontend/src/toolui/LICENSE.md) and [generated app template](../../backend/apps/outputs/webapp_template/frontend/src/toolui/LICENSE.md). |
| YouTube MCP server | `@kirbah/mcp-youtube` 1.1.12, identified by the [embedded package manifest](../../backend/mcp-bundles/kirbah-mcp-youtube.js#L82856). [Full MIT notice](licenses/kirbah-mcp-youtube-1.1.12/LICENSE) |
| Notion MCP server | `@notionhq/notion-mcp-server` 2.2.1, identified by the [bundled package manifest](../../backend/mcp-bundles/notionhq-notion-mcp-server/package.json). [Full MIT notice](licenses/notionhq-notion-mcp-server-2.2.1/LICENSE) |
| Microsoft 365 MCP server | `@softeria/ms-365-mcp-server` 0.95.0, identified by the [bundled package manifest](../../backend/mcp-bundles/softeria-ms-365-mcp-server/package.json). [Full MIT notice](licenses/softeria-ms-365-mcp-server-0.95.0/LICENSE) |
| Reddit MCP Buddy | `reddit-mcp-buddy` 1.1.12, identified by the [bundled server version](../../backend/mcp-bundles/reddit-mcp-buddy.js#L22400). [Full MIT notice](licenses/reddit-mcp-buddy-1.1.12/LICENSE) |
| gaxios | Version 7.3.0, identified by the [embedded manifest](../../backend/mcp-bundles/kirbah-mcp-youtube.js#L15860). [Full Apache-2.0 licence](licenses/gaxios-7.3.0/LICENSE) |
| Google APIs Common | Version 8.0.3, identified by the [embedded manifest](../../backend/mcp-bundles/kirbah-mcp-youtube.js#L55000). [Full Apache-2.0 licence](licenses/googleapis-common-8.0.3/LICENSE) |
| MongoDB Node.js driver | Version 7.5.0, identified by the [embedded manifest](../../backend/mcp-bundles/kirbah-mcp-youtube.js#L27343). [Full Apache-2.0 licence](licenses/mongodb-7.5.0/LICENSE.md) |
| Winston | Version 3.19.0, identified by the [embedded manifest](../../backend/mcp-bundles/softeria-ms-365-mcp-server/dist/index.js#L5764). [Full MIT notice](licenses/winston-3.19.0/LICENSE) |

On 2026-11-17, the preservation review copied the full licence files listed above from the matching npm release archives. It verified each archive against the npm registry's integrity digest and recorded the source URLs and file hashes in the [notice manifest](licenses/npm-notice-sources.json). The OpenSwarm baseline remains unchanged.

## Recovered dependency and asset notices

- [Google YouTube API client](licenses/google-youtube-api/README.md) includes Google's copyright credit, the Apache 2.0 licence and the evidence for the likely 34.0.0 release.
- [Notion server notices](licenses/notion-internals/README.md) include the original end-of-file comment naming 37 packages and full notices for the 165 package versions in the release's production dependency tree. Rebuilding the release CLI reproduced the archived JavaScript byte for byte.
- [Microsoft 365 dependency comparison](licenses/softeria-verification/README.md) identifies five differences from the author's lockfile and records the licence text for the compared versions.
- [Bundle dependency inventory](licenses/bundle-dependencies/README.md) lists the packages identified in the YouTube, Reddit and Microsoft 365 bundles. Its candidate versions and notice paths distinguish embedded version evidence from release-lock and publication-date estimates.
- [Asset notices](asset-notices.md) identify copied shader and template code, skill descriptions, branding and media, with links to recovered texts and the remaining rights questions.

## Limits of the review

Both the [macOS](../../scripts/build-app.sh) and [Windows](../../scripts/build-app-win.ps1) builds suppress legal comments in generated JavaScript. Some bundles lack an install lock that identifies the precise versions shipped. The inventory records the versions for which notices were recovered. It cannot establish that every dependency or attribution survived bundling.

Redistribution questions remain for the React Bits splash port, the Bayer shader and some copied skill descriptions. The original recordings also require privacy review. See the [asset review](asset-notices.md) before packaging a derivative. Retain the applicable notices with the files you redistribute and review [AGPL sections 5, 6 and 13](../../LICENSE) for modified or hosted versions.
