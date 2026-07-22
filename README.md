# RotaryWorks | Expert Mazda Rotary Engine Mechanics Landing Page

**RotaryWorks** is a modern, high-performance, dark-themed landing page designed for a specialized Mazda Wankel/rotary engine mechanics workshop located in Santiago, Chile. Built using **Astro v5** and modern CSS custom properties, it delivers an immersive experience with dynamic animations, rotor-inspired visuals, service showcases, customer reviews, interactive FAQ, and direct booking CTA options.

---

## 🌟 Key Features & Sections

- **Hero Section**: Dynamic spinning Wankel rotor graphics, key stats counter, dark aesthetic imagery (`rx7-fd.png`), and primary call-to-action buttons.
- **Services Showcase**: Detailed breakdown of workshop services (Engine Rebuilds, Porting, ECU Tuning, Apex Seal Upgrades, Maintenance, Performance Upgrades).
- **Vehicles & Engine Models**: Interactive cards highlighting Rotary platforms (13B-REW, 13B-DSP/Renesis, 20B-REW 3-Rotor, 12A).
- **Interactive Engine Specs & Diagnostics**: Real-time compression calculator tool allowing owners to check rotor compression values.
- **About Us & Workshop Philosophy**: Story, craftsmanship values, and technical expertise of the shop.
- **Customer Testimonials**: Reviews and ratings from Mazda RX-7 & RX-8 owners.
- **FAQ Accordion**: Interactive answers to common rotary engine maintenance and reliability questions.
- **Location & Booking Contact Form**: Interactive location details, contact info, and booking form.

---

## 🏗️ Architecture & Technology Stack

```text
       ┌────────────────────────────────────────────────────────┐
       │                       Astro v5                         │
       │     (Static Site Generation / Zero-JS by Default)      │
       └───────────────────────────┬────────────────────────────┘
                                   │
         ┌─────────────────────────┼─────────────────────────┐
         ▼                         ▼                         ▼
  ┌──────────────┐         ┌──────────────┐         ┌──────────────┐
  │ Astro Layout │         │ Astro Pages  │         │ Global CSS   │
  │ Layout.astro │ ──────> │ index.astro  │ <─────> │  global.css  │
  └──────────────┘         └──────────────┘         └──────────────┘
                                   │
                                   ▼
                       ┌───────────────────────┐
                       │  Static Build Output  │
                       │       (./dist)        │
                       └───────────┬───────────┘
                                   │
                                   ▼
                       ┌───────────────────────┐
                       │ GitHub Actions CI/CD  │
                       │  (Deploy to Pages)    │
                       └───────────────────────┘
```

### Core Technologies
- **Framework**: [Astro 5](https://astro.build/) (Static Site Generator delivering zero client-side JavaScript overhead by default for UI structure).
- **Styling**: Modern Vanilla CSS with custom properties (CSS variables), CSS grid, flexbox, glassmorphism UI, gradient overlays, and custom keyframe animations (`@keyframes`).
- **Icons & Visuals**: Inline vector SVGs and optimized asset delivery via `import.meta.env.BASE_URL` compatibility.
- **Deployment & CI/CD**: Automated GitHub Actions workflow (`.github/workflows/deploy.yml`) utilizing official `withastro/action` to build and publish to GitHub Pages.

---

## 📁 Project Directory Structure

```text
RotaryLanding/
├── .github/
│   └── workflows/
│       └── deploy.yml         # CI/CD pipeline for GitHub Pages deployment
├── public/                    # Static public assets (images, favicon, etc.)
│   └── rx7-fd.png             # Hero section background image
├── src/
│   ├── layouts/
│   │   └── Layout.astro       # Root HTML shell, metadata, OpenGraph tags, Google Fonts
│   ├── pages/
│   │   └── index.astro        # Main single-page landing page containing all sections & logic
│   └── styles/
│       └── global.css         # Complete CSS design system, typography, animations & utilities
├── astro.config.mjs           # Astro configuration (base path, site URL, GitHub Pages config)
├── package.json               # Node.js dependencies & scripts (Node >= 22.12.0)
└── tsconfig.json              # TypeScript configuration for Astro
```

---

## 🧞 Available Scripts & Commands

All commands are executed from the project root:

| Command | Action |
| :--- | :--- |
| `npm install` | Installs project dependencies |
| `npm run dev` | Starts local development server at `http://localhost:4321` |
| `npm run build` | Builds static production files to the `./dist/` folder |
| `npm run preview` | Previews the production build locally before deployment |
| `npm run astro ...` | Runs Astro CLI commands (e.g. `astro check`, `astro add`) |

---

## 🚀 Deployment Pipeline

The project is configured for automated deployment to **GitHub Pages**:
- **Triggers**: Pushes to the `main` branch or manual invocation (`workflow_dispatch`).
- **Node Requirement**: Node.js `22.12.0` or higher.
- **Workflow**: Automated build via `@withastro/action@v3` and deployment via `@actions/deploy-pages@v4`.

