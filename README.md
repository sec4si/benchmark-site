# Benchmark website — sec4si

Project website: **https://benchmark.sec4.si/**

This public repository, **sec4si/benchmark-site**, hosts the static Benchmark project website styled to match [sec4.si](https://sec4.si/).

The `sec4si/benchmark` repository name is reserved for transferring the existing benchmark project with its original history. Website source stays here so the public landing page can be maintained independently of the private question bank, answers, and evaluation code.

## Local development

```sh
npm ci
npm run dev
```

Open http://127.0.0.1:4175/. The starter has no third-party JavaScript dependencies. The fonts are self-hosted with their license notices in `public/licenses/`.

Edit `public/` for the placeholder. Run `npm run build` to produce `dist/`.

## GitHub Pages

- Source: **GitHub Actions**, not branch publishing.
- Workflow: [Deploy GitHub Pages](https://github.com/sec4si/benchmark-site/actions/workflows/pages.yml).
- Pages settings: https://github.com/sec4si/benchmark-site/settings/pages
- Pushes to `main` and manual workflow dispatches run `npm ci`, `npm run build`, and publish only `dist/`.
- The repository Pages custom domain is `benchmark.sec4.si`.
- Cloudflare: DNS-only CNAME `benchmark` → `sec4si.github.io`.

## Keeping the website separate

Keep the build contract: **`npm ci` + `npm run build` → `dist/`**. Keep the custom domain configured in Pages, and carry `public/CNAME` and `public/.nojekyll` into the static output. Only reviewed public website content belongs in this repository; private benchmark packages and their history are migrated separately.

The repository was renamed from `sec4si/benchmark` without recreating it, preserving its original commits and Pages settings. The website remains at **https://benchmark.sec4.si/**. GitHub links in the website point directly to `sec4si/benchmark-site`, so they do not depend on the old repository-name redirect once the benchmark project takes that name.

The main website, [Benchmark](https://benchmark.sec4.si/), and [Lens](https://lens.sec4.si/) are connected in the project navigation. No private research data or proprietary Pro component source is included in this starter.
