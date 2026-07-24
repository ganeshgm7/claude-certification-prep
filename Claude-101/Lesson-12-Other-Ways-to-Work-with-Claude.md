# Lesson 12 — Other Ways to Work with Claude

> **Estimated time:** 10 minutes

---

### 📌 What Is This About?

This final content lesson is a tour of all the other specialised places you can use Claude beyond claude.ai — Claude Code, @Claude in Slack, Claude Design, Claude for Excel/PowerPoint/Word/Outlook, and Claude in Chrome.

---

### 💡 Why Does This Matter?

Remember from Lesson 1 — Claude is an intelligence, and claude.ai is just one door into it. If you only ever use the web chat, you'll keep switching out of your actual tools to ask Claude something, then switching back to apply the answer. These specialised products remove that friction by bringing Claude directly into the place where the work already happens.

---

### 📖 The Explanation

#### Claude Code

An agentic coding tool that works where you work — terminal, IDE, browser, or even Slack. It understands your codebase, executes commands, and handles entire development workflows through natural language.

**When to use it:**
- Build features by describing what you need in plain English, and have Claude write the code, run tests, and create commits.
- Debug issues by pasting error messages and letting Claude analyse your codebase to find and fix problems.
- Navigate an unfamiliar codebase by simply asking how different parts work together.
- Automate tedious tasks like fixing lint errors, resolving merge conflicts, or writing release notes.
- You prefer working in your terminal alongside your existing IDE rather than switching to a separate interface.

#### @Claude (Slack)

Brings Claude directly into Slack — get help in channels and threads, or bring Slack context into your Claude conversations, just by tagging @Claude in any thread.

**When to use it:**
- Draft responses, summarise lengthy threads, or break down complex discussions without leaving Slack.
- Prepare for meetings by having Claude pull together relevant conversations and shared documents.
- Onboard to a new team by reviewing channel history to understand ongoing projects.
- Hand off coding tasks directly from a bug report or feature discussion — tag @Claude and it can spin up a Claude Code session using the surrounding context.
- Get quick answers about industry trends, technical concepts, or company info without leaving the conversation.

**From the "Claude Tag" launch video:** at Anthropic, Claude Tag opens **65% of their own product pull requests**. In one example, a sales rep hears that a feature ("Scheduled Exports") is blocking their biggest deals. The person who hears this doesn't own the feature, so they ask the owner in a thread; a teammate tags Claude, which follows the multi-player group conversation, reacts to decisions made in real time, opens the pull request, and lands the change — all while knowing the feature affects launch marketing too. A few important safety details: **Claude has its own account and its own permissions** — access is scoped per-team/per-channel (Claude in the legal channel can see contract info; in engineering it can edit the codebase, but tagging it in legal to edit code simply won't work — it literally cannot see the codebase from there). Memory respects the same boundaries: what Claude learns in a private channel or DM stays there. Every credential use is logged, since Claude has its own account.

#### Claude Design

A dedicated space for turning ideas into working interfaces. Describe what you want in plain language — or start from a sketch or screenshot — and Claude builds an interactive prototype you can refine through conversation and hand off to your team.

**When to use it:**
- Go from a written brief, sketch, or reference screenshot to a working UI prototype without writing code.
- Explore design directions and generate/compare several variations quickly.
- Iterate on layout, copy, or interactions by describing the change rather than editing markup.
- Get a prototype that uses your team's design system, so what you hand off matches what engineering will build.

#### Claude for Excel

Brings Claude directly into Microsoft Excel through a sidebar, letting you analyse, understand, and modify spreadsheets through conversation.

**When to use it:**
- Understand how formulas or calculation flows work across a complex, multi-tab workbook.
- Update assumptions/inputs across your model while preserving formula dependencies.
- Debug spreadsheet errors like #REF!, #VALUE!, or circular references, and get Claude to trace them to their source and suggest fixes.
- Create new spreadsheets or populate existing templates while maintaining proper formula structure.
- Quickly build pivot tables or charts to visualise your data.

**From the demo video:** the presenter had an inherited HR headcount planning model with multiple tabs and lots of cross-linked formulas. Asking Claude "Walk me through this workbook — what's on each tab and how do they connect?" got a full explanation of the data flow (Assumptions → Headcount → Compensation → Summary) in seconds — the kind of understanding you'd normally only get from the person who built it. Claude also proactively spotted a #REF! error, traced it, and fixed it after being told to "use your best judgement." It then handled a "what if attrition is 15% instead of 10%" scenario by updating the Assumptions tab and explaining what changed everywhere else, built a pivot table and chart for a department/level breakdown, and added a brand-new "fully loaded cost per employee" column using an actual formula (not just static numbers) referencing the Assumptions tab.

#### Claude for PowerPoint

Brings Claude into PowerPoint as a sidebar, so you can draft, edit, and restructure presentations through conversation while keeping your existing template and brand styling intact.

**When to use it:**
- Turn an outline, document, or set of notes into a first-draft slide deck without building each slide by hand.
- Rewrite or tighten slide copy — shortening bullets, adding speaker notes, adjusting tone for a specific audience.
- Restructure an existing deck — reordering sections, splitting dense slides, merging overlapping ones.
- Apply consistent formatting across the deck without manually fixing each slide.
- Get quick visual suggestions — which layout or chart type best fits the point you're making.

#### Claude for Word

Brings Claude into Word as a sidebar, so you can draft, revise, and restructure the document you have open — working with tracked changes and comments, and pulling context from connected sources.

**When to use it:**
- Turn an outline or rough notes into a structured first draft in your team's template.
- Revise a section — tighten the writing, adjust tone, or rework structure — without leaving the document.
- Respond to reviewer comments and tracked changes, working through them in place.
- Ground the draft in source material you've connected, so claims trace back to where they came from.

#### Claude for Outlook

Brings Claude into your inbox as a sidebar — triage mail, draft replies with context from related threads and your calendar, and turn a long email chain into a clear summary or set of next steps.

*Availability: currently in beta, installed separately from the other Microsoft 365 add-ins.*

#### Claude in Chrome

A browser extension that adds Claude as a sidebar in Google Chrome. It can observe what you're working on and take actions directly within your browser.

**When to use it:**
- Summarise articles, research papers, or web pages while browsing.
- Draft email responses or manage your inbox.
- Automate filling out repetitive forms.
- Test website features or navigate multi-step workflows without manually clicking through each step.
- Use it as a browsing assistant that keeps context as you move between tabs and tasks — great for pulling context from niche internal tools, CRMs, or dashboards.

**Important note:** Claude in Chrome is currently in public beta. Anthropic recommends using it only for low-risk tasks on trusted websites. The extension asks for permission before taking high-risk actions like purchasing or sharing personal data, and certain categories of websites (financial services, adult content) are blocked by default.

**From the demo video:** Claude in Chrome (powered by Sonnet 4.5) helped organise a home renovation budget spread across a planning doc and several contractor email exchanges — it found the relevant emails/receipts, updated the budget spreadsheet in real time, and drafted an email to share the plan with a partner (with the user still in control of the final send). Safety features shown: granular permissions on what actions Claude can take, protection against prompt-injection attacks, restrictions on which websites Claude can use, and it always asks before sensitive actions like making purchases.

#### Summary table

| Tool | Best For | Where It Runs |
|------|----------|----------------|
| **Claude.ai** | General tasks, research, writing, analysis, file creation | Web, desktop, and mobile apps |
| **Claude Code** | Software development, codebase navigation, git workflows | Terminal/command line, IDE, or your browser |
| **Claude Cowork** | Complex, multi-step tasks: research briefs, document creation, file organisation, data analysis | Desktop (and mobile via Dispatch) |
| **@Claude** | Team collaboration, meeting prep, quick answers in context | Slack workspace |
| **Claude Design** | UI prototypes, design exploration, design-system-aware mockups | Web |
| **Claude for Microsoft 365** | Editing in place and carrying context across documents | Excel, PowerPoint, Word, and Outlook sidebars |
| **Claude in Chrome** | Web research, email management, browser automation | Chrome browser sidebar |

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Claude Code** | Agentic coding tool across terminal/IDE/browser/Slack | Best door in for real software development |
| **@Claude** | Claude tagged directly inside Slack threads | Keeps team collaboration inside the tool your team already lives in |
| **Claude Design** | Turns briefs/sketches into working UI prototypes | No-code way to go from idea to interface |
| **Claude for Microsoft 365** | Sidebar inside Excel/PowerPoint/Word/Outlook | Lets Claude work in the exact document you already have open |
| **Claude in Chrome** | Browser sidebar with permission-gated actions | Brings Claude into any website you're browsing, safely |

---

### 🏢 Real-World Scenario

**Situation:** You're an engineer who just got tagged in a Slack thread about a customer-blocking bug, and you also need to update a project spreadsheet afterward.

**How this lesson applies:** You tag @Claude directly in the Slack thread — it already has the context of the discussion, and can spin up a Claude Code session to investigate and fix the bug, opening a pull request. Later, you open the project workbook and use Claude for Excel to update the affected timeline and regenerate a status chart — all without switching to a separate chat window and re-explaining your context each time.

---

### 🤔 Lesson Reflection

- Which of these tools would fit most naturally into your current daily workflow?
- Is there a task you do today by manually switching between apps that one of these integrations could simplify?

---

### ⏭️ What's Next

This wraps up the lesson content of Claude 101. The course itself closes with a short recap and a quiz to earn your **certificate of completion**, which you can share on LinkedIn and with your team. *(Note: the detailed content for the "Conclusion & Certificate" module — including the recap and quiz — was not provided in the source material for these notes, so it isn't covered here.)*
