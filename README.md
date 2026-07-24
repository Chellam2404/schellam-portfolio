# Chellam S — Portfolio

A single-page, static portfolio site. No build step, no framework — just `index.html` plus two assets. That makes it deployable literally anywhere in under 5 minutes.

## Files

```
portfolio/
├── index.html                     # entire site (HTML + CSS + JS)
├── assets/
│   ├── chellam-photo.jpeg         # hero photo
│   └── Chellam_S_Resume.pdf       # resume (View/Download buttons link here)
└── README.md
```

## Before you deploy — 2 things to change

1. **Contact form endpoint** — in `index.html`, find this line near the bottom of the `<script>`:
   ```js
   const FORMSPREE_ENDPOINT = "https://formspree.io/f/your-form-id";
   ```
   Sign up free at [formspree.io](https://formspree.io), create a form, and swap in your real endpoint. That's the only edit needed — the form already validates fields, shows inline errors, shows a loading/success/error banner, clears itself on success, and submits via `fetch` (no page reload) once this one line points to your real endpoint.
2. **Phone number** — the `tel:` link uses the number from your resume. Remove the phone row in the Contact section if you'd rather not list it publicly.

## Deploy for free, with a clean URL

I can't push code to GitHub or provision a domain on your behalf — I don't have network access or your GitHub credentials in this session. But any of these gets you a public, shareable link in a few minutes, no login required for visitors:

### Option A — Vercel (recommended, gives you `chellam.vercel.app`-style URLs)
1. Create a free account at vercel.com (sign in with GitHub).
2. Create a new GitHub repo (e.g. `chellam-portfolio`) and push these files to it.
3. In Vercel: **Add New Project → Import** your repo → Deploy (no build settings needed, it's static).
4. Vercel gives you `https://chellam-portfolio.vercel.app` by default. In **Project Settings → Domains**, you can rename the project so the URL becomes `https://chellam.vercel.app` (first-come-first-served on that subdomain).

### Option B — Cloudflare Pages (gives you `chellam.pages.dev`-style URLs)
1. Free account at pages.cloudflare.com.
2. Connect your GitHub repo, or just drag-and-drop the `portfolio` folder in the dashboard.
3. Deploy → you get `https://chellam-portfolio.pages.dev`, renameable similarly.

### Option C — GitHub Pages (gives you `yourusername.github.io`)
1. Push this folder to a repo named `<your-github-username>.github.io`.
2. In repo **Settings → Pages**, set source to the main branch root.
3. Live at `https://<your-github-username>.github.io` in a minute or two.

## Connecting a real custom domain (chellam.me / chellam.dev / etc.)

None of the above give you `chellam.me` automatically — that requires **buying the domain** from a registrar (Namecheap, Google Domains successor Squarespace, Porkbun, GoDaddy — typically $8–15/year for `.me`/`.dev`/`.in`). Once purchased:

1. In Vercel/Cloudflare Pages, go to **Domains** and add `chellam.me`.
2. They'll give you DNS records (usually a CNAME or A record) to add at your registrar.
3. Propagation takes a few minutes to a few hours; the platform auto-issues HTTPS.

Availability of `chellam.me`, `chellam.dev`, etc. varies — check at your registrar of choice before committing to messaging on your resume.

## Notes on content

Every project, internship, certification, and publication on the site is pulled directly from your resume and project reports. A few items from your original brief weren't in any uploaded document (Employee Management REST API, Sales Performance Dashboard, Fake News Detection, Azure/Oracle certifications) — I left those out rather than inventing details for them. Send me the specifics (tech stack, what it does, dates) and I'll add matching cards.

Project screenshots are represented with a terminal-style header instead of a placeholder image — swap in real screenshots by replacing the `.term-bar` div in each project card with an `<img>` tag once you have them.
