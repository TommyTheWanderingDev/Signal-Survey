# Signal Survey — WiFi heat mapper

> ⚠️ **Made by AI.** This tool was designed and written by Claude, an AI model made by Anthropic, guided by a human. Treat its output as an informed estimate, not a calibrated site survey.

A single-file, browser-based WiFi coverage planner for **TP-Link Deco** mesh systems. Draw your home to scale, choose realistic UK wall materials, drop mesh nodes, and see a wall-aware signal heatmap — then let it suggest where to put each Deco.

**Live demo:** `https://<your-username>.github.io/<your-repo>/`
_(fill in after you deploy — see below)_

---

## Features

- **Floor-plan editor** — draw rooms and walls to scale on an infinite grid, with grid + room-to-room snapping.
- **CAD-style editing** — select any wall to set its length, angle, or exact endpoints; select any room to set width, height, and position. Drag handles or type numbers.
- **UK/Scottish wall library** — solid stone (450–600 mm), Victorian solid brick, cavity walls, dense blockwork, Part E party walls, foil-backed insulated plasterboard, Low-E glazing, plus doors and windows.
- **Dual/tri-band heatmap** — a multi-wall path-loss model (COST-231 style) across 2.4 / 5 / 6 GHz.
- **12 Deco models** — from M4R (Wi-Fi 5) to BE85 (Wi-Fi 7), with correct band sets and dedicated-backhaul handling for tri-band units.
- **Optimal placement** — suggests node positions that maximise floor coverage while keeping a viable backhaul link between nodes (node 1 pins to your router).
- **Undo/redo, copy/paste, export/import** — plans save to a local JSON file. No account, no server.

## Privacy

Everything runs **entirely in your browser**. No data is sent anywhere; there is no analytics and no backend. Plans you export are ordinary local files.

## How to deploy to GitHub Pages

There are two easy ways. Pick one.

### Option A — Deploy from a branch (simplest)

1. Create a new GitHub repository and push these files to the `main` branch.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Select branch **`main`** and folder **`/ (root)`**, then **Save**.
5. Wait ~1 minute. Your site appears at `https://<your-username>.github.io/<your-repo>/`.

Because the app is a single `index.html`, that's all it needs.

### Option B — Deploy with GitHub Actions

This repo already includes `.github/workflows/deploy.yml`. To use it:

1. Push these files to `main`.
2. Go to **Settings → Pages → Source** and choose **GitHub Actions**.
3. Every push to `main` will publish automatically.

> The included `.nojekyll` file tells GitHub Pages to serve the files as-is (no Jekyll processing).

## How to use

1. Pick your Deco model (Hardware panel, top right).
2. Choose a wall material, then drag to draw each room. Add doors/windows onto walls.
3. Drop your router/ONT pin, then place Deco nodes — or hit **Suggest positions**.
4. Toggle the band (2.4 / 5 / 6 GHz) to compare coverage.
5. Fine-tune anything by selecting it and typing exact sizes/positions.

## Accuracy & limitations

This is a **planning aid**, not a measured survey. It models direct-path loss through the walls you draw, but it cannot see furniture, appliances, reflections, neighbouring networks, or floor-to-floor loss (it's single-floor). 6 GHz is deliberately modelled as short-range — that's realistic, especially through stone and dense block. For real numbers, walk the house with the TP-Link Deco app and compare.

## License

Released under the **GNU General Public License v3.0** — see [LICENSE](LICENSE). GPLv3 is a copyleft licence: anyone may use, study, share, and modify the software, but any distributed derivative must also be released under GPLv3 and keep its source available. Edit the copyright line in the source header (top of `index.html`) to your name before publishing.
