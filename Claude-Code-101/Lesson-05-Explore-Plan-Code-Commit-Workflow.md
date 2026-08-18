# Lesson 5 — The Explore → Plan → Code → Commit Workflow

[⬅ Previous: Lesson 4 — Your First Prompt](./Lesson-04-Your-First-Prompt.md) · [🏠 Course Home](./README.md) · [Next: Lesson 6 — Context Management ➡](./Lesson-06-Context-Management.md)

---

### 📌 What Is This About?

If you take away just one thing from this whole course, make it this workflow: **Explore, Plan, Code, and Commit.** This lesson walks through each of the four steps and why skipping straight to "write the code" causes more course-correcting later.

---

### 💡 Why Does This Matter?

Most people jump straight to asking Claude to write code. That feels faster in the moment, but it usually means more back-and-forth fixing things afterward. This workflow front-loads the thinking — so by the time code actually gets written, everyone (you and Claude) already agrees on what "done" looks like.

---

### 📖 The Explanation

#### Explore and Plan
The fastest way to handle these first two steps is with **Plan Mode**. In plan mode, Claude can't edit files — it just reads files to gather information about how it will tackle the implementation. To enter plan mode, press Shift+Tab until you see "Plan Mode" under the text input.

![Claude Code status bar showing plan mode on with shift+tab to cycle](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686390%2Fvideo5planmodeshifttab.1775686390450.jpg)

Example prompt:
```
I need to add WebP conversion to our image upload pipeline. Figure out where in the pipeline it should happen, whether we need new dependencies, and how to approach it.
```

Claude will read relevant files, run some web searches, and give you a plan of action. Review it and decide if it meets your criteria. If not, ask it to revise specific areas.

![Claude Code presenting the plan with options to approve, revise areas, or ask questions](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686389%2Fvideo5planmodereviseareas.1775686389692.jpg)

This is the best place to course-correct because it's before any code is written. You can also run the **explore subagent** without being in plan mode if you just want a general summary of your codebase without intending to make changes afterward.

#### Code
Once the plan looks good, select "approve" to accept it and let Claude work through the list items. You can choose whether Claude auto-accepts file edits or asks you each time.

Claude will do its best to troubleshoot before considering the plan "finished," but at times you'll need to step in. This is the benefit of working with Plan Mode — after execution, you also have the context of how you got to the results, which helps guide Claude's next decisions.

A few tips to make the coding phase smoother:
- **Define a success criteria.** For Claude to be confident in its results, it needs to be clear on what "correct" looks like. Make this explicit when writing your plan.
- **Add tools.** Tools that help Claude complete its goals remove a lot of back and forth. For example, if you're building web UIs, install the Claude in Chrome extension so Claude Code can control a browser tab and test the UI directly.

  ![The Claude in Chrome extension page in the Chrome Web Store](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686387%2Fvideo5claudeinchromeextension.1775686387012.jpg)
- **Include a test suite.** Give Claude a test suite it can continuously validate against. Claude can even write tests for you. Before handing this off, make sure the tests are a reliable source of truth to avoid false positives.

> **Quick tip:** If you find Claude keeps running into the same issues, ask it to save the solution to its **CLAUDE.md** file (covered in Lesson 8).

#### Commit
Once you've tested the changes yourself and are happy with the results, it's time to push your code. Before you commit, run a **subagent code reviewer** to look at your work. A subagent gets a fresh pair of eyes on the codebase — it doesn't carry the bias the main agent might have from the session.

![A code-reviewer subagent running in Claude Code, reading files and reviewing recent changes](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686388%2Fvideo5claudesubagentcodereviewer.1775686387773.jpg)

Then get Claude to generate a commit message in your style. Rinse and repeat.

#### Recap
To be effective with Claude Code, follow the Explore, Plan, Code, and Commit workflow:
- **Explore** gives Claude the relevant context it needs for your project.
- **Plan** creates a plan of action that Claude uses to measure success.
- **Code** is the back and forth between you and Claude before settling on the final outcome.
- **Commit** helps you review and push your code so you can start on your next feature.

---

### 📊 Key Concepts Snapshot

| Step | What Happens | Key Tip |
|---|---|---|
| **Explore** | Claude reads relevant files (read-only) | Best moment to course-correct — before any code exists |
| **Plan** | Claude proposes a step-by-step plan | Define success criteria explicitly |
| **Code** | Claude implements the approved plan | Add tools (e.g., Claude in Chrome) + a real test suite |
| **Commit** | Review, subagent code review, then push | Use a subagent reviewer for unbiased fresh eyes |

---

### 🏢 Real-World Scenario

**Situation:** You need to add WebP image conversion to an existing upload pipeline you didn't build.

**Following the workflow:** You enter Plan Mode and describe the goal. Claude explores the pipeline, researches dependencies, and proposes where the conversion step should go. You review and approve. Claude implements it, testing against your existing test suite. Before committing, a subagent code reviewer checks the diff with fresh eyes, then Claude writes the commit message in your team's style.

---

### 🤔 Lesson Reflection

- Think about your last few Claude Code sessions — did you skip straight to "Code" without exploring or planning first?
- What would a good "success criteria" look like for a feature you're currently building?

---

### ⏭️ What's Next

In the next lesson, you'll dig into **Context Management** — what the context window is, how compaction works, and when to use `/compact` vs. `/clear`.

---

[⬅ Previous: Lesson 4 — Your First Prompt](./Lesson-04-Your-First-Prompt.md) · [🏠 Course Home](./README.md) · [Next: Lesson 6 — Context Management ➡](./Lesson-06-Context-Management.md)
