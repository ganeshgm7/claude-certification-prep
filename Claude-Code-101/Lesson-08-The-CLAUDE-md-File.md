# Lesson 8 — The CLAUDE.md File

[⬅ Previous: Lesson 7 — Code Review](./Lesson-07-Code-Review.md) · [🏠 Course Home](./README.md) · [Next: Lesson 9 — Subagents: What They Are and Why They Matter ➡](./Lesson-09-Subagents-What-They-Are-and-Why-They-Matter.md)

---

### 📌 What Is This About?

One of the most useful features in Claude Code: the **CLAUDE.md** file. It gives Claude Code persistent memory about your project, so it doesn't start from zero every single session.

---

### 💡 Why Does This Matter?

Without a CLAUDE.md file, Claude re-explores your codebase every time, sometimes making assumptions that are hard to steer away from. The difference between a frustrating Claude Code session and a productive one often comes down to context — and CLAUDE.md is how you provide it, once, for good.

---

### 📖 The Explanation

#### The Problem It Solves
When you open Claude Code without a CLAUDE.md file, it starts fresh every time. It has to re-explore your codebase, figure out what dependencies are needed, and understand what features are already implemented. Sometimes it makes assumptions, which makes it harder to steer Claude in the right direction.

CLAUDE.md solves this. It's a Markdown file you add to the root of your project, and Claude Code reads it automatically every time you start a session. Think of it as an onboarding script for your codebase. The contents of the CLAUDE.md file are appended to your prompt.

#### An Example
Here's what a typical CLAUDE.md file looks like:
```
# Project

This is a Next.js 15 app using the App Router, Tailwind, and Drizzle ORM.

# Commands
- Dev server: `pnpm dev`
- Run tests: `pnpm test`
- Lint: `pnpm lint`

# Code Style
- Use 2-space indentation
- Prefer named exports
- All API routes go in app/api/
- Use server actions instead of API routes where possible
```
It's straightforward. Now if you ask Claude Code to create a React component, it already knows to use Tailwind for styling and to follow your code conventions.

![A CLAUDE.md file open in VS Code showing project info, commands, and code style rules](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686400%2Fvideo8claudemdexample.1775686400069.jpg)

#### CLAUDE.md is for Teams
You can (and should) commit your CLAUDE.md to version control so your team benefits from it. There's actually a hierarchy of memory files depending on who they're for:
- **Project-level CLAUDE.md** lives in the root directory of your project. Shared with the team.
- **User-level CLAUDE.md** lives in your configuration folder. This one is just for you and applies across all your projects. Put your personal preferences here.

#### Tips
- **Save corrections to memory.** If you find yourself correcting Claude repeatedly — like telling it to always use server actions instead of API routes — explicitly ask Claude to save that rule to memory. Next time you open the project, it'll know.

  ![Asking Claude to save a rule to the CLAUDE.md file — always use server actions instead of API routes](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686399%2Fvideo8Askingclaudetoputinmemory.1775686399417.jpg)

- **Reference project docs.** If you have documentation in your project that you want Claude to reference, use the `@` symbol with the file path:
```
## README.md

Please read if you need more info: @README.md
```

- **Start without one.** We recommend starting a project without a CLAUDE.md file so you can see where you constantly have to course-correct the model. This keeps your CLAUDE.md compact and focused on only the necessary information. When you're ready, run `/init` to have Claude generate one for you.

#### Recap
The difference between a frustrating Claude Code session and a productive one often comes down to context — and the CLAUDE.md file is how you provide that context. Start with your stack, your preferences, and your commands, then build from there as you go.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **CLAUDE.md** | A project-root Markdown file automatically read every session | Persistent memory — Claude doesn't start from zero each time |
| **Project-level CLAUDE.md** | Root of the repo, shared with the team via version control | Whole team gets the same context |
| **User-level CLAUDE.md** | Lives in your personal config folder, applies across all your projects | Your own personal preferences, everywhere |
| **`@filepath`** | Syntax to point Claude at a specific doc to reference | Avoids duplicating documentation inside CLAUDE.md |
| **`/init`** | Command that generates a CLAUDE.md automatically from your codebase | Fast starting point once you know what you need |

---

### 🏢 Real-World Scenario

**Situation:** Every new teammate who uses Claude Code on your Next.js project has to be told "we use server actions, not API routes" and "we use 2-space indentation."

**With CLAUDE.md:** You write these rules once into a project-level CLAUDE.md and commit it to the repo. From that point on, every teammate's Claude Code session — and yours — automatically follows these conventions from the very first prompt.

---

### 🤔 Lesson Reflection

- What stack details, commands, or code style rules do you find yourself repeating to Claude Code?
- Would starting a new project *without* a CLAUDE.md first (to spot the gaps) change how you write yours?

---

### ⏭️ What's Next

In the next lesson, you'll dive into **Subagents** — what they are, why they matter, and how they help manage context.

---

[⬅ Previous: Lesson 7 — Code Review](./Lesson-07-Code-Review.md) · [🏠 Course Home](./README.md) · [Next: Lesson 9 — Subagents: What They Are and Why They Matter ➡](./Lesson-09-Subagents-What-They-Are-and-Why-They-Matter.md)
