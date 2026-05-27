# forbidden-support

Static pages for the **Forbidden!** iOS app — Support and Privacy Policy.

Hosted via GitHub Pages under the **forbidden-app** GitHub organization.
Required by App Store Guideline 1.5.0 (Safety: Developer Information).

## Pages

- `index.html` — Support landing page (contact email)
- `privacy.html` — Privacy Policy (no data collection)
- `forbidden-icon.png` — F-Capsule app icon, 1024×1024 (use as org avatar)

## One-time setup (~10-15 min)

### 1. Create the GitHub organization

- GitHub → top-right "+" → **New organization** → Free plan
- **Organization name:** `forbidden-app`
- **Contact email:** `yasin.kbas12@gmail.com`
- This account is for: **My personal account**
- Skip invites / setup screens

### 2. Set the org avatar

- Org page → Settings → Profile → Logo → Upload
- Use `forbidden-icon.png` from this folder

### 3. Create the `forbidden-support` repository

- Org page → "+" → New repository
- **Owner:** `forbidden-app`
- **Repository name:** `forbidden-support`
- **Public** (required for free GitHub Pages)
- Initialize empty (no README, no .gitignore, no license — we have them locally)

### 4. Push these files

```bash
cd /Users/yasinkbas/Desktop/taboo/forbidden-support
git init
git add .
git commit -m "initial: support + privacy pages for Forbidden!"
git branch -M main
git remote add origin https://github.com/forbidden-app/forbidden-support.git
git push -u origin main
```

### 5. Enable GitHub Pages

- Repo → Settings → Pages
- **Source:** Deploy from a branch
- **Branch:** `main`, **Folder:** `/ (root)`
- Save → wait ~30-60 seconds

## Resulting URLs (paste into App Store Connect)

| Field in ASC | URL |
|---|---|
| **Support URL** | `https://forbidden-app.github.io/forbidden-support/` |
| **Privacy Policy URL** | `https://forbidden-app.github.io/forbidden-support/privacy.html` |
| **Marketing URL** (optional) | Same as Support URL |

## Verifying

After Pages reports the deployment as live (green check in Settings → Pages):
- Open both URLs in a browser — should render with Forbidden! branding
- Test the email link on mobile (should open Mail.app composing to `yasin.kbas12@gmail.com`)
- Both pages cross-link to each other in the footer

## Updating later

```bash
cd /Users/yasinkbas/Desktop/taboo/forbidden-support
# edit privacy.html or index.html
git add .
git commit -m "docs: update <what changed>"
git push
```

GitHub Pages rebuilds automatically (~30-60s).

## Design notes

- Pure HTML + inline CSS, no JS, no external dependencies
- Mobile-responsive (Apple reviewers may visit from iPhone)
- Brand palette matches the iOS app: `#FF7A3D` primary, `#B52640` accent, `#FFF5DC` background
- SF Pro / system font stack
- Lightweight (<5 KB each before compression)
