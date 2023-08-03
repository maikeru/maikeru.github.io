---
title: Ambiguous import in Vite with pnpm linked package
---

This probably won't make much sense to anyone but it's some notes while working on my glk (Interactive fiction UI) in Typescript using a Vite project to put a React frontend on things. After moving to a linux computer and realising that some of my most recent changes were missing it took a bit of fiddling to get things to build. These are the notes I took while fixing things. At some point I might come back and edit this into something coherent but no promises.

Error when running `pnpm build` (amounts to `tsc && vite build`)

```
"WinMethod_Above" is not exported by "../glkjs/lib/index.js", imported by "src/glkvms/model.ts".
```

Added this to the vite.config.js

```js
export default defineConfig({
  resolve: {
    preserveSymlinks: true, // <-- added this
  },
  plugins: [react()],
  server: {
    fs: {
      strict: false,
      // allow: ["../glkjs"],
    },
  },
})
```

Next problem, when running `pnpm dev`:

```
✘ [ERROR] Could not resolve "scheduler"

    node_modules/react-dom/cjs/react-dom.development.js:27:24:
      27 │ var Scheduler = require('scheduler');
         ╵                         ~~~~~~~~~~~

  You can mark the path "scheduler" as external to exclude it from the bundle, which will remove
  this error. You can also surround this "require" call with a try/catch block to handle this
  failure at run-time instead of bundle-time.
```

Installed scheduler with pnpm add `scheduler` -D
Weird that this would be necessary as it seems to be a react-dom dependency which is being pulled in by Vite (so not something my project depends on itself). Maybe it's a peer dependency?

Ended up switching more things to ES Module related settings in both glkjs (package) and sandbox (vite app):

tsconfig.json :

```json
...
  "compilerOptions": {

...
    "module": "ESNext",
    "moduleResolution": "NodeNext",
...
  }
...
```

Added Jest config to package to handle these changes as well in `jest.config.json`

```json
...
  "extendsionsToTreatAsEsm": [".ts"],
  "moduleNameMapper": {
    "^(\\.{1,2}/.*)\\.js$": "$1"
  },
  "transform": {
    "^.+\\.(t|j)sx?$": ["ts-jest", { "useESM": true }]
  },
...
```
