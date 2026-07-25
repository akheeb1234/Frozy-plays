# Graduation Ludo Club — Holiday Star Arena

A glass-effect, circular-board Ludo game built with React + Vite + Tailwind + Framer Motion.

## Run locally

```bash
npm install
npm run dev
```

## Build

```bash
npm run build
```

This produces a single self-contained `dist/index.html` (via `vite-plugin-singlefile`), plus `dist/images/` for the board texture.

## Deploy to Vercel

A `vercel.json` is included so Vercel knows exactly where to find the build output (this project bundles everything into a single `dist/index.html`, which Vercel doesn't auto-detect by default — that's what causes a `404: NOT_FOUND` if you deploy without it).

1. Go to [vercel.com/new](https://vercel.com/new) and import this repository (or run `vercel` from the project folder with the [Vercel CLI](https://vercel.com/docs/cli)).
2. Vercel will read `vercel.json` automatically:
   - Build command: `npm run build`
   - Output directory: `dist`
3. Deploy. If you already created the project before adding `vercel.json`, go to **Project Settings → General** and confirm **Output Directory** is set to `dist`, then redeploy.

## Deploy to GitHub Pages

This repo includes a ready-to-use GitHub Actions workflow at `.github/workflows/deploy.yml` that builds the app and publishes it to GitHub Pages automatically on every push to `main`.

### One-time setup

1. Push this project to a GitHub repository (see commands below).
2. On GitHub, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **GitHub Actions**.
4. Push to `main` (or run the workflow manually from the **Actions** tab) — the site will be built and deployed automatically.
5. Your game will be live at `https://<your-username>.github.io/<your-repo-name>/`.

### Push this project to GitHub

```bash
git init
git add .
git commit -m "Initial commit: glass-effect Ludo with hop movement animation"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

After the first push, check the **Actions** tab of your repo — the "Deploy to GitHub Pages" workflow will run automatically and publish the site.

## What's new: jump/hop token movement

Tokens now animate by bouncing tile-by-tile across the board (a "jump" motion) instead of gliding in a straight line to their destination. Each hop arcs slightly upward with a subtle scale "squash" and a matching sound effect, and this works for every kind of move: leaving base, moving along the shared track, entering a player's home stretch, reaching the crown (finishing), and being sent back to base after a capture.
