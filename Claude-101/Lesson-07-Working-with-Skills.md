# Lesson 7 — Working with Skills

> **Estimated time:** 15 minutes

> **Plan availability:** Skills are currently a feature preview for Pro, Max, Team, and Enterprise plans. If you're on the Free plan, read along to understand the concept and skip the hands-on steps.

---

### 📌 What Is This About?

This lesson introduces **Skills** — folders of instructions, scripts, and resources that Claude loads dynamically to get better at specialised tasks. Think of a Skill as a packet of "expertise" you hand to Claude so it repeats a specific process the exact same rigorous way, every single time.

---

### 💡 Why Does This Matter?

If your team has a specific way of doing something — a quarterly variance analysis, a brand-voice review checklist, a compliance process — you don't want Claude to improvise a slightly different approach every time. Skills let you codify that process once, so Claude follows your exact method consistently, without you having to re-explain it in every conversation.

---

### 📖 The Explanation

#### What are Skills?

Skills are folders of instructions, scripts, and resources that Claude loads dynamically to improve performance on specialised tasks. You've already seen Skills at work if you've used Claude to create Excel spreadsheets, PowerPoint presentations, Word documents, or PDFs — those file-creation capabilities are powered by Skills running behind the scenes.

But Skills go far beyond document creation. Custom Skills can codify entire repeatable workflows — a quarterly variance analysis methodology, a brand voice review process, or a compliance checklist — so Claude follows the same rigorous steps every time.

#### Two types of Skills

- **Anthropic Skills** — created and maintained by Anthropic. These include enhanced document creation for Excel, Word, PowerPoint, and PDF files. Available to all paid users, and Claude invokes them automatically when relevant — you don't need to do anything special.
- **Custom Skills** — created by you or your organisation for specialised workflows and domain-specific tasks. For example, applying your company's brand guidelines to presentations, structuring meeting notes in a specific format, or running your organisation's own data-analysis workflow.

#### Enabling Skills

Skills need Claude's secure, sandboxed computing environment to run, so you must have **Code execution and file creation** enabled first.

1. Go to **Settings > Capabilities**.
2. Ensure **Code execution and file creation** is toggled on.
3. Scroll to the **Skills** section.
4. Toggle individual skills on or off as needed.

- **Enterprise plans:** organisation Owners must first enable both Code execution and Skills in Admin settings before individual members can access them.
- **Team plans:** this is enabled by default at the organisation level.

Once enabled, you'll see available Skills listed in Settings — Anthropic's built-in ones plus any custom Skills you've uploaded.

#### Using Skills in practice

The nice thing about Skills is you usually don't need to think about them — Claude picks the right Skill automatically based on your request. Examples of prompts that would invoke Skills:
- "Create an Excel spreadsheet tracking monthly expenses with formulas for totals."
- "Turn this meeting notes document into a PowerPoint presentation."
- "Generate a PDF report summarising this data."
- "Build a financial model in Excel with scenario analysis."

When Claude uses a Skill, you'll see it mentioned in Claude's chain of thought as it works. The output will be a downloadable file you can save to your computer or directly to Google Drive.

#### File execution — working with your actual files

This same capability means Claude can work with your **actual files** (within a contained environment) to create updated versions. Note: in Chat, Claude creates a **new version** of the document rather than editing the original in place. You can upload slides, spreadsheets, contracts (.xlsx, .pptx, .docx, or .pdf), and Claude will create slides, run analyses, and add suggested edits — download the result, or open it in Drive.

> **Note:** To use these capabilities, you'll need to give Claude access to external data sources — simply toggle "Allow limited network access" on when prompted.

#### Security considerations

Because Skills can include executable code, use them thoughtfully:
- Only install custom Skills from trusted sources.
- Anthropic's built-in Skills are tested and maintained by Anthropic.
- Custom Skills you upload are private to your individual account.
- If installing a custom Skill from an external source, review its contents first to understand what it actually does.

#### Creating custom Skills

The real power of Skills comes from building your own — teaching Claude your specific workflows, brand guidelines, and ways of working, so Claude applies that knowledge automatically whenever relevant. The easiest way is through plain conversation with Claude itself — no code, no manual file creation required.

**Steps to create a Skill through conversation:**
1. **Start a new chat** and tell Claude what you want to create — e.g., "I want to create a skill for writing quarterly business reviews" or "I need a skill that applies our brand guidelines to presentations."
2. **Answer Claude's questions.** It will interview you: What should this skill do? What makes good output for this type of work? Can you give examples of when you'd use this skill?
3. **Upload reference materials** if you have them — templates, style guides, brand assets, or examples of proud work.
4. **Save your skill.** Claude generates a file containing your properly structured Skill — save it and it's ready to use.

**See your skills:** Find the **Customize** tab in the left sidebar to see all skills available to you, and edit them manually or by chatting with Claude. From that point on, Claude automatically invokes the Skill whenever you work on relevant tasks — no manual triggering needed. You can improve a Skill over time simply by asking Claude to edit it.

#### Skills vs. Projects — what's the difference?

Simple way to remember it: **Projects store knowledge, Skills perform tasks.**

- **Projects** are knowledge hubs — they hold the reference materials Claude needs to understand your work (specs, meeting notes, research documents). Claude draws on this across every conversation in that project.
- **Skills** are procedural machines — they encode *how* Claude should execute a task: the specific steps, order of operations, and methodology you want followed every time.

The two complement each other. A Skill can even reference knowledge stored in a Project — for example, a "customer call prep" skill might pull from customer profiles uploaded to a project's knowledge base. **The project provides the "what" (information); the skill provides the "how" (process).**

| | Projects | Skills |
|---|---|---|
| **Purpose** | Store knowledge Claude references | Define processes Claude executes |
| **Best for** | Long-term context, reference materials, team collaboration | Repeatable workflows, multi-step tasks, consistent methodology |
| **Example** | Customer hub, research buddy, feedback generator | Process guidelines (brand or legal), blog drafting, PDF creation |
| **Persistence** | Knowledge available across all chats in the project | Instructions applied whenever the skill is invoked |

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Skill** | A packaged set of instructions/scripts Claude loads for a specific task | Gives Claude a repeatable "how-to" for a specialised job |
| **Anthropic Skills** | Built-in Skills for document creation (Excel/Word/PPT/PDF) | Work automatically, no setup needed for most users |
| **Custom Skills** | Skills you or your org create for your own workflows | Lets you codify your team's exact process |
| **Code execution and file creation** | The sandboxed environment Skills need to run | Must be turned on before Skills will work |
| **Projects vs Skills** | Projects = knowledge, Skills = process | Use both together for the best result |

---

### 🏢 Real-World Scenario

**Situation:** Your marketing team always follows the same 5-step process for reviewing blog drafts against brand voice guidelines, but every writer explains this process to Claude differently.

**With a Custom Skill:** Someone creates a "Brand Voice Review" Skill through a simple conversation with Claude, uploading the brand guide and a couple of example "before/after" edits. From then on, anyone on the team can just say "review this draft against our brand voice," and Claude automatically applies the exact same 5-step method — consistent quality, no re-explaining.

---

### 🤔 Lesson Reflection

- What types of documents do you create regularly that could benefit from Claude's built-in Skills?
- Are there repetitive workflows in your work that might be good candidates for custom Skills?
- How might Skills change the way you think about document creation and data analysis?

---

### ⏭️ What's Next

Next module: **Expanding Claude's reach** — starting with Connectors, which make information gathering seamless and let Claude perform actions right inside the tools where your work is happening.
