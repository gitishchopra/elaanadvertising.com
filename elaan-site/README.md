# Elaan Advertising — Official Website

> **Louder than Noise. Sharper than Ads.**
> One-page marketing site for Elaan Advertising — an independent media agency out of Mohali.

Live URL (after deployment): **https://elaanadvertising.com**

---

## 📁 What's in this repo

```
elaan-site/
├── index.html              ← The entire site (single file, Tailwind via CDN)
├── assets/
│   ├── elaan-logo.png      ← Logo with transparent background (nav + footer)
│   └── elaan-logo-yellow.png ← Yellow-background variant (social previews)
├── CNAME                   ← Tells GitHub Pages your custom domain
├── .nojekyll               ← Skips Jekyll processing
├── robots.txt              ← Search-engine directives
├── sitemap.xml             ← Sitemap for SEO
├── .gitignore
└── README.md               ← This file
```

No build step. No npm install. Open `index.html` in any browser and it works.

---

## 🎨 Brand system applied

| Token       | Value      | Where it's used |
|-------------|------------|-----------------|
| Primary     | `#062950`  | Nav, hero, body text, dark sections |
| Secondary   | `#1094E6`  | "Sharper" word, contact section, accents |
| Accent (red) | `#D60201` | Stat strip, "ELAAN" highlight, CTAs |
| Accent (yellow) | `#FFC606` | Marker highlights, buttons, founder card |
| Cream       | `#F5F1E8`  | Manifesto + clients background (soulful warmth) |
| Headings    | Poppins (900/800/700) | All H1–H4, buttons, eyebrows |
| Body        | Open Sans (400/600) | Paragraphs, lists, addresses |

Marker-style highlights (yellow & red bands behind key words) mirror the portfolio PDF.

---

# 🚀 Deploy in 15 minutes — Free, forever

We're using **GitHub Pages** (free static hosting) + **GoDaddy DNS** (you already own the domain). Total cost after this: **₹0/month**.

## Step 1 — Push this folder to a new GitHub repo

> Skip to Step 2 if you've never used GitHub. The web upload works fine for this.

### Option A · Web upload (easiest, no terminal needed)

1. Go to **https://github.com/new** and sign in (create a free account if you don't have one).
2. Repository name: **`elaanadvertising.com`** (use this exact name — it's a convention).
3. Set it to **Public** (private repos can't use Pages on free plan).
4. **Do NOT** tick "Add a README" — we already have one.
5. Click **Create repository**.
6. On the next page, click **"uploading an existing file"**.
7. Drag in everything from the `elaan-site/` folder — including hidden files like `.nojekyll` and `CNAME`.
   - On macOS Finder: press `⌘ + Shift + .` to show hidden files first.
   - On Windows Explorer: View → Show → Hidden items.
8. Commit message: `Initial site` → **Commit changes**.

### Option B · Command line (if you prefer)

```bash
cd path/to/elaan-site
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/elaanadvertising.com.git
git push -u origin main
```

## Step 2 — Turn on GitHub Pages

1. In your new repo, click **Settings** (top tab) → **Pages** (left sidebar).
2. Under **Source**, select **Deploy from a branch**.
3. Branch: **`main`** · Folder: **`/ (root)`** → **Save**.
4. Wait ~60 seconds. Refresh. You'll see:
   > ✅ *Your site is live at `https://YOUR-USERNAME.github.io/elaanadvertising.com/`*
5. Open that link to confirm it works. If it does, you're 80 % done.

## Step 3 — Tell GitHub about your custom domain

Still in **Settings → Pages**:

1. Under **Custom domain**, type **`elaanadvertising.com`** → **Save**.
2. (The `CNAME` file in the repo already does this, but doing it via UI also kicks off the DNS check.)
3. Below it, you'll see "DNS check in progress". That's expected — we haven't pointed DNS yet. We'll do that next.

## Step 4 — Point GoDaddy DNS to GitHub

Open a new tab and log in to **https://dcc.godaddy.com** → **My Products** → find `elaanadvertising.com` → click **DNS**.

You'll see a table of records. We need to add 5 records and remove anything that conflicts.

### 4a. Delete conflicting records

Look for any existing **A** record with `@` as the name, or **CNAME** with `www` as the name. **Delete them** (they point to GoDaddy's parking page).

> ⚠️ Don't touch MX records (those are your email).

### 4b. Add 4 A records (for the apex `elaanadvertising.com`)

Click **Add New Record** four times and enter:

| Type | Name | Value          | TTL    |
|------|------|----------------|--------|
| A    | @    | `185.199.108.153` | 1 Hour |
| A    | @    | `185.199.109.153` | 1 Hour |
| A    | @    | `185.199.110.153` | 1 Hour |
| A    | @    | `185.199.111.153` | 1 Hour |

These are GitHub Pages' four edge IPs. They're public and stable — don't worry that you didn't generate them.

### 4c. Add 1 CNAME record (for the `www.` version)

| Type  | Name | Value                          | TTL    |
|-------|------|--------------------------------|--------|
| CNAME | www  | `YOUR-USERNAME.github.io.`     | 1 Hour |

> Replace `YOUR-USERNAME` with your actual GitHub username. **Keep the trailing dot.**

Click **Save** on each record. GoDaddy may show a yellow "propagating" banner.

## Step 5 — Wait for DNS propagation (10 min – 2 hours)

DNS takes time. To check progress:

- Run `dig elaanadvertising.com +short` in a terminal (should return the GitHub IPs).
- Or check **https://dnschecker.org** → paste your domain → most regions should show GitHub's IPs.

## Step 6 — Turn on HTTPS

Go back to **GitHub → Settings → Pages**:

1. Wait until the "DNS check successful" green tick appears.
2. Tick the box: **Enforce HTTPS**.
3. GitHub provisions a free Let's Encrypt SSL certificate automatically (can take up to 24 hours; usually < 30 min).

Once that's done, **https://elaanadvertising.com** is live, secure, and free forever.

---

## ✏️ Updating the site later

### To edit text or sections

1. Open `index.html` in any editor (VS Code, Sublime, even Notepad).
2. Search for the text you want to change — copy is plain HTML, easy to find.
3. Save → upload back to GitHub (drag-drop on the file → Commit).
4. GitHub Pages redeploys in ~30 seconds. Refresh your site.

### To swap the logo

Replace `assets/elaan-logo.png` with your new file (keep the same filename). Commit. Done.

### To add a blog or case studies later

Create a `case-studies/` folder, put HTML files inside, link to them from `index.html`. GitHub Pages serves any HTML file you push.

---

## 🔍 SEO checklist (already shipped)

- ✅ Semantic HTML5 (`<header>`, `<section>`, `<footer>`, `<address>`)
- ✅ `<title>` + meta description tuned for "media agency Mohali"
- ✅ Open Graph tags (rich previews in WhatsApp, LinkedIn, Twitter)
- ✅ Favicon + theme color
- ✅ `sitemap.xml` + `robots.txt`
- ✅ All links use real anchors (good for crawlers + accessibility)
- ✅ `tel:` and `mailto:` are clickable on mobile

> After deployment, submit `https://elaanadvertising.com/sitemap.xml` at **https://search.google.com/search-console** to get indexed faster.

---

## 🆘 Troubleshooting

| Symptom | Fix |
|--------|-----|
| GitHub Pages says "Site not published" | Check `Settings → Pages → Source` is set to `main / root` |
| Custom domain shows "DNS check unsuccessful" | DNS hasn't propagated yet. Wait 1–2 hours. |
| Site loads at `*.github.io` but not at `elaanadvertising.com` | The CNAME file got deleted on a commit. Re-add a file called `CNAME` with the content `elaanadvertising.com` |
| HTTPS won't enable | Wait. Let's Encrypt cert can take up to 24 hours after DNS resolves. |
| Fonts look wrong | Check the browser isn't blocking Google Fonts. Try a different network. |
| Logo doesn't show | Make sure `assets/elaan-logo.png` was uploaded along with `index.html` |

---

## 📞 Quick contact

**Gitish Chopra** · Founder & Chief Strategist
Elaan Advertising · Mohali

- 📞 +91 98174 90095 (Call & WhatsApp)
- ✉ create@elaanadvertising.com · elaan.advertising@gmail.com
- in/gitishchopra

---

© Elaan Advertising. *Louder than Noise. Sharper than Ads.*
