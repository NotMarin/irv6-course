# Note Passer (Next.js + React Server Components)

This project is a practical implementation of the **RSCs with Next.js** section from Frontend Masters Intermediate React v6.

It follows these lessons:

- https://intermediate-react-v6.holt.courses/lessons/rscs-with-nextjs/abbreviated-intro-to-nextjs
- https://intermediate-react-v6.holt.courses/lessons/rscs-with-nextjs/server-components
- https://intermediate-react-v6.holt.courses/lessons/rscs-with-nextjs/server-actions
- https://intermediate-react-v6.holt.courses/lessons/rscs-with-nextjs/server-and-client-components-together
- https://intermediate-react-v6.holt.courses/lessons/rscs-with-nextjs/limitations-of-rscs

## Goal

Build a small note-passing app to understand:

- Next.js App Router conventions
- React Server Components (RSC) by default
- Server Actions for form submissions
- How to compose server and client components together
- The practical limitations of RSC boundaries

## Tech Stack

- Next.js 15.1.7 (App Router)
- React 19
- SQLite (`sqlite3` + `promised-sqlite3`)
- `doodle.css` + custom global styles

## What Was Implemented

### 1) Abbreviated Intro to Next.js

- App Router structure under `src/app`
- Shared layout in `src/app/layout.js`
- Global styling in `src/app/globals.css`
- Home route with navigation to all feature pages

### 2) Server Components (`/my`)

- `src/app/my/page.js` is an async server component.
- Reads directly from SQLite on the server.
- Fetches both "notes sent" and "notes received" in parallel with `Promise.all`.
- Renders HTML tables without client-side data fetching.

### 3) Server Actions (`/write`)

- `src/app/write/page.js` renders a form and loads users from SQLite.
- `<form action={postNote}>` wires the form directly to a server function.
- `src/app/write/postNote.js` uses the `"use server"` directive to insert notes into DB.
- Demonstrates mutation without manually writing `fetch` request code.

### 4) Server + Client Components Together (`/teacher`)

- `src/app/teacher/page.js` (server component) loads initial notes.
- `src/app/teacher/fetchNotes.js` is a server function reused for first load and updates.
- `src/app/teacher/clientPage.js` (client component) polls every 5 seconds and appends new notes.
- Demonstrates a hybrid model: server-rendered initial payload + client interactivity.

### 5) Limitations of RSCs (`/who-am-i`)

- `src/app/who-am-i/whoAmI.js` is a server component that reads the current user.
- `src/app/who-am-i/clientPage.js` is a client wrapper receiving server-rendered children.
- `src/app/who-am-i/updateUsername.js` is a server action for username updates + redirect.
- Demonstrates the key caveat: client state cannot directly drive new server component renders without a new request/refresh cycle.

## Project Routes

- `/` Home
- `/my` My Notes (server component data read)
- `/write` Write a Note (server action form submit)
- `/teacher` Secret Teacher Feed (server + client composition)
- `/who-am-i` Who Am I (RSC limitation pattern)

## Data Layer

- Schema and seed data live in `seed.sql`.
- App expects a local `notes.db` SQLite database in the project root.
- For demo purposes, examples assume user ID `1` is the current user.

## Run Locally

1. Install dependencies:

```bash
npm install
```

2. Create/seed the SQLite database (example with sqlite3 CLI):

```bash
sqlite3 notes.db < seed.sql
```

3. Start the app:

```bash
npm run dev
```

4. Open http://localhost:3000

## Key Learning Outcomes

- RSCs let you run DB queries on the server directly in components.
- Server Actions simplify form-to-server workflows.
- Mixing server and client components gives strong first-load performance plus interactivity.
- RSC boundaries are powerful, but they impose architectural constraints you must design around.
