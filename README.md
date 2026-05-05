# ReachAI — Production Deployment Guide

AI-powered outreach message generator. Built with Claude AI.
Works in English + Bahasa Malaysia.

---

## What's included

```
reachai/
├── index.html          ← Complete app (landing + generator + dashboard)
└── README.md           ← This file
```

The entire app is ONE HTML file. No framework, no build step needed.

---

## Step 1 — Test locally

Just open `index.html` in your browser. Everything works immediately.

---

## Step 2 — Deploy to Vercel (free, 5 minutes)

### Option A — Drag and drop (easiest)
1. Go to https://vercel.com → Sign up free
2. Click "Add New Project" → "Deploy from file upload"
3. Drag your `reachai` folder
4. Done — you get a live URL like `reachai.vercel.app`

### Option B — Via Claude Code (recommended)
Open Claude Code in your terminal and paste:

```
Deploy this folder to Vercel. The folder is at ~/reachai.
The main file is index.html. Give me a live public URL.
```

Claude Code will handle everything automatically.

---

## Step 3 — Connect Stripe (to start charging users)

### 3a. Create Stripe account
1. Go to https://stripe.com → Sign up
2. Get your API keys from Dashboard → Developers → API Keys

### 3b. Create payment links (no code needed)
In Stripe Dashboard → Payment Links → Create:

| Plan     | Price   | Create link for...         |
|----------|---------|----------------------------|
| Starter  | $9/mo   | Monthly subscription       |
| Pro      | $29/mo  | Monthly subscription       |
| Agency   | $79/mo  | Monthly subscription       |

### 3c. Paste your Stripe links into index.html
Find these lines in index.html and replace with your actual Stripe links:

```html
<!-- Find: -->
onclick="openModal('signup')"

<!-- Replace the 3 pricing buttons with: -->
onclick="window.open('https://buy.stripe.com/YOUR_STARTER_LINK')"
onclick="window.open('https://buy.stripe.com/YOUR_PRO_LINK')"  
onclick="window.open('https://buy.stripe.com/YOUR_AGENCY_LINK')"
```

---

## Step 4 — Add your custom domain

1. Buy a domain (Namecheap ~$10/year) — e.g. `reachai.app`
2. In Vercel → Project Settings → Domains → Add domain
3. Point your DNS to Vercel (they give you exact instructions)
4. Done — your app is live on your own domain

---

## Step 5 — Set up user auth (optional but recommended)

For a proper login system, use Supabase (free):

1. Go to https://supabase.com → Create project
2. Enable Auth → Email provider
3. Ask Claude Code: "Add Supabase auth to my ReachAI index.html using project URL [YOUR_URL] and anon key [YOUR_KEY]"

---

## Step 6 — List on directories to get traffic

After deploying, list your app here for free traffic:

- https://theresanaiforthat.com (submit free)
- https://futurepedia.io (submit free)
- https://aitoolslist.io (submit free)
- https://producthunt.com (launch on Tuesday/Wednesday)
- https://trustmrr.com (once you have Stripe revenue)

---

## Revenue targets

| Users  | MRR       | TrustMRR sale value |
|--------|-----------|---------------------|
| 10     | $290/mo   | ~$5,000–$8,000      |
| 50     | $1,450/mo | ~$26,000–$43,000    |
| 100    | $2,900/mo | ~$52,000–$87,000    |

---

## Support

Built with Claude AI by Anthropic.
For deployment help, open Claude Code and describe what you need.
