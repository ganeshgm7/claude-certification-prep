# Lesson 2B — The 4D Framework Overview

---

### 📌 What Is This About?

This lesson formally introduces the **4 Ds** — the four core competencies of the AI Fluency Framework. Each D answers one critical question you face every time you work with AI. Together, they form a complete system for effective, efficient, ethical, and safe AI collaboration. These competencies are not tied to any specific AI tool — they are durable skills that grow with you.

---

### 💡 Why Does This Matter?

In IT, good engineers do not just know tools — they know principles. A developer who understands design patterns can pick up any framework. A network engineer who understands routing protocols can work with any vendor's equipment.

The 4 Ds are your **design patterns for AI collaboration**. They do not expire when the next model drops. They give you a consistent, principled way to approach every AI interaction — today and in the future.

---

### 📖 The Story

Imagine your IT company is building an internal AI assistant to help project managers write better Business Requirements Documents (BRDs). Let us walk through the entire process using all 4 Ds.

#### D1 — Delegation: "Who does what?"

Before opening Claude, the project manager sits down and thinks: *"What am I trying to accomplish here? And what role should AI play?"*

She breaks the work down deliberately:

- **AI handles:** Pulling in standard BRD sections, suggesting common requirement formats, flagging incomplete or missing details
- **Human handles:** Understanding the client's actual business problem, validating feasibility with the tech team, making final judgment calls, approving the output

This is **Delegation** — the strategic division of labour between human and AI. It is not about offloading work to AI. It is about being intentional about *what* AI does and *what* the human keeps.

**Three things needed for effective Delegation:**
1. A clear goal — what are you actually trying to achieve?
2. An honest assessment of what AI can and cannot do well
3. A deliberate split — which parts go to AI, which stay with the human

> **Key reminder:** Delegate execution. Keep judgment. Never delegate the thinking to AI and keep only the clicking for yourself — that is backwards.

#### D2 — Description: "How do I talk to AI so it understands?"

The PM opens Claude and types: *"Write a requirements document."*

Claude produces something generic. Useless.

She tries again — this time with proper Description:

*"You are helping a project manager at a software company write a Business Requirements Document for a client CRM migration project. The client is a mid-size logistics firm. The document must include: Objective, Scope, Functional Requirements, Non-Functional Requirements, and Assumptions. Use formal corporate tone. Ask me clarifying questions before starting if anything is unclear."*

The difference in output quality is dramatic.

**Description is not just writing prompts.** It covers:
- **What** you want to achieve (the desired output)
- **How** you want AI to approach the task (the process)
- **Context** and background AI needs to understand the situation
- **Format, tone, and style** of the output
- **Constraints** and things to avoid

> **IT Parallel:** Writing a Jira ticket with full acceptance criteria vs. a one-liner saying "fix the bug." The quality of what comes back is directly proportional to the quality of how you described the problem.

#### D3 — Discernment: "Is what I got actually good?"

Claude produces the BRD. The PM reads it carefully, applying **Discernment**:

- Are these requirements factually accurate? *(Did Claude hallucinate any technical details?)*
- Does the logic hold? *(Are requirements logically consistent and non-contradictory?)*
- Does this actually match the client's needs? *(Or is it just generically correct?)*
- Is there anything that should not be there? *(Claude added mobile app requirements — but the client explicitly said no mobile scope.)*

She flags the issue, removes the incorrect section, refines her prompt, and runs it again.

This loop — **Describe → Evaluate → Refine → Describe again** — is the most common real-world AI work pattern. Discernment is what makes this loop productive rather than frustrating and circular.

> **Key insight:** Discernment requires your domain expertise meeting the AI output. Claude does not know your client. You do. That is why humans cannot be removed from the loop entirely.

#### D4 — Diligence: "Am I being responsible here?"

The document is good. Now the PM asks herself the Diligence questions:

- Did I share any sensitive client PII in my prompts? *(Data protection)*
- Should I disclose to the client that AI assisted in drafting this? *(Transparency)*
- If there is an error in this document that causes scope creep later, am I ready to own it? *(Accountability)*
- Are any requirements worded in a way that could introduce unfair constraints? *(Bias and fairness)*

**Diligence** is the governance layer. It means you own the output. You cannot say "Claude wrote it" when something goes wrong. You reviewed it, you approved it, it carries your professional credibility.

> **IT Parallel:** Change management. Just because a script ran cleanly in UAT does not mean you skip the approval process, rollback plan, and stakeholder communication before production deployment.

#### How the 4 Ds Interact

The 4 Ds are not four sequential steps — they are **interlocking competencies**:

```
Delegation  →  sets the overall strategy (what AI does vs. human)
     ↓
Description →  communicates that strategy to AI (how you talk to it)
     ↓
Discernment →  evaluates what comes back (is this actually good?)
     ↓
Description →  refined and improved based on discernment feedback
     ↓
Diligence   →  runs as a continuous mindset throughout the entire process
```

**Diligence is not a final step — it is a mindset carried through all other Ds.**

---

### 📊 Key Concepts Snapshot

| D | Core Question | What It Covers | IT Parallel |
|---|--------------|----------------|-------------|
| **Delegation** | What work goes to AI vs. human? | Goal clarity, AI capability awareness, task division | Capacity planning — right work to right resource |
| **Description** | How do I communicate clearly with AI? | Context, instructions, format, constraints, examples | Writing detailed Jira tickets with acceptance criteria |
| **Discernment** | Is this output actually good? | Accuracy, logic, relevance, fitness for purpose | Code review — do not merge without proper review |
| **Diligence** | Am I being responsible? | Ethics, privacy, transparency, accountability | Change management — own what goes live |

---

### 🏢 Real-World Scenario

**Situation:** An IT company uses Claude to help HR draft job descriptions and assist with initial screening of candidate profiles.

**Delegation:** HR decides Claude will draft the initial job description and flag profiles that technically match the required skills. Final shortlisting and culture-fit assessment stays with the HR manager. Critical judgment = human only.

**Description:** HR gives Claude: role title, team context, required skills, preferred experience, company values, compensation band, and the instruction — *"Do not use gendered language. Avoid unnecessarily restrictive requirements. Flag if any requirement seems likely to limit diversity."*

**Discernment:** HR reviews Claude's job description output. Notices it used "rockstar developer" — potentially exclusionary language. Also notices it listed "10 years of Kubernetes experience" for a mid-level role — not realistic. Both flagged and corrected.

**Diligence:** HR confirms no candidate PII was shared with Claude during screening. The job posting includes a note that AI tools were used in the drafting process. The HR manager signs off personally on all shortlisting decisions — they are the accountable party, not the AI.

**Result:** Faster drafting, better quality output, a more inclusive process, and full accountability at every step.

---

### ⚠️ Watch Out For

**Trap 1: Treating Description as a one-shot activity**
Most beginners write one prompt and expect a perfect output. Description is iterative. The Describe → Discern → Refine loop is completely normal — not a sign that something is broken.

**Trap 2: Confusing Discernment with proofreading**
Discernment is not just grammar-checking. It is critically evaluating factual accuracy, logical soundness, relevance, completeness, and appropriateness. In IT, a wrong configuration suggestion from Claude could cause a real production outage.

**Trap 3: Treating Diligence as a legal disclaimer**
Adding "generated by AI" to a footer is not Diligence. Diligence means actively thinking about bias, data privacy, transparency, and accountability throughout the entire process — not tacking on a disclaimer at the end.

**Trap 4: Applying the Ds in isolation**
The 4 Ds work best together. Skipping Delegation and jumping to Description means you might be using AI for the wrong thing entirely. Skipping Discernment means bad outputs slip through. Skipping Diligence means you are exposed to professional and ethical risk.

---

### ✅ Quick Check

**Q1.** A developer pastes the full production database schema — including customer names and email addresses — into Claude and asks it to suggest performance optimisations. Which D did they fail?

- A) Delegation — they should have done this analysis themselves
- B) Description — they did not specify the format of the output
- C) Diligence — they shared sensitive customer data without considering data protection
- D) Discernment — they did not review the output carefully enough

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

This is a **Diligence** failure. Sharing sensitive customer data (PII) with an external AI system without checking data protection policies, privacy agreements, and organisational guidelines is a serious governance issue. A database schema alone might be acceptable, but schemas containing actual customer records are not. Diligence requires you to ask: *"Who may have access to the data I am inputting right now?"*

</details>

---

**Q2.** A PM asks Claude to generate a project plan and gets back a generic 5-step plan that does not match her project constraints at all. What should she do next?

- A) Apply Delegation — reassign this task entirely to a human project manager
- B) Apply Description — refine the input with specific project context, constraints, timelines, and stakeholder details, then try again
- C) Apply Discernment — accept the output and manually edit it without re-prompting
- D) Apply Diligence — disclose to stakeholders that the plan was AI-generated

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: B**

When an AI output does not meet your needs, the next step is to improve your **Description** — add more specific context, constraints, and requirements to your prompt and try again. The first response being off-target is expected and normal. The Describe → Discern → Refine loop is how quality improves over iterations. Option C (manual editing without re-prompting) misses the opportunity to improve the AI interaction itself.

</details>

---

**Q3.** Which statement best describes how the 4 Ds relate to each other?

- A) They are four sequential steps — you must complete all of Delegation before starting Description
- B) Diligence is only needed at the end, after the final output is approved
- C) They are interlocking competencies, with Diligence running as a continuous mindset throughout the entire process
- D) Description and Discernment are essentially the same competency — both involve evaluating AI output

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

The 4 Ds are **interlocking competencies** that work together. They are not strictly sequential — you may revisit Delegation if Discernment reveals a fundamental problem. Most importantly, **Diligence is not a final step** — it is a continuous mindset of responsibility, ethics, and accountability that runs throughout every interaction, from the moment you decide to use AI to the moment you share the final output.

</details>
