# Lesson 10 — Creating a Subagent

[⬅ Previous: Lesson 9 — Subagents: What They Are and Why They Matter](./Lesson-09-Subagents-What-They-Are-and-Why-They-Matter.md) · [🏠 Course Home](./README.md) · [Next: Lesson 11 — Designing Effective Subagents ➡](./Lesson-11-Designing-Effective-Subagents.md)

---

### 📌 What Is This About?

A step-by-step walkthrough of creating your own custom subagent — choosing its scope, letting Claude generate it, customizing which tools it can access, picking a model and color, and understanding the resulting config file.

---

### 💡 Why Does This Matter?

Custom subagents specialize in specific tasks — reviewing code, writing tests, checking documentation. Knowing how to build one properly (and what each field in its config actually controls) means you can create genuinely useful, reliable helpers instead of a subagent that wanders off-task.

---

### 📖 The Explanation

#### Creating a Subagent
The easiest way to create a subagent is with the `/agents` slash command. This opens the main interface for managing your subagents. From there, select **Create new agent**.

You will first be asked to choose the **scope** of your subagent:
- **Project-level** — available only in the current project.
- **User-level** — shared across all projects on your machine.

Next, you choose how to create it. You can write the configuration manually, but the recommended approach is to let Claude generate it for you — just describe what you want the subagent to do, and Claude will produce a name, description, and system prompt based on your input.

![Subagent creation flow in Claude Code](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1773974844%2Fsubagentsvideo2version3_04.1773974843174.png)

#### Customizing Tools
During creation, you get the chance to customize which tools the subagent can access. The tool categories include: Read-only tools, Edit tools, Execution tools, MCP tools, and Other tools.

Think about what your subagent actually needs. A code reviewer probably does not need edit tools — it should read and analyze code, not change it. However, you might want to keep execution tools enabled so it can more easily identify pending changes (like running `git diff`).

![Tool category selection when creating a subagent](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1773974881%2Fsubagentsvideo2version3_06.1773974881320.png)

#### Choosing a Model and Color
After configuring tools, you select which Claude model powers the subagent. The model picker offers four options:
- **Haiku** — best for fast, lightweight tasks.
- **Sonnet** — a good middle ground between speed and depth.
- **Opus** — best for complex analysis.
- **Inherit** — uses whatever model your main conversation is running.

Finally, you pick a color. This shows up in the UI so you can quickly tell which subagent is active — a small touch, but it helps when you have multiple subagents running.

![Model and color picker when creating a subagent](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1773974921%2Fsubagentsvideo2version3_07.1773974921584.png)

#### The Config File
Once creation is complete, the subagent config file is saved into your project (typically at `.claude/agents/your-agent-name.md`). Here is what a typical subagent config looks like:

```
---
name: code-quality-reviewer
description: Use this agent when you need to review recently written or modified code for quality, security, and best practice compliance.
tools: Bash, Glob, Grep, Read, WebFetch, WebSearch
model: sonnet
color: purple
---

You are an expert code reviewer specializing in quality assurance, security best practices, and
adherence to project standards. Your role is to thoroughly examine recently written or modified code
and identify issues that could impact reliability, security, maintainability, or performance.
```

Let's break down each field:
- **`name`** — a unique identifier for the subagent. This is how you reference it, either by asking Claude directly or by typing `@agent code-quality-reviewer` in your message.
- **`description`** — controls when Claude decides to use the subagent. This must be a single line (use escaped newline characters `\n` if you need breaks). You can include example conversations here to help Claude understand when delegation is appropriate.
- **`tools`** — lists which tools the subagent can access. This matches whatever you selected during generation, but you can edit the list here at any time.
- **`model`** — specifies which Claude model to use: `sonnet`, `opus`, `haiku`, or `inherit`.
- **`color`** — the UI color for identifying the subagent.

#### System Prompts
The body of the markdown file (everything below the YAML frontmatter) is the system prompt. This is where you give the subagent its instructions: what it should focus on, how it should analyze things, and how it should report findings back to the main agent.

A well-written system prompt is the difference between a useful subagent and one that misses the point. Be specific about what the subagent should look for and how it should structure its output.

#### Making Claude Use Your Subagent Automatically
If you want Claude to delegate tasks to the subagent without you explicitly asking, include the word **"proactively"** in the description field. For example:
```
description: Proactively suggest running this agent after major code changes...
```
You can also add example conversations to the description to help Claude understand specific scenarios where the subagent should be used. The more concrete your examples, the better Claude gets at knowing when to delegate.

#### Testing Your Subagent
After creating your subagent, test it by making some code changes and asking Claude to review them. If the subagent is not being used when you expect it to be, go back and check the description. Adding more specific examples and trigger scenarios helps Claude understand when to delegate work to your subagent.

![Testing a newly created subagent in Claude Code](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1773974991%2Fsubagentsvideo2version3_14.1773974991791.png)

#### Recap
Creating a subagent means making a directory (or file) with the proper config: choose a scope, let Claude generate a name/description/prompt, customize its tools, pick a model and color, then test and refine the description until it triggers reliably.

---

### 📊 Key Concepts Snapshot

| Field | Controls |
|---|---|
| **`name`** | Unique identifier; also how you reference it directly (`@agent name`) |
| **`description`** | *When* Claude decides to use the subagent — single line, add "proactively" to trigger it automatically |
| **`tools`** | Which tools the subagent can access (read-only, edit, execution, MCP, other) |
| **`model`** | `haiku` (fast) / `sonnet` (balanced) / `opus` (complex analysis) / `inherit` |
| **`color`** | UI color to visually identify the active subagent |
| **System prompt** | The body of the file — the actual instructions the subagent follows |

---

### 🏢 Real-World Scenario

**Situation:** You want a dedicated code-quality reviewer subagent for your team.

**Steps:** Run `/agents` → Create new agent → choose Project-level scope (so the whole team gets it) → describe "reviews recently written code for quality, security, and best practices" and let Claude generate the name/description/prompt → disable Edit tools (a reviewer shouldn't change code) but keep Bash enabled (so it can run `git diff`) → pick Sonnet as a balanced model → pick a color → test it by making a change and asking Claude to review it.

---

### 🤔 Lesson Reflection

- What's one task you do repeatedly that could become a custom subagent?
- Which tools would you disable for that subagent to keep its role clear and safe?

---

### ⏭️ What's Next

In the next lesson, you'll learn the patterns that make subagents genuinely **effective** — writing better descriptions, defining output formats, reporting obstacles, and limiting tool access.

---

[⬅ Previous: Lesson 9 — Subagents: What They Are and Why They Matter](./Lesson-09-Subagents-What-They-Are-and-Why-They-Matter.md) · [🏠 Course Home](./README.md) · [Next: Lesson 11 — Designing Effective Subagents ➡](./Lesson-11-Designing-Effective-Subagents.md)
