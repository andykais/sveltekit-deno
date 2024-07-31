## Repro

### With top level .npmrc
```bash
git clone git@github.com:andykais/sveltekit-deno.git
cd packages/web
deno run -A --allow-ffi npm:vite dev
```
```
error when starting dev server:
Error: Could not resolve peer dependency "@sveltejs/vite-plugin-svelte" relative to your project — please install it and try again.
    at resolve_peer_dependency (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/@sveltejs/kit/2.5.18/src/utils/import.js:15:9)
    at sveltekit (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/@sveltejs/kit/2.5.18/src/exports/vite/index.js:155:27)
    at async Promise.all (index 0)
    at async asyncFlatten (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/chunks/dep-mCdpKltl.js:17470:12)
    at async resolveConfig (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/chunks/dep-mCdpKltl.js:65842:27)
    at async _createServer (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/chunks/dep-mCdpKltl.js:62432:18)
    at async CAC.<anonymous> (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/cli.js:735:20)
```

### Without top level .npmrc
```bash
git clone git@github.com:andykais/sveltekit-deno.git
rm .npmrc
cd packages/web
deno run -A --allow-ffi npm:vite dev
```
```
failed to load config from /Users/andrew.kaiser/Code/andykais/sveltekit-deno/packages/web/vite.config.ts
error when starting dev server:
TypeError: npm package '@jsr/andykais__ts-rpc' does not exist.
    at file:///Users/andrew.kaiser/Code/andykais/sveltekit-deno/packages/web/vite.config.ts.timestamp-1722450597016-051c9ceef60ec.mjs:2:27
    at async loadConfigFromBundledFile (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/chunks/dep-mCdpKltl.js:66365:15)
    at async loadConfigFromFile (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/chunks/dep-mCdpKltl.js:66206:24)
    at async resolveConfig (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/chunks/dep-mCdpKltl.js:65816:24)
    at async _createServer (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/chunks/dep-mCdpKltl.js:62432:18)
    at async CAC.<anonymous> (file:///Users/andrew.kaiser/Library/Caches/deno/npm/registry.npmjs.org/vite/5.3.5/dist/node/cli.js:735:20)
```
