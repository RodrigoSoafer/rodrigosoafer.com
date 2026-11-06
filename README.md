# rodrigosoafer.com

The one-page link hub for Rodrigo Soafer (acoustic guitar and vocals, Adelaide, South Australia).
It is the page a Linktree would be, on his own domain. Built 6 Nov 2026.

## What it is

- `index.html` — the whole site. One file, no build step, no JavaScript.
- `.nojekyll` — tells GitHub Pages to serve the files as they are.
- `CNAME` — the custom domain (`rodrigosoafer.com`). Added once the github.io URL rendered.

Design: the Rodrigo Soafer identity, D6 INDEX layout (the ruled web/EPK exception). Source of
truth lives in ONION at `references/brand/rodrigo-soafer/` (`SOURCE.md`, `tokens.css`,
`templates/phone-epk.html`). Card `#ECE4D2`, ink `#1B1815`, purple `#5B3FA6` on the featured
number and rules only, Epilogue type, the family mark above the wordmark. Never redraw the mark.

## How to update

1. Edit `index.html`. Keep every fact verifiable (no claims, no numbers that are not true today).
2. Check it in a browser at 390px wide and at desktop width.
3. Commit and push `main`:

```bash
git add -A && git commit -m "Update" && git push
```

GitHub Pages redeploys in about a minute. The live show video has a commented slot in the
links list; add the row, uncomment, push.

## Hosting

- GitHub Pages, repo `RodrigoSoafer/rodrigosoafer.com`, branch `main`, folder `/`.
- HTTPS is GitHub's certificate, issued once DNS points at GitHub. Turn on "Enforce HTTPS"
  in the repo's Pages settings after the certificate shows as issued.

## DNS (at Hover — RSF's hand only)

Control panel: https://www.hover.com/control_panel/

Add these records. Leave the existing MX (`smtp.google.com`, Google Workspace mail) untouched.

| Type | Host | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | rodrigosoafer.github.io |

Why GitHub Pages and not Hover's own forwarding: Hover forwarding is HTTP-only. A forward
cannot serve `https://rodrigosoafer.com`, so browsers that default to HTTPS (and every link
that gets written with it) would fail. Pages serves the page itself, with a certificate.
