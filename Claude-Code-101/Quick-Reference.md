# Claude Code 101 — Quick Reference

A one-page cheat sheet covering the whole course. Use this to revise quickly before using Claude Code for real work.

---

## 1. What Claude Code Is
- An **agentic coding tool** — direct access to your files, terminal, and codebase (unlike Claude.ai).
- An **AI Agent**: software operating in a loop, using tools to reach a defined goal.
- Available in: terminal, VS Code, JetBrains, Claude Desktop app, and on the web (`claude.ai/code`).
- 3 things to keep in mind: the **context window** is finite; it **asks permission** by default; it **can make mistakes**.

## 2. How It Works — The Agentic Loop
Prompt → gather context → take action → verify results → done, or loop again.
- **Context window** — Claude's working memory; auto-**compacts** near the limit.
- **Tools** — let Claude *do* things (read files, run commands, search web), not just talk.
- **Permission modes** — Default (asks every time) / Auto-accept (files auto-approved, commands still ask) / Plan mode (read-only research first).

## 3. Installing & First Prompt
- Terminal: curl (macOS/Linux/WSL) or PowerShell `Invoke-RestMethod` (Windows). Run `claude` in your project directory.
- Also installable in VS Code, JetBrains, Desktop, and web.
- **Shift + Tab** cycles: Approval mode → Auto-accept mode → Plan Mode.
- Plan Mode = read-only research + clarifying questions → a plan you approve before code is written.

## 4. The Core Workflow: Explore → Plan → Code → Commit
1. **Explore & Plan** — use Plan Mode; Claude reads files, researches, proposes a plan. Best place to course-correct (before code exists).
2. **Code** — approve the plan; define success criteria; add tools (e.g., Claude in Chrome); include a real test suite.
3. **Commit** — run a **subagent code reviewer** first; then have Claude write the commit message; push.

## 5. Context Management
- `/compact` — summarize the session so far, free space, keep memory of what you did (use when continuing a feature near the limit).
- `/clear` — wipe everything, start fresh (use when starting a new feature, to avoid bias).
- `/context` — see a breakdown of what's consuming your context.
- Tips: be specific (vague prompts cost *more* context); manage/disable unused MCP servers; delegate "just need the answer" tasks to subagents.

## 6. Code Review Features
- Subagent code reviewer (read-only tools) before pushing a PR.
- `/commit-push-pr` — commit + push + open PR in one step.
- `claude --from-pr <PR_NUMBER>` — resume a session linked to an existing PR.

## 7. The CLAUDE.md File
- Root-level Markdown file, read automatically every session — persistent project memory.
- **Project-level** (`.claude`-root, shared via Git) vs. **User-level** (personal, all projects).
- `/init` generates one automatically from your codebase.
- Reference docs with `@filename`. Ask Claude to save recurring corrections to memory.

## 8. Subagents
- Specialized assistants with their own **isolated context window** — return just a summary.
- Built-in: **General purpose**, **Explore**, **Plan**.
- Create custom ones via `/agents` — choose scope (Project/User), tools, model (Haiku/Sonnet/Opus/Inherit), color.
- **Effective subagent = ** specific description + defined output format + obstacle reporting + limited tool access.
- **Use for:** research/exploration, code reviews, custom system prompts (e.g., copywriting, styling).
- **Avoid for:** "expert" persona claims, sequential pipelines (each step depends on the last), test runners (hides full output).
- **Decision rule:** does the intermediate work matter? No → subagent. Yes → main thread.

## 9. Agent Skills
- Markdown files (`SKILL.md`) that teach Claude a task once; Claude applies it automatically when relevant.
- **Personal** (`~/.claude/skills`) vs. **Project** (`.claude/skills`, shared via Git).
- Loads **on demand** (name + description only, until matched) — unlike CLAUDE.md (always loaded) or slash commands (need explicit typing).
- Required fields: `name`, `description`. Optional: `allowed-tools`, `model`.
- **Progressive disclosure:** keep SKILL.md under 500 lines; put details in `scripts/`, `references/`, `assets/`.
- **Priority on name conflict:** Enterprise → Personal → Project → Plugins.
- **Sharing:** commit to repo (team) / distribute via plugin (community) / enterprise managed settings (mandatory, org-wide).
- **Gotcha:** subagents don't auto-inherit skills — list them explicitly in the subagent's `skills` field.
- **Troubleshooting:** not triggering → fix the description/trigger phrases; not loading → check path/filename (`SKILL.md` in a named directory); wrong skill used → make descriptions more distinct; shadowed → check priority, rename; runtime error → check dependencies/permissions/path separators.

## 10. Skills vs. Other Features — Quick Decision Table

| Feature | Trigger | Best For |
|---|---|---|
| **CLAUDE.md** | Always loaded | Always-on project standards |
| **Skills** | On demand (matched by description) | Task-specific expertise |
| **Subagents** | Delegated, isolated context | Work needing isolation / different tools / fresh perspective |
| **Hooks** | Event-driven | Guaranteed, deterministic actions every time |
| **MCP servers** | Always-available tool connections | External tools/data sources |

## 11. MCP (Model Context Protocol)
- Open standard connecting Claude Code to external tools/data (Linear, docs, databases, etc.).
- Add with `claude mcp add`; manage with `/mcp`.
- Types: **HTTP** (remote services) / **Stdio** (local processes).
- Scopes: **Local** (just you, this project) / **User** (all your projects) / **Project** (`.mcp.json`, shared via Git).
- Costs context even when unused — disable unused servers; prefer a CLI (`gh`, `aws`) or a Skill when possible.
- Past 10% of context window in MCP tools → auto-switches to (less reliable) tool search mode.

## 12. Hooks
- Run commands **deterministically** at points in Claude Code's lifecycle — always run, no exceptions.
- Events: **PreToolUse**, **PostToolUse**, **UserPromptSubmit**, **Stop**, **Notification**.
- Configure via `/hooks` or `settings.json`.
- PreToolUse exit codes: **0** = proceed, **2** = block (stderr fed back to Claude), other = non-blocking error shown to you.
- Common use: PostToolUse auto-formatting; PreToolUse blocking dangerous commands (e.g., `rm -rf`, writes to production config).
- Share via `.claude/settings.json` (checked into repo); use `CLAUDE_PROJECT_DIR` for portable script paths.
- **Rule of thumb:** if it must happen every time without fail, put it in a hook — not a prompt.
