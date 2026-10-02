# Root Shell LLC

Static splash website for **https://getroot.sh**. Source repository: https://github.com/Team-Volt/getroot.sh, private.

The website lives in `docs/`. It needs no build, package manager, JavaScript, external fonts, analytics, or third-party runtime. The company information is readable without animation. All navigation links point to real sections on the page.

## Hosting status

Team-Volt currently uses GitHub Free for organizations. GitHub Pages requires GitHub Team or Enterprise to publish from an organization's private repository. Source visibility must stay private. No plan purchase, visibility change, or DNS change is authorized as a workaround.

This repository is prepared for Pages using **main /docs**. `docs/CNAME` contains `getroot.sh`; this file alone does not register the domain or enable hosting. The site has not been deployed while private Pages is unavailable. The expected Pages URL, once enabled, is `https://team-volt.github.io/getroot.sh/`; after adding the custom domain it redirects to `https://getroot.sh/`.

Choices to unblock publication:

- The owner can upgrade Team-Volt to GitHub Team, then enable Pages as below.
- Keep the repository private and connect another static host that supports private repositories, such as Cloudflare Pages or Netlify. Deployment and DNS values will depend on the selected host and its authorized account. Nothing has been provisioned with another provider.

GitHub documents plan eligibility at https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages.

## Preview locally

```sh
python3 -m http.server 8080 --directory docs
```

Open http://localhost:8080. To edit the page, change `docs/index.html` and `docs/styles.css`. The design contract is in `DESIGN.md`.

## Enable GitHub Pages after the plan supports it

In repository **Settings → Pages**, choose **Deploy from a branch**, branch **main**, folder **/docs**. Save, then set **Custom domain** to **getroot.sh** and save it before changing DNS. Subsequent pushes to `main` automatically rebuild Pages.

Equivalent commands with the existing authenticated GitHub CLI:

```sh
gh api --method POST repos/Team-Volt/getroot.sh/pages \
  -f 'source[branch]=main' -f 'source[path]=/docs'
gh api --method PUT repos/Team-Volt/getroot.sh/pages -f cname=getroot.sh
gh api repos/Team-Volt/getroot.sh/pages
```

Verify the domain for the Team-Volt organization in **organization Settings → Pages** if possible. GitHub generates a unique TXT verification value there; no value should be guessed. Configure the custom domain in Pages before pointing DNS to GitHub.

## DNS records for GitHub Pages

**Do not apply these records until Pages is enabled and its custom domain is registered.** These are GitHub Pages values, not instructions for another host. The domain owner handles DNS.

| Type | Name | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | team-volt.github.io |

TTL: use 3600 seconds or the provider's automatic setting. The `www` CNAME does not contain a URL scheme or repository path. With `getroot.sh` as the custom domain, GitHub redirects `www.getroot.sh` to the apex.

Optional IPv6 records, in addition to the A records:

| Type | Name | Value |
| --- | --- | --- |
| AAAA | @ | 2606:50c0:8000::153 |
| AAAA | @ | 2606:50c0:8001::153 |
| AAAA | @ | 2606:50c0:8002::153 |
| AAAA | @ | 2606:50c0:8003::153 |

Replace conflicting web-hosting records for `@` and `www`. Preserve unrelated email records, TXT verification records, and other services. Do not use wildcard records. GitHub's current authoritative instructions: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site.

## HTTPS and verification

DNS propagation can take up to 24 hours. GitHub provisions the custom-domain certificate after DNS is correct; HTTPS availability and the **Enforce HTTPS** option may take additional time, up to 24 hours. Enable it once available. Until then the desired `https://getroot.sh` URL is not a verified live deployment.

```sh
dig getroot.sh A +short
dig www.getroot.sh CNAME +short
gh api repos/Team-Volt/getroot.sh/pages
gh api repos/Team-Volt/getroot.sh/pages/builds/latest
curl -I https://getroot.sh/
```

Check the live page on desktop and mobile after deployment. Local visual/accessibility checks and screenshots are under `qa/`; they do not establish successful production deployment.
