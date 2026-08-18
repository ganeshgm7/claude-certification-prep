# Lesson 2 — How Claude Code Works

[⬅ Previous: Lesson 1 — What is Claude Code?](./Lesson-01-What-is-Claude-Code.md) · [🏠 Course Home](./README.md) · [Next: Lesson 3 — Installing Claude Code ➡](./Lesson-03-Installing-Claude-Code.md)

---

### 📌 What Is This About?

This lesson opens the hood on Claude Code — the **agentic loop** that powers it, how the **context window** works, why **tools** are the backbone of everything it does, and the **permission modes** that keep you in control.

---

### 💡 Why Does This Matter?

Claude Code is different from a typical chat application, and understanding *why* helps you use it more effectively. Once you know that Claude is gathering context, taking action, and verifying its own results in a loop — rather than just replying to a message — you'll know exactly where you can step in to add context, interrupt, or steer it.

---

### 📖 The Explanation

#### The Agentic Loop
Claude Code is best explained through the **agentic loop**:
1. You enter a prompt into Claude Code.
2. Claude gathers the context it needs by interacting with the model, which returns text or a tool call that Claude Code can execute.
3. It takes action — for example, editing a file or running a command.
4. It verifies the results and determines whether they achieve what your prompt set out to do.
5. If they do, Claude finishes and waits for the next prompt. If they don't, it loops back and tries again until the results are complete and verifiable.

Throughout this loop, you can add context, interrupt, or steer the model to help guide it toward your goal.

#### Context
Claude has a **context window** that determines how much of your conversation, file contents, command outputs, and more it can store and reference. Once you reach that limit, Claude Code **compacts** your conversation — automatically determining what it can remove or summarize to bring the context window back down to a usable size. (We'll go deeper on this in the Context Management lesson.)

#### Tools
Tools are the backbone of how agents work. Most AI assistants simply take text in and return text out. Tools let Claude Code determine *when* to execute code to get closer to completing a task — this could be a file-reading tool, a web search tool, or any number of other capabilities. Claude Code uses semantic understanding to determine when to call a tool and how to use the output.

#### Permissions
Claude Code has several permission modes:
- **Default behavior** — Claude asks for explicit permission before editing a file or running a shell command.
- **Auto-accept** — files are edited without asking, but commands still require approval.
- **Plan mode** — uses read-only tools to compile a plan of action before starting any work.

All of this can be configured in your settings file. Be cautious when skipping permissions — giving Claude Code free rein to run commands means a mistake could be harder to catch before it happens.

#### Recap
Claude Code combines several agentic concepts: an agentic loop, a managed context window, tools, and configurable permissions — all inside your terminal. It can read your codebase, take action, and verify its own work. That's what makes it fundamentally different from a chat window.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Agentic loop** | Prompt → gather context → take action → verify → repeat if needed | The core mechanism behind everything Claude Code does |
| **Compaction** | Automatic summarizing/trimming of context near the limit | Keeps long sessions usable without you managing it manually |
| **Tools** | The mechanism that lets Claude *do* things, not just talk | Backbone of agent behavior — read files, run commands, search web |
| **Permission modes** | Default (ask every time) / Auto-accept / Plan mode | Lets you dial in exactly how much control you want to keep |

---

### 🏢 Real-World Scenario

**Situation:** You ask Claude Code to "add input validation to the signup form."

**What happens under the hood:** Claude gathers context (reads the signup form file and related validation utilities), takes action (writes the validation code), and verifies (checks that the form now behaves correctly, maybe by running existing tests). If the first attempt misses an edge case, it loops back and tries again — all before reporting back to you as "done."

---

### 🤔 Lesson Reflection

- Which permission mode (default, auto-accept, or plan mode) matches how much control you'd want to keep on a typical task?
- Can you think of a recent coding task where "gather context → act → verify → repeat" is exactly what you did manually?

---

### ⏭️ What's Next

In the next lesson, you'll get Claude Code actually installed — in your terminal, VS Code, JetBrains, Desktop app, or on the web.

---

[⬅ Previous: Lesson 1 — What is Claude Code?](./Lesson-01-What-is-Claude-Code.md) · [🏠 Course Home](./README.md) · [Next: Lesson 3 — Installing Claude Code ➡](./Lesson-03-Installing-Claude-Code.md)
