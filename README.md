# Gigger landing page

The agency-to-agency partnership platform — public marketing site.

Single-file static page: HTML + CSS + vanilla JS, no build step.

## Run locally

Open `index.html` directly in a browser, or serve the folder:

```bash
npx serve .
# or
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploy (GitHub Pages)

1. Push to `main`.
2. Repo **Settings → Pages → Source: `main` / `(root)` → Save**.
3. Live at `https://<username>.github.io/<repo>/` within a minute.

For a custom domain, add a `CNAME` file at the root with the domain on a single line and configure DNS per [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Structure

```
.
├── index.html       # entire landing page (markup, styles, scripts)
└── assets/
    ├── gigger-logo.svg
    ├── favicon.svg
    ├── artem.png            # founder photo (used in lifetime modal)
    └── avatar-{ana,ana-sm,tom,jess}.png   # demo avatars in product mockups
```

## External services

Two third-party integrations — replace if you migrate them:

| What | Where | Used for |
|---|---|---|
| **Tally** | `https://tally.so/r/A766ZB` | "Apply to join beta" CTAs (4 spots: nav, hero, pricing free plan, final CTA) |
| **Formsubmit** | `https://formsubmit.co/ajax/c516ad938c7220351528553761be148e` (alias for the project owner's inbox) | Lead-magnet form (playbook download) and Lifetime Pro modal — both POST here, submissions land in inbox |

**One-time Formsubmit activation:** the first submission to a new email triggers an activation link sent to that address. Click it once and submissions start landing for real. After that, Formsubmit also gives you a random alias hash — replace the email in `index.html` with the hash if you want to keep your address out of the page source.

## Editing copy

All copy lives inline in `index.html`. Section anchors are flagged with `<!-- ============== SECTION ============== -->` comments — search for those to jump around.

The full copy + design brief (per-section verbatim copy and ICP context) is in `uploads/Gigger_LandingPage_Brief.docx` (kept locally, gitignored).
