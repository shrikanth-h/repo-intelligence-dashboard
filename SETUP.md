# Setup checklist

A click-by-click guide to finish publishing the dashboard. Total time: ~15 minutes.

Items are ordered so each step builds on the last. Don't skip steps 2 or 3 — they're the difference between a published page and a 404.

---

## 1. Commit and push these files

From the cloned repo root:

```bash
git add .
git commit -m "feat: initial dashboard publication"
git push origin main
```

The repo should now show a populated README, the social preview image under `docs/`, and the dashboard as `index.html` at the root.

---

## 2. Enable GitHub Pages

This is what turns `index.html` into a live website.

1. Open the repo on github.com.
2. Click **Settings** (top nav of the repo, not your account settings).
3. In the left sidebar, click **Pages**.
4. Under **Build and deployment**, set:
   - **Source**: `Deploy from a branch`
   - **Branch**: `main`
   - **Folder**: `/ (root)`
5. Click **Save**.

A banner appears at the top of the Pages screen saying the site is being built. Refresh after ~60 seconds; the banner becomes:

> Your site is live at `https://shrikanth-h.github.io/repo-intelligence-dashboard/`

Open that URL. You should see the dashboard. If you see a 404 or a README rendered as plain text, double-check the **Folder** is set to `/ (root)` and not `/docs`.

---

## 3. Configure the "About" panel

This is where Topics live (you couldn't find them earlier because they're not in Settings).

1. Go back to the repo's main page.
2. Look at the right sidebar. Below your avatar there's an **About** panel.
3. Click the small ⚙️ gear icon at the top-right of that panel.
4. A modal opens with three fields:

**Description** (paste verbatim):

```
A curated atlas of open-source repos shaping modern AI engineering — agent frameworks, RAG platforms, dev tooling. Architecture diagrams, alternatives, and learning paths for every entry. Single-file HTML dashboard, no build step.
```

**Website** (paste verbatim):

```
https://shrikanth-h.github.io/repo-intelligence-dashboard/
```

**Topics** (type each one and press Enter or comma):

```
ai-agents
llm
rag
mcp
claude
agent-framework
developer-tools
curated-list
ai-engineering
dashboard
```

Check **Use your GitHub Pages website** (it auto-fills the website field from your Pages config). Click **Save changes**.

---

## 4. Upload the social preview image

The image at `docs/social-preview.png` lives in the repo for the README to embed. GitHub also needs a separate upload for share cards on Twitter/X, LinkedIn, Slack, etc.

1. **Settings** → scroll down to **Social preview**.
2. Click **Edit** (or **Upload an image**).
3. Upload `docs/social-preview.png` (1280 × 640, ~100 KB).
4. Click **Save changes**.

To verify, paste the repo URL into Slack or X's tweet composer — the preview card should now show the editorial atlas image instead of the generic GitHub avatar.

---

## 5. Pin the repo on your profile

This puts the dashboard on your profile page where recruiters and collaborators land first.

1. Go to your profile: `https://github.com/shrikanth-h`.
2. Click **Customize your pins** (under the contribution graph).
3. Check `repo-intelligence-dashboard`. Uncheck anything you'd rather de-emphasize.
4. Save.

---

## 6. Verify the live page

Open `https://shrikanth-h.github.io/repo-intelligence-dashboard/` in a private/incognito window. Confirm:

- [ ] Page loads with the masthead, summary metrics, and all sections rendered
- [ ] Architecture diagrams render inside the repository cards (expand one)
- [ ] The Comparison Matrix populates
- [ ] Filter chips and search both work
- [ ] Deep links work: open `?category=Memory%20%26%20context` and verify the index pre-filters
- [ ] Footer shows today's date as the compile date

If any of these fail, check the browser console for errors (most common cause: a CDN being blocked by the CSP — see the head of `index.html`).

---

## 7. Replace the placeholder handles inside the HTML

The dashboard's masthead and footer reference `@your-handle` and `YOUR-HANDLE`. Replace them:

```bash
# Inside the repo root:
sed -i.bak 's/YOUR-HANDLE/shrikanth-h/g; s/@your-handle/@shrikanth-h/g' index.html
rm index.html.bak
git add index.html
git commit -m "chore: fill in author handles"
git push
```

Pages will redeploy automatically within a minute.

---

## 8. Distribution (optional, do later)

Once steps 1–7 are clean, the dashboard is publishable. Don't blast every channel the same day — space them so each gets a clean window:

- **Day 1**: Show HN — `https://news.ycombinator.com/submit`
- **Day 2 or 3**: LinkedIn post or Twitter/X thread with the social preview card
- **Day 4+**: PRs to other awesome-lists pointing back to the dashboard as a related resource (e.g., `kyrolabs/awesome-agents`, `e2b-dev/awesome-ai-agents`)
- **Week 2**: Reddit (`r/LocalLLaMA`, `r/MachineLearning`'s self-promotion thread)

Track which channel drives the most stars in the first 48 hours — that tells you which audience this resonates with and where to invest next.

---

## What's next (batch 2)

The community-standards files (`CODE_OF_CONDUCT.md`, `SECURITY.md`, issue templates, PR template) come in the next batch. They're not launch-blocking; you can publish today and add them this week.

The metadata-refresh GitHub Action — the one that auto-updates star counts nightly — requires splitting the `repositories` array out of `index.html` into a separate `repos.json`. That's a follow-up task, not a launch task.

---

That's it. If anything in steps 1–6 fails or the rendered page looks off, capture the error and we'll fix it before batch 2.
