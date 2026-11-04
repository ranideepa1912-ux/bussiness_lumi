# Lumi — Manual Steps to Complete Submission

This document walks you through every manual step needed to finish the Lumi startup project submission. The PDF and website are already built — you just need to:

1. **Deploy the website to Vercel** (so it has a public URL)
2. **Create the social media accounts** (Instagram, X, LinkedIn)
3. **Record the team introduction video** (1–2 minutes)
4. **Fill in your team details** in the PDF
5. **Upload the final PDF** to your course portal

> Total time required: ~90 minutes (mostly the video).

---

## Prerequisites

Before you start, make sure you have:

- A Vercel account (free at [vercel.com](https://vercel.com)) — sign in with GitHub, GitLab, or email
- The project folder at `/home/z/my-project/` (this contains the full Next.js website)
- A Google/YouTube account for uploading the video
- An email address for social media accounts (can be the same as your team email)
- Your team's names and student IDs ready

---

## Step 1 — Deploy the website to Vercel (15 min)

### 1a. Install the Vercel CLI (one-time setup)

If you don't have Node.js installed, install it first from [nodejs.org](https://nodejs.org) (LTS version).

Then in a terminal:

```bash
npm install -g vercel
```

Verify it works:

```bash
vercel --version
```

### 1b. Log in to Vercel

```bash
vercel login
```

This will prompt you for your email. Follow the link Vercel sends to authenticate.

### 1c. Deploy the project

In a terminal, navigate to the project folder and run:

```bash
cd /home/z/my-project
vercel
```

Vercel will ask a few questions. Accept the defaults (just press Enter) for each:

| Question | Answer |
|----------|--------|
| `Set up and deploy "<folder>"?` | **Y** (Enter) |
| `Which scope should contain your project?` | Pick your personal account |
| `Link to existing project?` | **N** (Enter) |
| `What's your project's name?` | `lumi-study` (or any name you like) |
| `In which directory is your code located?` | `./` (Enter) |
| `Want to modify these settings?` | **N** (Enter) |

Vercel will upload the project and give you a URL like:

```
https://lumi-study-abc123.vercel.app
```

**Open this URL in your browser** to verify the site loads. You should see the Lumi homepage with the purple-to-cyan gradient hero, flashcard demo, pricing, FAQ, and footer with social links.

### 1d. Production deploy

The first deploy is a "preview" deploy. To get a clean production URL, run:

```bash
vercel --prod
```

This redeploys to your production URL. The URL is the same — `https://lumi-study.vercel.app` (or whatever name you chose).

### 1e. Verify the public URL

Open the URL in an **incognito window** in your browser. Also try opening it on **mobile data** (not your home Wi-Fi) — this confirms the site is publicly accessible from anywhere, not just your machine.

The site **must** be publicly accessible — `localhost` URLs will fail the assignment.

### 1f. Update the PDF with your real URL

The PDF currently shows the placeholder URL `https://lumi-study.vercel.app`. If you used a different project name, update the PDF:

1. Open `/home/z/my-project/download/Lumi_Startup_Submission.pdf` in any PDF editor (Adobe Reader, Preview on Mac, or [pdfescape.com](https://www.pdfescape.com) in a browser)
2. Find/replace `https://lumi-study.vercel.app` with your actual Vercel URL
3. Save the updated PDF

Or send me your real Vercel URL and I'll regenerate the PDF for you.

---

## Step 2 — Create the social media accounts (20 min)

The assignment requires **social media business pages** that reflect the Lumi brand. Set up profiles on Instagram, X (Twitter), and LinkedIn.

### 2a. Prepare the brand assets

All the profile images you need are already in the project folder at `/home/z/my-project/public/`:

| File | Use as |
|------|--------|
| `logo-mark.svg` | **Profile picture / avatar** (all platforms) |
| `og-image.svg` | **Cover image / banner** (X, LinkedIn, Facebook) |
| `logo.svg` | In-post logo (light backgrounds) |
| `logo-on-dark.svg` | In-post logo (dark backgrounds) |

To convert SVG to PNG (most platforms require PNG/JPG for upload):

```bash
cd /home/z/my-project
# Avatar (400x400 PNG)
bun -e "const sharp = require('sharp'); sharp(require('fs').readFileSync('public/logo-mark.svg')).resize(400, 400, {fit:'fill'}).flatten({background:{r:15,g:15,b:26,alpha:1}}).png().toFile('download/avatar-400.png');"

# Cover image (1500x500 PNG for X/LinkedIn banners)
bun -e "const sharp = require('sharp'); sharp(require('fs').readFileSync('public/og-image.svg')).resize(1500, 500, {fit:'cover'}).flatten({background:{r:15,g:15,b:26,alpha:1}}).png().toFile('download/banner-1500x500.png');"
```

The PNGs will be saved to `/home/z/my-project/download/`.

### 2b. Instagram business account

1. Open the Instagram app on your phone (or [instagram.com](https://instagram.com) on desktop)
2. Sign up with your team email — use `lumistudy@gmail.com` (or whatever you control) as the username if available, otherwise `lumi.study` or `lumi.study.app`
3. Set account type to **Professional / Business** (Settings → Account type → Switch to professional account → Business)
4. **Profile picture**: upload `avatar-400.png` (the Lumi icon mark)
5. **Name field**: `Lumi — AI Study Buddy`
6. **Bio**: `Your AI study buddy. Learn faster, cram less. Try Lumi free → lumi-study.vercel.app`
7. **Link in bio**: your Vercel URL
8. **Category**: Education / E-learning
9. **Pinned post** (after first post): the 60-second flashcard demo

### 2c. X / Twitter business account

1. Go to [twitter.com](https://twitter.com) → Sign up
2. Create account with team email, username `@lumistudy` (or `@lumi_study` if taken)
3. **Profile picture**: upload `avatar-400.png`
4. **Header / banner**: upload `banner-1500x500.png`
5. **Bio**: `Your AI study buddy. Learn faster, cram less. Built for university students. → lumi-study.vercel.app`
6. **Location**: `Global` or your city
7. **Website**: your Vercel URL

### 2d. LinkedIn company page

> Requires a personal LinkedIn account. If you don't have one, create one first.

1. Go to [linkedin.com/company/setup](https://www.linkedin.com/company/setup)
2. Page name: `Lumi`
3. URL: `linkedin.com/company/lumistudy` (the slug must be unique — try `lumistudy`, `lumi-study`, or `lumi-study-app`)
4. Industry: `E-Learning Providers` (or `Software Development`)
5. Company size: `1-10 employees`
6. Company type: `Private`
7. **Logo**: upload `avatar-400.png`
8. **Cover image**: upload `banner-1500x500.png` (LinkedIn uses 1128x191 — the same image will be cropped, that's fine)
9. **Tagline**: `Your AI study buddy for university students.`
10. **Description**: copy the startup overview from the PDF (the Solution paragraph)
11. **Website**: your Vercel URL

### 2e. Update the PDF with your social URLs

Once accounts are created, open the PDF and update page 8 ("Social Media Presence") with the real URLs:

- Replace `instagram.com/lumistudy` with your actual Instagram URL
- Replace `twitter.com/lumistudy` with your actual X URL
- Replace `linkedin.com/company/lumistudy` with your actual LinkedIn URL

---

## Step 3 — Record the team introduction video (30–45 min)

This is the most time-consuming manual step. The video must be 1–2 minutes long and include every team member.

### 3a. Preparation

- **Quiet room** with no echo, no background noise
- **Front lighting**: position yourself facing a window or lamp (not behind you)
- **Camera**: phone on a tripod or laptop webcam, eye-level
- **Screen recording tool**:
  - macOS: QuickTime Player → File → New Screen Recording
  - Windows: built-in Game Bar (Win+G) or [OBS Studio](https://obsproject.com) (free)
  - Browser tab: [loom.com](https://www.loom.com) (free, 5-min limit)

### 3b. Record each team member intro

Have each member say, on camera, one at a time:

> "Hi, I'm **[Full Name]**, student ID **[ID]**. My role on Lumi was **[role like 'founder and CEO']**. My key contributions were **[2-3 specific things like 'product vision, market research, the business model']**."

Aim for ~13 seconds per member.

### 3c. Record the screen demo (15–20 seconds)

1. Open your deployed Vercel URL in a browser at 1920×1080
2. Screen-record while you:
   - Scroll through the hero section (3s)
   - Click the **flashcard demo** to flip it (3s)
   - Scroll to **Pricing** and toggle Monthly → Yearly (3s)
   - Scroll to **FAQ** and open one question (3s)
   - Scroll to the bottom to show the **footer with social links** (3s)
3. Voiceover during the screen demo:

   > "Here's the live site — fully responsive, interactive, deployed on Vercel."

### 3d. Record the hook and closing

- **Hook** (5–10s, before team intros): `Hey, we're the team behind Lumi — your AI study buddy. Let me show you what we built.`
- **Closing** (5–10s, after demo): `That's Lumi. Try it free at lumi-study.vercel.app. Thanks for watching.`

### 3e. Edit and export

Use any free editor:
- **macOS**: iMovie (free)
- **Windows**: Clipchamp (free, built into Windows 11) or DaVinci Resolve (free)
- **Online**: [capcut.com](https://www.capcut.com) (free, web-based)

Cut together: hook → team intros → screen demo → closing.

Add the Lumi logo at the start and end (use `/home/z/my-project/public/logo-on-dark.svg` on a dark background).

Export at **1080p MP4**, H.264. Total length must be 60–120 seconds.

### 3f. Upload to YouTube as Unlisted

1. Go to [youtube.com/upload](https://www.youtube.com/upload)
2. Sign in with your Google account
3. Upload the MP4
4. Title: `Lumi — Team Introduction`
5. Description: `Team introduction video for the Lumi startup project submission. Members: [names]. Deployed site: [your Vercel URL]`
6. **Visibility**: select **Unlisted** (anyone with the link can view, but it won't appear in YouTube search)
7. Click **Publish**
8. Copy the YouTube URL (looks like `https://youtu.be/abc123XYZ`)

### 3g. Alternative: Google Drive

If you don't have a YouTube account, upload to Google Drive:
1. Upload the MP4 to your Google Drive
2. Right-click → Share → set to "Anyone with the link"
3. Copy the share link

### 3h. Update the PDF with the video URL

Open the PDF and find page 9 ("Team Introduction Video"). Replace the placeholder text `[ Add YouTube unlisted link or Google Drive shareable link here after recording ]` with your actual YouTube or Drive URL.

---

## Step 4 — Fill in your team details (5 min)

Open the PDF (`/home/z/my-project/download/Lumi_Startup_Submission.pdf`) in any PDF editor and update:

### 4a. Cover page (page 1)

Update the **TEAM** block at the bottom:

```
[Your Name] — [Student ID] — Founder & CEO
[Member 2] — [Student ID] — Product & Engineering
[Member 3] — [Student ID] — Brand & Marketing
```

Replace each placeholder with the actual name and student ID.

### 4b. Team Members table (page 2)

Update the **Name** and **Student ID** columns in the table:

| Name | Student ID | Role | Key Contributions |
|------|------------|------|-------------------|
| (your actual name) | (your actual ID) | Founder & CEO | (keep as-is or customize) |
| (member 2 actual name) | (member 2 actual ID) | Product & Engineering | (keep as-is or customize) |
| (member 3 actual name) | (member 3 actual ID) | Brand & Marketing | (keep as-is or customize) |

If this is an **individual submission**, delete rows 2 and 3, leaving only your row.

### 4c. Solo submission note

If you're submitting solo, also update the muted note below the table:

> "If submitted as an individual project, only the first row applies..."

You can leave this as-is, or replace it with:

> "Submitted as an individual project."

---

## Step 5 — Final checklist and upload (10 min)

Before uploading the final PDF to your course's eFlow portal, verify each item:

- [ ] **Team member names + student IDs** are filled in on the cover and Team Members table
- [ ] **Deployed website URL** is filled in (cover page + page 3 + page 10 row 3)
- [ ] **Website is publicly accessible** — open the URL in an incognito window on a different network (mobile data) and confirm it loads
- [ ] **Logo + brand guidelines** are present (pages 4–7) — no action needed, already done
- [ ] **Social media URLs** are filled in on page 8 — Instagram, X, LinkedIn
- [ ] **Social media profiles** use the Lumi avatar (logo mark) and have the brand bio
- [ ] **Video link** is filled in on page 9 — YouTube unlisted or Google Drive link
- [ ] **Video** is 1–2 minutes long and includes every team member
- [ ] **Video** shows the screen demo of the deployed site
- [ ] **PDF opens correctly** — test in Adobe Reader or browser
- [ ] **No leftover placeholders** like `[Your Name]`, `[Student ID]`, `[Add YouTube link]`

Once all checked, upload `Lumi_Startup_Submission.pdf` to your course's eFlow portal.

---

## Troubleshooting

### "My Vercel deploy shows a 404"

Make sure you ran `vercel --prod` (not just `vercel`). The first `vercel` command creates a preview deployment that's only accessible to you. `vercel --prod` creates the public production deployment.

### "The website looks broken on mobile"

The site is built mobile-first and tested at iPhone 14 viewport (390×844). If something looks off on a specific device, try:
1. Hard-refresh the page (Ctrl+Shift+R / Cmd+Shift+R) — Vercel's CDN may be serving a cached version
2. Wait 60 seconds and reload — Vercel propagates deploys globally within a minute

### "agent-browser can't take a screenshot"

If you need to take a fresh screenshot of the website for any reason (e.g. to update the PDF cover image), use:
```bash
cd /home/z/my-project
agent-browser set viewport 1440 900
agent-browser open http://localhost:3000
agent-browser wait 2000
agent-browser screenshot scripts/pdf-assets/website-hero.png
agent-browser close
```
Then re-run `python3 scripts/generate_pdf.py` to regenerate the PDF with the new screenshot.

### "I want to regenerate the PDF after editing content"

After editing the script at `/home/z/my-project/scripts/generate_pdf.py`:
```bash
cd /home/z/my-project
cp scripts/pdf-assets/website-hero.png /tmp/render/lumi-hero.png
python3 scripts/generate_pdf.py
```
The PDF will be regenerated at `/home/z/my-project/download/Lumi_Startup_Submission.pdf`.

### "The Vercel URL changed and I need to update the PDF"

The URL appears in three places in the PDF:
- Cover page (DEPLOYED LINK field)
- Page 3 (Live URL heading)
- Page 10 (Submission checklist row 3)

Easiest fix: edit the script to use a single `VERCEL_URL` variable at the top, then regenerate:

```python
# Add at the top of generate_pdf.py, after imports:
VERCEL_URL = "https://your-actual-url.vercel.app"
```

Then replace all hardcoded `https://lumi-study.vercel.app` references with `{VERCEL_URL}` (Python f-string).

---

## Files delivered

All final deliverables are in `/home/z/my-project/download/`:

| File | What it is |
|------|------------|
| `Lumi_Startup_Submission.pdf` | The final submission PDF (upload this to your course portal) |

Brand assets you may also want to keep (already in `/home/z/my-project/public/`):

| File | What it is |
|------|------------|
| `logo.svg` | Primary logo (horizontal lockup) for light backgrounds |
| `logo-on-dark.svg` | Logo with white wordmark for dark backgrounds |
| `logo-mark.svg` | Icon mark only (for avatars, favicons) |
| `og-image.svg` | Social share preview image (1200×630) |
| `favicon.svg` | Browser tab icon |

The full website source code is in `/home/z/my-project/` (Next.js 16 project). You can `cd` into it, run `bun install` if needed, then `bun run dev` to start the dev server locally.

---

## Quick summary — what to do right now

1. `cd /home/z/my-project && vercel --prod` — deploy
2. Open the Vercel URL in your browser to confirm it works
3. Create Instagram, X, LinkedIn accounts using the avatars in `download/avatar-400.png` and `download/banner-1500x500.png`
4. Record the 1–2 min team video (script in PDF page 9)
5. Upload video to YouTube as Unlisted, copy the link
6. Open the PDF and edit: cover, page 2 (team), page 3 (URL), page 8 (social URLs), page 9 (video link)
7. Upload the edited PDF to your course's eFlow portal

That's it — you're done. Good luck with the submission! 🎓
