# Frontend Template (Vite + React + TS)

A reusable frontend template using **Vite 7**, **React**, **TypeScript**, and **Tailwind CSS 4**, designed for quick setup and easy deployment to Vercel. Use it as a starting point for new projects rather than a finished app.

## Quick Start

1. Pick a folder to host your GitHub projects, then clone your repo:
   - Example parent folder: `C:/Users/<you>/Github`
   - Open a terminal and `cd` into that parent folder.
   - Clone your repo (use the repo name you chose on GitHub):
     - `git clone https://github.com/<your-username>/<project-name>.git`
     - `cd <project-name>`
   - Note: `<project-name>` can be anything you want (it’s whatever you named the repo on GitHub).
   - Replace placeholders like `<your-username>` and `<project-name>` with your own values (do not include the `<` or `>` characters).
2. Create the `client` app (only if needed):
   - This template includes a `client/` folder already.
   - If your cloned repo already has `client/`, skip this step.
   - If you do *not* have `client/`, create it with:
     - `npm create vite@7 client -- --template react-ts`
3. Install and run the frontend:
   - `cd client`
   - `npm install`
   - `npm run dev` → open `http://localhost:5173`
4. Commit and push your changes:
   - `git add .`
   - `git commit -m "Initial setup (Vite + React + TS)"`
   - `git push origin main`
5. For detailed repo setup and deployment instructions, see:
   - `readme/reposetup.md`
   - `readme/verceldeploy.md`

## Included Packages

This template’s packages are split between the app in `client/` and some root-level tooling.

### Client (runtime) dependencies (`client/package.json`)

- `react`
- `react-dom`
- `react-router-dom`
- `tailwindcss`
- `@tailwindcss/vite`

### Client (dev/build tooling) (`client/package.json`)

- `vite`
- `@vitejs/plugin-react`
- `typescript`
- `eslint`
- `@typescript-eslint/parser`
- `@typescript-eslint/eslint-plugin`
- `@types/react`
- `@types/react-dom`

### Template root tooling (linting/formatting) (`package.json`)

- `eslint`
- `@typescript-eslint/parser`
- `@typescript-eslint/eslint-plugin`
- `prettier`
- `stylelint`
- `markuplint`
- `typescript`

Exact versions are in `client/package.json` and the root `package.json`.
