# Lesson 6 — Creating with Artifacts

[⬅ Previous: Lesson 5 — Introduction to Projects](./Lesson-05-Introduction-to-Projects.md) · [🏠 Course Home](./README.md) · [Next: Lesson 7 — Working with Skills ➡](./Lesson-07-Working-with-Skills.md)

> **Estimated time:** 20 minutes

---

### 📌 What Is This About?

This lesson covers **Artifacts** — the standalone, interactive outputs Claude creates in a dedicated window next to your conversation. Instead of a long code block or wall of text buried in chat, you get a working website, an interactive chart, or a downloadable document, ready to use immediately.

---

### 💡 Why Does This Matter?

Chat is great for conversation, but not every output belongs mixed into a scrolling chat log. When Claude builds something substantial — a code snippet, a diagram, a small app — you want to *see* and *use* it directly, not hunt for it inside paragraphs. Artifacts give you a clean, separate, reusable space for exactly that.

---

### 📖 The Explanation

#### What are Artifacts?

Artifacts are standalone, interactive outputs that Claude creates in a dedicated window alongside your conversation. Claude automatically creates one when the content:
- Is significant and self-contained — typically over 15 lines.
- Is something you're likely to want to edit, iterate on, or reuse.
- Represents complex content that stands on its own without needing the surrounding conversation.
- Is content you'll want to reference or use later.

#### Common artifact types

- **Documents** (markdown/plain text) — meeting notes, reports, project plans, blog posts — anything text-heavy you'll want to export or keep editing.
- **Code snippets** — working code in any programming language (Python, JavaScript, C++, and more); view, copy, or download it.
- **HTML pages** — complete web pages with HTML, CSS, and JavaScript in a single file — great for landing pages, forms, interactive demos, or quick prototypes.
- **SVG images** — scalable vector graphics for logos, icons, illustrations — rendered directly in the artifact window.
- **Mermaid diagrams** — flowcharts, sequence diagrams, Gantt charts, org charts. Describe the relationships you want, and Claude builds a diagram you can refine.
- **React components** — interactive UI elements with real functionality: calculators, dashboards, games, data visualisations. These include actual logic and respond to user input — not just mockups.

> **Note:** Word documents, Excel spreadsheets, PowerPoint presentations, and PDFs work differently — Claude creates those through a **separate file creation capability** (covered in the Skills lesson), not as artifacts, and returns them to you as downloadable files.

#### Creating your first artifact

Creating an artifact is as simple as having a conversation. Just describe what you want, and Claude decides whether to present it as an artifact. For example:
- "Create a flowchart showing our customer onboarding process."
- "Build an interactive dashboard that lets me input monthly expenses and see a breakdown."
- "Design a landing page for a productivity app with a hero section and feature list."
- "Write a project brief template I can reuse for new initiatives."

If Claude doesn't automatically create an artifact when you expect one, you can explicitly ask: "Create this as an artifact" or "Show me this in an artifact."

When Claude generates an artifact, it appears in a dedicated window to the right of your conversation. From there, you can:
- **View different formats** — toggle between a preview (how it looks) and the underlying code.
- **Copy content** — click the copy icon to grab it for use elsewhere.
- **Download files** — save the artifact to your computer.
- **View code** — see exactly what Claude generated under the hood.

#### Sharing and publishing artifacts

- **Copy or download** — for personal use or sharing via other channels, use the buttons in the lower right of the artifact window.
- **Share within your organisation (Claude for Work)** — Team and Enterprise users can share artifacts internally; they stay within your organisation and require team authentication to access.
- **Publish publicly** (Free, Pro, and Max users) — make an artifact accessible to anyone with the link:
  - Only the selected version becomes public — your chat itself remains private.
  - Anyone can view and interact with the artifact, even without a Claude account.
  - Others can **"remix"** your artifact — opening it in their own Claude conversation to modify and build upon it.
  - To publish, click the "Share"/"Publish" button in the upper right of the artifact. You can unpublish at any time.
  - Published artifacts are **not indexed by search engines**, so they won't show up in Google results — but the link itself is public to anyone who has it.

#### Tips for getting the most from artifacts

- **Be specific about what you want.** "Build a budget tracker" is fine, but "Build a monthly budget tracker where I can input expenses by category, see a pie chart breakdown, and get a warning when I'm over budget" is much better.
- **Describe the end user.** "This flowchart is for new employees" leads to a different result than "this flowchart is for the engineering team."
- **Iterate incrementally.** Ask Claude to add one feature or make one change at a time — easier to spot what's working and catch issues early.
- **Request artifacts when needed.** If Claude answers in chat instead of building an artifact for something substantial, just say "Please create that as an artifact."

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Artifact** | A standalone, interactive output shown in its own window | Keeps substantial work usable and separate from the chat log |
| **React component artifact** | An artifact with real, working logic — not just a mockup | Lets you build actual mini-tools/calculators/dashboards |
| **Publishing** | Making an artifact accessible via public link | Lets anyone view/interact without needing a Claude account |
| **Remix** | Others opening your published artifact in their own chat to modify it | Turns your artifact into a reusable starting point for others |
| **File creation (separate from artifacts)** | The way Word/Excel/PowerPoint/PDF outputs are generated | Different mechanism, but same idea of a finished, usable output |

---

### 🏢 Real-World Scenario

**Situation:** Your manager asks for a quick internal tool to track monthly team expenses, without waiting for the IT/dev team.

**With artifacts:** You ask Claude: "Build a monthly expense tracker where I can input expenses by category, see a pie chart breakdown, and get a warning if I go over budget." Claude creates it as a React component artifact — a real, working mini-app in the artifact window. You test it, ask for one tweak ("add a monthly total at the top"), then publish it so your team can use the link directly, without needing a Claude account.

---

### 🤔 Lesson Reflection

- What recurring work could benefit from having an interactive artifact you can reuse?
- Are there processes in your work that would be clearer as a flowchart or diagram?
- What prototype or tool would help you test an idea quickly?

---

### ⏭️ What's Next

In the next lesson, you'll learn about **Skills** — reusable instruction sets that teach Claude specialised workflows.

---

[⬅ Previous: Lesson 5 — Introduction to Projects](./Lesson-05-Introduction-to-Projects.md) · [🏠 Course Home](./README.md) · [Next: Lesson 7 — Working with Skills ➡](./Lesson-07-Working-with-Skills.md)
