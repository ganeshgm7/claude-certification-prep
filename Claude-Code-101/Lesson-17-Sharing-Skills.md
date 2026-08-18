# Lesson 17 — Sharing Skills

[⬅ Previous: Lesson 16 — Skills vs. Other Claude Code Features](./Lesson-16-Skills-vs-Other-Claude-Code-Features.md) · [🏠 Course Home](./README.md) · [Next: Lesson 18 — Troubleshooting Skills ➡](./Lesson-18-Troubleshooting-Skills.md)

---

### 📌 What Is This About?

Skills become much more valuable when they're shared across a team or organization. This lesson covers the three main distribution methods — repository commits, plugins, and enterprise managed settings — plus an important gotcha: subagents don't inherit skills automatically.

---

### 💡 Why Does This Matter?

A PR review skill that only you use is helpful. That same skill shared across your entire team standardizes code review and creates a consistent experience across your organization. Knowing which sharing method fits which scenario prevents inconsistent adoption.

---

### 📖 The Explanation

#### Committing Skills to Your Repository
The simplest sharing method is committing skills directly to your repository. Place them in `.claude/skills`, and anyone who clones the repo gets those skills automatically — no extra installation needed.

When you push updates, everyone gets them on the next pull. This approach works well for: team coding standards, project-specific workflows, and skills that reference your codebase structure.

The `.claude` directory contains your agents, hooks, skills, and settings — all version-controlled and shared with the team through normal Git workflows.

#### Distributing Skills Through Plugins
Plugins are a way to extend Claude Code with custom functionality designed to be shared across teams and projects. In your plugin project, create a `skills` directory that follows a similar file structure to the `.claude` directory — each skill gets its own folder with a `SKILL.md` file inside.

After you distribute your plugin to a marketplace, other users can discover and install it into Claude Code for themselves. This approach is best when your skills aren't too project-specific and can be useful to community members beyond your immediate team.

#### Enterprise Deployment Through Managed Settings
Administrators can deploy skills organization-wide through managed settings. Enterprise skills take the highest priority — they override personal, project, and plugin skills with the same name.

The managed settings file supports features like `strictKnownMarketplaces` to control where plugins can be installed from:
```
"strictKnownMarketplaces": [
  {
    "source": "github",
    "repo": "acme-corp/approved-plugins"
  },
  {
    "source": "npm",
    "package": "@acme-corp/compliance-plugins"
  }
]
```
This is the right choice for mandatory standards, security requirements, compliance workflows, and coding practices that *must* be consistent across the organization. The keyword here is "must."

#### Skills and Subagents
Here's something that surprises people: subagents don't automatically see your skills. When you delegate a task to a subagent, it starts with a fresh, clean context.

There are important distinctions to understand:
- **Built-in agents** (like Explorer, Plan, and Verify) can't access skills at all.
- **Custom subagents** you define *can* use skills, but only when you explicitly list them.
- Skills are loaded when the subagent starts, not on demand like in the main conversation.

To create a custom subagent with skills, add an agent markdown file in `.claude/agents`. You can use the `/agents` command in Claude Code to create one interactively. The generated agent file includes a `skills` field that lists which skills to load:
```
---
name: frontend-security-accessibility-reviewer
description: "Use this agent when you need to review frontend code for accessibility..."
tools: Bash, Glob, Grep, Read, WebFetch, WebSearch, Skill...
model: sonnet
color: blue
skills: accessibility-audit, performance-check
---
```
When you delegate to this subagent, it has both skills loaded and applies them to every review. First make sure the skills exist in your `.claude/skills` directory, then either create a new subagent or add the `skills` field to an existing agent's markdown file.

This pattern works really well when: you want isolated task delegation with specific expertise; different subagents need different skills (frontend reviewer vs. backend reviewer); you want to enforce standards in delegated work without relying on prompts.

---

### 📊 Key Concepts Snapshot

| Sharing Method | Best For | Priority |
|---|---|---|
| **Repository commit** (`.claude/skills`) | Team coding standards, project-specific workflows | Standard (below Enterprise & Personal) |
| **Plugins** | Cross-team/cross-repo distribution via marketplace | Lowest |
| **Enterprise managed settings** | Mandatory, org-wide standards and compliance | Highest — overrides all others |
| **Subagent `skills` field** | Giving a custom subagent specific expertise | Loads at subagent start, not on demand |

---

### 🏢 Real-World Scenario

**Situation:** Your company wants a mandatory accessibility-review standard applied to all frontend work, company-wide, no exceptions — and you also want a dedicated subagent that always applies it during reviews.

**Sharing approach:** Deploy the accessibility skill through **enterprise managed settings** so it overrides any personal or project-level skill with the same name. Then create a custom `frontend-security-accessibility-reviewer` subagent with `skills: accessibility-audit, performance-check` explicitly listed in its frontmatter — since subagents don't inherit skills automatically, this ensures the reviewer subagent always has that expertise loaded.

---

### 🤔 Lesson Reflection

- Which sharing method (repository, plugin, enterprise) makes the most sense for the skills you've been thinking about building?
- Do you have workflows where custom subagents with specific skills would improve consistency in delegated work?

---

### ⏭️ What's Next

In the final skills lesson, you'll learn how to troubleshoot common skill issues — from skills that don't trigger, to priority conflicts, to runtime errors — with a practical checklist you can reference anytime.

---

[⬅ Previous: Lesson 16 — Skills vs. Other Claude Code Features](./Lesson-16-Skills-vs-Other-Claude-Code-Features.md) · [🏠 Course Home](./README.md) · [Next: Lesson 18 — Troubleshooting Skills ➡](./Lesson-18-Troubleshooting-Skills.md)
