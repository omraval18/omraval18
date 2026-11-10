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

*AI platform*
- Designed and shipped the conversational agent: RAG over tenant-scoped documents and records, multi-turn state, and tool-calling handoffs into transactional services.
- Built the document ingestion pipeline: multimodal parsing (images, PDFs), schema-enforced extraction into structured records, and downstream fan-out to the agent and the knowledge base.
- Owned the knowledge-base layer: retrieval, intent classification and routing across sources.
- Built the gRPC and FastAPI service tier, plus async workers for property enrichment, HMAC-verified webhook ingestion and user provisioning.

*Cloud infrastructure*
- Led the migration of the Python gRPC services from hand-managed EC2 to ECS Fargate behind an Envoy-based service mesh (ECS Service Connect).
- Ran old and new stacks side by side with no production cutover, then validated the mesh with real end-to-end transactions (live pricing and quote generation), not synthetic health probes.
- Root-caused a mesh-only failure: the gRPC client's c-ares resolver bypassed the sidecar's DNS interception, so service names never resolved. Fixed it by switching the caller to the native resolver.
- Replaced manual image build and task-definition rollout with a CodeBuild and CodePipeline CI/CD path, scoped with IAM permission boundaries so delegated roles can't escalate.
- Audited and decommissioned legacy DNS, ACM and Amplify resources after the rebrand, without touching anything live.
- Enforced secret hygiene across the migration: no credential ever surfaced in commands, logs or output.

*Security and compliance*
- Led application-security hardening toward SOC 2 Type II: repeated SAST sweeps across 70+ vulnerability pattern families (authz bypass, XSS, SSRF, secrets exposure).
- Found and closed a token-forgery path that led to privilege escalation. Rebuilt signup, bootstrap and impersonation tokens with full-payload HMAC-SHA256 signing and constant-time verification.
- Added fail-closed, Redis-backed rate limiting on authentication, admin, impersonation and chat surfaces.

**Fondu: stablecoin business banking**
- Engineered on a regulated money-movement stack: fiat on-ramps to USDC via Bridge, with ERC-4337 smart-account multisig treasuries on Safe.
- Implemented World ID proof-of-personhood for Sybil-resistant onboarding.
- Hardened the transfer and smart-account integration layer, where correctness failures are financial, for ACH and wire to USDC flows.
- Worked under a split-privilege Postgres model: a DDL-only migration role, a least-privilege runtime role and row-level security enforced at the database boundary.

**Internal agent platforms**
- Built a multi-tenant agent platform with the team as the isolation boundary: durable execution on Postgres-backed LangGraph checkpointing, so runs survive restarts and execute unattended.
- Used per-thread sandboxed execution (E2B), runtime-composed team and personal skills, and one orchestration path shared by interactive, scheduled and channel-triggered runs.
- Built an org-wide agent application with RBAC, long-term memory, cron-scheduled runs and MCP integrations with Slack, Notion, Linear and Sentry.

**Before that**
- **Travelarrow:** shipped a production iOS client (Swift, SwiftUI) and backend services for hotel booking. Built retry and backoff, queueing and concurrency control, and used optimistic locking to prevent double-booking under concurrent multi-room reservations.
- **AllEvents:** front-end and platform engineering: page-performance work, organizer tooling and cross-client email deliverability.

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
