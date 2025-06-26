# Reproduction Steps

1. Run dev server
``bun run dev``
2. Make a change (ex. /src/routes/+page.svelte)
```
<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<h2>jj is really cool</h2>
```
3. Save the change and view debug console to encounter the following error
```
22190 |         sysPath$2.resolve(path, evPath), KEY_LISTENERS, sysPath$2.join(path, evPath)
22191 |       );
22192 |     }
22193 |   };
22194 |   try {
22195 |     return fs$4.watch(path, options, handleEvent);
                        ^
EINVAL: invalid argument, watch '/kit-jj-incompat-repro/.jj/working_copy/working_copy.lock'
     path: "/kit-jj-incompat-repro/.jj/working_copy/working_copy.lock",
  syscall: "watch",
    errno: -22,
 filename: "/kit-jj-incompat-repro/.jj/working_copy/working_copy.lock",
     code: "EINVAL"

      at new FSWatcher (node:fs:30:31)
      at watch (node:fs:295:10)
      at createFsWatchInstance (/kit-jj-incompat-repro/node_modules/vite/dist/node/chunks/dep-DBxKXgDP.js:22195:17)
      at setFsWatchListener (/kit-jj-incompat-repro/node_modules/vite/dist/node/chunks/dep-DBxKXgDP.js:22242:15)
      at _watchWithNodeFs (/kit-jj-incompat-repro/node_modules/vite/dist/node/chunks/dep-DBxKXgDP.js:22397:14)
      at _handleFile (/kit-jj-incompat-repro/node_modules/vite/dist/node/chunks/dep-DBxKXgDP.js:22461:23)
      at _addToNodeFs (/kit-jj-incompat-repro/node_modules/vite/dist/node/chunks/dep-DBxKXgDP.js:22703:21)

Bun v1.2.11 (Linux x64 baseline)
error: script "dev" exited with code 1
```