# Lesson 6 — Context Management

[⬅ Previous: Lesson 5 — The Explore → Plan → Code → Commit Workflow](./Lesson-05-Explore-Plan-Code-Commit-Workflow.md) · [🏠 Course Home](./README.md) · [Next: Lesson 7 — Code Review ➡](./Lesson-07-Code-Review.md)

---

### 📌 What Is This About?

Context is Claude's working memory. This lesson explains the context window, what happens when it fills up, the `/compact`, `/clear`, and `/context` commands, and practical tips to save context space.

---

### 💡 Why Does This Matter?

Every file Claude reads, every command it runs, every message you send — it all takes up space in a finite context window. If you don't manage it, Claude either loses track of earlier details or gets bogged down carrying irrelevant baggage from three features ago. Managing context well is one of the biggest levers for staying productive in longer sessions.

---

### 📖 The Explanation

#### What is the Context Window?
Think of the context window as the amount of space Claude can hold in its memory. Whenever you enter a prompt, Claude reads a file, runs a tool call, or receives a tool call result — it's all adding to the context window. Since there's a finite amount of space, it becomes important to optimize how you use it.

![Diagram showing the context window as a grid of tokens — some taken, most available](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686395%2Fvideo6contextwindowdiagram.1775686395676.jpg)

#### What Happens When Context Fills Up
When you approach the limit, the context window is automatically **compacted**. Compaction summarizes important details and removes unnecessary tool call results to free up space. Note that this process can potentially lose details.

![Claude Code showing 'Compacting conversation...' as it summarizes the context](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686393%2Fvideo6compactingcontext.1775686393619.jpg)

#### Commands
- **`/compact`** — run compaction manually. This compacts everything up to that point. Handy when you want to free up context space while keeping a memory of what you previously worked on.
- **`/clear`** — if you want to completely start from scratch with no memory of the previous session, run this. It removes everything.
- **`/context`** — check the state of your context. You'll get a high-level overview of your context size, the categories taking up the most space, and a visual graphic showing the breakdown.

#### When to Use Which
A general rule of thumb:
- **Use `/compact`** when you're working on a specific feature and running up against the context limit but need to continue. Keeping the context relevant to your current feature is important.
- **Use `/clear`** when you want to start a new feature. You don't want the previous conversation to introduce bias into something new. For things you want Claude to remember across sessions, put them in your **CLAUDE.md** file so it doesn't have to rediscover things from scratch.

  ![A CLAUDE.md file with commands, important notes, and architecture sections](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686391%2Fvideo6claudemdfile.1775686391669.jpg)

#### Tips for Saving Context Space
- **Be specific.** A vague prompt might seem smaller, but it actually costs more context in the long run. Without clear instructions, Claude is forced to explore your codebase more and do its own reasoning — which takes up far more context space than a detailed prompt would.
- **Manage your MCP servers.** MCP servers load all of their available tools into context by default, even when you're not using them. If you have servers configured for things unrelated to the current project, consider turning them off. You can also try "Skills," which work similarly to MCP servers but don't load everything into context upfront.
- **Use subagents.** Subagents run in parallel with your main agent but have a completely separate context window. For tasks where you only need the answer — like "where are the authentication endpoints located?" — a subagent does the work and returns just a summary to your main agent, keeping your primary context clean.

#### Recap
Managing context within Claude Code is crucial. Use `/compact` to summarize long sessions and `/clear` to start fresh. To use your context window effectively: be specific with your prompts, check what's consuming your current context, and use subagents to delegate tasks where you only need the result.

---

### 📊 Key Concepts Snapshot

| Command / Tip | What It Does |
|---|---|
| **`/compact`** | Manually summarizes the conversation so far, freeing space while keeping a memory of it |
| **`/clear`** | Wipes everything — starts a completely fresh session |
| **`/context`** | Shows a breakdown of what's consuming your context window |
| **Be specific** | Vague prompts cost *more* context long-term, not less |
| **Manage MCP servers** | Unused servers still load tool definitions into context by default |
| **Use subagents** | Delegate "just need the answer" tasks to keep the main context clean |

---

### 🏢 Real-World Scenario

**Situation:** You've been deep in a long refactor and Claude Code is nearing its context limit, but you're not done yet.

**What to do:** Run `/compact` to summarize the session so far and free up space, while keeping the memory of what you've already done — rather than losing everything with `/clear`. Once you move on to a completely different feature next week, that's when you'd reach for `/clear` instead, so the old refactor doesn't bias the new work.

---

### 🤔 Lesson Reflection

- Have you noticed Claude "forgetting" earlier parts of a long session? Would `/compact` at the right moment have helped?
- Do you have MCP servers configured that you rarely use? Would disabling them free up meaningful context?

---

### ⏭️ What's Next

In the next lesson, you'll learn about built-in **Code Review** features — subagent reviewers, the `/commit-push-pr` skill, and resuming work with `--from-pr`.

---

[⬅ Previous: Lesson 5 — The Explore → Plan → Code → Commit Workflow](./Lesson-05-Explore-Plan-Code-Commit-Workflow.md) · [🏠 Course Home](./README.md) · [Next: Lesson 7 — Code Review ➡](./Lesson-07-Code-Review.md)
