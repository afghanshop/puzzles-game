# MINDFORGE — A Puzzle Laboratory

An 80-level mind-bending puzzle game across four tiers — Pattern, Logic, Lateral, and Language — built as a single static HTML file (no build step, no dependencies).

## Files

```
.
├── index.html      ← the entire game (HTML + CSS + JS)
├── vercel.json      ← tells Vercel this is a static site
├── package.json      ← lets Vercel detect the project / run it locally
└── .gitignore
```

## Deploy to Vercel

**Option A — Vercel CLI (fastest)**
```bash
npm i -g vercel
cd mindforge-vercel
vercel
```
Follow the prompts (set up and deploy → yes, accept defaults). Vercel will give you a live URL immediately, and `vercel --prod` promotes it to production.

**Option B — GitHub + Vercel dashboard**
1. Push this folder to a new GitHub repo:
   ```bash
   git init
   git add .
   git commit -m "Initial commit — MINDFORGE"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
2. Go to [vercel.com/new](https://vercel.com/new), import the repo.
3. Framework preset: **Other** (it's a static file — Vercel will auto-detect `index.html`).
4. Click **Deploy**. No environment variables or build settings are needed.

**Option C — Drag and drop**
Go to [vercel.com/new](https://vercel.com/new) and drag the whole `mindforge-vercel` folder onto the page. Vercel deploys static folders instantly without any CLI or Git.

## Local preview
```bash
npm install -g serve   # one-time
npm run dev
```
Then open the printed local URL in your browser.

## Notes
- Game state (score, streak, solved levels) lives only in memory for the current browser session — it resets on page reload, by design (no backend/database is wired up).
- Everything — game logic, styling, and puzzle data — lives in `index.html`. To edit puzzles, search for the `PATTERN`, `LOGIC`, `LATERAL`, or `LANGUAGE` arrays near the top of the `<script>` block.
