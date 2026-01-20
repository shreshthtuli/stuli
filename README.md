# stuli.ai - Personal Website

Personal website for Shreshth Tuli, hosted on GitHub Pages with custom domain.

## 🚀 Auto-Deployment

This repository uses GitHub Actions to automatically deploy to GitHub Pages whenever you push to the `main` branch.

## 📋 Initial Setup Guide

### 1. Create GitHub Repository

```bash
# Create a new repo on GitHub named 'stuli.ai' or 'personal-website'
# Then clone and add files:

git init
git add .
git commit -m "Initial commit: personal website"
git branch -M main
git remote add origin https://github.com/shreshthtuli/stuli.ai.git
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages** (in left sidebar)
3. Under "Build and deployment":
   - **Source**: Select "GitHub Actions"
4. Wait for the first deployment to complete (check Actions tab)

### 3. Configure Custom Domain on GitHub

1. Go to **Settings** → **Pages**
2. Under "Custom domain", enter: `stuli.ai`
3. Click **Save**
4. Check "Enforce HTTPS" (after DNS propagates)

### 4. Configure DNS on Porkbun

1. Log into [Porkbun](https://porkbun.com)
2. Go to **Domain Management** → **stuli.ai** → **DNS**
3. Delete any existing A or CNAME records for the root domain
4. Add these **A Records** (for apex domain `stuli.ai`):

| Type | Host | Answer | TTL |
|------|------|--------|-----|
| A | (leave blank) | 185.199.108.153 | 600 |
| A | (leave blank) | 185.199.109.153 | 600 |
| A | (leave blank) | 185.199.110.153 | 600 |
| A | (leave blank) | 185.199.111.153 | 600 |

5. Add this **CNAME Record** (for `www` subdomain):

| Type | Host | Answer | TTL |
|------|------|--------|-----|
| CNAME | www | shreshthtuli.github.io | 600 |

> **Note**: Replace `shreshthtuli` with your actual GitHub username

### 5. Wait for DNS Propagation

- DNS changes can take 10 minutes to 48 hours to propagate
- Check status at: https://dnschecker.org/#A/stuli.ai
- Once propagated, enable "Enforce HTTPS" in GitHub Pages settings

## 🔄 Making Updates

Simply push changes to the `main` branch:

```bash
git add .
git commit -m "Update website content"
git push
```

GitHub Actions will automatically deploy your changes within 1-2 minutes.

## 📁 Project Structure

```
├── index.html          # Main website file
├── CNAME               # Custom domain configuration
├── README.md           # This file
└── .github/
    └── workflows/
        └── deploy.yml  # GitHub Actions deployment workflow
```

## 🛠 Local Development

Simply open `index.html` in your browser, or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .
```

Then visit `http://localhost:8000`

## 📝 License

© 2025 Shreshth Tuli. All rights reserved.
