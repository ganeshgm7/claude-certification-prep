# Lesson 1 — What is Claude Code?

[🏠 Course Home](./README.md) · [Next: Lesson 2 — How Claude Code Works ➡](./Lesson-02-How-Claude-Code-Works.md)

---

### 📌 What Is This About?

This lesson introduces **Claude Code** — an agentic coding tool that reads your codebase, edits your files, runs commands, and connects to your existing developer tools to help you ship faster. It's available in your terminal, Visual Studio Code, JetBrains IDEs, the Claude Desktop app, and on the web.

---

### 💡 Why Does This Matter?

If you've used Claude.ai, you already know Claude can write and explain code. But Claude Code is a different animal altogether — it doesn't just hand you a code snippet to copy-paste. It goes into your project itself, reads the real files, makes the actual edits, and runs the actual commands. Understanding this difference upfront saves you from treating Claude Code like a fancier chatbot when it's really more like a junior developer sitting at your keyboard.

---

### 📖 The Explanation

#### What separates Claude Code from Claude?
Unlike Claude.ai, Claude Code has **direct access to your files, your terminal, and your entire codebase**. Instead of copying and pasting code back and forth between a chat window and your editor, it goes in and does the work itself. The key differentiator: Claude Code works as an **AI Agent**.

#### What is an Agent?
An AI Agent is software that can interact with its environment and perform actions to complete a defined goal. At its core, this works by having a large language model operating in a loop, in real time. AI Agents can have access to tools, external services, or even other AI Agents to help them reach their goals.

#### What can Claude Code actually do?
- **Read and understand your codebase** — ask it to explain a feature or trace a bug throughout your code.
- **Edit files across your project** — it can refactor a function and update every file that references it.
- **Run terminal commands** — execute your build script, run your tests, install packages, and use the output to decide what to do next.
- **Search the web** — if it needs documentation or the latest API references, it can look that up for you.

#### Using Claude Code effectively — 3 concepts to keep in mind
1. **The context window.** Think of this as Claude's working memory — it can hold a lot, but not everything at once. This is where the "agentic" part comes in: Claude finds strategic ways to locate answers within your codebase without loading the entire thing into context.
2. **It asks for permission.** By default, Claude Code asks you before running commands or making changes. You're always in control, whether you prefer a hands-on or hands-off approach.
3. **It can make mistakes.** Just like any tool, Claude Code isn't perfect — it might misunderstand your intent, introduce a bug, or over-engineer a solution. Staying in the loop helps you catch these early.

#### Recap
Claude Code is an agentic coding tool. It reads your codebase, edits your files, runs commands, and connects to external tools to help you ship faster. You can use it today in your terminal, VS Code, JetBrains IDEs, and the Claude Desktop app.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Claude Code** | An agentic coding tool with direct file/terminal/codebase access | The main tool this whole course is about |
| **AI Agent** | Software that acts on its environment in a loop to reach a goal | Explains *why* Claude Code can do more than a chatbot |
| **Context window** | Claude's working memory — finite, so it must be used strategically | Sets the stage for later lessons on managing context |
| **Permission-asking** | Claude Code's default habit of checking before acting | Keeps you in control, hands-on or hands-off |
| **Mistakes happen** | Claude Code isn't perfect — misunderstandings, bugs, over-engineering | Reason to stay in the loop rather than fully "fire and forget" |

---

### 🏢 Real-World Scenario

**Situation:** You're handed an unfamiliar codebase and asked to trace a bug in a feature you've never touched.

**With Claude Code:** Instead of manually clicking through dozens of files, you simply ask Claude Code to explain the feature and trace the bug. It reads the relevant files itself, follows the logic across file boundaries, and reports back — the same kind of exploration a senior teammate might do for you, done in seconds instead of an afternoon.

---

### 🤔 Lesson Reflection

- What repetitive coding tasks in your day-to-day work could Claude Code take off your plate?
- Which environment (terminal, VS Code, JetBrains, Desktop, web) fits your current workflow best?

---

### ⏭️ What's Next

In the next lesson, you'll look under the hood at **how Claude Code actually works** — the agentic loop, context, tools, and permissions.

---

[🏠 Course Home](./README.md) · [Next: Lesson 2 — How Claude Code Works ➡](./Lesson-02-How-Claude-Code-Works.md)
