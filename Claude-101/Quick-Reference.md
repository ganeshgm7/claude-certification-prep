# Claude 101 — Quick Reference

A one-page cheat sheet covering the whole course. Use this to revise quickly before you use Claude for real work, or before any assessment.

---

## 1. What Claude Is

- Claude = an AI assistant designed to be a **thinking partner**, not just a chatbot.
- Built on **Constitutional AI** to be **helpful, harmless, and honest**.
- **Steerable** — takes direction on tone, personality, behaviour.
- Access it via **web, desktop, and mobile apps**, on Free/Pro/Max/Team/Enterprise plans.
- Big strengths: writing, research & analysis (large context window: 200K+ tokens, up to 1M on some plans), coding, problem-solving/reasoning (hybrid models + extended thinking), and learning (Learning mode).

## 2. The 3-Part Prompt Framework

1. **Setting the stage** — your role, objective, relevant context.
2. **Defining the task** — the specific action you want (write/analyse/build/etc.).
3. **Specifying rules** — tone, style, format, examples.

*(Adapted from the 4D Framework for AI Fluency — Delegation, Description, Discernment, Diligence.)*

## 3. Fixing Common Problems

| Problem | Fix |
|---|---|
| Too generic | Add audience/role/constraint details |
| Too long/short | State the exact length you want |
| Wrong format | Show an example format or describe structure explicitly |
| Confidently wrong facts | Verify independently; ask for citations/confidence; enable web search |
| Wrong tone | Describe the tone in plain words; give a style example |

## 4. AI Fluency & the 4 Ds

- **AI Fluency** = judgement to use AI well, not just tool tricks.
- **Delegation** — who does what (human vs AI).
- **Description** — communicating clearly with AI.
- **Discernment** — critically evaluating AI output.
- **Diligence** — using AI responsibly/transparently.
- **Evals** = testing Claude against known-answer examples from your own work (the "delegation-diligence loop").

## 5. Claude Desktop App — 3 Modes

| Mode | Best For |
|---|---|
| **Chat** | Quick Q&A, brainstorming, drafting (+ quick entry, screenshots, dictation on Mac) |
| **Cowork** | Big multi-step jobs: research, file organisation, scheduled tasks, subagents |
| **Code** | Real software development — Ask/Code/Plan modes, visual diffs, git, local or remote |

## 6. Projects

- Self-contained workspace: own memory, knowledge base, and instructions.
- Setup: New Project → name/description/visibility → write instructions → upload knowledge base.
- Auto-scales via **RAG** (Retrieval Augmented Generation) up to 10x capacity.
- Permission levels for sharing: **Can view / Can edit / Owner**.

## 7. Artifacts

- Standalone outputs shown in their own window: documents, code, HTML pages, SVGs, Mermaid diagrams, React components.
- Auto-created when content is significant/self-contained (typically 15+ lines).
- Can copy, download, share within org, or **publish publicly** (link-only, not search-indexed).
- Word/Excel/PowerPoint/PDF use a **separate file-creation** capability, not artifacts.

## 8. Skills

- Folders of instructions/scripts Claude loads for specialised, repeatable tasks.
- **Anthropic Skills** (built-in, e.g. document creation) vs **Custom Skills** (your own workflows).
- Enable via Settings > Capabilities > Code execution and file creation, then toggle Skills.
- Create custom Skills just by chatting with Claude and answering its questions.
- **Rule of thumb:** Projects store knowledge, Skills perform tasks.

## 9. Connectors

- Link Claude to your tools: **web connectors** (Slack, Gmail, Notion, Google Drive, etc.) or **desktop extensions** (local apps via Desktop app).
- Powered by **MCP (Model Context Protocol)** — "USB-C for AI."
- Setup: find in directory (claude.ai/directory) → Connect → Authenticate → Grant permissions → Test.
- Claude only ever sees what *you* have access to; access is revocable anytime.

## 10. Enterprise Search

- Team/Enterprise only. Adds "Ask {Your Org}" to sidebar — a pre-built Project for the whole company.
- Two-step setup: Admin configures Documents + Chat connectors org-wide → each user authenticates personally.
- Shows only what you already have permission to see; always cites sources.

## 11. Research Mode

- Agentic, multi-step, multi-source deep-dive investigation.
- Auto-enables extended thinking; takes 5–45 minutes; always cites sources.
- Use Research for: comprehensive/comparative reports. Use **web search** for quick facts. Use **extended thinking** for pure reasoning (no external info needed). Use **Enterprise Search** for internal company knowledge.
- Enable via "+" menu > Research (requires web search on).

## 12. Use-Cases by Role (examples)

- **Sales:** battle cards, deal prep, pipeline reports.
- **Marketing:** campaign analysis, repurposing content.
- **Finance:** financial models, investment memos, understanding inherited spreadsheets.
- **HR:** onboarding guides.
- **Legal:** discovery timelines.
- **Research:** literature review planning, verifying stats.

## 13. Other Ways to Work with Claude

| Tool | Where It Lives | Best For |
|---|---|---|
| Claude Code | Terminal/IDE/browser/Slack | Software development |
| @Claude | Slack | Team collaboration, meeting prep |
| Claude Design | Web | UI prototypes from briefs/sketches |
| Claude for Excel/PowerPoint/Word/Outlook | MS 365 sidebar | Editing in place, carrying context across docs |
| Claude in Chrome | Chrome sidebar | Web research, form-filling, browser automation (public beta, permission-gated) |

---

> **Note on missing content:** The "Conclusion & Certificate" module (final recap, quiz, and certificate of completion) was not provided in the source material used to build these notes, so it is not covered here. Everything else from the Claude 101 curriculum (12 lessons across 4 modules) is captured above and in the individual lesson files.
