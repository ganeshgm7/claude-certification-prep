# Lesson 19 — MCP (Model Context Protocol)

[⬅ Previous: Lesson 18 — Troubleshooting Skills](./Lesson-18-Troubleshooting-Skills.md) · [🏠 Course Home](./README.md) · [Next: Lesson 20 — Hooks ➡](./Lesson-20-Hooks.md)

---

### 📌 What Is This About?

**Model Context Protocol (MCP)** is an open standard that lets Claude Code connect to external tools and data sources — databases, productivity apps, and public repositories included. This lesson covers what MCP does, how to add servers, how to scope them, and how to manage the context they cost you.

---

### 💡 Why Does This Matter?

A lot of the context you need for real work doesn't live in your codebase at all — it lives in Linear tickets, documentation sites, or internal databases. MCP bridges that gap so Claude Code can reach it directly, instead of you copy-pasting information back and forth.

---

### 📖 The Explanation

#### What Can You Do With It?
First, it's important to understand the concept of "tools" in agentic AI. Tools give agents like Claude Code the ability to perform actions that help them complete tasks more effectively. This is different from typical AI, where you just get a text response back.

For example, if your team uses Linear for project management, you can add a Linear MCP server to bring in the details of your specific issues. If you need up-to-date documentation for a dependency, a docs MCP server like Context7 can provide that to Claude Code. There are also hundreds of different connectors available at claude.com/connectors.

#### Adding an MCP Server
You can add MCP servers with the `claude mcp add` command. There are two main types:
- **HTTP servers** are for remote services. These are hosted by the service provider and connect over the network.
- **Stdio servers** are for local processes that run on your machine.

You can manage your servers with `/mcp` inside a Claude Code session to see what's connected, check status, and disable servers you don't need.

#### Scoping Servers
MCP servers can be scoped in three ways:
- **Local** — only available in the current project, just for you.
- **User** — available across all your projects.
- **Project** — uses a `.mcp.json` file that you check into version control so anyone on the codebase gets the exact same servers automatically.

#### Context Costs
MCP servers add tool definitions to your context window — even when you're not actively using them. If you have a lot of servers configured, this eats into your available context. Run `/mcp` to see what's connected and disable anything you're not actively using.

If a tool has a CLI equivalent (like `gh` for GitHub or `aws` for AWS), the CLI is more context-efficient because it doesn't add persistent tool definitions.

You might also benefit from using a Skill instead. A Skill has a name and description loaded into context, and Claude only loads the full skill contents when it determines it needs to use it.

If your MCP tools exceed 10% of your context window, Claude Code automatically switches to **tool search mode**, which discovers the right tools on demand — though this may not work as reliably.

#### Recap
MCP connects Claude Code to your external tools and data sources. Add servers with `claude mcp add`. Scope them to your project with `.mcp.json` so your team gets them automatically. And keep an eye on context usage by disabling servers you're not actively using.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **MCP** | Open standard connecting Claude Code to external tools/data | Bridges the gap to context outside your codebase |
| **HTTP server** | Remote MCP service over the network | For cloud-hosted integrations (e.g., Linear) |
| **Stdio server** | Local process on your machine | For local tools/data sources |
| **Local / User / Project scope** | Controls who gets access to a configured server | Project scope (`.mcp.json`) shares servers with your whole team |
| **Context cost** | MCP servers load tool definitions even when unused | Disable unused servers, or use a CLI/Skill instead |
| **10% tool-search threshold** | Auto-switches to on-demand tool discovery past this point | A safety valve, but less reliable than normal loading |

---

### 🏢 Real-World Scenario

**Situation:** Your team uses Linear for issues and needs Claude Code to pull ticket details, but you're worried about bloating everyone's context window with unrelated servers.

**Setup:** Add the Linear MCP server with `claude mcp add`, scope it at the **Project** level via `.mcp.json` so the whole team gets the same server automatically. Periodically run `/mcp` to check what's connected and disable anything the team isn't actively using — keeping context usage lean.

---

### 🤔 Lesson Reflection

- Which of your team's external tools (project management, docs, databases) would benefit most from an MCP server connection?
- Do you have MCP servers configured today that you rarely use? Would a CLI tool or a Skill be more context-efficient?

---

### ⏭️ What's Next

In the final lesson of the course, you'll learn about **Hooks** — how to run commands deterministically at specific points in Claude Code's lifecycle.

---

[⬅ Previous: Lesson 18 — Troubleshooting Skills](./Lesson-18-Troubleshooting-Skills.md) · [🏠 Course Home](./README.md) · [Next: Lesson 20 — Hooks ➡](./Lesson-20-Hooks.md)
