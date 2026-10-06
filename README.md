# FitQuest

Space-fantasy RPG fitness tracker. Static single-page app, no backend. All data is stored in the browser's localStorage.

## Deploy on GitHub Pages
1. Create a new GitHub repo and upload everything in this folder (keep the `icons/` folder).
2. Repo **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*, Branch = `main`, folder = `/ (root)`.
3. Wait a minute, then open `https://<your-username>.github.io/<repo-name>/`.

## Install on iPhone
1. Open the Pages URL in **Safari**.
2. Tap **Share → Add to Home Screen**.
3. Launch it from the home screen icon; it runs full-screen like an app and works offline.

## Notes
- The home-screen app has its own storage, separate from Safari. Start fresh in the installed app.
- Use **⚙︎ Settings → Backup** to copy your save data, and **Restore** to move it to a new device or browser.
- Updates: push changes to GitHub, then fully close and reopen the app (the service worker is network-first).

## Rank emblems & cosmetics
Your rank badge is the centerpiece of the Base screen (images in `ranks/rank1.png` to `rank6.png`, Recruit to Titan). Spend credits in the **Shop** on cosmetics for it: Aura (glow color), Frame (border style) and Backdrop. Equip them from the **Gear** tab. To swap an emblem, replace the matching PNG in `ranks/` (keep the same file name).

## Game rules (hardcoded in `index.html`)
- Level N → N+1 costs `100 + (N-1)*50` EXP (L1→2 = 100, L2→3 = 150, …). Quest EXP counts toward both level and Rank.
- Base EXP: Easy Run 40, Tempo 55, Easy Long 70, Interval 85, Structured Long 100, Lifting 70, Meditation 40.
- Bonuses: runs +10 EXP/mile; lifting +2/set (max +30); meditation +1 per 5 min (max +20).
- Ranks (total EXP): Recruit 0, Prospect 500, Centurion 1500, Vanguard 4000, Sentinel 9000, Titan 20000.
- Each completed quest: +10 credits, `3 + floor(EXP/50)`% territory, +10 HP.
- Missed planned quest (date passes): −5% territory, −15 HP.
- Random threat events: complete within 20 h for +50 EXP, +10 credits, +5% territory; ignore and lose 10% territory and 20 HP.
