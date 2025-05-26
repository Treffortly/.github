```markdown
# Treffortly – AI-Powered, Gamified Productivity Ecosystem

> **Status:** Pre-alpha • 2025 Roadmap published  
> **Demo URL:** coming soon | **Docs:** `/docs/*`

---

## ✨ Overview
Treffortly unifies task- & habit-management, real-time collaboration, and AI coaching into a single, reward-driven workspace.  
XP, levels, and badges turn daily work into playable quests, while modular AI services provide smart tagging, summarisation, forecasting, and XR visualisation.

| Core Pillars | Highlights |
|--------------|------------|
| **Gamification** | XP economy, adaptive rewards (RL tuned), global + team leaderboards |
| **AI-First UX** | Llama-3 chat assistant, Whisper voice capture, Pegasus daily briefs, Graph ML buddy-matching |
| **Real-Time** | Socket.io live updates, Redis leaderboard ZSETs, optimistic UI |
| **Polyglot Clients** | Web (Next 15), Android (Jetpack Compose), Desktop (Qt 6), CLI daemon (`treffd`) |
| **Integrations** | GitHub, Spotify, Slack, Google Calendar, custom webhooks |
| **XR Ready** | React-Three-Fiber scene renders depth-aware XP orbs on XReal / Rokid via WebXR + MiDas |

---

## 🗂️ Repo Structure (Monorepo)

```

apps/
web/            # Next.js 15 frontend
api/            # Node 18 + Apollo GraphQL gateway
admin/          # Internal admin console
android/        # Kotlin Jetpack-Compose client
desktop/        # Qt 6 C++ desktop
daemon/         # C++20 CLI sync agent
packages/
ui/             # Tailwind v4 + shadcn-based component kit
utils/          # Shared TS helpers & hooks
proto/          # gRPC definitions (Java + C++)

```

---

## 🛠 Tech Stack (Core)

| Layer                 | Tech                                         |
|-----------------------|----------------------------------------------|
| API Gateway           | Node 18 · Apollo Server v4 · GraphQL Subgraph|
| Database              | Neon Postgres · Prisma ORM · Timescale ext   |
| Real-Time             | Socket.io · Redis (Upstash)                  |
| Auth                  | Auth0 (JWT, RBAC)                            |
| AI Services           | FastAPI sidecar (Pegasus, Whisper, SAM, etc) |
| Payments              | Stripe Billing + Webhooks                    |
| Front-End             | Next.js 15 · Tailwind v4 · Framer Motion      |
| CI/CD                 | GitHub Actions → Vercel / Railway            |

---

## 🤖 AI Model → Feature Map

| Task Type | Model | Feature |
|-----------|-------|---------|
| Chat / Gen | **Llama-3 / Mistral** | Conversational assistant, SMART task creation |
| Summarise  | **Pegasus-X**        | Daily/weekly progress brief |
| Translation| **SeamlessM4T**      | Live multilingual UI & comments |
| Zero-Shot CLS| **Qwen-VL-Max**   | Automatic task tagging |
| Table QA   | **TAPEX**            | Natural-language analytics queries |
| ASR        | **Whisper-v3**       | Voice-to-task on mobile/PWA |
| TTS        | **Bark v2**          | Focus-mode audio coach |
| Image→Text | **BLIP-2**           | Photo-to-task ingestion |
| Depth/XR   | **SAM + MiDas**      | XR gamified XP orbs (WebXR) |
| TimeSeries | **DLinear**          | Burn-out forecasting |
| Graph ML   | **Graphormer**       | Accountability buddy suggestions |
| RL Reward  | Custom RL agent      | Adaptive XP economy |

---

## 🔌 Integrations

- **GitHub** – auto-pull requests → tasks, commit XP multiplier  
- **Google Calendar** – bi-directional event sync  
- **Spotify** – current track widget → focus timer playlists  
- **Slack / WhatsApp** – notification bridge  
- **Custom Webhooks** – `/integrations/webhooks` wizard

---

## 🏗 Architecture at a Glance

```

+---------------+        WebSockets        +---------------------+
\|  Next.js Web  | ───────────────────────▶ |  Redis Leaderboard   |
+-------▲-------+                         +----------▲----------+
\| GraphQL                                   |
▼                                          REST
+----------------------+          gRPC         +------------------+
\|  Apollo Gateway (TS) | ───────────────▶      |  Java Rules Svc  |
+----------▲-----------+                       +------------------+
|HTTP                                 |
\|                                     |
▼                                     ▼
+-----------------+      AI RPC/REST     +-----------------+
\|    FastAPI AI   |  ─────────────────▶  | C++ Native CLI  |
+-----------------+                     +-----------------+

````

---

## 🚦 Quick Start (Dev)

```bash
# Monorepo root
pnpm i
pnpm nx run-many -t dev -p api,web
# GraphQL at http://localhost:4000/graphql
# Web at http://localhost:3000
````

---

## 📅 Roadmap (90-Day MVP)

| Week  | Milestone                             |
| ----- | ------------------------------------- |
| 1-2   | Repo scaffold, Auth0, Prisma schema   |
| 3-4   | Task & Habit CRUD, XP logic, basic UI |
| 5-6   | Socket.io real-time + Leaderboard     |
| 7-8   | AI Assistant (LLM) & Smart Tagging    |
| 9-10  | GitHub & Calendar integrations        |
| 11-12 | Stripe Billing, CI/CD, public demo    |

---

## License

MIT © 2025 Wesley van der Kraan and contributors

```
```
