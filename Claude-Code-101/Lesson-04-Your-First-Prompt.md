# Lesson 4 — Your First Prompt

[⬅ Previous: Lesson 3 — Installing Claude Code](./Lesson-03-Installing-Claude-Code.md) · [🏠 Course Home](./README.md) · [Next: Lesson 5 — The Explore → Plan → Code → Commit Workflow ➡](./Lesson-05-Explore-Plan-Code-Commit-Workflow.md)

---

### 📌 What Is This About?

This lesson covers how to actually talk to Claude Code — the difference between **Auto-Accept** and **Approval** modes, what **Plan Mode** is, and a worked example: adding a dark mode toggle to an app.

---

### 💡 Why Does This Matter?

You talk to Claude Code like you would any AI assistant — but a few small choices (how much it auto-approves, whether it plans before it codes) change how safe and how smooth the experience feels. Knowing these options upfront means you're never caught off guard by an unexpected file edit.

---

### 📖 The Explanation

#### Auto-Accept vs. Approval
You can choose whether Claude auto-accepts every file change it suggests, or asks for your explicit permission each time. Press **Shift + Tab** to cycle between modes.
- **Approval mode** — Claude asks permission each time it wants to edit a file or run a command.
- **Auto-accept mode** — file edits are automatically approved, but commands still require your permission.

There's no right or wrong answer — it's whatever you're comfortable with.

![Claude Code in auto-accept mode, reading files and working through a task](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686381%2Fvideo4autoaccept.1775686381332.jpg)

#### Plan Mode
Within the Shift+Tab menu is **Plan Mode**. Plan mode takes your prompt and uses read-only tools to analyze your codebase and research your suggested implementation. It asks clarifying questions along the way, then returns a detailed plan it can execute.

Plan mode is great for planning complex changes or doing a safe code review — many times you'll be asking Claude to handle multi-step implementations toward a feature, and this is exactly where Plan Mode excels.

![Claude Code with plan mode on, showing the status bar indicator](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686384%2Fvideo4planmode.1775686383837.jpg)

#### Example: Add a Dark Mode Toggle
Let's walk through an example. Say your app needs a dark mode toggle. Open the root directory of your project and run `claude`. Press Shift+Tab a couple of times to enter Plan Mode, then write a prompt like:

```
My app needs a dark mode implemented across the entire app. Can you create a toggle switch on the header that allows a user to toggle between light mode and dark mode? I need you to find a good contrast color that works based on my existing light theme.
```

![Entering the dark mode prompt in Claude Code with plan mode enabled](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686383%2Fvideo4demoenteringpromptinplanmode.1775686382790.jpg)

Let Claude plan it out. After reviewing the plan, if it looks good, accept it and let Claude ask you for approval at each step. At the end, you can see exactly what Claude did and how it reached its conclusions.

#### Recap
When using Claude Code, try to be as descriptive as possible with your prompt. If you want to stay in the loop at every step, you can. Use Plan Mode to let Claude dig into the details of what you want to achieve before executing on any code.

---

### 📊 Key Concepts Snapshot

| Mode | What Happens | Toggle |
|---|---|---|
| **Approval mode** | Claude asks before every file edit or command | Default |
| **Auto-accept mode** | File edits auto-approved; commands still ask | Shift + Tab |
| **Plan Mode** | Read-only research + clarifying questions → a plan you approve before any code is written | Shift + Tab (cycle further) |

---

### 🏢 Real-World Scenario

**Situation:** You need a dark mode toggle added across your entire app, touching many components.

**With Plan Mode:** You enter Plan Mode, describe the goal in one detailed prompt, and Claude researches your codebase, picks a good contrast color based on your existing theme, and proposes a plan. You review and approve before a single line of code changes — reducing the chance of a messy, half-finished implementation.

---

### 🤔 Lesson Reflection

- Would you default to Approval mode or Auto-accept mode for your typical day-to-day tasks?
- Think of a multi-step feature you're currently building — how would writing one detailed Plan Mode prompt change your approach?

---

### ⏭️ What's Next

In the next lesson, you'll learn the single most important workflow in this course: **Explore, Plan, Code, and Commit.**

---

[⬅ Previous: Lesson 3 — Installing Claude Code](./Lesson-03-Installing-Claude-Code.md) · [🏠 Course Home](./README.md) · [Next: Lesson 5 — The Explore → Plan → Code → Commit Workflow ➡](./Lesson-05-Explore-Plan-Code-Commit-Workflow.md)
