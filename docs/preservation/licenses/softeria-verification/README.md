# Microsoft 365 server dependency evidence

The archived [server manifest](../../../../backend/mcp-bundles/softeria-ms-365-mcp-server/package.json) identifies `@softeria/ms-365-mcp-server` 0.95.0. Its [endpoint definitions](../../../../backend/mcp-bundles/softeria-ms-365-mcp-server/dist/endpoints.json) match the integrity-verified npm archive byte for byte. All 22 source paths labelled as Softeria's own files in the shipped JavaScript occur in that archive. [Release metadata](https://registry.npmjs.org/@softeria%2fms-365-mcp-server/0.95.0)

OpenSwarm installed the server by name in a temporary directory, bundled its entry point and kept `keytar` external. Softeria's [release lockfile](https://github.com/softeria/ms-365-mcp-server/blob/4821aa9df086fa85e31f19d77c33f570c3e3f05c/package-lock.json) records the dependency tree for Softeria's checkout. Five observed differences prevent its use as a recipe for reproducing OpenSwarm's JavaScript. [OpenSwarm build script](../../../../scripts/build-app.sh#L207)

| Dependency at the archived path | Softeria lock | Evidence from OpenSwarm |
| --- | --- | --- |
| `@azure/msal-common` at the top level | 16.4.0 | The [package metadata](../../../../backend/mcp-bundles/softeria-ms-365-mcp-server/dist/index.js#L20142) says 16.5.2. |
| `@azure/msal-node` under `@azure/identity` | 5.1.1 | The [package metadata](../../../../backend/mcp-bundles/softeria-ms-365-mcp-server/dist/index.js#L26817) says 5.1.5. A separate top-level copy reports 3.8.10. |
| `@typespec/ts-http-runtime` | 0.3.4 | The [SDK constant](../../../../backend/mcp-bundles/softeria-ms-365-mcp-server/dist/index.js#L31349) says 0.3.5. That release contains the same literal and all labelled files. |
| `@azure/keyvault-secrets` | 4.10.0 | The [SDK constant](../../../../backend/mcp-bundles/softeria-ms-365-mcp-server/dist/index.js#L40202) says 4.11.1. That release supplies eight labelled source paths missing from 4.10.0. |
| `readable-stream` at the top level | 2.3.8 | OpenSwarm labels [15 source files](../../../../backend/mcp-bundles/softeria-ms-365-mcp-server/dist/index.js#L5947). Release 2.3.8 lacks seven and 4.7.0 lacks four. Release 3.6.2 supplies all 15. Softeria's lock also places 3.6.2 underneath Winston and Winston Transport. The path comparison alone cannot pin the patch version. |

Each of the five matching candidates supplies a licence with the same SHA-256 digest as its release-lock candidate. The [five licence texts](candidate-notices.txt) and the [source comparison](source-comparison.json) preserve the archive URLs, integrity digests, file hashes and byte offsets. The SDK constant in [Azure Core REST Pipeline](../../../../backend/mcp-bundles/softeria-ms-365-mcp-server/dist/index.js#L34228) illustrates the limit of version strings. The archived value is `1.22.3`, and Softeria's locked npm release `1.23.0` contains that exact value.

## Coverage

On 2026-11-17 the comparison grouped 990 distinct JavaScript source labels into 151 installation paths, including Softeria itself. For each dependency it verified the npm archive against the source lock's integrity digest and checked whether the archive contained the labelled members. Eight missing paths in Key Vault Secrets and seven in Readable Stream were the only absent members. Matching filenames alone do not establish the contents of those files. The comparison also checked version literals in selected labelled modules.

These checks establish the packaged resource and the listed dependency differences. A byte-for-byte reproduction of the complete JavaScript remains unverified. Source labels can also omit attributions for components embedded inside a dependency. The [general notices](../../third-party-notices.md) cover the wider archive.
