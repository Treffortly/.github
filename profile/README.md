# Treffortly – AI-Powered Gamified Productivity Ecosystem

> Productivity turned into an XP-driven game.  
> **Web (Next.js 15 + Tailwind v3) · Node + GraphQL API · Android & Desktop companions · AI micro-services**

---

## 📂 Repository Layout ­(Poly-Repo)

| Repo | Visibility | Purpose | Tech |
|------|------------|---------|------|
| **`webapp-client`** | Private | Main web UI (dashboard, tasks, calendar, analytics) | Next.js 15 · React · Tailwind v3 · Apollo/URQL |
| **`webapp-api`** | Private | GraphQL back-end & WebSocket server | Node.js · Apollo Server · Prisma · PostgreSQL (Neon) |
| **`mobile-app`** | Private | Native Android client | Kotlin · Jetpack Compose · Apollo Kotlin |
| **`desktop-app`** | Private | Cross-platform desktop client | C++20 · Qt 6 · gRPC/GraphQL |
| **`website`** | Private | Marketing & docs site | Next.js (static export) |

> 💡 Shared code (TypeScript types, GraphQL schema artefacts, ESLint configs) is published as **GitHub Packages**  
> (e.g. `@treffortly/shared-types`) and consumed by each repo.

---

## ✨ Core Features

- **Task & Habit Management** with due dates, subtasks, reminders
- **Gamification**: XP, level-ups, badges, adaptive reward curve
- **AI Layer**: LLM chat assistant, zero-shot task tagging, daily brief, burn-out forecasting
- **Integrations**: GitHub commits, Spotify “Now Playing”, Slack/WhatsApp notifications, Google Calendar sync
- **Collaboration**: Team boards, live chat, real-time leaderboards
- **Customization**: Drag-and-drop dashboard editor, dark/light themes, indigo accent

---

## 🏗️ Tech Highlights

| Layer | Stack |
|-------|-------|
| Front-end (Web) | Next.js 15 · RSC · TailwindCSS v4 · Framer Motion |
| API & Realtime | Node.js · Apollo GraphQL · Prisma · Redis + Socket.io |
| Auth & Billing | Auth0 · Stripe |
| AI Micro-services | Python FastAPI (Ollama / HF models) · Java Rules Engine |
| Mobile | Kotlin + Jetpack Compose + Apollo Kotlin |
| Desktop | Qt 6 (QML) + CMake + gRPC-C++ |
| DevOps | GitHub Actions CI/CD per repo · Vercel deploy for web / api |

---

## 🔌 AI Model-to-Feature Map

| Task Type | Model Suggestion | Treffortly Module |
|-----------|------------------|-------------------|
| Chat / LLM | Llama 3 / Mistral | Conversational assistant |
| Summarisation | Pegasus-X | Daily brief |
| Translation | SeamlessM4T | Live UI localisation |
| Zero-shot Classification | Qwen-VL | Auto-tagging |
| Table QA | TAPEX | “Ask your data” analytics |
| ASR | Whisper-v3 | Voice-to-task |
| TTS | Bark v2 | Focus Mode narration |
| Image-to-Text | BLIP-2 | Photo-to-TODO |
| **XR Gamification** | SAM + MiDaS | Spatial XP overlay (XReal, Rokid) |

---

## 🔄 Development Quick-Start

> Clone only the repo you plan to work on.

### Web Client

```bash
git clone git@github.com:Treffortly/webapp-client.git
pnpm install
pnpm dev   # http://localhost:3000
````

### API

```bash
git clone git@github.com:Treffortly/webapp-api.git
pnpm install
pnpm prisma generate
pnpm dev   # GraphQL at http://localhost:4000/graphql
```

> Ensure `DATABASE_URL`, `AUTH0_*`, `REDIS_URL` are set in `.env`.

---

## 🚀 Deployment

| Repo          | Target                              | Notes                         |
| ------------- | ----------------------------------- | ----------------------------- |
| webapp-client | **Vercel** (static + RSC functions) | Auto-deploy on `main`         |
| webapp-api    | **Vercel functions** or **Railway** | Serverless GraphQL            |
| mobile-app    | Google Play Beta                    | CI builds with GitHub Actions |
| desktop-app   | GitHub Releases (DMG/EXE)           | Cross-compile via CMake       |
| website       | Vercel static export                | Marketing site                |

CI workflows live in each repo’s `.github/workflows/`.

---

## 📝 Roadmap Snapshot

* [ ] Finish burn-out forecasting micro-service (FastAPI + DLinear)
* [ ] Release public REST wrapper for GraphQL queries
* [ ] XR overlay POC on XReal Air 2
* [ ] Launch Pro subscription tier (Stripe) Q3-2025

---

### Contributing

Fork the repo you’re interested in, open a descriptive PR, and follow the Conventional Commit spec.
Issues welcome for bug reports or feature ideas.

---
