# Notices for the bundled Notion server

OpenSwarm 1.7.7 contains the CLI from `@notionhq/notion-mcp-server` 2.2.1. On 2026-11-17, esbuild 0.28.1 reproduced every byte of the [archived JavaScript](../../../../backend/mcp-bundles/notionhq-notion-mcp-server/dist/index.js) from the npm release. The [OpenAPI document](../../../../backend/mcp-bundles/notionhq-notion-mcp-server/scripts/notion-openapi.json) also matched the release byte for byte. The [server's own MIT licence](../notionhq-notion-mcp-server-2.2.1/LICENSE) accompanies these dependency notices.

## Notices to retain

- The [original legal trailer](cli-legal-trailer.txt) preserves the complete comment from the end of the npm CLI. It names 37 packages. OpenSwarm's [build script](../../../../scripts/build-app.sh#L244) strips legal comments when it bundles the CLI for Node.
- The [collected notices](THIRD-PARTY-NOTICES.txt) cover all 165 distinct package versions across 180 non-development dependency entries in Notion's [release lockfile](https://github.com/makenotion/notion-mcp-server/blob/d802a0cd7d77c77b0a659be3fd98a9a23975b6e9/package-lock.json). Each notice starts with its package name, version and archive path. For `cookie-signature` 1.0.6 and `data-uri-to-buffer` 4.0.1, the full licence comes from the release README.
- The [source manifest](sources.json) records the npm archive URL and integrity digest for every dependency. Each file entry gives its SHA-256 hash, byte length and offset in the collected notices. The two README entries also give the source offset and full README hash.

## Verification and limits

The [npm release metadata](https://registry.npmjs.org/@notionhq%2fnotion-mcp-server/2.2.1) identifies source commit `d802a0cd7d77c77b0a659be3fd98a9a23975b6e9`. The archive matched npm's SHA-512 integrity digest. It contains a licence and a bundled CLI. It contains no source map, build manifest listing the CLI's inputs, or separate third-party notice file. Notion's [build script](https://github.com/makenotion/notion-mcp-server/blob/d802a0cd7d77c77b0a659be3fd98a9a23975b6e9/scripts/build-cli.js) bundles and minifies the original TypeScript.

For the OpenSwarm comparison, an existing esbuild compiler read the npm CLI on standard input. Its binary matched the integrity-verified compiler archive. With the arguments in `exactRegeneration` in the source manifest, it emitted 1,616,445 bytes with SHA-256 `0fa6b8233b46be332a5dbde2e15c41fb9a1215a162463c239851b4e0c42ef40c`. The check compiled JavaScript as data and did not run the server.

The release lockfile identifies dependency versions. It also includes files the upstream bundler may have omitted. The notice collection therefore includes every non-development entry. The exact set of individual modules retained by Notion's minifier remains unverified. Packages may carry additional attributions within source code or data files beyond their licence documents.
