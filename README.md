<div align="center">

# Om Raval

**I build developer tools and the systems underneath them.**

Ahmedabad, India · [omraval.com](https://omraval.com)

</div>

---

## What I do

I like knowing how things work, so I tend to build them from scratch. An Express-style framework on Node's core modules. An S3-shaped blob store. An end-to-end encrypted chat. A tiling window manager in about 0.4 MB. A coding-agent harness that ships as one static binary.

Most of it is Rust, TypeScript and Swift. I started in front-end and UI design, and I still can't ship something that feels wrong to use, however clean the internals are.

## Projects I'm proudest of

**[rig](https://github.com/omraval18/rig)** · Rust
A coding-agent harness for the terminal. One static binary, any model, profiles, and autonomy levels so you decide how much the agent may do without asking. I built it because I wanted an agent I could read end to end.

**[blox](https://github.com/omraval18/blox)** · Swift
A tiling window manager for macOS. Workspaces and keybindings in the AeroSpace style, borders and animation in the Hyprland style. About 0.4 MB, a TOML config, and no SIP changes needed.

**nflows** · TypeScript (private for now)
A durable workflow engine with a TypeScript SDK and a distributed worker runtime. Retry policies with backoff, task leases, dead-letter queues, idempotency keys, a full event history per run, and metrics. It's a study of the core ideas behind engines like Temporal, not a replacement for one.

**ntrace** · TypeScript (private for now)
A log aggregation and query engine. Logs go in through an API-key-protected endpoint, pass through Kafka to workers, land in Postgres, and get indexed in Redis for fast search and a live-tail stream. Malformed or failed messages go to a dead-letter topic instead of being dropped.

**[nchat](https://github.com/omraval18/nchat)** · TypeScript
Terminal messaging with real cryptography: X25519 key exchange, AES-256-GCM payloads, Argon2id password hashing, per-device identity keys with pinning and fingerprints. Messages are stored locally in SQLite, with Postgres behind the transport server.

**[n3](https://github.com/omraval18/n3)** · TypeScript
S3-shaped blob storage: a versioned REST API, a Hono gateway with API-key auth, a session-based dashboard, a pluggable storage adapter and a typed SDK.

**[prunemymac](https://github.com/omraval18/prunemymac)** · Rust
A disk cleaner and health monitor on Zed's GPUI. An 18 MB binary that idles around 75 MB of RAM.

**[flow-record](https://github.com/omraval18/flow-record)** · Rust
Record a terminal session once, replay it as a parameterized workflow. Project-aware and native to zsh.

Smaller things I like: [nGen](https://github.com/omraval18/ngen) (AI music generation on serverless GPUs), [nClip](https://github.com/omraval18/nclip) (long video to short clips), [mini-express](https://github.com/omraval18/mini-express), [ntypo](https://github.com/omraval18/ntypo), [nbot](https://github.com/omraval18/nbot).

## Work

I'm a software engineer at **ztudio**, a development studio where I work on client AI and full-stack products and on our own agent tooling. Client details are under NDA, so this covers the problems and not the internals.

**Stealth startup: a US-based flood insurance firm, run by 8-figure exit founders**

*AI product*
- Built the AI chat assistant: retrieval over each customer's own documents and data, with long conversations and tool handoffs.
- Built the ingestion pipeline: messy uploads (images, PDFs) in, validated structured data out, feeding the chat and the knowledge base.
- Built the knowledge-base services: retrieval and intent-aware routing.
- Built the gRPC and FastAPI service layer, with background workers for enrichment, webhooks and user sync.

*Infrastructure*
- Moved the Python backend from hand-managed EC2 to ECS Fargate behind a service mesh.
- Ran it as a parallel deployment, so the old servers stayed untouched and production never carried the risk.
- Proved it with real business logic, not health checks: real lookups and a full quote generated through the mesh.
- Debugged a failure where every config looked right and services still couldn't connect, and fixed it at the root with one setting.
- Replaced a manual deploy routine with CodeBuild and CodePipeline, under IAM permission boundaries.
- Audited the legacy AWS estate after the rebrand: orphaned domains, stuck certificates, dangling DNS records.
- Kept secrets out of every command, log and output.

*Security*
- Led the SOC 2 Type II push, with repeated static scans across 70+ pattern families.
- Found and closed a privilege-escalation path: tokens with unsigned fields, rebuilt with full-payload signing and constant-time checks.
- Added fail-closed rate limiting on login, admin, impersonation and chat endpoints.

**Fondu: stablecoin business banking**
- Worked on a product that moves real money: fiat rails in, USDC out, multisig smart-account treasuries.
- Shipped proof-of-personhood sign-in so one person can't open many accounts.
- Fixed reliability bugs in the transfer and smart-account layer, where a bug costs money.
- Worked inside a strict database model: an admin role runs migrations, a restricted role runs the app, row-level security between them.

**Internal agent platforms**
- A self-hosted, multi-tenant agent platform where a team is the tenant boundary. Chats survive restarts and run unattended for long stretches, with isolated sandboxes for code execution.
- An org-wide agent app with roles, long-term memory, scheduled runs and connections to Slack, Notion, Linear and Sentry.

**Before that**
- **Travelarrow:** built the production iOS app and worked on the backend. Booking retries, queueing and optimistic locking to stop double bookings under concurrent requests.
- **AllEvents:** front-end and platform work focused on page speed, organizer tools and email deliverability.

## What I'm exploring now

Mostly the layers most people never look under:

- **Databases.** How storage engines lay data out, how a query planner picks a plan, what a write-ahead log buys you.
- **Operating systems.** Scheduling, memory, processes, and what a window manager or a shell actually asks the kernel for.
- **Networks.** What happens between `connect()` and the first byte, and why it's slow when it is.
- **AI systems.** Agent harnesses, tool use, context handling, and the plumbing that makes a model usable in a real workflow.

I learn by building a small version of the thing and breaking it.

I also share what I learn as short system design explainers on Instagram at [@bitofsys](https://www.instagram.com/bitofsys/). The idea is to make how real systems work easy to follow for anyone, not just people who already work in the field.

## Tech I've worked with

- **Languages:** TypeScript, JavaScript, Python, Rust, Swift, SQL, Lua, shell, C++
- **AI**
  - *Coding agents:* Claude Code, Cursor, Codex, cloud agents, OpenClaw, Grokbot
  - *Agent building:* LangGraph, LangChain, Vercel AI SDK, MCP, ACP, skills, tool calling, harness design, long-running and resumable agent runs
  - *Retrieval and memory:* RAG, Gemini File Search, Mem0, document parsing with structured outputs
  - *Models and providers:* Claude, GPT, Gemini, Qwen, OpenRouter, plus open models I ran myself
  - *Multimodal:* ACE-Step (music), Kokoro (TTS), SDXL Turbo (images), WhisperX (speech to text), active-speaker detection
  - *Infra:* sandboxed code execution (E2B), serverless GPUs (Modal), inference tuning (bfloat16, CPU offload)
  - *Quality and tracing:* Langfuse, OpenTelemetry, Playwright and Midscene end-to-end tests for AI flows
- **Web and mobile:** React, Next.js, Hono, FastAPI, Fastify, Express, Vue, SwiftUI, Tailwind
- **Data and messaging:** PostgreSQL, SQLite, MySQL, MongoDB, Redis, Kafka, BullMQ, Prisma, Drizzle
- **Cloud and infra:** AWS (ECS Fargate, ALB, IAM, CodePipeline), Cloudflare, Docker, Modal, DigitalOcean, CI/CD
- **Testing and tools:** Playwright, Vitest, GitHub Actions, Better Auth, gRPC, REST, GraphQL, WebSockets, Neovim

## Elsewhere

[omraval.com](https://omraval.com) · [github.com/omraval18](https://github.com/omraval18) · [@bitofsys](https://www.instagram.com/bitofsys/)
