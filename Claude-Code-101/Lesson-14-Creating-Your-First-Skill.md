# Lesson 14 — Creating Your First Skill

[⬅ Previous: Lesson 13 — What Are Skills?](./Lesson-13-What-Are-Skills.md) · [🏠 Course Home](./README.md) · [Next: Lesson 15 — Configuration and Multi-File Skills ➡](./Lesson-15-Configuration-and-Multi-File-Skills.md)

> **Estimated time:** 20 minutes

---

### 📌 What Is This About?

A hands-on walkthrough of building a skill from scratch, testing it, and understanding how Claude Code discovers and matches skills to your requests — plus the priority hierarchy that decides which skill wins when names conflict.

---

### 💡 Why Does This Matter?

Knowing the exact mechanics — where the file goes, what the frontmatter must contain, and how Claude decides to load it — is what separates a skill that works reliably from one that never triggers.

---

### 📖 The Explanation

#### Creating a Skill
We'll build a personal skill that teaches Claude how to write PR descriptions in a consistent format. Since it's a personal skill, it lives in your home directory and works across all your projects.

First, create a directory for your skill inside the skills folder — the directory name should match your skill name:
```
mkdir -p ~/.claude/skills/pr-description
```
Then create a `SKILL.md` file inside that directory:
```
---
name: pr-description
description: Writes pull request descriptions. Use when creating a PR, writing a PR, or when the user asks to summarize changes for a pull request.
---

When writing a PR description:

1. Run `git diff main...HEAD` to see all changes on this branch
2. Write a description following this format:

## What
One sentence explaining what this PR does.

## Why
Brief context on why this change is needed

## Changes
- Bullet points of specific changes made
- Group related changes together
- Mention any files deleted or renamed
```
The **name** identifies your skill. The **description** tells Claude when to use it — this is the matching criteria. Everything after the second set of dashes is the instructions Claude follows when the skill is activated.

#### Testing Your Skill
Claude Code loads skills at startup, so restart your session after creating one. You can verify it's available by checking the available skills list.

To test it, make some changes on a branch and say something like "write a PR description for my changes." Claude will indicate it's using the PR description skill, check your diff, and write a description following your template — same format every time.

#### How Skill Matching Works
When Claude Code starts, it scans four locations for skills but only loads the **name and description** — not the full content. This is an important detail.

When you send a request, Claude compares your message against the descriptions of all available skills. For example, "explain what this function does" would match a skill described as "explain code with visual diagrams" because the intent overlaps.

Once a match is found, Claude asks you to confirm loading the skill. This confirmation step keeps you aware of what context Claude is pulling in. After you confirm, Claude reads the complete `SKILL.md` file and follows its instructions.

#### Skill Priority
If you clone a repository that has a skill with the same name as one of your personal skills, which one wins? There's a clear priority order:
1. **Enterprise** — managed settings, highest priority.
2. **Personal** — your home directory (`~/.claude/skills`).
3. **Project** — the `.claude/skills` directory inside a repository.
4. **Plugins** — installed plugins, lowest priority.

This lets organizations enforce standards through enterprise skills while still allowing individual customization. If your company has an enterprise "code-review" skill and you create a personal "code-review" skill with the same name, the enterprise version takes precedence.

To avoid conflicts, use descriptive names. Instead of just "review," use something like "frontend-review" or "backend-review."

#### Updating and Removing Skills
To update a skill, edit its `SKILL.md`. To remove one, delete its directory. **Always restart Claude Code** for changes to take effect.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Skill directory** | A named folder inside `~/.claude/skills` or `.claude/skills` containing `SKILL.md` | Directory name should match the skill's `name` field |
| **Name + description at startup** | Only these two fields load into context initially | Keeps skills lightweight until actually matched |
| **Confirmation prompt** | Claude asks before loading full skill content | Keeps you aware of what's entering your context |
| **Priority order** | Enterprise → Personal → Project → Plugins | Decides which skill wins on a name conflict |
| **Restart required** | Skills load at startup only | Changes won't apply until you restart Claude Code |

---

### 🏢 Real-World Scenario

**Situation:** You keep writing PR descriptions in inconsistent formats and want every one to follow the same "What / Why / Changes" structure.

**Building the skill:** Create `~/.claude/skills/pr-description/SKILL.md` with the name, description, and the 3-section format shown above. Restart Claude Code, make a code change, and say "write a PR description for my changes" — Claude activates the skill, runs `git diff`, and writes the description in your exact format, every single time.

---

### 🤔 Lesson Reflection

- What's one task in your daily workflow that you could turn into a skill right now? What would the description look like?
- How might the priority hierarchy affect your team's skill management strategy? Would you rely more on personal or project-level skills?

---

### ⏭️ What's Next

In the next lesson, you'll learn about advanced configuration — metadata fields, tool restrictions with `allowed-tools`, and how to structure larger skills using progressive disclosure and multi-file organization.

---

[⬅ Previous: Lesson 13 — What Are Skills?](./Lesson-13-What-Are-Skills.md) · [🏠 Course Home](./README.md) · [Next: Lesson 15 — Configuration and Multi-File Skills ➡](./Lesson-15-Configuration-and-Multi-File-Skills.md)
