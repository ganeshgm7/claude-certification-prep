# Lesson 4 — Claude Desktop App: Chat, Cowork, Code

> **Estimated time:** 6 minutes

---

### 📌 What Is This About?

The Claude desktop app is not just "Claude.ai but on your computer." It actually gives you **three different modes** — Chat, Cowork, and Code — each built for a different kind of work, from a quick question to a full, unattended research project to writing production software.

---

### 💡 Why Does This Matter?

If you only ever use "Chat" mode, you are missing out on Cowork's ability to handle big, multi-step jobs on its own, and Code's ability to work directly inside a real software project. Knowing which mode to reach for saves you time and gets you a much more finished result.

---

### 📖 The Explanation

#### The three modes, in one line each

- **Chat** — the same Claude you know from claude.ai, plus quick entry, screenshots, dictation, and connectors that come from running natively on your computer.
- **Cowork** — an agentic tool: you give it a goal, connect it to your tools and resources, and let it do the work. It has the reach and the room to do more — thorough research, cross-source analysis, and complex documents.
- **Code** — for building software: writing, testing, and deploying code.

**Important:** Cowork and Code run on the *same engine* underneath — both are Claude Code. This means both are local to your machine, capable of independent work, able to spin up sub-agents, and able to sustain long tasks. This lets Claude work through bigger tasks on its own.

#### Chat mode

Excels when you need to ask questions, brainstorm, draft, or work through a problem back-and-forth. It works the same as claude.ai, plus a few native-desktop extras:

- **Quick entry** — double-tap the Option key on Mac to pull up Claude in a compact window that stays on top as you switch between apps. You never have to leave what you're doing to ask a question.
- **Screenshots and window sharing** (Mac) — capture a screenshot or share a window so Claude sees exactly what you're looking at — faster and more precise than describing it in words.
- **Dictation** (Mac) — talk through a problem instead of typing.
- **Desktop connectors** — connect local tools and services so Claude can work with other apps on your machine.

**Try it out when:**
- You're staring at an unfamiliar dashboard — double-tap Option, screenshot it, and ask "what do these metrics mean?"
- You're between meetings and want to structure a presentation — open quick entry, switch to voice, and talk it through; Claude drafts an outline.
- You've been jotting ideas across Apple Notes for weeks — add the Notes connector and ask Claude to pull it all together, spot what's unfinished, and check other connected tools for gaps.

#### Cowork mode

Built for work that takes real effort: pulling information from many sources, making sense of it, and producing something finished — thorough research briefs, cross-source financial analysis, end-to-end contract review, polished slide decks from scattered material.

Before starting, Claude often asks a short set of questions to pin down scope, format, and constraints, and it builds a plan you can review in the sidebar. While it works, you see sources it's drawing from, files taking shape, and progress through the plan. You can run multiple tasks at once, each in its own conversation.

**Key features of Cowork:**

- **Folder access** — point Claude to a folder on your computer; it reads what's there, figures out what's relevant, and saves finished work back to the same place.
- **Scheduled tasks** — Claude can handle recurring work on a schedule — a daily briefing pulling from Slack and calendar, a weekly roundup, or a morning inbox triage. If your computer/app was closed when a task was due, it catches up when you're back.
- **Subagents** — background workers Claude spins up to handle parts of a task in parallel — it breaks a complex request into subtasks, assigns each to a subagent, and coordinates the results into one finished deliverable.
- **Dispatch** — a persistent conversation thread that lets you continue your Cowork conversations from your phone (needs both desktop + mobile app, with your computer awake and the desktop app open).
- **Projects (in Cowork)** — group related tasks into dedicated workspaces with their own files, context, instructions, and memory — but these live locally on your desktop and are built around Cowork tasks.
- **Browser use** — connect Claude in Chrome so it can navigate websites, interact with pages, and pull findings directly into the task (e.g., checking competitor pricing across ten sites).
- **Computer use** — when Claude has no connector/plugin for something, it can navigate your computer directly (clicking, typing, opening apps). It follows a priority order: connectors first, then Chrome, then screen interaction — always the fastest, most reliable path. You get a permission prompt before it accesses each app, plus a blocklist option. *(Research preview, Pro/Max plans, macOS only — Windows coming soon.)*
- **Plugins** — add capabilities Claude doesn't have on its own, like live financial data, internal knowledge-base search, or a specific compliance framework.
- **Protected environment** — Cowork runs in a contained space; Claude can read/create/edit files only within the folders you share, never outside them.

**Try it out when:**
- You want to query all your tools like a database: "review what we decided about pricing last quarter across meeting notes, Slack, and email, then update our Q3 deck with the findings."
- You're researching a new market or scoping competitors across many browser tabs.
- You have a folder of 50+ project documents (contracts, financial reports, transcripts) and want the most relevant ones summarised into one memo.
- You do the same routine every morning (checking messages, status update, meeting prep) — set it up once as a scheduled task.

*Availability: Pro, Max, Team, and Enterprise, with new capabilities added regularly.*

#### Code mode

Gives you access to the full power of Claude Code, right inside the desktop app — a complete development environment for building software. Claude works directly in your codebase: reading what's there, writing/modifying code, and running commands. Visual diffs show what changed, a built-in terminal shows commands as they run, and git tracks every version so you can always roll back.

The difference from Cowork: Cowork stays contained to the folders you share; **Code runs directly in your project with full access** to your file system, terminal, and development tools.

**Where the work happens:**
- **Local** — you pick a folder on your computer; Claude works directly with those files, accesses local tools, and can run a dev server you preview in your browser.
- **Remote** — you connect a GitHub repository; Claude works in a cloud environment. Sessions continue even if you close the app — good for larger codebases, or big refactors you want to check back on later.

**Three interaction modes control how much Claude does on its own:**
- **Ask** — Claude proposes every change and waits for your approval (visual diff review before anything is modified).
- **Code** — Claude applies file changes automatically, but checks before running terminal commands.
- **Plan** — Claude outlines its full approach first, with a dedicated plan viewer you can revisit as work progresses.

You can run multiple sessions across projects, filtered by status (Active/Archived) and environment (Local/Cloud).

*Availability: Pro, Max, Team, and Enterprise.*

#### Comparing the three modes

| | Chat | Cowork | Code |
|---|---|---|---|
| **Optimised for** | Quick exchanges: exploring ideas, iterative drafting, quick answers, learning through dialogue | Complex/sustained work: research, analysis, file organisation, finished documents/deliverables | Building software: writing, testing, running, deploying code |
| **Key features** | Quick entry, dictation | Local folders, plugins, subagents, scheduled tasks | Ask/Code/Plan modes, visual diffs, git integration, local and remote environments |
| **Tools & extensions** | Connectors, Skills, Claude in Chrome | Connectors (local + remote), Skills, Claude in Chrome, Plugins, Computer Use | Connectors, Skills, Claude in Chrome, Plugins, Hooks |

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Chat mode** | Native-desktop version of claude.ai chat, plus quick entry/dictation/screenshots | Best for quick, back-and-forth thinking |
| **Cowork mode** | Agentic mode for complex, multi-source, multi-step work | Best when you need a finished deliverable, not just an answer |
| **Code mode** | Full dev environment powered by Claude Code | Best for actual software development work |
| **Subagents** | Background workers Cowork spins up in parallel | Lets Claude break a big task into pieces and finish faster |
| **Ask / Code / Plan** | The three levels of autonomy in Code mode | Lets you control exactly how much Claude does unsupervised |

---

### 🏢 Real-World Scenario

**Situation:** Your team needs a competitor pricing comparison across 10 websites, a codebase bug fixed, and a quick answer about "what does this error mean" — all in the same week.

**How you'd use each mode:** For the quick error question, you'd use **Chat** with a screenshot. For the pricing comparison across many sites (a multi-step, multi-source research job), you'd hand it to **Cowork** with browser use enabled, and let it deliver a structured brief. For the bug fix, you'd open **Code**, point Claude at the local repo, use **Ask** mode so you can review every diff before it's applied, and let git track your history for safety.

---

### 🤔 Lesson Reflection

- Which mode — Chat, Cowork, or Code — best fits the tasks you most commonly use Claude for?
- Think of a recent project where you needed information from multiple sources. How might Cowork have changed that workflow?

---

### ⏭️ What's Next

Next module: **Organizing your work and knowledge**, starting with Projects.
