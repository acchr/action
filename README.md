# ACtion ipTV — website

Static marketing + legal site for the ACtion ipTV Samsung TV app. No build step,
no dependencies, no external CDNs — just HTML, CSS and one SVG. Deploy the
contents of this folder to any static host.

## Pages
| File | Purpose |
|------|---------|
| `index.html` | Marketing landing page (hero, features, how-it-works, pricing, FAQ) |
| `privacy.html` | Privacy Policy (Samsung Seller Office requires a privacy URL) |
| `terms.html` | Terms of Service |
| `support.html` | Help / FAQ / troubleshooting / contact |
| `styles.css` | Shared stylesheet |
| `favicon.svg` | Site icon / logo mark |

## Before you publish — replace these placeholders
Search the folder for each bracketed token and fill in real values:

- `[CONTACT_EMAIL]` — a real support/privacy email (appears in privacy, terms, support)
- `[ENTITY]` — the legal name of the developer/operator (terms.html)
- `[JURISDICTION]` — governing-law country/state (terms.html)

The legal pages are a solid starting template tailored to how the app actually
behaves (player only, local storage, Samsung Checkout, 7-day trial, $4.99/mo).
**Have a legal professional review them for your region before relying on them.**

The pricing ($4.99/mo, 7-day trial, plan name "ACtion ipTV Premium") mirrors
`licensing.js`. If you change pricing there, update `index.html` and `terms.html`.

## Local preview
From the **project root**:

```sh
python -m http.server 5173
# then open http://localhost:5173/website/index.html
```

…or serve this folder directly as the web root:

```sh
cd website
python -m http.server 8080
# then open http://localhost:8080/
```

## Deploy
Upload the files to any static host (GitHub Pages, Netlify, Cloudflare Pages,
Vercel, S3, or plain nginx/Apache). Point the domain at the folder; `index.html`
is the entry point. Use the resulting URLs (e.g. `/privacy.html`, `/support.html`)
in your Samsung Seller Office app listing.

> This `website/` folder is **not** part of the Tizen app package — keep it out
> of the `.wgt` build (it isn't referenced by `config.xml`).
