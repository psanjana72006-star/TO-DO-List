# TO-DO-List (SEPM project) - version 2

Multi-page task manager with an AI assistant, deadline reminders, progress tracking and a Node.js + SQLite backend.

## Run it

1. Install Node.js LTS (version 18 or newer) from nodejs.org.
2. In this folder run: `npm install`
3. Start: `node server.js`
4. Open http://localhost:3000 in Google Chrome or Microsoft Edge.

## Turn on the real AI (optional)

Without a key the AI page works in "offline smart mode" (rule-based planning).
To use Claude, create an API key at console.anthropic.com, then start the server like this:

- Windows PowerShell: `$env:ANTHROPIC_API_KEY="sk-ant-..."; node server.js`
- Windows CMD: `set ANTHROPIC_API_KEY=sk-ant-...` then `node server.js`
- Mac/Linux: `ANTHROPIC_API_KEY=sk-ant-... node server.js`

The terminal prints which AI mode is active when the server starts.

## Pages

| Page | File | What it does |
|---|---|---|
| Login / Register | index.html | Secure accounts (hashed passwords, JWT) |
| Dashboard | dashboard.html | Stats, today's attention list, progress ring, demo data |
| Tasks | tasks.html | Smart quick-add (typed or spoken), search, filters, edit |
| Board | board.html | Drag-and-drop To Do / In Progress / Done |
| Reminders | reminders.html | Overdue, due today, next 7 days, snooze, notifications |
| Focus | focus.html | Pomodoro timer, saved sessions |
| Progress | progress.html | Charts, on-time rate, activity history |
| AI Assistant | ai.html | Chat, plan my day, break a goal into tasks |

## Where data is saved

Everything is stored in `todo.db` (SQLite) next to `server.js`: users, tasks, focus sessions,
AI chat history and an activity log of every action. Delete `todo.db` to start completely fresh.
