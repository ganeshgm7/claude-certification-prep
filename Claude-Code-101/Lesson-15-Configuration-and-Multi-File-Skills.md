# Lesson 15 — Configuration and Multi-File Skills

[⬅ Previous: Lesson 14 — Creating Your First Skill](./Lesson-14-Creating-Your-First-Skill.md) · [🏠 Course Home](./README.md) · [Next: Lesson 16 — Skills vs. Other Claude Code Features ➡](./Lesson-16-Skills-vs-Other-Claude-Code-Features.md)

---

### 📌 What Is This About?

This lesson covers the advanced techniques that make skills more powerful: the full set of metadata fields, how to write descriptions that trigger reliably, restricting tool access for security-sensitive workflows, and organizing larger skills across multiple files using **progressive disclosure**.

---

### 💡 Why Does This Matter?

A basic skill works with just a name and description, but real-world skills often need more — a way to restrict what tools they can touch, and a way to stay efficient even when they need a lot of supporting reference material. Getting this right keeps your skills powerful *and* light on context.

---

### 📖 The Explanation

#### Skill Metadata Fields
The agent skills open standard supports several fields in the SKILL.md frontmatter. Two are required, and the rest are optional:
- **name** (required) — identifies your skill. Use lowercase letters, numbers, and hyphens only. Maximum 64 characters. Should match your directory name.
- **description** (required) — tells Claude when to use the skill. Maximum 1,024 characters. This is the most important field because Claude uses it for matching.
- **allowed-tools** (optional) — restricts which tools Claude can use when the skill is active.
- **model** (optional) — specifies which Claude model to use for the skill.

#### Writing Effective Descriptions
Be explicit with your instructions. If someone told you "your job is to help with docs," you wouldn't know what to do — and Claude thinks the same way. A good description answers two questions:
1. What does the skill do?
2. When should Claude use it?

If your skill isn't triggering when you expect it to, try adding more keywords that match how you actually phrase your requests. The description is what Claude uses to decide whether a skill is relevant, so the language matters.

#### Restricting Tools with allowed-tools
Sometimes you want a skill that can only read files, not modify them — useful for security-sensitive workflows, read-only tasks, or any situation where you want guardrails. Here's one complete example:
```
---
name: codebase-onboarding
description: Helps new developers understand the system works.
allowed-tools: Read, Grep, Glob, Bash
model: sonnet
---
```
When this skill is active, Claude can only use those tools (`Read`, `Grep`, `Glob`, `Bash`) without asking permission — no editing, no writing. If you omit `allowed-tools` entirely, the skill doesn't restrict anything; Claude uses its normal permission model.

#### Progressive Disclosure
Skills share Claude's context window with your conversation. When Claude activates a skill, it loads the contents of that SKILL.md into context. But sometimes you need references, examples, or utility scripts that the skill depends on.

Cramming everything into one huge file has two problems: it takes up a lot of context window space, and it's not fun to maintain. **Progressive disclosure** solves this — keep essential instructions in SKILL.md and put detailed reference material in separate files that Claude reads only when needed.

The open standard suggests organizing your skill directory with:
- **scripts/** — executable code.
- **references/** — additional documentation.
- **assets/** — images, templates, or other data files.

Link to the supporting files from SKILL.md with clear instructions about when to load them. For example, Claude reads `architecture-guide.md` only when someone asks about system design — if they're asking where to add a component, it never loads that file. It's like having a table of contents in the context window rather than the entire document.

A good rule of thumb: **keep SKILL.md under 500 lines**. If you're exceeding that, consider whether the content should be split into separate reference files.

#### Using Scripts Efficiently
Scripts in your skill directory can run without loading their contents into context. The script executes and only the output consumes tokens. The key instruction to include in your SKILL.md is to tell Claude to *run* the script, not *read* it.

This is particularly useful for: environment validation, data transformations that need to be consistent, and operations that are more reliable as tested code than generated code.

---

### 📊 Key Concepts Snapshot

| Field / Concept | Meaning |
|---|---|
| **name** (required) | Lowercase/numbers/hyphens only, max 64 chars, matches directory name |
| **description** (required) | Max 1,024 chars; answers "what" + "when"; the most important field for matching |
| **allowed-tools** (optional) | Restricts tools usable while the skill is active — good for read-only/security workflows |
| **model** (optional) | Which Claude model powers the skill |
| **Progressive disclosure** | Keep SKILL.md lean; link to `scripts/`, `references/`, `assets/` for details loaded only when needed |
| **Scripts** | Run without loading contents into context — only output consumes tokens |

---

### 🏢 Real-World Scenario

**Situation:** You want to build an onboarding skill for new developers, but it should only read code, never modify it — and it needs a full architecture guide too big to keep in the main file.

**Applying the lesson:** Set `allowed-tools: Read, Grep, Glob, Bash` so the skill is read-only by design. Keep SKILL.md under 500 lines with the essential instructions, and put the full architecture write-up in `references/architecture-guide.md`, telling Claude in SKILL.md to load that file only when someone asks about system design — keeping the skill efficient for simpler questions.

---

### 🤔 Lesson Reflection

- Think about a skill you'd like to build that involves multiple files. How would you structure the SKILL.md versus supporting reference files?
- Are there workflows in your team where restricting tool access with `allowed-tools` would add an important safety layer?

---

### ⏭️ What's Next

In the next lesson, we'll compare skills to the other ways you can customize Claude Code — CLAUDE.md, subagents, hooks, and MCP servers — so you can choose the right tool for each situation.

---

[⬅ Previous: Lesson 14 — Creating Your First Skill](./Lesson-14-Creating-Your-First-Skill.md) · [🏠 Course Home](./README.md) · [Next: Lesson 16 — Skills vs. Other Claude Code Features ➡](./Lesson-16-Skills-vs-Other-Claude-Code-Features.md)
