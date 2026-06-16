# Lesson 4 — A Closer Look at Delegation

---

### 📌 What Is This About?

This lesson takes the **Delegation** competency apart in detail. It reveals that good delegation is less about AI than it is about you — your clarity of purpose, your understanding of the problem, and your knowledge of what AI can realistically do. The lesson introduces three sub-concepts: **Problem Awareness, Platform Awareness, and Task Delegation**.

---

### 💡 Why Does This Matter?

In IT project management, one of the most common causes of failure is a poorly defined scope. Teams build what they think was asked for, not what was actually needed. The same failure mode exists with AI. If you do not have a clear understanding of your goal and the problem you are solving, you will use AI in the wrong way — no matter how powerful the model is.

Delegation is the strategic thinking that prevents AI from being used as a solution looking for a problem.

---

### 📖 The Story

Here is something surprising: **the cornerstone of good Delegation is not about AI at all.** It is about your own expertise and your own clarity about what you are trying to accomplish.

Before involving AI in any project, you must stop and genuinely answer these questions:

- *What exactly am I trying to accomplish?*
- *What is my vision for this project?*
- *What does success look like?*
- *What kinds of thinking and work are needed to get there?*

Without clear answers to these questions, even the most advanced AI will not get you where you need to go. You will struggle to give it useful direction, evaluate its outputs, or know when to step in.

> **The most effective AI collaborators are experts in their fields first, and AI users second.** AI amplifies expertise — it does not replace it.

#### Sub-Concept 1: Problem Awareness

**Problem Awareness** is the ability to clearly define your goals and understand what work is needed *before* bringing AI into the picture.

When analysing a project for AI involvement, it helps to categorise the work:

| Type of Work | Description | Example |
|-------------|-------------|---------|
| **Simple but time-consuming** | Repetitive, well-defined tasks | Formatting 200 documents, generating weekly reports |
| **Exploratory** | Areas of uncertainty where you need a thinking partner | Designing a new system architecture, brainstorming solutions |
| **Knowledge gaps** | Areas where you need more information or data | Researching best practices, summarising research papers |
| **Critical judgment** | Areas requiring human expertise, ethics, or accountability | Final approval of a major deployment, hiring decisions |

AI is generally excellent at the first two categories, useful with caution for the third, and should not replace humans in the fourth.

#### Sub-Concept 2: Platform Awareness

**Platform Awareness** is a working knowledge of available AI systems — their specific capabilities, limitations, and tradeoffs.

Different AI systems genuinely differ in:
- **Reasoning depth:** Some models are better at complex, multi-step problems
- **Speed vs. depth:** Smaller, faster models vs. larger, more capable ones
- **Modalities:** Some handle images, audio, or code better than others
- **Tool connectivity:** Some have web search, code execution, document analysis
- **Safety and data policies:** Critical for enterprise use — who stores your data and how?

Platform Awareness does not mean knowing every model's benchmark score. It means knowing enough to make an informed choice for your specific use case — and experimenting to build that knowledge over time.

> **Key reminder:** The AI landscape evolves almost daily. Platform Awareness is not a one-time research exercise. Build it through regular hands-on experimentation with different systems.

#### Sub-Concept 3: Task Delegation

**Task Delegation** is the actual strategic process of dividing work between humans and AI.

Given what you know about your problem and the available AI systems, ask yourself:

1. **Which parts benefit from full automation?** — Repetitive, well-defined tasks with clear success criteria
2. **Which parts benefit from augmentation?** — Complex, exploratory work where an AI thinking partner adds value
3. **Which parts need human-only judgment?** — Ethical decisions, accountability, final approval, client relationships
4. **What can AI agents handle on your behalf?** — Ongoing, dynamic tasks that run without per-step human input

The key output of Task Delegation is not a prompt — it is a **clear, deliberate plan** for how AI fits into your workflow.

---

### 📊 Key Concepts Snapshot

| Concept | Definition | Key Questions to Ask |
|---------|-----------|---------------------|
| **Problem Awareness** | Clarity about your goals and the work needed before involving AI | What am I trying to achieve? What does success look like? What types of work are involved? |
| **Platform Awareness** | Working knowledge of available AI systems and their strengths/limitations | Which model suits this task? What are the data policies? Speed vs. depth tradeoff? |
| **Task Delegation** | Strategic division of work between humans and AI | What gets automated? What needs augmentation? What stays human-only? What can an agent handle? |

---

### 🏢 Real-World Scenario

**Situation:** Your company wants to use AI to speed up the security audit process for new software deployments.

**Problem Awareness:**
- Goal: Reduce time-to-audit without reducing audit quality
- Work breakdown: (a) reviewing boilerplate checklist items — simple but time-consuming; (b) identifying unusual configurations — requires exploration; (c) sign-off and accountability — must stay human; (d) generating the audit report — automatable once findings are confirmed

**Platform Awareness:**
- Claude (with document analysis) is well-suited for reading through configuration files and policy documents
- A code analysis tool (e.g., Semgrep) is better for static code analysis — Claude is not a replacement for purpose-built security scanners
- Data sensitivity: Never paste production secrets or credentials into an AI tool — verify the platform's data handling policies first

**Task Delegation:**
- **Automate:** Checklist verification, report drafting, formatting
- **Augment:** Discussing unusual findings, exploring risk implications, refining recommendations
- **Human-only:** Final sign-off, accountability for audit conclusions, communication with the development team
- **Agent-based (future):** Scheduled automated pre-audit checks on every new deployment

**Result:** A well-designed process that uses AI where it genuinely saves time, keeps humans accountable where it matters, and does not create false confidence through over-reliance on AI judgment.

---

### ⚠️ Watch Out For

**Trap 1: Delegating before you understand the problem**
If you are not clear on your goals, any AI output will feel wrong — because you have no benchmark to evaluate it against. Problem Awareness must come first.

**Trap 2: Delegating judgment to AI**
AI can assist with judgment (surfacing considerations, identifying patterns, presenting options), but the actual decision — especially in high-stakes professional contexts — must remain with a human who carries accountability.

**Trap 3: Assuming one AI tool fits all tasks**
Different tasks genuinely benefit from different tools. Using Claude for tasks better suited to a purpose-built security scanner, database query tool, or data analytics platform leads to disappointing results. Platform Awareness prevents this.

**Trap 4: Making delegation decisions once and never revisiting**
As AI capabilities improve and your own expertise grows, the right human-AI split will change. Revisit your delegation decisions periodically.

---

### ✅ Quick Check

**Q1.** A team lead wants to use Claude to help manage a complex cloud migration project. Before doing anything with AI, what is the most important first step according to the Delegation competency?

- A) Choose the right Claude model based on context window size
- B) Write a detailed system prompt defining Claude's role
- C) Clearly define the project goals, understand the work involved, and identify which parts are best suited to AI vs. human
- D) Check Claude's API documentation for the latest features

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

This is **Problem Awareness** — the foundational first step in Delegation. Before thinking about AI tools, models, or prompts, you must have a clear understanding of what you are trying to accomplish, what the work involves, and where AI can genuinely add value vs. where human judgment is essential. Without this clarity, even the best AI tool will not get you to a good outcome.

</details>

---

**Q2.** When making Platform Awareness decisions for an enterprise AI deployment, which consideration is most critical from a professional responsibility standpoint?

- A) The benchmark performance score of the model on standard AI tests
- B) The data handling and privacy policies of the AI platform — who stores input data and how
- C) The visual design of the AI platform's user interface
- D) Whether the AI platform supports the most recent model version

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: B**

For enterprise deployments, **data handling and privacy policies** are the most professionally critical Platform Awareness consideration. Before putting any business data — especially sensitive customer information, financial data, or PII — into an AI tool, you must verify the platform's data retention policies, security certifications, compliance with relevant regulations (GDPR, DPDPA, etc.), and your organisation's own policies on approved AI tools. Benchmark scores matter for capability decisions; data policies matter for safety and compliance decisions.

</details>

---

**Q3.** Which of the following tasks should be kept as "human-only" and NOT delegated to AI, even a capable one?

- A) Summarising a 50-page technical specification document into a 2-page executive summary
- B) Drafting the first version of a project status report
- C) Making the final hiring decision for a senior security engineer role
- D) Generating test cases for a new API endpoint

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

A **final hiring decision** involves significant human judgment, ethical responsibility, legal accountability, and cultural considerations that go beyond what AI can reliably handle. This is a "critical judgment" category task — AI can assist (screen resumes, surface candidates, draft interview questions) but the final decision must remain with a human who carries professional and organisational accountability. Options A, B, and D are all appropriate for AI assistance or automation.

</details>
