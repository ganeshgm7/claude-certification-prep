# Lesson 8 — Connecting Your Tools

> **Estimated time:** 20 minutes

---

### 📌 What Is This About?

This lesson covers **Connectors** — the feature that lets Claude actually read information from, and take actions inside, the tools you already use every day: Gmail, Slack, Notion, Google Drive, Asana, and many more.

---

### 💡 Why Does This Matter?

Without connectors, you have to manually copy-paste information into Claude every time — an email thread, a spreadsheet, a Slack conversation. That's slow and error-prone. With connectors, Claude works directly with your real, live data — turning it from "an assistant you feed information to" into "a collaborator who already has the context."

---

### 📖 The Explanation

#### What are connectors? — Key takeaways

- Connectors transform Claude from an assistant into an **informed collaborator** by giving it access to the same tools, data, and context you use every day. Instead of starting every conversation from scratch, Claude works directly with your actual information.
- Connectors let Claude **read information and perform actions** on your behalf. Depending on the connector and the permissions you grant, Claude can search files, retrieve documents, analyse data, create content, update records, and execute tasks across your connected apps — all from within your conversation.
- The **Model Context Protocol (MCP)** powers connectors. Think of MCP like **USB-C for AI** — a universal standard that lets Claude connect to many different applications through one single, consistent interface. Because it's an open standard, developers can build connectors for any tool, and those connectors work seamlessly with Claude.
- There are **two types of connectors**: **web connectors**, which link Claude to cloud services like Google Drive, Notion, Slack, and Asana; and **desktop extensions**, which run locally on your computer through the Claude Desktop app, giving Claude access to local files and native applications.

#### Finding and connecting tools

Anthropic maintains a directory of recommended connectors at **claude.ai/directory**, organised into two tabs:
- **Web** — cloud services and applications (Gmail, Notion, Slack, Asana, Linear, Stripe, and many more).
- **Desktop extensions** — local tools that run on your computer through the Claude Desktop app.

You can also browse connectors by clicking the **+** button in the lower left of the chat window, then selecting **Connectors**.

**Setting up a web connector:**
1. **Find the connector** — go to claude.ai/directory, or click "+" > Connectors in any chat.
2. **Click Connect** on the connector you want to add.
3. **Authenticate** — you'll be redirected to the service's login page; sign in with your existing credentials.
4. **Grant permissions** — review the specific permissions Claude is requesting, then authorise access.
5. **Test the connection** — return to Claude and try a simple request like "Can you access my [tool name]?"

Once connected, Claude can search, read, and in some cases take actions within that service — depending on the permissions you granted.

**Desktop extensions** require the Claude Desktop app rather than the web interface. They let Claude interact with local applications, your file system, and native OS features on macOS or Windows — examples include local file access for reading/organising documents, browser control for automated web tasks, and native app integration (like Figma for design work).

To install a desktop extension:
1. Download and install the Claude Desktop app.
2. Open the app and go to **Settings > Extensions**.
3. Browse available extensions and click **Install**.
4. Follow any additional setup steps specific to that extension.

#### Using connectors in your work — practical examples

**Project management (Asana, Linear, Jira):**
- "What are my highest priority tasks due this week?"
- "Create a new task for reviewing the Q4 budget proposal."
- "Summarize the status of our product launch project."

**Communication (Slack, Gmail):**
- "Find the email thread where we discussed the vendor contract."
- "Draft a reply to the latest message in the #marketing channel."
- "What did the team decide about the timeline in yesterday's discussion?"

**Documentation (Notion, Google Drive, Confluence):**
- "Search our documentation for our brand voice guidelines."
- "Summarize the meeting notes from last week's product review."
- "What does our style guide say about using contractions?"

**Business tools (Stripe, PayPal, Salesforce):**
- "Show me revenue trends for the past quarter."
- "What's the status of the Acme Corp opportunity?"
- "List recent transactions over $1,000."

#### Security and permissions

When you connect Claude to an external service, you're granting it access to read — and sometimes modify — data within that service. A few important points to keep in mind:

- **Scoped access** — permissions are specific to what the connector needs, and you can toggle individual permissions on/off within each application's menu.
- **Claude sees what you see** — Claude can only access data *you* have access to. Connecting your work email doesn't give Claude access to your CEO's inbox, only yours.
- **Revocable at any time** — you can disconnect a service through Claude's settings, or through the third-party service's own security settings. Just like with Skills, you can also find or build custom connectors — exercise the same caution and only install connectors from trusted sources.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Connector** | A link between Claude and an external app/tool | Gives Claude real, live access to your data instead of manual copy-paste |
| **Model Context Protocol (MCP)** | The open standard that powers connectors — "USB-C for AI" | Lets any tool builder create a connector that works with Claude |
| **Web connector** | Connects Claude to a cloud service (Slack, Gmail, Notion, etc.) | Covers most day-to-day SaaS tools |
| **Desktop extension** | Connects Claude to local apps/files via the Desktop app | Covers native, on-computer tools and file systems |
| **Scoped access** | Claude only sees what your own account can see | Keeps connectors safe — no accidental over-access |

---

### 🏢 Real-World Scenario

**Situation:** Before a client meeting, you need to know what was last discussed in Slack, find the relevant email thread, and check the project's current status in Asana — normally three separate app switches.

**With connectors set up:** You simply ask Claude in one chat: "Summarize the latest Slack discussion, find the email thread about the vendor contract, and give me the current status of the project in Asana." Claude pulls from all three connected tools and gives you one consolidated answer — no manual searching required.

---

### 🤔 Lesson Reflection

- Which of your daily work tools would be most valuable to connect to Claude?
- What tasks currently require you to copy and paste information that connectors could handle automatically?
- Are there workflows where combining data from multiple connected sources would save you significant time?

---

### ⏭️ What's Next

In the next lesson, you'll learn about **Enterprise Search** — a specialised feature for Claude for Work users that connects Claude to your organisation's knowledge sources, with custom prompts optimised for your company's context.
