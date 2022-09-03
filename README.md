# Astro Monorepo Vercel Test

This shows the bug that is found when using vercel and astro in a monorepo.

https://astro-nx-vercel-test.vercel.app/

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


## Reproduce

To test that it works locally:

```console
npm run dev
```

### On vercel

![image](https://user-images.githubusercontent.com/36089469/187648750-6e0c9783-36e1-4d3a-a848-703959c4f0af.png)
