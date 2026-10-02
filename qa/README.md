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
