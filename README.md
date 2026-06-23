# The Signal
### A weekly AI & design culture resource for BA Graphic & Media Design students

---

## What's in this folder

| File | Purpose |
|------|---------|
| `index.html` | Student-facing page — this is what you share with students |
| `curator.html` | Your private approval interface — password protected |
| `content.json` | The data file both pages read from — updated when you publish |
| `README.md` | This file |

---

## First-time setup

### Step 1 — Create a GitHub repository

1. Go to [github.com](https://github.com) and sign in
2. Click **+** → **New repository**
3. Name it `the-signal` (or anything you like)
4. Set visibility to **Public** (required for free GitHub Pages hosting)
5. Click **Create repository**

### Step 2 — Upload these files

1. On your new repository page, click **uploading an existing file**
2. Drag all four files (`index.html`, `curator.html`, `content.json`, `README.md`) into the upload area
3. Click **Commit changes**

### Step 3 — Enable GitHub Pages

1. Go to your repository **Settings** → **Pages** (left sidebar)
2. Under **Source**, select **Deploy from a branch**
3. Branch: `main`, Folder: `/ (root)`
4. Click **Save**
5. Wait 1–2 minutes. Your site will appear at:
   `https://YOUR-USERNAME.github.io/the-signal/`

Your student page is now live at that URL.  
Your curator page is at: `https://YOUR-USERNAME.github.io/the-signal/curator.html`

---

## Curator setup (one-time)

Visit your curator page and go to **Settings** (tab in the navigation).

### Anthropic API Key
1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up or sign in → **API Keys** → **Create Key**
3. Copy the key (starts with `sk-ant-`) and paste it into Settings

### GitHub Personal Access Token
1. Go to GitHub → your profile photo → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
2. Click **Generate new token (classic)**
3. Give it a name like `the-signal`
4. Check the **repo** scope (full control of private repositories)
5. Click **Generate token**
6. Copy the token (starts with `ghp_`) and paste it into Settings
7. Fill in your **Repository** as `your-username/the-signal`
8. Branch: `main`

Click **Save settings**.

---

## Weekly workflow

1. Open `curator.html` and log in (default password: `signal2024`)
2. Click **↻ Fetch this week** — Claude will find ~12 recent stories across the three strands (takes 20–30 seconds)
3. Review each item: click **Approve** to keep it, **Remove** to discard
4. When happy, click **Publish approved →**
5. The student page updates within 1–2 minutes

Your draft is auto-saved in the browser between sessions, so you can come back to it.

---

## Changing the password

Go to **Settings** in the curator interface → **Curator Password** section. The password is stored in your browser's local storage.

> Note: this is a lightweight password for convenience, not high-security authentication. Don't reuse a password you use elsewhere.

---

## Customising the design

All visual decisions live in the `:root { }` block at the top of the `<style>` section in both `index.html` and `curator.html`. The variables are:

```css
:root {
  --font-sans:     /* body typeface */
  --font-mono:     /* monospace typeface for labels, dates, codes */

  --c-ink:         /* primary text colour */
  --c-paper:       /* page background */
  --c-mid:         /* secondary / muted text */
  --c-rule:        /* divider line colour */

  --c-strand-a:    /* AI & Industry accent colour */
  --c-strand-b:    /* Environmental cost accent colour */
  --c-strand-c:    /* Creative opposition accent colour */

  --max-width:     /* maximum page width */
  --page-padding:  /* horizontal page padding */
}
```

To change a font, replace the Google Fonts `<link>` tag with a different font and update the variable. To change the colour scheme, edit the hex values.

---

## Embedding in Moodle

To embed the student page in Moodle:

1. In your Moodle course, add a **Text and media area** resource
2. Switch to HTML source mode
3. Paste: `<iframe src="https://YOUR-USERNAME.github.io/the-signal/" width="100%" height="700" frameborder="0" style="border:none;"></iframe>`
4. Save

Adjust the `height` value to suit your layout.

---

## Renaming the strands

Strand names appear in the navigation tabs in both HTML files. Search for `AI &amp; industry`, `Environmental cost`, and `Creative opposition` and replace with your preferred labels.

---

## Troubleshooting

**Fetch fails with an API error**  
Check your Anthropic API key in Settings. Make sure you have credit on your Anthropic account.

**Publish fails with a 404 or 401**  
Check your GitHub token has the `repo` scope and hasn't expired. Check the repository name is exactly `username/repo-name`.

**Student page shows "Content unavailable"**  
The `content.json` file may be missing from the repository. Re-upload it via the GitHub website.

**Changes don't appear immediately**  
GitHub Pages caches aggressively. Wait 2–3 minutes and do a hard refresh (Ctrl+Shift+R / Cmd+Shift+R).
