# Swarm Cabinet

An independent community preservation copy of OpenSwarm 1.7.7.

OpenSwarm is a desktop workspace for running agents and organising their sessions, files, tools, and outputs on a dashboard. This archive records a specific upstream snapshot. It carries no endorsement from the original project and has no independent installer or update channel.

## Provenance and authors

The original project is [OpenSwarm by openswarm-ai](https://github.com/openswarm-ai/openswarm). The Electron manifest credits `openswarm-ai`. GitHub attributes the pinned upstream commit to [ciregenz](https://github.com/ciregenz). The preservation commits record the import and subsequent documentation. The upstream contributors retain credit for their work.

The source came from the local ZIP `openswarm-14120a43f7e43cbe5a1263fe379b8dfe0a195fb0.zip`. See the [pinned upstream tree](https://github.com/openswarm-ai/openswarm/tree/14120a43f7e43cbe5a1263fe379b8dfe0a195fb0). The archive has 2,024 files, all of which matched GitHub's tree by path, Git blob SHA, and executable mode. The independent root commit `d2c3e0ff057f4a6c47fea7c8ce826a56646b6972` preserves that tree. [Provenance record](docs/preservation/provenance.md)

`electron/package.json` and `backend/apps/help/changelog.py` both identify the application as **1.7.7**. The `frontend` package has its own version number.

## Features

- Use dashboards to arrange agent sessions, browser cards, and app previews. [Upstream screenshot](assets/screenshot.png)
- Run a local FastAPI backend with a React frontend and Electron desktop shell. [Backend entry point](backend/main.py), [frontend manifest](frontend/package.json), [desktop manifest](electron/package.json)
- Configure model access, agent modes, skills, and MCP tools through the application. MCP lets an agent call tools exposed by a local or remote server. [Settings code](backend/apps/settings), [MCP configuration](backend/apps/tools_lib/mcp_config.py)

## Quick start

These are the development entry points as shipped. They were inspected but have not been run for this archive. Review the scripts and use an isolated development environment. Both root launchers can install dependencies and download tools.

| Platform | Requirements and entry point |
| --- | --- |
| Windows | `run.ps1` specifies Python 3.12+, Node.js 20+, and npm. From the repository root run `./run.ps1` in PowerShell. |
| macOS | The original guide lists Python 3.11+, Node.js 18+, npm, and Git. Use the Node.js `20.18.1` pin in `.nvmrc`. From the repository root run `bash run.sh`. The script downloads Darwin-specific `uv` binaries if needed. |

The launchers start the backend, frontend, and Electron window. By default the frontend is at `http://localhost:3000`, the backend at `http://localhost:8324`, and the FastAPI docs at `http://localhost:8324/docs`. Windows binds its backend to `127.0.0.1`. The macOS backend script binds to `0.0.0.0` and the root launcher may terminate processes using its selected ports. Use an isolated network and check port ownership before you start it. [Windows launcher](run.ps1), [macOS launcher](run.sh), [backend launcher](backend/run.sh)

Once the window opens, the upstream flow is to configure a model in Settings, open or create a dashboard, and add an agent session. Start with a disposable workspace and check which files, tools, and external providers the session can access. The [upstream screenshot](assets/screenshot.png) shows the dashboard at this snapshot. Functional onboarding, account sign-in, and provider connectivity remain unverified.

## Configuration

| Scope | Where to look |
| --- | --- |
| Model access and tools | See [backend environment reference](backend/ENV_README.md), [settings](backend/apps/settings), and [MCP configuration](backend/apps/tools_lib/mcp_config.py). Use your own account or API credentials. Keep real values out of Git. |
| Google Workspace | The upstream example lists `GOOGLE_OAUTH_CLIENT_ID` and `GOOGLE_OAUTH_CLIENT_SECRET` for optional Google OAuth. The historical setup guide lists `http://localhost:8324/api/tools/oauth/callback`. Verify this flow with your own OAuth client before relying on it. [Environment example](backend/.env.example), [upstream setup guide](GETTING_STARTED.md) |
| Development analytics | Both root launchers have an `OPENSWARM_ANALYTICS=1` opt-in path that defaults to the upstream analytics endpoint. Leave it unset for ordinary development. The application also contains other network integrations, so use network isolation if you need to prevent egress. [Windows launcher](run.ps1), [macOS launcher](run.sh), [analytics client](backend/apps/service/analytics/client.py) |
| Signing and publishing | The example files name Apple, Azure, and GitHub release variables for upstream builds. They are outside the development setup. The Electron manifest still identifies `openswarm-ai/openswarm` as the release repository. [Windows example](.env.windows.example), [desktop manifest](electron/package.json) |

## Documentation and checks

- [Provenance and checks](docs/preservation/provenance.md) records the import, static verification, and limits.
- [Licence and third-party notices](docs/preservation/third-party-notices.md) records the licence evidence and outstanding redistribution questions.
- From the source root, `node scripts/run-phase-tests.js` is the upstream dependency-free phase-test entry point. It runs checks for build and release helpers. [Phase-test script](scripts/run-phase-tests.js)
- From `electron/`, the manifest's `test` script runs four Node test files. The Python test dependencies are listed in `backend/requirements-dev.txt`, and the suite lives under `backend/tests/`. [Electron manifest](electron/package.json), [test dependencies](backend/requirements-dev.txt)
- The Playwright jobs require a packaged Electron build on macOS or Windows. Follow the platform-specific setup in the [end-to-end guide](e2e/README.md).

## Known limitations

The original `GETTING_STARTED.md` refers to `backend/run/dev.sh` and `frontend/run/dev.sh`, which are absent from the archive. The original README also contains old desktop dependencies and platform support claims. Use the actual manifests and launch scripts to identify what ships in this tree. Native Windows and macOS behaviour, packaged updates, Linux desktop support, sign-in, and independent release distribution have not been verified. The upstream CI and publishing workflows are preserved as source, including tag and manual release triggers.

## Contributing

Propose a change with its scope, source evidence, and checks. Keep the root import intact. Make changes on a topic branch and propose them against `dev` once the preservation repository is open to contributions. Keep upstream attribution and describe changes prominently. For a report containing credentials or private data, contact the repository maintainer privately rather than opening a public issue. [Historical upstream contribution guide](CONTRIBUTING.md)

## Licence

The root [LICENSE](LICENSE) contains GNU Affero General Public License version 3. The [Electron manifest](electron/package.json) and [frontend manifest](frontend/package.json) declare `AGPL-3.0-only`. The imported upstream README had a conflicting MIT label. The project licence and any separately licensed material are recorded in [third-party notices](docs/preservation/third-party-notices.md).

Preservation changes on 2026-11-17 add documentation and a proposed archive logo. The application source retains the upstream identity and version.
