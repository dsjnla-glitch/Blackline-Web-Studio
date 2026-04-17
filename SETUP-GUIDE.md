# Blackline Web Studio — Setup Guide
### Deploying to Netlify + Setting Up Your Portfolio Admin

---

## YOUR SITE FILES

Upload ALL of these to Netlify (keep the folder structure exactly as-is):

```
index.html
services.html
portfolio.html
about.html
netlify.toml
admin/
  index.html
  config.yml
_data/
  projects/
    manifest.json
    nomadic-needlework.json
```

---

## STEP 1 — Deploy to Netlify

1. Go to **netlify.com** and log in
2. From your dashboard, click **"Add new site"** → **"Deploy manually"**
3. Drag and drop your entire site folder onto the upload area
4. Netlify will give your site a random URL like `quirky-name-123.netlify.app`
5. To use your own domain, go to **Site Settings → Domain Management** and add it

---

## STEP 2 — Enable Netlify Identity (required for admin login)

This is what lets you log into your admin panel securely.

1. In your Netlify dashboard, click your site
2. Go to **Site Settings → Identity**
3. Click **"Enable Identity"**
4. Scroll down to **Registration preferences** → set to **"Invite only"**
   *(This means only you can have an account — no one else can sign up)*
5. Scroll to **Git Gateway** → click **"Enable Git Gateway"**

---

## STEP 3 — Create Your Admin Account

1. Still in **Site Settings → Identity**, click **"Invite users"**
2. Enter your own email address and send the invite
3. Check your email — click the confirmation link
4. Set your password
5. That's your login for the admin panel — done!

---

## STEP 4 — Log Into Your Admin Panel

1. Go to **yoursite.com/admin**
2. Click **"Login with Netlify Identity"**
3. Enter your email and password
4. You're in!

---

## STEP 5 — Adding a New Portfolio Project

Once you're logged in to the admin panel:

1. Click **"Portfolio Projects"** in the left sidebar
2. Click **"New Portfolio Projects"** (top right)
3. Fill in:
   - **Client / Project Name** — e.g. The Hair Loft
   - **Business Type** — e.g. Hair Salon
   - **Live Website URL** — e.g. https://thehairloft.com
   - **Project Description** — what you built and why it matters
   - **Tags** — click "Add tag" for each one (Custom Design, Gallery, etc.)
   - **Package Used** — which package they bought
   - **Display Order** — 1 shows first, 2 shows second, etc.
4. Click **"Publish"** (top right)
5. Wait about 60 seconds for Netlify to rebuild
6. Refresh your portfolio page — your new project is live! 🎉

---

## STEP 6 — Update the Manifest When You Add a Project

> **Important:** Every time you add a new project through the CMS, you also
> need to add its filename to `_data/projects/manifest.json`.
>
> The CMS creates a file like `the-hair-loft.json` in `_data/projects/`.
> Open `manifest.json` and add that filename to the list:
>
> ```json
> [
>   "nomadic-needlework.json",
>   "the-hair-loft.json"
> ]
> ```
>
> Then save and redeploy. Your new project will appear on the portfolio page.

---

## TIPS

- **Admin URL:** yoursite.com/admin — bookmark this on your phone and laptop
- **Your portfolio page** automatically reads from the project files — no code editing needed
- **Display Order** controls which project shows first. Nomadic Needlework is set to 1.
- **Never delete** `nomadic-needlework.json` or `manifest.json` from your `_data/projects/` folder

---

## IF SOMETHING LOOKS WRONG

- Make sure your folder structure matches exactly what's listed at the top of this guide
- Make sure Git Gateway is enabled (Step 2)
- Make sure you accepted the invite email (Step 3)
- If the portfolio shows "Portfolio Loading..." instead of projects — check that manifest.json lists the correct filenames

---

*Built by Claude for Blackline Web Studio · Jessica Quick*
