# Lesson 9 — Enterprise Search

> **Estimated time:** 15 minutes

> **Plan availability:** Enterprise Search is available on Team and Enterprise plans, and must be enabled by a workspace admin. If you're on a Free, Pro, or Max plan, you can skip this lesson.

---

### 📌 What Is This About?

This lesson covers **Enterprise Search** — a dedicated "Ask {Your Org Name}" option that turns Claude into a search engine for your entire company's knowledge: documents, chats, emails, and more, all in one place.

---

### 💡 Why Does This Matter?

In any company, useful information gets scattered across SharePoint, Slack, Gmail, and Google Drive. Normally you'd have to remember *where* something was discussed and go hunting for it. Enterprise Search removes that hunting — you just ask a plain-language question, and Claude finds and combines the answer from across all your connected company tools, with sources cited.

---

### 📖 The Explanation

#### What is Enterprise Search?

Enterprise Search adds a dedicated **"Ask {Your Org Name}"** option to your sidebar, designed specifically for finding and combining knowledge buried across your company's tools and data sources. Think of it as a **pre-built Project for your entire organisation** — your company's knowledge base is already loaded, so you can jump right in and get context-aware answers.

Unlike a regular chat with connectors enabled, Enterprise Search is specifically designed for information gathering, using custom instructions configured by the Anthropic team.

#### What can you ask?

Enterprise Search is especially valuable for questions that span multiple sources or need synthesis across the organisation:

**Getting up to speed:**
- "What happened yesterday while I was out?"
- "Summarize key updates across the business from the last week."
- "What are the current blockers on the Platform project?"

**Policy and process questions:**
- "What is our company's remote work policy?"
- "How do I submit an expense report?"
- "What's the process for requesting time off?"

**Research and analysis:**
- "What are the main reasons customers cite for choosing competitors?"
- "Summarize discussions about the Q4 product roadmap."
- "Find information about our customer onboarding process."

**Onboarding new team members:**
- "How does our authentication system work?"
- "Who should I talk to about learning the billing system?"
- "What tools does the engineering team use for deployment?"

**Performance and project tracking:**
- "Find discussions and documents related to the marketing campaign."
- "What were the key decisions from last week's leadership meetings?"
- "Summarize team contributions to the Infrastructure initiative."

When you ask a question, Claude searches across all your connected tools — SharePoint documents, Slack conversations, Gmail threads, Google Drive files — and synthesises the information into one unified response. It always cites its sources, so you can check the full context yourself.

#### Setting up Enterprise Search

This is a **two-step process**: first, an admin configures it for the organisation; then individual users authenticate with their own personal accounts.

**For admins (Owners):**

Enterprise Search is enabled by default for all Team and Enterprise organisations, but an Owner still needs to complete the initial setup before team members can use it:

1. Click **"Ask Your Org"** in the left sidebar.
2. Click **"Set up for your org"** to continue (or "Disable" to turn the feature off).
3. Connect your organisation's tools — you'll choose a connector for **Documents** (like Google Drive or SharePoint) and **Chat** (like Slack or Microsoft Teams). Email is recommended but optional.
4. Click **"+ Add more"** for any additional tools your team needs.
5. Customise the project name — whatever you enter appears as "Ask [Name]" in everyone's sidebar.
6. Add a description, then click **"Finish set up."**

Once complete, the project becomes available to all members of your organisation.

**For users:**

Once an admin has set it up, you'll see the **"Ask {Org Name}"** project starred in your sidebar:
1. Click on the project in your sidebar.
2. Follow the guided onboarding flow to connect to the recommended services.
3. Authenticate with each service you want to search (Slack, Google, Microsoft 365, etc.).
4. Start asking Claude questions about your organisation's knowledge.

The more connectors you enable, the more comprehensive your search results become. You can always add more connectors later by clicking "Connect" in the project's Instructions section.

#### Is this safe?

Yes. Enterprise Search only shows what you **already have permission to access** in the original connected tool. Your conversations remain private, and your connected data is not indexed or stored separately.

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Enterprise Search** | Sidebar option that searches across all your org's connected tools | Removes the need to manually hunt across apps for information |
| **"Ask {Org Name}"** | The project name shown in the sidebar once set up | Your one-stop entry point to organisational knowledge |
| **Admin setup** | An Owner configures Documents + Chat (+ Email) connectors org-wide | Must be done once before anyone else can use the feature |
| **User authentication** | Each employee signs into the services they personally want searched | Ensures Enterprise Search only shows what *you* are allowed to see |
| **Citations** | Every answer links back to its original source | Lets you verify information instead of just trusting the summary |

---

### 🏢 Real-World Scenario

**Situation:** A new employee joins the engineering team and wants to quickly understand "how does our authentication system work?" and "what tools does the team use for deployment?"

**With Enterprise Search:** Instead of pinging five different colleagues or searching four different tools, the new hire simply opens "Ask [Company Name]" and asks both questions directly. Claude searches Slack, SharePoint, and Google Drive, and returns a synthesised, cited answer in seconds — dramatically speeding up onboarding.

---

### 🤔 Lesson Reflection

- What questions do you frequently ask colleagues that could be answered by searching your organisation's documents and communications?
- Are there onboarding or training scenarios where Enterprise Search could help new team members get up to speed faster?
- Which data sources would be most valuable to connect for your specific role?

---

### ⏭️ What's Next

In the next lesson, you'll learn about **Research mode** — Claude's capability for deep, multi-step investigations that go beyond quick lookups to comprehensive analysis.
