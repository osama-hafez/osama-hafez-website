# osamahafez.me

Personal website for Osama Hafez. Plain HTML/CSS, no build step, served via
GitHub Pages on a custom domain.

> **Note:** this repo is **public**. Keep it that way for free GitHub Pages, and
> never commit secrets, tokens, or account credentials. Everything below is
> non-sensitive (DNS values are publicly resolvable anyway).

## Structure

- `index.html` — the whole page (single file)
- `style.css` — styling: responsive, cream & coffee theme with emerald accents, auto light/dark
- `me.jpg` — hero avatar
- `CNAME` — custom domain for GitHub Pages (`osamahafez.me`)
- `robots.txt` — crawler directives

## Preview locally

Open `index.html` directly, or serve it:

```bash
python -m http.server 8000   # then visit http://localhost:8000
```

## Deployment

| | |
|---|---|
| **Repo** | `osama-hafez/osama-hafez-website` (public) |
| **Host** | GitHub Pages — source: `main` branch, `/` (root) |
| **Live URL** | https://osamahafez.me |
| **Custom domain** | `osamahafez.me` (set in Settings → Pages; also in the `CNAME` file) |
| **HTTPS** | Enforced (auto Let's Encrypt cert via GitHub) |
| **Registrar / DNS** | Namecheap (Advanced DNS) |

**To publish a change:** commit and push to `main`. GitHub Pages rebuilds
automatically (usually under a minute). The `CNAME` file must stay in the repo
root — deleting it drops the custom domain.

## DNS (Namecheap → Advanced DNS)

Apex (`@`) uses A records to GitHub's Pages IPs; `www` is a CNAME to the org's
Pages host. Keep the existing email-forwarding `TXT` (SPF) record untouched.

| Type  | Host | Value                   |
|-------|------|-------------------------|
| A     | @    | 185.199.108.153         |
| A     | @    | 185.199.109.153         |
| A     | @    | 185.199.110.153         |
| A     | @    | 185.199.111.153         |
| CNAME | www  | osama-hafez.github.io   |

Optional IPv6 (`AAAA`, Host `@`): `2606:50c0:8000::153` … `::8003::153`.

## Troubleshooting

- **Domain shows "unverified" / 404** — confirm the `CNAME` file is present and
  the A/CNAME records above resolve (`nslookup osamahafez.me`).
- **No HTTPS / cert pending** — GitHub provisions the cert after DNS verifies;
  can take a few minutes. Re-toggle the custom domain in Settings → Pages if stuck.
- **Change didn't appear** — check the latest Pages build under the repo's
  Actions/Pages, and hard-refresh (GitHub's CDN caches briefly).
