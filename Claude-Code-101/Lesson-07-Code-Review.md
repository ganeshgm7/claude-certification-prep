# Lesson 7 — Code Review

[⬅ Previous: Lesson 6 — Context Management](./Lesson-06-Context-Management.md) · [🏠 Course Home](./README.md) · [Next: Lesson 8 — The CLAUDE.md File ➡](./Lesson-08-The-CLAUDE-md-File.md)

---

### 📌 What Is This About?

Claude Code has a few built-in features that make your git workflow faster — reviewing with a subagent, the `/commit-push-pr` skill, and resuming work on a PR with `--from-pr`.

---

### 💡 Why Does This Matter?

The commit-review-push cycle is something every developer does dozens of times a week. A few small habits here — an unbiased review before pushing, a one-step commit-to-PR flow, and an easy way to resume later — remove a surprising amount of daily friction.

---

### 📖 The Explanation

#### Review with a Subagent
Before you push a PR, ask Claude to use a **subagent** to review your changes. The subagent runs in its own context window with fresh eyes — it doesn't carry the bias of the main agent that just spent the session writing the code.

When creating a code-reviewer subagent, restrict it to read-only tools. A reviewer should flag issues, not edit files. Check the subagent configuration into your repo so your whole team uses the same reviewer.

#### The /commit-push-pr Skill
The `/commit-push-pr` skill handles the commit, push, and PR creation all in one step. Instead of doing each manually, just run the skill and Claude takes care of it.

If you have a Slack MCP server configured with channels listed in your CLAUDE.md, it will automatically post the PR link to your team's channel.

#### Session Linking with --from-pr
When Claude creates a PR through `gh pr create`, the session gets linked to that PR automatically. If you need to come back to it later — maybe to address review comments or fix a failing build — run:
```
claude --from-pr <PR_NUMBER>
```
This picks up right where you left off.

#### Recap
Use a subagent for an unbiased code review before pushing. Use `/commit-push-pr` to handle the full commit-to-PR flow in one step. And use `--from-pr` to resume work on a PR later. These are small features, but they remove a lot of friction from your daily workflow.

---

### 📊 Key Concepts Snapshot

| Feature | What It Does |
|---|---|
| **Subagent code reviewer** | Reviews your diff with fresh eyes, isolated from the main session's bias |
| **`/commit-push-pr`** | One skill that commits, pushes, and opens the PR in a single step |
| **`claude --from-pr <PR_NUMBER>`** | Resumes a session linked to an existing PR — pick up right where you left off |

---

### 🏢 Real-World Scenario

**Situation:** You've finished a feature and are ready to open a PR, but you want a sanity check first — and later, a reviewer leaves comments you need to address.

**Workflow:** Run a subagent code reviewer (read-only, so it can only flag issues, not fix them behind your back). Once satisfied, run `/commit-push-pr` to commit, push, and open the PR in one step — it even posts the link to your team's Slack channel if configured. A day later, when review comments come in, run `claude --from-pr <PR_NUMBER>` to resume exactly where you left off.

---

### 🤔 Lesson Reflection

- Do you currently review your own code before opening a PR, or would a subagent reviewer add real value?
- How much manual effort does your current commit → push → PR flow take that `/commit-push-pr` could remove?

---

### ⏭️ What's Next

In the next lesson, you'll learn about the **CLAUDE.md file** — how it gives Claude Code persistent memory about your project.

---

[⬅ Previous: Lesson 6 — Context Management](./Lesson-06-Context-Management.md) · [🏠 Course Home](./README.md) · [Next: Lesson 8 — The CLAUDE.md File ➡](./Lesson-08-The-CLAUDE-md-File.md)
