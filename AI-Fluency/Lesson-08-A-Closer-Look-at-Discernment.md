# Lesson 8 — A Closer Look at Discernment

[⬅ Previous: Lesson 7 — Effective Prompting Techniques](./Lesson-07-Effective-Prompting-Techniques.md) · [🏠 Course Home](./README.md) · [Next: Lesson 10 — A Closer Look at Diligence ➡](./Lesson-10-A-Closer-Look-at-Diligence.md)

---

### 📌 What Is This About?

This lesson explores the **Discernment** competency in depth — your quality control system for AI collaboration. Discernment is the flip side of Description: if Description is about communicating what you want to AI, Discernment is about evaluating whether what you got back actually meets your needs. The lesson introduces three layers: **Product Discernment, Process Discernment, and Performance Discernment**.

---

### 💡 Why Does This Matter?

In IT, no code goes to production without code review. No configuration change goes live without a change management review. No infrastructure deployment happens without a pre-deployment checklist. These practices exist because even experienced engineers make mistakes — and catching them before they cause problems is far cheaper than fixing them after.

The same discipline applies to AI outputs. Claude can produce technically polished, grammatically perfect output that is factually wrong, logically flawed, or completely misaligned with your actual needs. Discernment is your code review for AI collaboration.

---

### 📖 The Story

Discernment requires two things working together:
1. **Domain expertise** — you need to know enough about the subject to judge the quality of the output
2. **Understanding of AI limitations** — you need to know where AI typically goes wrong

Without domain expertise, you cannot evaluate accuracy. Without understanding AI limitations, you will not know what to watch for.

#### Sub-Concept 1: Product Discernment

**Product Discernment** is the ability to judge the accuracy and value of AI-created output.

When reviewing any AI-generated content, systematically ask:

- **Is this factually accurate?** — Especially important for specific facts, statistics, dates, and names
- **Is this appropriate for my audience and purpose?** — Does the tone, level of detail, and framing fit the use case?
- **Is this coherent and well-structured?** — Does the logic flow? Is it internally consistent?
- **Does this meet my stated requirements?** — Did it include everything I asked for? Did it avoid what I said to avoid?
- **Does this actually solve the problem I intended?** — Sometimes the output meets the literal request but misses the underlying need

Product Discernment is the most straightforward layer — it is about evaluating the deliverable itself.

#### Sub-Concept 2: Process Discernment

**Process Discernment** is the ability to judge the quality and effectiveness of the AI's *approach* to the task — not just the final output.

When working through complex tasks with AI, watch for:
- **Logical errors** — gaps in reasoning, invalid inferences
- **Attention lapses** — the AI losing track of important constraints you mentioned earlier
- **Inappropriate steps** — the AI taking a shortcut or using an approach you did not intend
- **Getting stuck in a loop** — the AI fixating on one interpretation and failing to consider alternatives
- **Circular reasoning** — using a conclusion as justification for itself

**Practical example:** You are working with Claude to develop a system architecture. You explicitly rejected Option A in round 2. By round 5, you notice elements of Option A quietly reappearing in the design. That is an AI attention lapse — a Process Discernment catch.

This type of discernment is especially critical for complex, multi-turn tasks where the AI needs to maintain consistency across many exchanges.

#### Sub-Concept 3: Performance Discernment

**Performance Discernment** is the ability to judge the quality of the *interaction itself* — how well Claude is engaging with you as a collaborator.

Ask yourself:
- Is Claude communicating information in a format that actually helps me?
- Is it asking too many clarifying questions when I just need direct answers?
- Is it being too brief when I actually need comprehensive depth?
- Does it respond well when I redirect or correct it?
- Is the interaction efficient, or is it creating unnecessary overhead?

**Example:** You are doing a rapid security review and need quick, direct assessments. But Claude keeps adding three paragraphs of background context before every answer. That is a performance issue — Claude's interaction style is not calibrated to your current workflow. Performance Discernment spots this, and the remedy is a Performance Description correction.

#### The Critical Feedback Loop: Discernment + Description

When Discernment flags a problem, the typical response is to improve your Description:

```
Description → AI Output → Discernment (evaluates) → Better Description → Better Output
```

But the course makes an important additional point: **sometimes the issue is not your Description — it is your Delegation**. If you keep getting outputs that are fundamentally wrong for your purpose despite excellent prompting, it may mean:
- You are using AI for a task it genuinely cannot do well
- You have the wrong tool for the job (Platform Awareness issue)
- The task genuinely requires human judgment and should not be delegated to AI

Discernment, used properly, can surface these deeper delegation problems — not just prompt-level issues.

---

### 📊 Key Concepts Snapshot

| Concept | Definition | What to Look For |
|---------|-----------|-----------------|
| **Product Discernment** | Evaluating the accuracy and value of AI output | Factual accuracy, appropriateness, completeness, fitness for purpose |
| **Process Discernment** | Evaluating how the AI approached the task | Logical errors, attention lapses, circular reasoning, inappropriate steps |
| **Performance Discernment** | Evaluating the quality of the AI interaction itself | Communication style, efficiency, responsiveness to feedback, depth vs. brevity |
| **Feedback loop** | Using Discernment findings to improve Description | When output is wrong, improve the prompt; when fundamentally off, reconsider Delegation |
| **Domain expertise** | Your knowledge of the subject matter | Required to evaluate factual accuracy and contextual appropriateness |
| **AI limitation awareness** | Knowing where AI typically goes wrong | Helps you know what to verify and where to be sceptical |

---

### 🏢 Real-World Scenario

**Situation:** Your team uses Claude to help draft a technical RFP (Request for Proposal) for a new data centre cooling solution.

**Product Discernment in action:**
- The PM reviews the output and notices Claude has specified a particular cooling technology that was standard in 2022 but has since been superseded by more efficient approaches. Knowledge cutoff issue — factual accuracy fail. She corrects this section.
- Claude listed "99.9% uptime" as a standard SLA requirement. The PM knows the company's actual requirement is 99.99% (four nines). Requirement alignment fail. She corrects this.

**Process Discernment in action:**
- In the technical requirements section, the PM notices Claude has structured the requirements in order of alphabetical category rather than in order of business criticality — which is the standard for RFPs in their industry. Process approach issue. She adds explicit step-by-step ordering instructions to the next prompt iteration.
- Later in the document, she notices Claude has incorporated a budget constraint she rejected in the second exchange. Attention lapse — previously rejected constraint reappearing. She calls it out explicitly in her next prompt.

**Performance Discernment in action:**
- Claude keeps adding lengthy disclaimers at the end of each section ("Note: these specifications should be reviewed by qualified engineers..."). The PM is an experienced engineer — this is unnecessary overhead. She adds a Performance Description: *"Stop adding disclaimer notes at the end of sections — I am a qualified engineer and will take responsibility for the technical review."*

**Result:** Three types of Discernment working together to catch different categories of problems — producing a significantly better final RFP than if the output had been accepted uncritically.

---

### ⚠️ Watch Out For

**Trap 1: Skipping Discernment under time pressure**
When deadlines are tight, the temptation is to use the first output that "looks good." This is exactly when errors slip through. Build at least a rapid Discernment pass into every AI-assisted workflow.

**Trap 2: Only checking for surface-level errors**
Spell-checking and grammar review is not Discernment. Discernment means evaluating factual accuracy, logical soundness, contextual appropriateness, and completeness — a much higher bar.

**Trap 3: Trusting confident-sounding output more than uncertain-sounding output**
LLMs do not reliably signal their own uncertainty. Claude can sound equally confident when it is right and when it is hallucinating. The confidence of the language is not a reliable indicator of accuracy. Always verify factual claims independently.

**Trap 4: Applying only Product Discernment and missing Process and Performance issues**
Many people only review the final output (Product). But the AI's reasoning process (Process) and interaction quality (Performance) also affect the quality of the collaboration. All three layers are needed for complete Discernment.

---

### ✅ Quick Check

**Q1.** A data analyst uses Claude to write a SQL query for a complex business report. Claude produces a well-formatted, syntactically correct query. The analyst runs it and gets results, but the numbers are 15% lower than expected. She digs deeper and finds that Claude's JOIN logic excluded a key table. What type of Discernment failure occurred?

- A) Performance Discernment — Claude's interaction style was poor
- B) Product Discernment — the output was syntactically correct but logically wrong, producing incorrect results
- C) Process Discernment — Claude took an inappropriate approach to the task
- D) No Discernment failure — the query was syntactically valid

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: B**

This is a **Product Discernment** failure. The output looked correct (syntactically valid, well-formatted) but was factually/logically wrong — it produced incorrect results due to a flawed JOIN logic. This is one of the most dangerous types of AI output error: superficially convincing output that is subtly wrong. The analyst needed to verify the output not just by running it, but by validating the results against expected values. Product Discernment requires checking whether the output actually achieves the intended purpose — not just whether it looks right.

</details>

---

**Q2.** You are working with Claude over 10 turns to design a microservices communication pattern. In turn 7, you explicitly rejected a synchronous REST approach due to latency concerns. In turn 10, Claude's proposed architecture includes synchronous REST calls between three core services. Which type of Discernment is most relevant here?

- A) Product Discernment — the final architecture output is wrong
- B) Process Discernment — Claude lost track of a constraint you established earlier, indicating an attention lapse in the AI's reasoning process
- C) Performance Discernment — Claude's interaction style is not tracking your decisions
- D) Both A and B are equally relevant

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: B**

This is primarily a **Process Discernment** issue — specifically, an **attention lapse**. Claude failed to maintain consistency with a constraint you explicitly established earlier in the conversation (the rejection of synchronous REST). This is a known AI behaviour pattern in long, multi-turn conversations, especially as earlier context approaches the edges of the context window. Process Discernment means monitoring not just what the AI produces, but whether its reasoning and decision-making are staying consistent and coherent throughout the interaction.

</details>

---

**Q3.** After reviewing Claude's output for a project proposal, you determine that Claude has produced a high-quality document but has fundamentally misunderstood the core objective. Every section is well-written but addresses the wrong problem. Which is the most appropriate response?

- A) Apply Product Discernment — correct the factual errors section by section
- B) Apply Process Discernment — guide Claude to reapproach the task using the correct methodology
- C) Apply Description — go back and improve your initial prompt with a clearer statement of the actual objective, then regenerate from scratch
- D) Apply Delegation — reconsider whether this task should be delegated to AI at all

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

When the output fundamentally misses the objective, the root cause is almost always a **Description** failure — the initial prompt did not communicate the actual goal clearly enough. The remedy is to go back, improve your Product Description (clearer objective statement), and regenerate. Editing section by section (Option A) is inefficient when the foundation is wrong. Option D (rethinking Delegation) is relevant only if repeated Description improvement still does not produce the right output — suggesting AI may genuinely be the wrong tool for this particular task.

</details>

---

[⬅ Previous: Lesson 7 — Effective Prompting Techniques](./Lesson-07-Effective-Prompting-Techniques.md) · [🏠 Course Home](./README.md) · [Next: Lesson 10 — A Closer Look at Diligence ➡](./Lesson-10-A-Closer-Look-at-Diligence.md)
