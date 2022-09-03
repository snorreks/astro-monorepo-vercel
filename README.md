# Astro Monorepo Vercel Test

This shows the bug that is found when using vercel and astro in a monorepo.

https://astro-monorepo-vercel.vercel.app/

```console
2022-08-31T09:39:48.226Z	undefined	ERROR	Error [ERR_MODULE_NOT_FOUND]: Cannot find package '@astrojs/vercel' imported from /var/task/entry.js
    at new NodeError (node:internal/errors:372:5)
    at packageResolve (node:internal/modules/esm/resolve:954:9)
    at moduleResolve (node:internal/modules/esm/resolve:1003:20)
    at defaultResolve (node:internal/modules/esm/resolve:1218:11)
    at ESMLoader.resolve (node:internal/modules/esm/loader:580:30)
    at ESMLoader.getModuleJob (node:internal/modules/esm/loader:294:18)
    at ModuleWrap.<anonymous> (node:internal/modules/esm/module_job:80:40)
    at link (node:internal/modules/esm/module_job:78:36) {
  code: 'ERR_MODULE_NOT_FOUND'
}
RequestId: 1dc723e6-1657-4c14-88ab-7c0a879065ae Error: Runtime exited with error: exit status 1
Runtime.ExitError
```

<details>
  <summary>Vercel Build log</summary>
  
```console
[14:22:14.130] Cloning github.com/snorreks/astro-monorepo-vercel (Branch: master, Commit: 72c4e23)
[14:22:14.322] Cloning completed: 191.394ms
[14:22:15.250] Looking up build cache...
[14:22:15.549] Build Cache not found
[14:22:15.576] Running "vercel build"
[14:22:16.116] Vercel CLI 28.2.2
[14:22:16.350] Running "install" command: `cd ../.. && npm i`...
[14:22:23.683] npm WARN deprecated node-pre-gyp@0.13.0: Please upgrade to @mapbox/node-pre-gyp: the non-scoped node-pre-gyp package is deprecated and only the @mapbox scoped package will recieve updates in the future
[14:22:26.087] 
[14:22:26.087] added 525 packages, and audited 526 packages in 10s
[14:22:26.087] 
[14:22:26.087] 182 packages are looking for funding
[14:22:26.087]   run `npm fund` for details
[14:22:26.112] 
[14:22:26.112] found 0 vulnerabilities
[14:22:26.406] 
[14:22:26.406] > build
[14:22:26.406] > npm --prefix apps/astro-app run build
[14:22:26.407] 
[14:22:26.706] 
[14:22:26.706] > build
[14:22:26.706] > astro build
[14:22:26.706] 
[14:22:28.215] 12:22:28 PM [build] output target: server
[14:22:28.216] 12:22:28 PM [build] deploy adapter: @astrojs/vercel/serverless
[14:22:28.216] 12:22:28 PM [build] Collecting build info...
[14:22:28.216] 12:22:28 PM [build] Completed in 10ms.
[14:22:28.217] 12:22:28 PM [build] Building server entrypoints...
[14:22:30.375] 12:22:30 PM [build] Completed in 2.16s.
[14:22:30.383] 
[14:22:30.383]  finalizing server assets 
[14:22:30.383] 
[14:22:30.383] 12:22:30 PM [build] Rearranging server assets...
[14:22:30.495] 12:22:30 PM [build] Server built in 2.29s
[14:22:30.495] 12:22:30 PM [build] Complete!
[14:22:30.524] Build Completed in /vercel/output [14s]
[14:22:33.792] Generated build outputs:
[14:22:33.793]  - Static files: 0
[14:22:33.794]  - Serverless Functions: 1
[14:22:33.794]  - Edge Functions: 0
[14:22:33.794] Serverless regions: Washington, D.C., USA
[14:22:33.794] Deployed outputs in 3s
[14:22:35.545] Build completed. Populating build cache...
[14:22:41.986] Uploading build cache [31.28 MB]...
[14:22:43.588] Build cache uploaded: 1.602s
[14:22:43.616] Done with "."
```  
</details>


## Reproduce

To test that it works locally:

```console
npm run dev
```

### On vercel

![image](https://user-images.githubusercontent.com/36089469/187648750-6e0c9783-36e1-4d3a-a848-703959c4f0af.png)
