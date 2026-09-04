# Gin Rummy Scorepad

A single-file web app for keeping score in Gin Rummy. Two players, running totals, hand-by-hand history, Gin and Undercut bonuses, target-score win detection. State is saved to `localStorage` so you can close the tab and pick the game up later.

## Files

- `index.html` — the whole app (HTML, CSS and JS in one file). No build step, no dependencies beyond a Google Fonts stylesheet loaded from the browser.

## Deploy to GitHub Pages

1. Create a new GitHub repo (e.g. `gin-rummy-scorepad`).
2. Add `index.html` at the repo root, commit and push:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial scorepad"
   git branch -M main
   git remote add origin https://github.com/<your-username>/gin-rummy-scorepad.git
   git push -u origin main
   ```
3. In the repo on GitHub: **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick the `main` branch and the `/ (root)` folder, then **Save**.
5. Wait ~1 minute. Your app will be live at `https://<your-username>.github.io/gin-rummy-scorepad/`.

## Using it

- On first load, enter both players' names and the target score (default 100), then **Start game**.
- After each hand, type the points each player earned. Blank counts as 0.
- Tap **Gin** (+25) or **Undercut** (+25) on a player's tile if it applies. Bonuses are added on top of the entered points.
- **Enter** in any field records the hand.
- **Undo last hand** rolls back the most recent entry.
- When someone reaches the target, a winner card appears. **New game** clears the scorepad but you can also **Keep viewing** to review the final pad first.

## Customising

The scoring bonuses and the storage key are near the top of the `<script>` block in `index.html` — search for `ginBonus`, `undercutBonus` and `STORAGE_KEY`. Colours are CSS variables at the top of the `<style>` block (`--paper`, `--ink`, `--red`, `--rule`).
