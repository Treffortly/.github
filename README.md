# Treffortly – AI-Powered Gamified Productivity Ecosystem

> Next-gen task, habit & team-productivity platform that turns real-world work into an engaging XP-based game.  
> Built with **Next.js 15 + Tailwind v4** on the front-end and a **Node + GraphQL** cloud back-end—augmented by AI micro-services, a native desktop daemon, and mobile / XR companions.

---

## ✨ Key Capabilities

| Domain | Feature Highlights |
|--------|--------------------|
| **Productivity Core** | Tasks / subtasks · recurring habits & streaks · smart calendar · Pomodoro timer |
| **Gamification** | XP, levels & badges · adaptive reward curve (RL-tuned) · real-time leaderboards |
| **AI Layer** | ⮡ LLM chat assistant (task entry, coaching)<br>⮡ Zero-shot task auto-tagging & categorisation<br>⮡ Daily brief & summarisation<br>⮡ Time-series burn-out forecasting<br>⮡ XR progress overlay (depth-aware) |
| **Integrations** | GitHub commits, Spotify “now playing”, Slack / WhatsApp notifications, Google Calendar sync |
| **Collaboration** | Team projects, live chat, role-based access, shared docs |
| **Customisation** | Drag-and-drop dashboard editor · theme & accent picker (default **Indigo**) |
| **Platforms** | Web (RSC) · PWA · Android (Compose) · Desktop Qt/CLI daemon · XR overlay |

---

## 🏗️ Tech Stack

| Layer | Tech |
|-------|------|
| Front-end | **Next.js 15** · React 18 · TailwindCSS v4 · Framer Motion · Zustand · Apollo/URQL |
| Back-end | **Node.js** · Apollo Server · Prisma ORM · PostgreSQL (Neon) · Redis + Socket.io |
| Auth & Billing | Auth0 · Stripe |
| AI Services | Local Ollama LLM side-car · Python FastAPI for inference · Java Rules-Engine (gRPC) |
| Native | **Android** (Jetpack Compose, Kotlin) · **C++** Qt desktop & CLI daemon |
| DevOps | Vercel deploy · GitHub Actions CI/CD · Docker compose for micro-services |

---

## 🗺️ Monorepo Layout (Turborepo)

```

apps/
web/           -> Next.js 15 front-end
admin/         -> Internal admin panel
api/           -> Node + Apollo GraphQL
android/       -> Jetpack-Compose client
desktop/       -> Qt desktop client
packages/
ui/            -> shadcn-derived component kit
types/         -> Shared TypeScript types
utils/         -> Re-usable helpers & hooks
services/
rules-java/    -> Spring Boot XP Rules Engine
ai-python/     -> FastAPI inference side-car
daemon-cpp/    -> File-watch & CLI sync tool

````

---

## 🔌 AI Model-to-Feature Map

| HF Task | Model Suggestion | Treffortly Module |
|---------|------------------|--------------------|
| Text-Generation (chat) | Llama 3 / Mistral | Conversational assistant, SMART-task rewrite |
| Summarisation | Pegasus-X | Daily brief & weekly digest |
| Translation | SeamlessM4T | Real-time UI/content localisation |
| Zero-shot Classification | Qwen-VL | Auto-tag / colour-code incoming tasks |
| Table QA | TAPEX | “Ask your data” analytics panel |
| ASR | Whisper.v3 | Voice-to-task capture |
| TTS | Bark v2 | Hands-free focus mode |
| Image → Text | BLIP-2 | Photo-to-todo extraction |
| XR Depth / Segmentation | **SAM + MiDaS** | **XR gamification overlay** (XReal / Rokid) |
| Time-Series Forecast | DLinear | Burn-out & workload forecasting |
| Graph ML | Graphormer | Social accountability recommendations |

---

## 🔒 Authentication Flow

1. **Auth0 Universal Login** → returns JWT  
2. JWT validated in GraphQL context → user in `ctx.user`  
3. RBAC roles (`user`, `pro`, `admin`) enforced at resolver level  

---

## ⚡ Real-Time Layer

* Socket.io channels: `tasks`, `leaderboard`, `ai`
* Redis Pub/Sub for multi-instance fan-out
* Optimistic UI via TanStack Query cache updates

---

## 🛠️ Local Dev

```bash
pnpm i
pnpm turbo run dev   # spins up web + api + ui kit
docker compose up    # optional – redis, postgres, ollama
````

Environment variables (see `.env.example`) include `DATABASE_URL`, `AUTH0_*`, `STRIPE_*`, `REDIS_URL`.

---

## 🚀 Production Deploy

* **Vercel**: `apps/web` + `apps/api` (serverless)
* **Railway / Fly**: Redis + Java & Python micro-services
* **GitHub Actions**: lint → test → build → deploy green

---

## 📜 License

Apache-2.0 © 2025 Wesley van der Kraan / Treffortly Contributors

```

> Replace model names or services as you refine your implementation.  
> PRs, issues, and feature ideas welcome!
