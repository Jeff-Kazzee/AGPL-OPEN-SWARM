# Licence and third-party notices

The original [LICENSE](../../LICENSE) is GNU Affero General Public License version 3. The [Electron](../../electron/package.json) and [frontend](../../frontend/package.json) manifests identify the licensing choice as `AGPL-3.0-only`. The original README in the root commit labels the project MIT. That statement conflicts with both manifests and the licence text. The archived files preserve the original evidence. The Free Software Foundation copyright line in `LICENSE` applies to the licence document. The Electron authorship field credits `openswarm-ai`. A separate project copyright statement was not located in the archive.

## Notices present in the archive

| Component | Evidence |
| --- | --- |
| Tool UI | MIT, Copyright (c) 2025 AgentbaseAI Inc. The source carries a notice in the [main frontend](../../frontend/src/toolui/LICENSE.md) and [generated app template](../../backend/apps/outputs/webapp_template/frontend/src/toolui/LICENSE.md). |
| Notion MCP server | `@notionhq/notion-mcp-server` 2.2.1 in the [bundled package manifest](../../backend/mcp-bundles/notionhq-notion-mcp-server/package.json). Exact-version [registry metadata](https://registry.npmjs.org/@notionhq%2fnotion-mcp-server/2.2.1) identifies MIT. |
| Microsoft 365 MCP server | `@softeria/ms-365-mcp-server` 0.95.0 in the [bundled package manifest](../../backend/mcp-bundles/softeria-ms-365-mcp-server/package.json). Exact-version [registry metadata](https://registry.npmjs.org/@softeria%2fms-365-mcp-server/0.95.0) identifies MIT. |
| YouTube MCP server | The [macOS build script](../../scripts/build-app.sh) identifies the checked-in bundle as `@kirbah/mcp-youtube` with a Google YouTube API dependency. The exact bundled server version is unverified. |

The package metadata identifies direct packages. It does not supply the required copyright and permission notices for their bundled code and dependencies. The [macOS build script](../../scripts/build-app.sh) and [Windows build script](../../scripts/build-app-win.ps1) explicitly use `--legal-comments=none` when producing bundles. The snapshot contains no complete bundle-level notice inventory. Recover the exact dependency lists and applicable notices before public redistribution.

The source also includes a [skill snapshot](../../backend/apps/skill_registry/skills_snapshot.json), upstream artwork, and onboarding media. Their separate redistribution terms and embedded content need review. The presence of these files at the upstream GitHub revision is provenance evidence. It does not settle their licence.

Preserve notices in the independent history and in any agency derivative. For shipped or hosted modifications, check the corresponding-source requirements in [AGPL sections 5, 6, and 13](../../LICENSE). Keep new project branding separate from the original product marks and authorship.
