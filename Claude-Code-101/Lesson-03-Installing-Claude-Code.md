# Lesson 3 — Installing Claude Code

[⬅ Previous: Lesson 2 — How Claude Code Works](./Lesson-02-How-Claude-Code-Works.md) · [🏠 Course Home](./README.md) · [Next: Lesson 4 — Your First Prompt ➡](./Lesson-04-Your-First-Prompt.md)

---

### 📌 What Is This About?

A step-by-step walkthrough of installing Claude Code — in your terminal, Visual Studio Code, JetBrains IDEs, the Claude Desktop app, and on the web — plus guidance on which option to pick.

---

### 💡 Why Does This Matter?

Claude Code works a little differently in each environment. Picking the right one for how you actually work (and knowing how to set it up correctly) means less friction on day one and lets you get to real, productive use faster.

---

### 📖 The Explanation

#### Terminal
- **macOS, Linux, or WSL** — use the curl command to install in one go. If you prefer Homebrew, `brew install` also works, but note this method doesn't support auto-updates.
- **Windows** — a few options: in PowerShell, use the `Invoke-RestMethod` command; in CMD, use the curl command. There's also a winget command, though like Homebrew, it won't auto-update.

![Terminal showing Claude Code successfully installed via curl](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686381%2Fvideo3terminalinstall.1775686380887.jpg)

After installation, you should be able to run the `claude` command (restart your terminal if not). Navigate to your project directory and run:
```
claude
```
You'll go through initial setup — choosing your color theme and signing in with your Claude account (Pro, Max, or Enterprise) or using an API key. If your organization has a Claude Enterprise account, select that option.

![Claude Code login method selection: subscription, API, or third-party platform](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686379%2Fvideo3claudeinitaccounts.1775686379767.jpg)

Whatever directory you run `claude` in, it will have access to that directory and all of its subfolders.

#### Visual Studio Code
Open your Extensions panel, search for "Claude Code," and look for the extension by Anthropic with the blue verification check. Hit install.

![Claude Code extension page in VS Code marketplace](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686378%2Fvideo3claudecodevscode.1775686378631.jpg)

After installation, you may need to restart VS Code. Once running, open the command palette with `Ctrl/Cmd + Shift + P` and search for "Claude Code Open in New Tab." You can also click the Claude logo in your sidebar. The VS Code extension provides a very similar experience to the terminal — you can also opt out of the UI and use the terminal experience directly in your settings.

#### JetBrains
Install the Claude Code plugin from the JetBrains Marketplace, then restart your IDE. When you reopen it, you'll see the Claude logo — clicking it opens a pane with the terminal experience that works alongside your editor.

![Claude Code plugin in the JetBrains Marketplace](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686367%2Fclaudecodejetbrainsvideo3.1775686367876.jpg)

#### Desktop
After installing and signing into Claude Desktop, you'll see a toggle at the top labeled "Code." The look and feel is similar to the chat side of things, but it lets you work in a specific folder, change permissions, and even work in a cloud environment.

![Claude Desktop Code view showing recent project folders](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686367%2Fclaudecodedesktopvideo3github.1775686366970.jpg)

#### Web
Access Claude Code by going to `claude.ai/code`, or by clicking the "Code" label in the sidebar of the chat app. This works similarly to the desktop app, but you're restricted to GitHub repositories — a good option if you want to work remotely on a project through a repo, or run multiple sessions in parallel.

![Claude Code on the web at claude.ai/code with repository selection](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2F8lsy243ftffjjy1cx9lm3o2bw%2Fpublic%2F1775686365%2Fclaudeaislashcodevideo3.1775686365598.jpg)

#### Which one should I use?
- **Terminal** — if you want to stay on the cutting edge; features ship there first.
- **IDE integrations** (VS Code, JetBrains) — a nearly identical experience if you want Claude Code to feel more intertwined with your code editor.
- **Desktop** — great for letting Claude run in the background while you handle other tasks.
- **Web** — solid if you want to remotely work on projects through a GitHub repository, or run multiple sessions in parallel.

However you want to use Claude Code is up to you.

---

### 📊 Key Concepts Snapshot

| Environment | Best For |
|---|---|
| **Terminal** | Cutting-edge features, first to receive updates |
| **VS Code / JetBrains** | Working intertwined with your existing code editor |
| **Desktop app** | Letting Claude work in the background while you do other things |
| **Web (claude.ai/code)** | Remote work via GitHub repos, or running multiple parallel sessions |

---

### 🏢 Real-World Scenario

**Situation:** You're a VS Code power-user who doesn't want to juggle a separate terminal window all day.

**Solution:** Install the Claude Code extension from the VS Code Marketplace, restart VS Code, and open it via the command palette or sidebar icon — you get nearly the same experience as the terminal, but without leaving your editor.

---

### 🤔 Lesson Reflection

- Which installation option fits how you already work — terminal, an IDE, Desktop, or the web?
- If you work across multiple machines, would the web version's GitHub-repo access be useful for you?

---

### ⏭️ What's Next

In the next lesson, you'll write your first prompt and learn about Auto-Accept vs. Approval and Plan Mode.

---

[⬅ Previous: Lesson 2 — How Claude Code Works](./Lesson-02-How-Claude-Code-Works.md) · [🏠 Course Home](./README.md) · [Next: Lesson 4 — Your First Prompt ➡](./Lesson-04-Your-First-Prompt.md)
