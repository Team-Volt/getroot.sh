# Website verification

Verified on 2026-10-02 against the actual HTML/CSS served by Python at http://127.0.0.1:8080, using Playwright with installed Google Chrome. Screenshots are full-page captures, inspected at desktop and both phone widths.

| View | Width × viewport height | Overflow | WCAG Axe violations | Fragment links | Keyboard skip link |
| --- | --- | --- | --- | --- | --- |
| Desktop | 1440 × 1100 | None | 0 | Pass | Pass |
| Tablet | 768 × 1024 | None | 0 | Pass | Pass |
| Mobile | 390 × 844 | None | 0 | Pass | Pass |
| Small mobile | 320 × 700 | None | 0 | Pass | Pass |

`browser-checks.json` records the measured widths, HTTP status, real link targets, activated capability anchor, keyboard focus outline, console errors, and reduced-motion scroll behavior. All pages loaded with HTTP 200; no page errors; reduced motion produced `scroll-behavior: auto`.

Lighthouse ran through Playwright Chrome with `playwright-lighthouse`, three times each on desktop and mobile. All six runs scored **100 performance, 100 accessibility, 100 best practices, 100 SEO**. `lighthouse-summary.json` records all scores and advisory findings; the full JSON reports preserve configuration and diagnostics. These are **local, unthrottled measurements**, not production speed claims. Python's server lacks production caching/compression, and Lighthouse recorded corresponding advisory findings. Re-measure network performance on the deployed host, including its TLS, cache headers, and actual mobile throttling.

Design review: the hero remains readable at 320px, shell text wraps without internal horizontal scrolling, the capabilities collapse into ruled rows, and navigation remains visible. All content is present immediately with no typing simulation or animation required to read it. Legal entity identification appears in the terminal and footer on every width. No contact address, customer claims, external fake links, trackers, or runtime dependencies were added. Automatic accessibility checks do not replace human screen-reader testing.

Visitor walkthrough: desktop and phone visitors can read the company purpose, activate the capabilities link, read the three services, and return to the top. A keyboard visitor can use the visible skip link and focus outline. These tasks were exercised in the browser.

Initial hosting verification, before the owner approved public visibility: the repository was private, and its main branch contains the website. Pages creation returned HTTP 422 with `Your current plan does not support GitHub Pages for this repository.` The organization plan is `free`; no deployment was created, the custom domain is only prepared in `docs/CNAME`, and DNS was not changed. The owner subsequently approved public visibility to use GitHub Pages. Current deployment information is in the root README.

## Public deployment verification

After owner approval, the complete tracked tree and both existing commits were inspected before changing repository visibility. The history contained no credential patterns or local filesystem paths. QA screenshots contain only this site's rendered content; Lighthouse reports contain this site's localhost audit data. No private customer data or unrelated application captures were found.

GitHub Pages built and deployed commit `8ce769237464bd13cb2e1e8137a887fcbb67bf7e` successfully in [run 37006229192](https://github.com/Team-Volt/getroot.sh/actions/runs/37006229192). The source is `main /docs` and the registered custom domain is `getroot.sh`. A request using a temporary DNS override returned HTTP 200 and an exact SHA-256 match with the source HTML: `7e58961f896d7fe1483163efc216e238e708d898a174f38e383fb60b4cc0605e`.

`deployed-desktop.png`, `deployed-mobile.png`, and `deployed-checks.json` document the deployed page, rather than the local server. The browser temporarily mapped `getroot.sh` to a GitHub Pages IP and requested HTTP. This verifies served content and responsive layout, not public DNS or certificate readiness. Both widths returned HTTP 200 with the expected title and no horizontal overflow.

Public DNS at the check: apex A `127.0.0.1`; `www` CNAME `team-volt.github.io`. GitHub domain health reported the apex did not point to GitHub Pages IPs and was not HTTPS eligible. HTTPS enforcement was false and a direct verified TLS request failed with certificate name mismatch. DNS and HTTPS remain pending; no DNS was altered.
