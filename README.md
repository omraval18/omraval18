<div align="center">

# Om Raval

**I build developer tools and the systems underneath them.**

Ahmedabad, India · [omraval.live](https://omraval.live)

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

Smaller things I like: [mini-express](https://github.com/omraval18/mini-express), [ntypo](https://github.com/omraval18/ntypo), [nbot](https://github.com/omraval18/nbot).

## What I'm exploring now

Mostly the layers most people never look under:

- **Databases.** How storage engines lay data out, how a query planner picks a plan, what a write-ahead log buys you.
- **Operating systems.** Scheduling, memory, processes, and what a window manager or a shell actually asks the kernel for.
- **Networks.** What happens between `connect()` and the first byte, and why it's slow when it is.
- **AI systems.** Agent harnesses, tool use, context handling, and the plumbing that makes a model usable in a real workflow.

I learn by building a small version of the thing and breaking it.

## Stack

![Rust](https://img.shields.io/badge/rust-%23000000.svg?style=for-the-badge&logo=rust&logoColor=white)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![Swift](https://img.shields.io/badge/swift-F54A2A?style=for-the-badge&logo=swift&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Lua](https://img.shields.io/badge/lua-%232C2D72.svg?style=for-the-badge&logo=lua&logoColor=white)
![Shell Script](https://img.shields.io/badge/shell_script-%23121011.svg?style=for-the-badge&logo=gnu-bash&logoColor=white)
![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![React](https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB)
![Next JS](https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/tailwindcss-%2338B2AC.svg?style=for-the-badge&logo=tailwind-css&logoColor=white)
![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![Bun](https://img.shields.io/badge/bun-%23000000.svg?style=for-the-badge&logo=bun&logoColor=white)
![Hono](https://img.shields.io/badge/hono-E36002?style=for-the-badge&logo=hono&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-%234ea94b.svg?style=for-the-badge&logo=mongodb&logoColor=white)
![Neovim](https://img.shields.io/badge/NeoVim-%2357A143.svg?style=for-the-badge&logo=neovim&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=for-the-badge&logo=Cloudflare&logoColor=white)
![Vercel](https://img.shields.io/badge/vercel-%23000000.svg?style=for-the-badge&logo=vercel&logoColor=white)
![Figma](https://img.shields.io/badge/figma-%23F24E1E.svg?style=for-the-badge&logo=figma&logoColor=white)

## Stats

<div align="center">

![GitHub stats](https://github-readme-stats.vercel.app/api?username=omraval18&show_icons=true&theme=radical&hide_border=true&include_all_commits=true)
![Top languages](https://github-readme-stats.vercel.app/api/top-langs/?username=omraval18&theme=radical&hide_border=true&layout=compact)

</div>

## Elsewhere

[omraval.live](https://omraval.live) · [github.com/omraval18](https://github.com/omraval18)

---

<sub>The previous version of this README is kept in [archive/README.previous.md](archive/README.previous.md).</sub>
