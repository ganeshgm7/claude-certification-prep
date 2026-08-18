# Lesson 20 — Hooks

[⬅ Previous: Lesson 19 — MCP (Model Context Protocol)](./Lesson-19-MCP-Model-Context-Protocol.md) · [🏠 Course Home](./README.md) · [Quick Reference ➡](./Quick-Reference.md)

---

### 📌 What Is This About?

This final lesson covers **Hooks** — a way to run commands at specific points in Claude Code's lifecycle. The key difference between hooks and everything else covered in this course is that hooks are **deterministic** — they always run.

---

### 💡 Why Does This Matter?

You can tell Claude in your CLAUDE.md to run Prettier after every file edit, and most of the time it will. But sometimes it won't — it's not perfect. If something absolutely must happen every single time, with no exceptions, a hook is how you guarantee it.

---

### 📖 The Explanation

#### Why Use Hooks
Common use cases include:
- Auto-formatting after file edits.
- Logging all executed commands for compliance.
- Blocking dangerous operations like modifying production files.
- Sending yourself notifications when Claude finishes a task.

#### How They Work
Hooks are configured in your `settings.json`. You pick an event, optionally set a matcher for which tools it applies to, and provide a command to run. The available events are:
- **PreToolUse** — runs before a tool call.
- **PostToolUse** — runs after a tool call completes.
- **UserPromptSubmit** — runs when you submit a prompt, before Claude processes it.
- **Stop** — runs when Claude finishes responding.
- **Notification** — runs when Claude sends a notification.

You configure them through the `/hooks` command inside Claude Code, or by editing `settings.json` directly.

#### A Practical Example
The most common hook: auto-formatting after edits. Set a **PostToolUse** hook with a matcher of `"Edit|MultiEdit|Write"` so it fires whenever Claude modifies a file. The command checks the file extension and runs the appropriate formatter — Prettier for TypeScript, gofmt for Go, whatever your project uses.

#### Blocking with PreToolUse
PreToolUse hooks can block tool calls before they execute. Your hook receives the tool name and input as JSON on stdin. The exit code determines the behavior:
- **Exit code 0** — proceed normally.
- **Exit code 2** — block the action. The stderr message gets fed back to Claude as feedback so it knows why it was blocked and can adjust.
- **Any other exit code** — a non-blocking error that gets shown to you but doesn't stop anything.

This is how you enforce hard rules. Block writes to a production config directory. Block bash commands that contain `rm -rf`. Block commits to main. Whatever your team needs to be **guaranteed, not suggested**.

#### Sharing Hooks with Your Team
Hooks configured in `.claude/settings.json` are project-level and can be checked into your repo. This means your entire team gets the same hooks automatically. Use the `CLAUDE_PROJECT_DIR` environment variable in your commands to reference scripts stored in your project, so they work regardless of Claude's current working directory.

#### Recap
Hooks give you deterministic control over Claude Code's behavior. Use PostToolUse for auto-formatting and logging. Use PreToolUse to block dangerous operations. Configure them with `/hooks` or in `settings.json`. And check them into your repo so your team gets them too.

**If something needs to happen every time without fail, don't put it in a prompt. Put it in a hook.**

---

### 📊 Key Concepts Snapshot

| Event | Fires When |
|---|---|
| **PreToolUse** | Before a tool call — can block it (exit code 2) |
| **PostToolUse** | After a tool call completes — good for auto-formatting/logging |
| **UserPromptSubmit** | When you submit a prompt, before Claude processes it |
| **Stop** | When Claude finishes responding |
| **Notification** | When Claude sends a notification |

| Exit Code | Meaning |
|---|---|
| **0** | Proceed normally |
| **2** | Block the action; stderr message fed back to Claude as feedback |
| **Other** | Non-blocking error shown to you, nothing stops |

---

### 🏢 Real-World Scenario

**Situation:** Your team wants Prettier to run after every single file edit, without fail — and to make sure no one (including Claude) ever accidentally runs `rm -rf` on a production config folder.

**Setup:** Configure a **PostToolUse** hook with matcher `"Edit|MultiEdit|Write"` that runs the right formatter based on file extension. Configure a **PreToolUse** hook that checks the command for `rm -rf` against protected paths and exits with code 2 to block it if matched — with a clear stderr message explaining why. Check both into `.claude/settings.json` so the whole team gets them automatically.

---

### 🤔 Lesson Reflection

- What's one thing you currently *ask* Claude to do consistently (via CLAUDE.md or a prompt) that would be safer as a deterministic hook instead?
- Are there any dangerous operations in your codebase (production configs, protected branches) that a PreToolUse hook could guard against?

---

### ⏭️ What's Next

That's a wrap on **Claude Code 101**! Head to the [Quick Reference](./Quick-Reference.md) for a one-page cheat sheet covering every lesson in this course.

---

[⬅ Previous: Lesson 19 — MCP (Model Context Protocol)](./Lesson-19-MCP-Model-Context-Protocol.md) · [🏠 Course Home](./README.md) · [Quick Reference ➡](./Quick-Reference.md)
