# PromptInputBox Component

A modern, AI-style prompt input box component built with Next.js, Tailwind CSS, and shadcn/ui. This repository is a reusable chat-style input UI (like the message boxes in ChatGPT / Claude / Gemini) with support for file attachments, built as a Next.js demo app with a ready-to-copy `PromptInputBox` component.

## Features

- **PromptInputBox component** (`src/components/ui/ai-prompt-box`) — a polished, AI-chat-style message input with attachment support
- Demo page showcasing the component with a gradient background and a send handler
- shadcn/ui component library pre-configured (`components.json`)
- Tailwind CSS + PostCSS styling pipeline
- TypeScript with relaxed build settings (`ignoreBuildErrors`) for rapid prototyping
- Prisma setup included for backend persistence (schema under `prisma/`)
- Example API route (`src/app/api/route.ts`) for backend integration
- `examples/` and `mini-services/` folders with usage references

## Tech Stack

- **Framework:** Next.js (standalone output mode)
- **UI:** React, Tailwind CSS, shadcn/ui (Radix UI primitives), Framer Motion
- **Language:** TypeScript
- **Database:** Prisma (SQLite/SQL support via `db/` and `prisma/`)
- **Other:** dnd-kit (drag & drop), MDX editor, react-hook-form + zod

## Quick Start

Requirements: Node.js 18+ (or Bun).

```bash
# install
npm install --legacy-peer-deps
# or
bun install

# run dev server
npm run dev
# or
bun dev
```

Open http://localhost:3000 to see the PromptInputBox demo.

### Database (optional)

```bash
npm run db:generate   # generate Prisma client
npm run db:push       # push schema to database
```

### Production build

```bash
npm run build   # builds + prepares standalone server output
npm run start   # starts the standalone server (bun .next/standalone/server.js)
```

## Project Structure

```
├── src/
│   ├── app/
│   │   ├── page.tsx          # demo page using PromptInputBox
│   │   ├── layout.tsx
│   │   └── api/route.ts      # sample API route
│   └── components/ui/        # shadcn/ui components incl. ai-prompt-box
├── components/               # extra components (e.g. websocket)
├── prisma/                   # Prisma schema
├── public/                   # static assets
├── examples/                 # usage examples
├── mini-services/            # small companion services
├── components.json           # shadcn/ui config
├── next.config.ts            # Next.js config (standalone output)
└── tailwind.config.ts        # Tailwind config
```

## Reusing the Component

Copy `src/components/ui/ai-prompt-box` into your own Next.js + shadcn/ui project, pass an `onSend(message, files)` handler, and you're done.

## Deploy Notes

This app is configured for **standalone server output** (`output: "standalone"`) and includes Prisma + a sample API route, so it needs a Node.js host (not a static host). Deploy to a Node-capable platform (e.g. a VPS, Render, Railway, Fly.io), run `npm run build`, then start with `bun .next/standalone/server.js` (see `package.json` scripts). Set any required database/env vars for Prisma before running migrations.

## Environment Variables

- Database connection details for Prisma (see `prisma/schema.prisma` and `.env.example` if present).

---

**Built by Girish Lade** — https://ladestack.in
