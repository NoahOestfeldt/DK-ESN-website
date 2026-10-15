# ESN Denmark — GitHub Pages recreation

This repository is a **best-effort static recreation**, not a 1:1 extraction of the original Plasmic project. The original repository ZIP provided was an unmodified Next.js starter. It did not include the live website source.

## Publish to GitHub Pages

1. Upload `index.html` and `.nojekyll` to the root of the existing GitHub repository. Remove or archive the Next.js starter files if replacing its content.
2. In **Settings → Pages**, choose **Deploy from a branch**, branch **main**, folder **/(root)**.
3. Test `https://USERNAME.github.io/REPOSITORY/` before changing DNS.
4. In **Settings → Pages → Custom domain**, set `esndenmark.org`. Optionally rename `CNAME.example` to `CNAME` and commit it. GitHub Pages usually manages that file when you set the custom domain in Settings.
5. In Cloudflare DNS, create apex `A` records to `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, and `185.199.111.153`, and a `www` CNAME to `USERNAME.github.io` (replace USERNAME). Set **DNS only** (grey cloud) for initial verification.
6. Wait until GitHub issues the TLS certificate; enable **Enforce HTTPS**. Preserve existing email DNS records (MX, TXT, DKIM).

## Site fidelity notes

- Publicly verified text: main headline and intro, six local sections, mission paragraph, postal address and CVR.
- Section destinations on the public original site: ESN Aarhus, ESN Kolding, ESN Haderslev, ESN Odense, ESN Copenhagen, ESN DTU; linked from this reconstruction.
- Not verified: exact Plasmic CSS, layout metrics, original images, fonts, animation or any backend features. Current decorative image is a **substitute photo** from Unsplash. Fonts load from Google Fonts and require internet.
- Before treating this as production-equivalent, compare desktop/mobile screenshots side-by-side and check every outbound link.

## Editing

Everything needed for the recreated homepage is in `index.html` (inline CSS and minimal JavaScript). No Node.js build step is required.

## Domain cutover caution

Do **not** switch Cloudflare DNS before the GitHub Pages preview has been checked. Cloudflare is the DNS manager; GitHub Pages is the origin web host.
