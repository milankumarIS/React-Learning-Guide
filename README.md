# React Engineering Learning Guide 🚀

> A structured, hands-on 27-step React curriculum designed for software engineering interns. From foundational mental models to production-grade architecture.

---

## 📌 Architecture & How Modules Are Accessed

The project uses a clean, zero-build static architecture that works out-of-the-box locally, on GitHub, and on Netlify.

```
React Learning Guide/
├── index.html                   # Central Dashboard & Module Portal
├── netlify.toml                 # Netlify routing, redirects & headers
├── .gitignore                   # Ignored files for clean version control
├── README.md                    # Project documentation
└── modules/
    ├── react-learning-step-01-fundamentals.html   # Step 01: Core Fundamentals
    ├── react-learning-step-02-state-and-logic.html # Step 02: (Drop your next files here)
    └── ...
```

### 1. The Portal Hub (`index.html`)
- Serves as the landing page when anyone visits your site (e.g. `https://your-site.netlify.app/`).
- Features a **27-step interactive roadmap**, search bar, phase filters, and live progress indicators.
- Automatically connects to modules in the `modules/` directory.

### 2. Individual Modules (`modules/`)
- Each module is a self-contained learning canvas with layman analogies, deep conceptual breakdowns, editable code snippets, and self-check questions.
- Built-in **navigation bar** at the top and bottom allows learners to jump back to the central portal or progress to the next step.
- Concept checklist progress is saved directly in browser `localStorage`.

---

## 🛠️ How to Add Future Steps (e.g. Step 02, Step 03)

Adding new modules takes **less than 1 minute**:

1. **Create the file in `modules/`**:
   Follow the naming convention:
   ```
   modules/react-learning-step-02-state-and-logic.html
   ```
2. **Include the Top Navigation Bar**:
   Inside your `<header>`, add the navigation bar to allow interns to return to the portal:
   ```html
   <nav class="top-nav">
     <a href="../index.html" class="back-btn">← All Modules Portal</a>
     <span class="nav-meta">React Intern Canvas • Step 2 of 27</span>
   </nav>
   ```
3. **Commit & Push to GitHub**:
   ```bash
   git add .
   git commit -m "Add Step 02: State & Component Logic"
   git push
   ```
4. **Automatic Deployment**:
   Netlify will detect the new commit and rebuild the live site within seconds!

---

## 🌐 Deploying to Netlify

### Option A: Connected with GitHub (Recommended — Continuous Deployment)
1. Push this repository to GitHub (see GitHub Setup below).
2. Log into [Netlify](https://app.netlify.com).
3. Click **"Add new site"** → **"Import an existing project"**.
4. Select **GitHub** and choose your `react-learning-guide` repository.
5. In the build settings:
   - **Base directory**: (Leave blank)
   - **Build command**: (Leave blank — no build step needed)
   - **Publish directory**: `.` (or leave default root)
6. Click **Deploy Site**.
7. *Every time you push a new module to GitHub, Netlify automatically deploys it!*

### Option B: Netlify CLI
```bash
npx netlify-cli deploy --prod --dir .
```

---

## 🐙 Git & GitHub Setup

To initialize and push this project to your GitHub account:

```bash
# 1. Initialize git (if not already initialized)
git init

# 2. Add all files and make the initial commit
git add .
git commit -m "Initial commit: React Learning Guide portal and Step 01 module"

# 3. Create a GitHub repository using GitHub CLI:
gh repo create react-learning-guide --public --source=. --remote=origin --push

# Or connect to an existing GitHub repository manually:
# git remote add origin https://github.com/<your-username>/react-learning-guide.git
# git branch -M main
# git push -u origin main
```

---

## 🧭 Curriculum Overview (27 Steps)

- **Phase 1: Fundamentals (Steps 1–5)**: React mental models, JSX, Virtual DOM, State & Logic, Hooks & Effects, Advanced Hooks, Forms.
- **Phase 2: Hooks & State Mastery (Steps 6–10)**: Context API, Component Composition, Async Data, React Router, Error Boundaries.
- **Phase 3: Component Architecture (Steps 11–16)**: Zustand/Redux, TanStack Query, Styling Strategies, Performance Profiling, Accessibility, Vitest & Testing Library.
- **Phase 4: Advanced & Modern React (Steps 17–22)**: TypeScript with React, Framer Motion, Security (XSS/Auth), Next.js & Server Components, Fullstack Auth, Folder Architecture.
- **Phase 5: Production & Capstones (Steps 23–27)**: CI/CD Pipelines, Analytics Dashboard Capstone, E-Commerce Storefront Capstone, Production Monitoring & Sentry, Senior System Design Interview Mastery.
