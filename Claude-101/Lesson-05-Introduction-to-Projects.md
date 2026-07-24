# Lesson 5 — Introduction to Projects

> **Estimated time:** 20 minutes

---

### 📌 What Is This About?

This lesson introduces **Projects** — self-contained workspaces inside Claude with their own memory, chat history, knowledge base, and custom instructions. Think of a Project as a dedicated room for one specific piece of ongoing work, where Claude always remembers what that room is about.

---

### 💡 Why Does This Matter?

Without Projects, you'd have to re-upload the same reference documents and re-explain the same background every single time you start a new chat. That's a huge waste of time, especially for ongoing work like a marketing campaign, a client account, or a recurring report. Projects solve this — set it up once, and every future chat in that Project already "knows" the context.

---

### 📖 The Explanation

#### What are Projects?

Projects are self-contained workspaces with their own memory, chat histories, knowledge bases, and customised instructions — dedicated environments for a specific work stream. They are ideal for:
- Storing knowledge Claude should reference regularly.
- Organising related chats around one topic or work area.
- Collaborating with teammates who need access to the same shared context.

#### When to use Projects

Projects shine for **ongoing** work — not a one-off question. Consider creating a Project when you have:
- **Reference materials you'll use repeatedly** (meeting notes, survey results, reports, historical data).
- **Consistent requirements** for how Claude should respond (always formal, always cite sources, always follow our template).
- **Team collaboration needs**, where multiple people should work from the same foundation.

#### Creating your first project — 3 simple steps

**Step 1 — Set up your project:**
1. Hover the left sidebar and click "Projects," or go to claude.ai/projects.
2. Click "+ New Project."
3. Give it a descriptive name (e.g., "Q4 Marketing Campaign").
4. Add a brief description — Claude doesn't see this directly, but it helps you and your teammates understand the project's purpose.
5. Choose visibility: keep it private, or share with your organisation (Claude for Work users).

**Step 2 — Add project instructions:**
Click "Instructions" to open the panel. Good project instructions typically include:
- **Context** about what you're working on: "This project is for creating marketing content for our B2B software product."
- **Process instructions**: "First consider a blog structure that will entice this audience, then write the draft."
- **Tone and style preferences**: "Use a professional but conversational tone. Avoid jargon when possible."
- **Specific requirements**: "Always include a call-to-action at the end of marketing copy."

Click "Save instructions" — these apply to every chat in the project, alongside any personal preferences and styles you've set. You can even use instructions to automate small workflows: "When I upload a meeting transcript, create a structured summary using this template." Think of instructions as programming Claude's behaviour for this project.

**Step 3 — Build your knowledge base:**
The files menu sits on the right of the project's main page. Click "+" to add content — PDF, DOCX, CSV, TXT, HTML, and more — or connect Google Drive directly.

What to upload: reference documents (brand guidelines, style guides, templates), background materials (research reports, meeting notes, requirement docs), examples of work you want Claude to emulate, and technical documentation.

> **Pro-tip:** Name your files descriptively. Claude uses file names to understand and retrieve the right information, so "Q4-2024-Brand-Guidelines.pdf" is far more useful than "document1.pdf."

#### How Projects handle large knowledge bases

You might wonder what happens when you upload a *lot* of content. Projects automatically scale using a process called **Retrieval Augmented Generation (RAG)**. In simple terms, this means Claude can automatically find and use the most relevant parts of your uploaded documents when answering — without you needing to tell it which file to look at.

When your project knowledge approaches the context window limit, Claude seamlessly switches on RAG mode. Instead of loading everything into memory at once, it intelligently searches and retrieves only the most relevant information needed for your question. This expands your project's capacity by **up to 10x** while keeping response quality high. You'll see a visual indicator when RAG mode is active, but the day-to-day experience stays the same.

#### Working within your project

Once your project is set up, just start chatting. Every conversation inside the project automatically has access to your knowledge base and follows your project instructions.

> **Important nuance:** Context is **not** shared across separate chats within a project unless the information has actually been added to the project's knowledge base. Pasting something into one chat doesn't magically make it available in another chat — only the knowledge base does that. You can also upload content just during one conversation, without adding it to the knowledge base — good for one-off context you don't want cluttering the shared library.

#### Collaboration features (Claude for Work: Team/Enterprise)

**Three permission levels when sharing a project:**
1. **Can view** — see project contents, access knowledge, and chat, but can't make changes (read-only + discussion rights).
2. **Can edit** — full collaboration power: modify instructions, update knowledge, manage other members, contribute actively.
3. **Owner** — project creators control everything, including who can see the project; can share with specific people or the whole organisation.

**To share a project:**
- Open it and click "Share project" (to the right of the project name).
- Add individual members by name/email, or paste a list of emails for bulk sharing.
- Or share with "Everyone at [organisation]" to make it discoverable in the Team tab.
- Teammates get an email notification when shared with them, and can find it under "Shared with me."

#### Example projects to inspire you

- **Q4 product launch** — product specs, competitive analysis, messaging notes, always top of mind for any draft.
- **Research support** — competitive review, user research, customer feedback centralised so Claude can synthesise and draft consistently.
- **Client account hub** — brand guidelines, past deliverables, communication history, so Claude matches the client's tone in every proposal.
- **Event planning workspace** — venue contracts, speaker bios, attendee data feeding into run-of-show documents and post-event reports.
- **Job description generator** — past JDs, team charters, and headcount docs so drafts reflect your team's real culture.
- **New product launch** (e.g., an eco-friendly water bottle) — centralise all product info; use Claude for creative ideation and to track design evolution.
- **Educational course design** (Anthropic even built its own AI Fluency course this way) — organise course materials, explain complex concepts, iteratively improve content.
- **Personal finance tracking** — keep all financial info in one secure place; Claude analyses spending patterns and helps with calculations.
- **Home renovation planning** — centralise contracts, design ideas, budget calculations, and decision history.

#### Best practices for Projects

- **Start focused, then expand** — begin with a specific use case rather than one giant project for everything.
- **Keep your knowledge base current** — outdated documents lead to outdated responses; review periodically.
- **Write clear instructions** — vague instructions lead to inconsistent results.
- **Name documents descriptively** and group related files together — Claude uses filenames and proximity to understand relationships.
- **Reference documents by name** when asking questions: "Based on our Q3 report, what were the top customer concerns?"

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Project** | A self-contained workspace with its own memory, files, and instructions | Avoids re-explaining context every single chat |
| **Project instructions** | Standing rules that apply to every chat in the project | "Programs" Claude's behaviour for that specific work stream |
| **Knowledge base** | The uploaded files a project references automatically | Gives Claude your reference material without re-uploading |
| **RAG (Retrieval Augmented Generation)** | Automatic technique to search large knowledge bases for relevant parts | Lets a project scale up to 10x its normal capacity |
| **Permission levels (View/Edit/Owner)** | Controls over who can see or change a shared project | Keeps collaboration safe and organised on Team/Enterprise plans |

---

### 🏢 Real-World Scenario

**Situation:** You manage a client account and constantly re-explain the client's brand voice and past deliverables to Claude in every new chat.

**With a Project:** You create a "Client Account Hub" project, upload the brand guidelines, past proposals, and communication history once, and write an instruction: "Always match this client's professional-but-warm tone; reference past deliverables when relevant." Every new chat inside this project now automatically knows the client's context — no more re-explaining.

---

### 🤔 Lesson Reflection

- What ongoing work could benefit from having a dedicated project with persistent context?
- What documents do you expect you'll be re-uploading or re-explaining to Claude on a regular basis?
- If you're on a team, are there projects that would benefit from shared knowledge and instructions?

---

### ⏭️ What's Next

In the next lesson, you'll learn how to create mini-apps and outputs with **Artifacts** — actual, usable things Claude builds that you can share right away.
