# webpack-boilerplate

[![CI](https://github.com/erseco/webpack-boilerplate/actions/workflows/ci.yml/badge.svg)](https://github.com/erseco/webpack-boilerplate/actions/workflows/ci.yml)

Minimal, modern Webpack 5 starter with Babel and Sass (Dart Sass).

This template gives you a simple starting point for small web apps and component demos with zero framework assumptions.

## Features

- Webpack 5 with fast dev server and HMR
- Babel (`@babel/preset-env`) for modern JavaScript
- Sass (Dart Sass) via `sass` + `sass-loader`
- Asset modules for images (no `file-loader` needed)
- HTML generation with `html-webpack-plugin`
- GitHub Actions CI for Node 18/20

## Requirements

- Node.js >= 18 (recommend LTS 20)
- npm >= 8 (comes with Node)

Use a version manager like `nvm`/`fnm` if you work across projects.

## Getting Started

1. Install dependencies

   - `npm install`

2. Start the dev server

   - `npm start`
   - Open the printed URL (usually `http://localhost:8080`).

3. Build for production

   - `npm run build`
   - Output goes to `dist/`.

## Scripts

- `npm start`: Run dev server in development mode.
- `npm run dev`: Create a development build to `dist/` without serving.
- `npm run build`: Create an optimized production build.

## Project Structure

```
.
├─ src/
│  ├─ index.html        # HTML template for HtmlWebpackPlugin
│  ├─ index.js          # Entry point (imports styles.scss)
│  └─ styles.scss       # Global styles (Sass)
├─ webpack.config.js    # Webpack configuration
├─ .babelrc             # Babel preset configuration
└─ package.json         # Scripts, dependencies
```

Add your images to `src/` and import or reference them:

```js
import logoUrl from './logo.png';
const img = new Image();
img.src = logoUrl; // handled by asset/resource
document.body.appendChild(img);
```

You can also reference images from CSS as usual — Webpack will resolve them via `css-loader` + asset modules.

## Configuration Notes

- Sass uses Dart Sass (`sass` package). No native binaries are required.
- Images use Webpack 5 asset modules (`type: 'asset/resource'`).
- HTML minification is handled automatically in production mode by the plugin/tooling.

If you need additional loaders (e.g., fonts, SVG as components), add rules to `webpack.config.js`.

## Continuous Integration

GitHub Actions (`.github/workflows/ci.yml`) runs installs and builds on Node 18 and 20. If you want reproducible installs with `npm ci`, regenerate and commit `package-lock.json` locally with Node 18/20 and switch CI back to `npm ci`.

## Troubleshooting

- Port already in use: set a different port via `WEBPACK_DEV_SERVER_PORT` or `--port` flag: `webpack-dev-server --port 3000`.
- Node version errors: ensure `node -v` is >= 18. Use `nvm use` if needed.
- Stale dependencies: run `rm -rf node_modules && npm install`.

## Contributing

See CONTRIBUTING.md for guidelines. Issues and PRs are welcome.

## License

ISC. See LICENSE for details.
