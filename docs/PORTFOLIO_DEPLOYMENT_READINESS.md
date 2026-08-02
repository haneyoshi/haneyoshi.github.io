# Portfolio Deployment Readiness Audit

## 1. Purpose

This document records a focused, repository-based audit of the portfolio's readiness for an Astro deployment to GitHub Pages. It separates verified repository facts from risks, checks that require access to GitHub or the production site, and recommended future work. No deployment configuration or application files were changed as part of this audit.

Audit date: 2026-08-01. Audited branch: `docs/deployment-readiness-audit`.

## 2. Current repository state

### Verified repository facts

- The repository is the GitHub Pages user-site repository `haneyoshi.github.io`.
- The Astro application is present under `src/`; its only generated route is `/index.html`.
- `package.json` pins Astro `7.1.6`, `@astrojs/check` `0.9.10`, and TypeScript `6.0.3`. `package-lock.json` is present at lockfile version 2 and records the same direct versions.
- The declared runtime requirements are Node.js `>=22.12.0` and npm `>=9.6.5`. The workflow selects Node.js `22.12.0`.
- `dist/`, `.astro/`, and `node_modules/` are ignored. Generated output is therefore not intended to be committed.
- There is no `public/` directory in the current repository.
- The legacy production-site files remain tracked at the repository root, including `index.html`, `mediCheckIntro.html`, `css/`, `images/`, `videos/`, and `YuShan Hung.pdf`.
- The worktree was clean before the audit. `npm.cmd ci` did not change tracked files.

### Concern

The README and workflow describe an Astro deployment that is already implemented, while the rebuild plan still describes deployment migration as pending. This is a documentation/status mismatch, not evidence that production is configured or successfully serving the Astro output.

## 3. Current GitHub Pages deployment path

### Verified repository facts

The sole workflow, `.github/workflows/static.yml`, is named `Deploy Astro site to Pages` and has two triggers:

- a push to `main`;
- a manual `workflow_dispatch` invocation.

It does not run on pull requests. Its build job checks out the repository, selects Node.js `22.12.0`, restores npm caching based on `package-lock.json`, runs `npm ci`, runs `npm run check`, and runs `npm run build`. It then configures Pages and uploads `dist/` through `actions/upload-pages-artifact`. The dependent deploy job publishes that artifact with `actions/deploy-pages` to the `github-pages` environment.

Therefore, the content represented by the workflow is the generated contents of `dist/`, not the repository root and not the legacy root `index.html`. `dist/` is currently the configured deployment artifact even though it is ignored by Git.

### GitHub verification still required

Repository files cannot establish whether GitHub Pages is enabled, whether its source is set to **GitHub Actions**, whether the `github-pages` environment has approval or branch rules, whether a custom domain is configured outside the repository, or whether recent workflow runs have succeeded. These settings and the deployed URL must be checked manually on GitHub.

## 4. Astro configuration

### Verified repository facts

`astro.config.mjs` sets:

```js
site: 'https://haneyoshi.github.io/'
```

It does not set `base`, so Astro uses the root base path `/`. For the user-site repository named exactly `haneyoshi.github.io`, the configured `site` origin and the default root base are appropriate. A repository-project site would require a repository-name base, but that is not this repository's documented hosting model.

The build reports static output and writes to the default `dist/` directory. No server adapter is configured or required for the generated one-page static site.

### Future-change boundary

Do not add a repository-name `base` while the site remains the root user site. Revisit `site` and `base` only if the production hostname, custom-domain strategy, or repository hosting model changes.

## 5. Build commands and generated output

### Verified results

The required commands completed as follows:

- `npm.cmd ci`: passed after local preview processes holding a native build module were stopped; 279 packages were installed, 280 packages were audited, and npm reported 0 vulnerabilities. No tracked file changed.
- `npm.cmd run check`: passed for 7 files with 0 errors, 0 warnings, and 0 hints.
- `npm.cmd run build`: passed; Astro reported static output, one generated page, and output in `dist/`.

The clean production build generated exactly:

```text
dist/
|-- index.html                                      12,576 bytes
`-- _astro/
    |-- index.CUS4sBvM.css                          14,495 bytes
    `-- Medi_main_window.v-hD0Ayo_hsSe9.png         23,266 bytes
```

The filename hashes are build artifacts and may change in later builds. The generated HTML points to the stylesheet and image with root-relative URLs under `/_astro/`, which matches root user-site hosting.

## 6. Legacy production-site preservation

### Verified repository facts

The root legacy site and its linked local assets remain tracked, but the current Pages workflow does not upload them. The generated `dist/` tree contains neither the legacy HTML pages nor their CSS, images, video, JavaScript, favicon, or résumé PDF.

### Required preservation

Until an Astro workflow run is confirmed successful and the production URL is verified, retain at minimum all currently tracked legacy site material:

- root `index.html` and `mediCheckIntro.html`;
- `css/`, `images/`, and `videos/`;
- `YuShan Hung.pdf`;
- any other tracked file proven to support the legacy site during production verification.

Keeping these files preserves a recoverable repository version of the former production site. Their presence does not provide an automatic runtime fallback once Pages is configured to deploy the `dist/` artifact. Removal should be a later, separately reviewed cleanup after production verification.

## 7. GitHub Pages constraints

### Verified implications

- GitHub Pages serves the uploaded static artifact; it does not run Astro at request time.
- Only files in `dist/` are available after this workflow deploys. Root files that are not copied into `dist/` cannot be reached at their old production URLs.
- Root-relative `/_astro/...` URLs are correct for `https://haneyoshi.github.io/`, but would break if the same artifact were served beneath a repository subpath without matching Astro configuration.
- The workflow needs the declared `contents: read`, `pages: write`, and `id-token: write` permissions. Those permissions are present.
- The workflow uses a concurrency group named `pages` and does not cancel an in-progress deployment.

### GitHub verification still required

Manually confirm the Pages source, Actions permissions, environment protection behavior, successful run history, production URL, HTTPS behavior, and any configured custom domain. No repository `CNAME` file exists, and repository inspection cannot rule out a custom domain configured only in GitHub settings.

## 8. Path and asset review

### Verified repository facts

- All internal navigation links in the generated page are same-document fragments: `#top`, `#main-content`, `#about`, `#projects`, `#experience`, `#skills`, and `#contact`. Corresponding IDs are present in the generated HTML.
- Generated local assets use `/_astro/...` root-relative paths. The generated files exist in `dist/_astro/`.
- External project links point to `https://github.com/haneyoshi/MediCheck` and `https://github.com/haneyoshi/WebAppMVP`.
- The contact links are a `mailto:` link for `pokemonbotno001@gmail.com` and a LinkedIn profile URL.
- There is no résumé link or résumé placeholder in the generated Astro page. The legacy root `YuShan Hung.pdf` is not emitted into `dist/`.
- The page says `Interface preview in development.` for EchoTask. This is an intentional public status statement, not a broken local asset reference.
- The Astro layout defines no favicon link, and no favicon is present in `dist/`. The tracked legacy `images/favicon.ico` is not published by the Astro artifact.
- The generated document includes a title, description, viewport, language, and Astro generator metadata, but no canonical link, social metadata, or 404 page was generated.

### Risks and production checks

- Missing favicon support is a launch-quality gap, although it does not block basic deployment.
- The absence of a public résumé is intentional according to the rebuild plan, but users cannot access the tracked legacy PDF through the Astro deployment. Production copy and calls to action should be reviewed to ensure none implies that a résumé download exists.
- The two GitHub project URLs, LinkedIn URL, and email action require live/manual verification. Repository inspection establishes their values, not their availability, visibility, or destination correctness.
- Because only `index.html` is generated, old URLs such as `/mediCheckIntro.html`, `/css/...`, `/images/...`, `/videos/...`, and `/YuShan%20Hung.pdf` will not exist in the new artifact. Any inbound links or search results targeting them may return 404 after migration.

## 9. Deployment risks and blockers

### Blockers before an intentional production launch

1. GitHub Pages must be manually confirmed to use GitHub Actions as its source and to allow the workflow's Pages deployment.
2. A successful `main` workflow run and the resulting production deployment have not been verified by this repository-only audit.
3. The production site must be checked before legacy files are removed, because the artifact has no automatic legacy fallback.

### Non-blocking risks and concerns

- Old legacy URLs are omitted from `dist/`; redirects or an explicit decision to accept those 404s have not been documented in repository configuration.
- No favicon is emitted.
- External links and contact actions have not been verified against the live services.
- There is no generated custom 404 page, canonical URL, or social-sharing metadata. These are launch-quality considerations rather than proof that deployment will fail.
- The workflow's current Action major versions and Node version are internally consistent with the repository at audit time, but future dependency or Action updates should be handled in separate reviewed maintenance.

### Workflow disposition

The existing workflow should be **retained for the minimum deployment step**, not replaced. It already performs the required Astro checks, builds `dist/`, uploads only `dist/`, uses Pages permissions, and deploys through the official Pages artifact flow. No repository evidence identifies a structural Astro deployment defect requiring replacement or revision before the first verification run. Any later hardening or version maintenance should be a separate change based on a specific requirement or failed-run evidence.

## 10. Minimum pre-launch QA checklist

- [ ] Confirm the intended commit is reviewed and is the commit that will reach `main`.
- [ ] Run `npm ci`, `npm run check`, and `npm run build` from a clean checkout.
- [ ] Confirm `dist/` contains `index.html` and every generated `/_astro/` asset referenced by it.
- [ ] Preview the production build and check mobile, tablet, and desktop layouts at representative widths.
- [ ] Test keyboard-only navigation, visible focus, the skip link, every navigation anchor, and 200% zoom without horizontal content loss.
- [ ] Check the generated page for missing assets and browser-console errors.
- [ ] Open both GitHub project links, LinkedIn, and the email action; confirm the destinations and public visibility are intentional.
- [ ] Confirm no résumé control is displayed and no current copy promises a résumé download.
- [ ] Decide whether missing favicon, canonical/social metadata, and a custom 404 page are acceptable for the staged launch or must be handled in a separate pre-launch task.
- [ ] Inventory important legacy production URLs and decide whether redirects/preservation are needed.
- [ ] In GitHub, confirm Pages uses GitHub Actions, review environment rules, and confirm Actions permissions permit Pages deployment.
- [ ] After merging to `main`, observe the workflow through both jobs and verify the deployed production URL over HTTPS.
- [ ] On production, hard-refresh the root page and recheck layout, local assets, anchors, external links, contact actions, and browser-console/network failures.
- [ ] Keep all legacy files until the production verification is recorded and rollback needs are resolved.

## 11. Recommended deployment-migration scope

The smallest safe migration task is a reviewed operational verification of the workflow that already exists:

1. Confirm GitHub Pages is set to **GitHub Actions** and that repository/environment permissions permit the workflow.
2. Re-run the clean install, check, build, and compact `dist/` inspection on the exact candidate commit.
3. Merge the approved candidate to `main` without combining unrelated deployment changes.
4. Monitor the existing build and deploy jobs, then verify the production root URL and the minimum QA checklist.
5. Record the deployed commit and results; retain the legacy files.

No workflow replacement is necessary within that minimum scope. If GitHub settings or an actual workflow run exposes a failure, make the smallest evidence-driven workflow revision in a new, dedicated task rather than speculatively redesigning the deployment.

## 12. Explicitly deferred work

The following work is not implemented or authorized by this audit:

- changing the workflow, Astro configuration, package metadata, dependencies, application source, or `public/` assets;
- changing GitHub Pages settings, deploying, committing, or pushing;
- adding a favicon, résumé, canonical URL, social metadata, analytics, custom domain, or custom 404 page;
- adding redirects or preserving legacy URLs inside the Astro artifact;
- removing, moving, or editing the legacy root site and its assets;
- Phase 5 visual features, interactions, animation, screenshots, or other polish;
- broad Phase 6 accessibility, performance, SEO, cross-browser, copy, or link remediation beyond the minimum launch checks;
- updating `docs/PORTFOLIO_REBUILD_PLAN.md` or reconciling its deployment status language.

## 13. Audit conclusion

The repository is technically prepared to build and deploy the Astro site through GitHub Pages: the configuration is appropriate for the root user site, the required clean install/check/build sequence passes, the workflow uploads `dist/`, and the artifact's generated local paths resolve within its compact structure. The existing workflow should be retained for the first controlled deployment verification.

Readiness is conditional rather than fully proven. Repository evidence cannot confirm GitHub Pages settings, workflow success on `main`, or production behavior. The material pre-launch blockers are therefore operational verification of GitHub settings and a successful production run, followed by focused production QA. Legacy files must remain tracked until that verification is complete. Missing favicon/metadata, omitted legacy URLs, and unverified external destinations are explicit launch risks to accept or address in separate, scoped work.
