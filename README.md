# 👷 Modules Wrangler template

#### Project Use

Generate with:
```
wrangler generate e9 git@github.com:cloudflare/modules-webpack-commonjs.git --type webpack
```

Run locally with:
```
npx miniflare --live-reload
```

Publish to Cloudflare with:
```
wrangler login
wrangler publish
```



## NOTE: You must be using wrangler 1.16 or newer to use this template

A template for kick starting a Cloudflare Workers project using:

- Modules (CommonJS modules to be specific)
- Webpack
- Wrangler

Worker code is in `src/index.js`

Webpack is configured to output a bundled CommonJS module to `dist/index.js`

This project uses a shim ES module at `src/shim.mjs` that imports the commonjs bundle, and re-exports it. This is necessary because commonjs does not support named exports, and the only way to export a durable object class is using named exports.

- This shim is also configured to be the main module, using the `module` key in `package.json`.
