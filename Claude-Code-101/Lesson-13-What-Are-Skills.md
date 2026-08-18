# Lesson 13 — What Are Skills?

[⬅ Previous: Lesson 12 — When to Use Subagents](./Lesson-12-When-to-Use-Subagents.md) · [🏠 Course Home](./README.md) · [Next: Lesson 14 — Creating Your First Skill ➡](./Lesson-14-Creating-Your-First-Skill.md)

> **Estimated time:** 15 minutes

---

### 📌 What Is This About?

This lesson introduces **Skills** — reusable markdown files that teach Claude Code how to handle specific tasks automatically. Instead of repeating instructions every time you ask Claude to review a PR or write a commit message, you write a skill once and Claude applies it whenever the task comes up.

---

### 💡 Why Does This Matter?

Every time you explain your team's coding standards to Claude, you're repeating yourself. Every PR review, you re-describe how you want feedback structured. Every commit message, you remind Claude of your preferred format. Skills fix this — write it once, Claude applies it automatically whenever it's relevant.

---

### 📖 The Explanation

#### What Skills Are
Skills are folders of instructions and resources that Claude Code can discover and use to handle tasks more accurately. Each skill lives in a `SKILL.md` file with a name and description in its frontmatter.

The description is how Claude decides whether to use the skill. When you ask Claude to review a PR, it matches your request against available skill descriptions and finds the relevant one. Claude reads your request, compares it to all available skill descriptions, and activates the ones that match.

![A skill's frontmatter with name and description fields](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2Fa46l9irobhg0f5webscixp0bs%2Fpublic%2F1771527257%2FSkills1_05.1771527257795.png)

Here's what a skill's frontmatter looks like:
```
---
name: pr-review
description: Reviews pull requests for code quality. Use when reviewing PRs or checking code changes.
---
```
Below the frontmatter, you write the actual instructions — your review checklist, formatting preferences, or whatever Claude needs to know for that task.

#### Where Skills Live
You can store skills in different places depending on who needs them:
- **Personal skills** go in `~/.claude/skills` (your home directory; on Windows, `C:/Users/<your-user>/.claude/skills`). These follow you across all your projects — your commit message style, your documentation format, how you like code explained.
- **Project skills** go in `.claude/skills` inside the root directory of your repository. Anyone who clones the repo gets these skills automatically. This is where team standards live, like your company's brand guidelines, preferred fonts, and colors for web design.

Project skills get committed to version control alongside your code, so the whole team shares them.

#### Skills vs. CLAUDE.md vs. Slash Commands
Claude Code has several ways to customize behavior. Skills are unique because they're automatic and task-specific.
- **CLAUDE.md** files load into every conversation. If you want Claude to always use TypeScript's strict mode, that goes in CLAUDE.md.
- **Skills** load on demand when they match your request. Claude only loads the name and description initially, so they don't fill up your entire context window. Your PR review checklist doesn't need to be in context when you're debugging — it loads when you actually ask for a review.
- **Slash commands** require you to explicitly type them. Skills don't. Claude applies them when it recognizes the situation.

![Claude Code loading a matched skill in the terminal](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2Fa46l9irobhg0f5webscixp0bs%2Fpublic%2F1771527259%2FSkills1_17.1771527259668.png)

#### When to Use Skills
Skills work best for specialized knowledge that applies to specific tasks:
- Code review standards your team follows.
- Commit message formats you prefer.
- Brand guidelines for your organization.
- Documentation templates for specific types of docs.
- Debugging checklists for particular frameworks.

The rule of thumb is simple: if you find yourself explaining the same thing to Claude repeatedly, that's a skill waiting to be written.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Skill** | A `SKILL.md` file with name+description (frontmatter) + instructions below | Teaches Claude a task once; applies it automatically after |
| **Personal skill** | Lives in `~/.claude/skills`, follows you everywhere | Your own preferences across all projects |
| **Project skill** | Lives in `.claude/skills` inside a repo | Shared automatically with anyone who clones the repo |
| **CLAUDE.md** | Always loads, every conversation | Best for always-on rules, not task-specific ones |
| **Slash commands** | Need explicit typing | Skills activate automatically instead |

---

### 🏢 Real-World Scenario

**Situation:** Every time you ask Claude Code to review a PR, you re-explain your team's checklist: check for security issues, verify tests exist, look for code style violations.

**With a skill:** You write this once into a `pr-review` skill with a clear description ("Reviews pull requests for code quality. Use when reviewing PRs or checking code changes."). From then on, simply asking Claude to "review this PR" automatically activates the skill — no more re-explaining the checklist every time.

---

### 🤔 Lesson Reflection

- Think about your most recent interactions with Claude Code. Which instructions did you find yourself repeating? How might a skill have saved you time?
- Consider your team's workflow. Which standards or processes would benefit most from being encoded as skills?

---

### ⏭️ What's Next

In the next lesson, you'll create your first skill from scratch and learn how Claude Code discovers, matches, and loads skills behind the scenes.

---

[⬅ Previous: Lesson 12 — When to Use Subagents](./Lesson-12-When-to-Use-Subagents.md) · [🏠 Course Home](./README.md) · [Next: Lesson 14 — Creating Your First Skill ➡](./Lesson-14-Creating-Your-First-Skill.md)
