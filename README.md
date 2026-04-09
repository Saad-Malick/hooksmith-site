# HOOKSMITH — Landing Page

Gen-Z Gaming Hook Writer · Personal Brand Site

---

## Stack
- Pure HTML / CSS / JS — zero build tools, zero dependencies
- Netlify (free tier) — auto-deploy on git push
- Netlify Forms OR Formspree for CTA form submissions

---

## 🚀 Deploy in 3 Steps

### 1. Local Setup
```bash
mkdir hooksmith-site
cd hooksmith-site
git init
git add .
git commit -m "init: hooksmith landing page"
```

### 2. Push to GitHub
```bash
# Create a new repo on github.com (name it hooksmith-site or similar)
git remote add origin https://github.com/YOUR_USERNAME/hooksmith-site.git
git branch -M main
git push -u origin main
```

### 3. Connect Netlify
1. Go to app.netlify.com → New site from Git
2. Choose GitHub → select your repo
3. Build settings:
   - Build command: *(leave blank)*
   - Publish directory: `.`
4. Click Deploy

**That's it.** Every `git push` auto-redeploys.

---

## 📬 Form Submissions (Pick One)

### Option A — Netlify Forms (easiest, free up to 100/month)
Add `netlify` attribute to your form tag in index.html:
```html
<form class="cta-form" id="ctaForm" name="hook-requests" netlify>
```
Submissions appear in your Netlify dashboard.

### Option B — Formspree (free up to 50/month, no limit on pages)
1. Sign up at formspree.io
2. Create a form, get your endpoint
3. In script.js, replace the `setTimeout` mock with:
```js
const res = await fetch('https://formspree.io/f/YOUR_ID', {
  method: 'POST',
  headers: { 'Accept': 'application/json' },
  body: formData
});
```

---

## 🎨 Customise

| Thing | Where |
|---|---|
| Your name / brand | index.html → nav-logo, footer-logo |
| Instagram handle | index.html → hero CTA link |
| Email | index.html → footer |
| Spec hook content | index.html → `.spec-card` sections |
| Pricing | index.html → `.offer-card` sections |
| Accent color | style.css → `--accent` |

---

## 📁 Structure
```
hooksmith-site/
├── index.html      ← All content
├── style.css       ← Design system
├── script.js       ← Cursor, reveals, form, nav
├── netlify.toml    ← Deploy config
└── README.md
```

---

## Future Upgrades (all free)
- **Custom domain** → Netlify gives you one free subdomain; connect your own via Namecheap/Porkbun (~$10/year)
- **Analytics** → Add Umami (self-hosted) or Plausible free tier
- **Email list** → Swap Formspree for ConvertKit free (1000 subscribers)
- **Blog / case studies** → Add a `/work` folder with more HTML files
