# Ten Minutes to Alpha Centauri

**An interactive relativity explainer. 4.37 light-years away — but only 10 minutes on your watch.**

Inspired by Gregory Gbur's [Relativity: Ten Minutes to Alpha Centauri](https://skullsinthestars.com/2012/09/10/relativity-ten-minutes-to-alpha-centauri/) (Skulls in the Stars, 2012).

## What's inside

A single-page microsite that walks through the problem of interstellar travel from both Newtonian and Einsteinian perspectives:

- **§1 The distance** — a scale ruler for 4.37 light-years.
- **§2 The naïve menu** — travel times at walking pace through Voyager, through project Orion, through fusion drives, right up to the relativistic rocket.
- **§3 The speed dial** — drag a slider from 0 to 0.99999999999c and watch both the Earth clock and ship clock update live, along with Lorentz γ and length contraction.
- **§4 How it feels** — a live canvas of the relativistic starfield, with aberration + Doppler shift baked in. Stars collapse forward into a ring as β approaches 1.
- **§5 The 10-minute trip** — the extreme case made concrete: γ ≈ 230,000, what that costs in energy, why you'd be paste.
- **§6 Share** — LinkedIn / X / copy-link buttons.

## Tech

- One `index.html`. No build step. No dependencies beyond Google Fonts.
- Vanilla JS, canvas 2D for both the background starfield and the aberration viewer.
- GitHub-Pages-ready — just push the repo and enable Pages.

## Run locally

```bash
cd TenMinutesToAlphaCenturi
python3 -m http.server 8080
# http://localhost:8080
```

## Deploy to GitHub Pages

1. Create a new public repo (e.g. `TenMinutesToAlphaCentauri`) on GitHub.
2. Push this directory.
3. Settings → Pages → Source: `Deploy from a branch` → `main` / `/ (root)`.
4. Live at `https://<your-username>.github.io/TenMinutesToAlphaCentauri/`.

## The physics (cheat sheet)

Alpha Centauri is `D = 4.37 ly`. At cruise velocity `v = βc`, Lorentz factor `γ = 1/√(1−β²)`.

- **Earth-frame travel time:** `t = D/v`
- **Proper (ship) time:** `τ = t/γ`
- **Length contraction:** `D' = D/γ` (distance as seen from the ship)
- **For the 10-minute trip:** `τ = 10 min` ⇒ `γ ≈ 230,000` ⇒ `β ≈ 1 − 9.5×10⁻¹²`
- **For the 1g flip-and-brake rocket:** proper acceleration `a = 9.81 m/s²`, flip at midpoint, solve `τ_½ = (c/a)·arccosh(1 + a·D/(2c²))`. Total `τ ≈ 3.58 years`, Earth time `≈ 5.87 years`.

Relativistic aberration (used in the starfield viewer):
```
cos θ' = (cos θ − β) / (1 − β·cos θ)
```
Doppler brightness factor: `D = 1 / [γ(1 − β·cos θ')]`, surface brightness scales ∼`D⁴`.

## License

MIT.
