## Vercel Deployment Guide

This project template is set up to work smoothly with Vercel for deploying React + Vite front-end applications. This document explains:

- **What this template already provides for Vercel**
- **What you still need to provide yourself**
- **Step-by-step deployment instructions**
- **Baseline install instructions for Node, npm, and Vercel**

---

## 1. What this template already provides

- **Frontend structure**
  - `client/` directory containing a **Vite + React + TypeScript** app.
  - Standard `npm` scripts in `client/package.json`:
    - **`npm run dev`** – local development server.
    - **`npm run build`** – production build.
    - **`npm run preview`** – preview built app locally.

- **Vercel-compatible build setup**
  - Vite defaults that Vercel understands out of the box.
  - Production builds output to `client/dist/`.
  - No machine-specific paths or secrets are hard-coded.

- **Repository layout**
  - Repo root (this folder)
  - `client/` – actual front-end app that Vercel should build and deploy.

When you create a new repo from this template, Vercel can deploy it by pointing the **Root Directory** at `client`.

---

## 2. What you still need to provide

These items are **not** part of the template and must be supplied by each user:

- **Node.js and npm installation**
  - You must have a working Node.js LTS (for example Node 18+ or 20+/24+) installed on your machine.
  - To verify they’re available in your terminal, open a new terminal window and run:
    ```bash
    node -v
    npm -v
    ```
    If both commands print version numbers (and not “command not found” or an error), Node and npm are correctly installed and available. If either command fails, follow the **“4.1. Install Node.js and npm (Windows)”** instructions below (or the equivalent for your OS) before continuing.

- **Your own Vercel account and project settings**
  - A personal (or team) account on Vercel.
  - A Vercel project connected to **your** GitHub repository created from this template.
  - Any framework/project settings inside Vercel (Root Directory, build command, etc.).

- **Secrets / environment variables (if needed)**
  - Any API keys, tokens, or other sensitive values needed by your app.
  - These should be set in **Vercel → Project → Settings → Environment Variables**, not committed to the repo.

---

## 3. How to deploy this template on Vercel

Follow these steps **after** you have:
1. Created a GitHub repo from this template.
2. Pushed your code to GitHub.

### 3.1. Prepare the project locally

In your terminal:

```bash
cd /path/to/your/repo          # e.g. C:/Users/<you>/Github/GameHub
npm install                    # if you have a package.json at the root and want tooling there (optional)

cd client
npm install                    # install frontend dependencies
npm run dev                    # optional: confirm it runs locally
```

If `npm run dev` works and you can open the local URL in a browser (usually `http://localhost:5173`), you are ready to deploy.

### 3.2. Connect GitHub repo to Vercel

1. Go to `https://vercel.com` and log in.
2. Click **“Add New…” → “Project”**.
3. Choose **“Import Git Repository”**.
4. Select the GitHub repo you created from this template.

### 3.3. Configure Vercel project settings

On the Vercel project setup screen:

- **Root Directory**
  - Click **“Edit”** next to the root directory (if prompted).
  - Set it to: **`client`**
  - This tells Vercel that your actual front-end app lives in the `client` folder.

- **Framework Preset**
  - Vercel should auto-detect **Vite** or **React**.
  - If not, choose **Vite** manually.

- **Build & Output Settings** (normally auto-detected)
  - **Build Command**: `npm run build`
  - **Install Command**: `npm install`
  - **Output Directory**: `dist`

- **Environment Variables (if needed)**
  - If your app uses runtime configuration (API keys, URLs, etc.), add them here.
  - Example:
    - `VITE_API_BASE_URL = https://api.example.com`

When everything looks correct, click **“Deploy”**.

### 3.4. Verify the deployment

Once the build finishes:

1. Vercel will give you a **preview URL**.
2. Open it in your browser to confirm the app loads.
3. You can later assign a custom domain in **Project → Settings → Domains**.

---

## 4. Baseline installation instructions

This section gives minimal, practical instructions for setting up prerequisites on a fresh machine.

### 4.1. Install Node.js and npm (Windows)

1. Go to `https://nodejs.org/en`.
2. Download the **LTS (Long-Term Support)** installer for Windows (64-bit).
3. Run the installer:
   - Keep defaults.
   - Ensure **“Add to PATH”** remains checked.
4. After installation, open a new terminal and verify:

   ```bash
   node -v
   npm -v
   ```

   Both commands should print version numbers (e.g. `v24.14.0`, `11.x.x`).

> On macOS or Linux, you can also use a version manager like `nvm`, but the essential requirement is the same: `node` and `npm` must work in your shell.

### 4.2. Install Git

1. Go to `https://git-scm.com/downloads`.
2. Download and run the installer for your OS.
3. After installation, verify:

   ```bash
   git --version
   ```

   You should see a version number.

### 4.3. Set up a Vercel account

1. Visit `https://vercel.com`.
2. Sign up with **GitHub** (recommended) or another login method.
3. Authorize Vercel to access your GitHub repositories when prompted.

### 4.4. (Optional) Install the Vercel CLI

The CLI is optional but useful if you like deploying from the terminal.

```bash
npm install -g vercel
vercel login
```

Follow the interactive prompt in your browser to log in. After that you can run:

```bash
cd /path/to/your/repo/client
vercel
```

to deploy directly from the terminal (this is an alternative to the Git-based flow described earlier).

---

## 5. Quick checklist for new users

For any new project created from this template:

1. **Clone the repo from GitHub.**
2. **Ensure Node.js and npm are installed** (see section 4.1).
3. In the repo root:
   - Optionally run `npm install` if you add root tooling.
4. In `client/`:
   - Run `npm install`.
   - Run `npm run dev` to verify locally.
5. On Vercel:
   - Create a project from your GitHub repo.
   - Set **Root Directory = `client`**.
   - Ensure **Build Command = `npm run build`**, **Output Directory = `dist`**.
   - Add any required **environment variables**.
6. Click **Deploy** and open the generated URL.

With these steps, this template should be reusable for you (and others) as a straightforward starting point for Vercel-hosted front-end projects.

