# Frontend Masters Intermediate React v6

Language: English | [Español](README.es.md)

This repository contains the exercises and builds developed while following the Frontend Masters course [Intermediate React v6](https://frontendmasters.com/courses/intermediate-react-v6/), along with the companion course site at [intermediate-react-v6.holt.courses](https://intermediate-react-v6.holt.courses/).

Each folder is an independent example or mini-app focused on a specific React or React-adjacent concept. The projects are intentionally separated so each technique can be explored, run, and modified on its own.

## What is included

- `deferred`: demonstrates `useDeferredValue` with an image filter UI so the expensive preview stays responsive while slider values update.
- `optimistic`: shows optimistic UI updates with `useOptimistic`, `useTransition`, and a small server-backed “deep thoughts” feed.
- `perf`: explores performance tuning with `useMemo`, `useCallback`, `memo`, and a deliberately expensive Markdown preview.
- `rsc`: a React Server Components example with separate server and client components, plus a custom server pipeline.
- `ssg`: a static site generation example that renders React to static markup during build time.
- `ssr`: a server-side rendering example that streams HTML from a Fastify server and hydrates on the client.
- `transitions`: uses `useTransition` to keep a sports score UI responsive while fetching new game data.
- `note-app`: a Next.js app with server components, server actions, SQLite-backed data, and multiple routes for reading and writing notes.

## Repository structure

| Folder         | Focus                                               |
| -------------- | --------------------------------------------------- |
| `deferred/`    | Deferred rendering and expensive UI updates         |
| `optimistic/`  | Optimistic mutations and async state reconciliation |
| `perf/`        | React rendering performance patterns                |
| `rsc/`         | React Server Components                             |
| `ssg/`         | Static site generation                              |
| `ssr/`         | Server-side rendering and hydration                 |
| `transitions/` | Transition-driven loading states                    |
| `note-app/`    | Next.js notes app with server actions and SQLite    |

## Getting started

Each example has its own dependencies and scripts. Install and run the folder you want to explore.

### Vite-based examples

The following folders use Vite:

- `deferred/`
- `optimistic/`
- `perf/`
- `transitions/`

Typical workflow:

```bash
cd deferred
npm install
npm run dev
```

Replace `deferred` with any of the other Vite examples.

### Next.js note app

```bash
cd note-app
npm install
npm run dev
```

The app uses SQLite data stored in the project directory and includes routes for:

- `/` for the main navigation
- `/my` for personal notes
- `/write` for creating a note
- `/teacher` for the teacher feed
- `/who-am-i` for updating the current user name

### React Server Components example

The `rsc/` project uses separate client and server processes:

```bash
cd rsc
npm install
npm run dev:client
```

In another terminal:

```bash
cd rsc
npm run dev:server
```

### SSR example

```bash
cd ssr
npm install
npm run build
npm start
```

### SSG example

```bash
cd ssg
npm install
npm run build
```

## Notes

- These folders are meant to be studied independently, not as a single combined application.
- Some examples rely on local assets, generated build output, or a SQLite database file inside the project folder.
- The course focuses on understanding the rendering model, data flow, and tradeoffs behind each pattern rather than shipping a polished product.

## Course references

- Frontend Masters course: https://frontendmasters.com/courses/intermediate-react-v6/
- Companion site: https://intermediate-react-v6.holt.courses/
