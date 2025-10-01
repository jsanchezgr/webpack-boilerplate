# Changelog

All notable changes to this project will be documented in this file.

## Unreleased

- Add CONTRIBUTING.md and expanded README with setup, usage, and CI details.

## 2.0.0 – Modernize toolchain

- Upgrade to Webpack 5 (`webpack`, `webpack-cli`, `webpack-dev-server`).
- Replace `node-sass` with Dart Sass (`sass`) and update `sass-loader`.
- Use asset modules (`type: 'asset/resource'`) instead of `file-loader`.
- Upgrade `html-webpack-plugin` and `html-loader` to Webpack 5 compatible versions.
- Require Node >= 18; update CI to test on Node 18 and 20.

## 1.x – Initial boilerplate

- Webpack 4 setup with Babel, SCSS support, and basic dev server.

