# Enzara Therapeutics website: deploy guide

Static site for GitHub Pages (free), using the domain enzara-therapeutics.com registered at Wix.

## Files
- `index.html`, `science.html`, `leadership.html`, `investors.html`, `news.html`, `contact.html`: the pages
- `assets/styles.css`: all styling (colors at the top)
- `assets/favicon.svg`: browser-tab icon
- `CNAME`: tells GitHub Pages the custom domain. Keep it.
- `404.html`: shown for missing pages

## 1. Put the site on GitHub (about 10 minutes)
1. Create a free account at github.com (or use an existing one). An organization named `enzara-therapeutics` keeps it company-owned.
2. Create a new **public** repository, for example `website`.
3. Choose **uploading an existing file**, drag in everything from this folder (including the `assets` folder and `CNAME`), and commit.
4. Go to **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**. Save.
5. The site appears at `https://<account>.github.io/website/` within a few minutes.

## 2. Point the Wix domain at GitHub (about 10 minutes, then up to 48 hours to propagate)
In Wix: **Domains → enzara-therapeutics.com → Manage DNS records**.

**A records** (Host: `@`, the bare domain). Replace the existing Wix A record with these four:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```
**CNAME record** (Host: `www`). Point to `<account>.github.io` (account or organization name only, no repository name).

Leave MX and TXT records alone; those are for email.

## 3. Turn on HTTPS
Back in **Settings → Pages**, enter `enzara-therapeutics.com` as the custom domain if it is not already there, wait for the DNS check to pass, then tick **Enforce HTTPS**. GitHub notes this can take up to 24 hours to become available.

Optional: under your GitHub account or organization **Settings → Pages**, verify the domain. This stops anyone else from claiming it on GitHub Pages.

## Before going public
- Search the files for `todo` placeholders (Leadership page: co-founder, advisors, confirm bio and title).
- Set up the `info@enzara-therapeutics.com` mailbox, or change the address in `contact.html`, `investors.html`.
- Check with UT Austin and UMB on use of the university names (both have name-use policies, and UT faculty startups typically go through conflict-of-interest review).

## Adding a news item
In `news.html`, copy one `<li>…</li>` block inside `<ul class="feed">`, put it first, and edit the date, tag, headline and text. Do the same on `index.html` (home shows the two newest). Upload the changed files to the repository; the site updates in a minute or two.
