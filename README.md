# osamahafez.me

Personal website for Osama Hafez. Plain HTML/CSS, no build step, served via GitHub Pages.

## Structure

- `index.html` — the whole page
- `style.css` — styling (responsive, auto light/dark)
- `CNAME` — custom domain for GitHub Pages (`osamahafez.me`)
- `robots.txt` — crawler directives

## Preview locally

Just open `index.html` in a browser, or:

```bash
python -m http.server 8000   # then visit http://localhost:8000
```

## Deploy

Pushing to `main` publishes automatically via GitHub Pages
(Settings → Pages → Source: `main` branch, `/root`).

## DNS (Namecheap)

Point the apex + `www` at GitHub Pages:

| Type  | Host | Value                 |
|-------|------|-----------------------|
| A     | @    | 185.199.108.153       |
| A     | @    | 185.199.109.153       |
| A     | @    | 185.199.110.153       |
| A     | @    | 185.199.111.153       |
| CNAME | www  | osama-hafez.github.io |
