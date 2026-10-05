# Versioning and releases

By ICODEDIGITA. This is how the toolkit is versioned so you can depend on it with confidence.

## One version for everything
All packages (`@icodedigita/jazzcash`, `-next`, `-express`, `-react`, `-react-native`, `-setup`, `@icodedigita/n8n-nodes-jazzcash`) move together (Changesets "fixed" group). If you use several, use the same version for all of them.

## Semantic Versioning
| Bump | When |
|---|---|
| **patch** `0.1.0 → 0.1.1` | Bug fixes, hint/message wording, simulator accuracy, docs. Safe to take automatically. |
| **minor** `0.1.x → 0.2.0` | New features or payment methods, new routes/options. Before 1.0 a minor may also change an API: read the changelog. |
| **major** `1.x → 2.0` | Breaking changes to the public API, route names, or env variable names. |

While the major version is `0`, treat **minor** bumps as potentially breaking. Pin accordingly:
- Cautious: `"@icodedigita/jazzcash-next": "~0.1.0"` (patches only).
- Normal after 1.0: `"^1.0.0"`.

## Gateway changes
JazzCash can change its API. The build records which spec it follows:
```ts
import { SPEC, VERSION } from '@icodedigita/jazzcash';
console.log(VERSION, SPEC); // { version: 'v1', sha256: '…', fetchedAt: '2026-10-05', paths: 37 }
```
A change that only adds endpoints is a **minor**. A change to a field we send or verify is described in the changelog and shipped as a **patch** if backwards compatible, otherwise a **major**. The spec is refreshed and reviewed before every release.

## Release channels (npm dist-tags)
- `latest`: the stable version most people should use.
- `beta`: pre-release candidates (`npm i @icodedigita/jazzcash@beta`).

Check your version with `npx @icodedigita/jazzcash-setup --version` or the badge in the wizard.

## Deprecation
Anything removed is first marked deprecated for at least one minor release and listed in `CHANGELOG.md`. A broken release is fixed with a new patch and the bad version is `npm deprecate`d with a pointer to the fix. Versions are never unpublished.
