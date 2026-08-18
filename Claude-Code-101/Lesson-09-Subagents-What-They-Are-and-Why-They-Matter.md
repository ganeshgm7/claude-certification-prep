# Lesson 9 — Subagents: What They Are and Why They Matter

[⬅ Previous: Lesson 8 — The CLAUDE.md File](./Lesson-08-The-CLAUDE-md-File.md) · [🏠 Course Home](./README.md) · [Next: Lesson 10 — Creating a Subagent ➡](./Lesson-10-Creating-a-Subagent.md)

---

### 📌 What Is This About?

This lesson introduces **subagents** — specialized assistants Claude Code can delegate tasks to. Each one runs in its own isolated context window, does its work, and returns just a summary — keeping your main conversation clean.

---

### 💡 Why Does This Matter?

Every file read, every search, every tool call adds to your main context window. A lot of that exploration work isn't something you need to see in detail — you just need the answer. Subagents let Claude do the messy exploration somewhere else, and hand you back only what matters.

---

### 📖 The Explanation

#### What are subagents?
Subagents are specialized assistants that Claude Code can delegate tasks to. Think of them as focused helpers: each one runs in its own conversation context window with a **custom system prompt you define**, does its work, and returns a summary to the main thread. The intermediate steps — all the file reads, searches, and tool calls — stay isolated and never clutter your main conversation.

#### Why subagents matter
Every time you chat with Claude Code, you're adding to the main context window. Every tool call and its results get stored there. That space is finite, and once it fills up, Claude starts losing track of earlier parts of the conversation.

Subagents solve this by spinning up a separate context window. The subagent receives two things:
- **A custom system prompt** from your configuration file that defines the subagent's role and behavior.
- **A task description** written by the parent agent based on what you asked for.

The subagent then works on its own — reads files, runs searches, edits code, whatever it needs to do. When it's done, only a summary comes back to your main conversation. The entire subagent conversation is then discarded.

This means your main context stays clean. You get the answer without all the noise of the journey it took to find it. The tradeoff is that you lose visibility into how the subagent reached its conclusions.

#### A Practical Example
Say you're exploring an unfamiliar codebase and you want to know which service handles refunds. Without a subagent, Claude might read 15 files, run several searches, and trace through multiple function calls — all of that fills your context window, even though you only needed one fact.

With a subagent, the experience is much cleaner. You ask the question, the Explore subagent spins up, does all that digging in its own context, and hands back a focused answer. Your main context window only records the question and the summary — not the 15 files that were read along the way.

#### Built-in Subagents
Claude Code ships with several built-in subagents you can use right away:
- **General purpose** — for multi-step tasks that require both exploration and action.
- **Explore** — for fast searching and navigation of codebases.
- **Plan** — used during plan mode for research and analysis of your codebase before presenting a plan.

#### Custom Subagents
Beyond the built-in options, you can create your own subagents with custom system prompts and tool access. This lets you define specialized agents tailored to your workflow — a code reviewer, a test writer, a documentation generator, or anything else you need. (Lesson 10 walks through creating one step by step.)

#### Further Customization
- **Persistent memory** — lets your subagent retain memory across conversations. Great if you use it consistently on the same projects.
- **Preload skills** — add the `skill` key and list skills by name. Note: unlike skills in your main conversation, the entire skill is loaded into context here.

#### Recap
Subagents give you three main benefits:
- They break work into focused pieces, letting each subagent concentrate on a specific task.
- They keep your main context window clean by isolating all the intermediate work.
- They bring back just the information you need as a concise summary.

Whether you're using the built-in subagents or creating your own, they're a practical way to get more out of longer Claude Code sessions.

> **Want to go deeper?** This lesson is just the overview. The next three lessons (10, 11, and 12) form a mini deep-dive into subagents — creating one, designing it well, and knowing exactly when to use (or avoid) one.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Subagent** | An isolated assistant with its own context window, spun up for a task | Keeps exploration noise out of your main conversation |
| **Custom system prompt** | Instructions defining a subagent's role/behavior | Lets you tailor a subagent to a specific job |
| **Task description** | What the parent agent tells the subagent to do | Shapes exactly what the subagent works on |
| **General purpose / Explore / Plan** | The 3 built-in subagents | Ready to use immediately, no setup |
| **Custom subagents** | Ones you define yourself | Specialized helpers like a code reviewer or test writer |

---

### 🏢 Real-World Scenario

**Situation:** You're new to a large, unfamiliar codebase and need to know where authentication happens before you can safely make a change.

**With a subagent:** Instead of manually reading dozens of files yourself, you ask Claude, and it spins up the **Explore** subagent. That subagent reads through the codebase in its own isolated context, then reports back something like "Authentication is handled in `middleware/auth.js`, validated via JWT" — a clean, one-line answer instead of a context window full of files you never needed to see.

---

### 🤔 Lesson Reflection

- Think of a recent task where you only needed the final answer, not the exploration journey — would a subagent have kept your context cleaner?
- Which built-in subagent (General purpose, Explore, or Plan) matches something you already do often?

---

### ⏭️ What's Next

In the next lesson, you'll create your own subagent from scratch — choosing its scope, tools, model, and color.

---

[⬅ Previous: Lesson 8 — The CLAUDE.md File](./Lesson-08-The-CLAUDE-md-File.md) · [🏠 Course Home](./README.md) · [Next: Lesson 10 — Creating a Subagent ➡](./Lesson-10-Creating-a-Subagent.md)
