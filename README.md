# Problem Pulse — deploy free in ~10 minutes

A real-time validation board: people post problems they'd pay to solve, upvote live, and join waitlists.
Cost: ₹0. Supabase free tier (database + real-time) + Netlify free hosting.

## 1. Free database (5 min)
1. Sign up at https://supabase.com → **New project** (pick region *South Asia (Mumbai)*).
2. Open **SQL Editor → New query**, paste all of `schema.sql`, click **Run**.
3. Go to **Project Settings → API**. Copy the **Project URL** and the **anon public** key.
4. Paste both into `config.js`.

## 2. Free hosting (2 min) — pick one
- **Netlify Drop (easiest):** go to https://app.netlify.com/drop and drag this whole folder onto the page. You get a live link instantly. Sign in to keep it and rename it (e.g. `problempulse.netlify.app`).
- **GitHub Pages:** create a public repo, upload these files, then Settings → Pages → Deploy from branch `main` / root.
- **Cloudflare Pages / Vercel:** "Upload assets" / "Deploy" with this folder. No build step.

## 3. Check it works
Open the link on your phone and laptop at once. Post a problem on one — it appears on the other within a second, and the header shows "Live · 2 here now".

## 4. Read your results
- Votes & posts: Supabase → **Table Editor** → `problems`, `marks`.
- Emails of people who'd pay: Supabase → Table Editor → `waitlist` (only you can see this).
- Decision rule: a problem with **20 upvotes + 10 "I'd pay"** is a build signal. Interview those waitlist people before writing code.

## Notes
- Without config values the site runs in demo mode (data stays in the visitor's browser).
- Supabase free projects pause after 7 days without traffic; open the dashboard and click **Restore** if that happens.
- Votes use an anonymous browser id, so one person could vote twice from two browsers. Fine for early signal; add sign-in later if you need it.
"# problem-pulse" 
