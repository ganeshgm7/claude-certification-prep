# Lesson 6 — A Closer Look at Description

[⬅ Previous: Lesson 4 — A Closer Look at Delegation](./Lesson-04-A-Closer-Look-at-Delegation.md) · [🏠 Course Home](./README.md) · [Next: Lesson 7 — Effective Prompting Techniques ➡](./Lesson-07-Effective-Prompting-Techniques.md)

---

### 📌 What Is This About?

This lesson dives deep into the **Description** competency — the art of communicating effectively with AI systems. Description is far more than writing clever prompts. It is about building a shared understanding between your intentions and the AI's capabilities. The lesson introduces three layers: **Product Description, Process Description, and Performance Description**.

---

### 💡 Why Does This Matter?

In software development, there is a saying: *"Garbage in, garbage out."* The same principle applies to AI interactions — but with a twist. Unlike a traditional program that will throw an error if you give it bad input, an LLM will confidently produce something that *looks* like what you asked for, even if it is completely wrong. You will not get an error message. You will get plausible-sounding output that does not actually meet your needs.

Good Description is the difference between an AI that helps you and one that wastes your time.

---

### 📖 The Story

Think of description as **building a bridge between your intentions and the AI's capabilities**. The quality of that bridge determines the quality of the output.

#### Sub-Concept 1: Product Description

**Product Description** is the ability to clearly define *what* you want the AI to create or provide.

This means stopping the assumption that AI knows what you are looking for. Instead, explicitly communicate:
- **What is the context** for this work?
- **What exactly** do you want the AI to produce?
- **What format** should the output take? (bullet points, table, prose, code, JSON?)
- **Who is the audience** for this output?
- **What style and tone** is appropriate?

**Example of weak Product Description:**
> *"Write a report on our system downtime."*

**Example of strong Product Description:**
> *"Write a 1-page executive summary of the system downtime incident on [date] for our CTO. The audience is non-technical. Include: what happened, root cause, business impact, and three concrete preventive measures. Use formal tone. Keep it under 400 words."*

The second prompt leaves almost nothing to interpretation. The AI knows exactly what to produce.

#### Sub-Concept 2: Process Description

**Process Description** is the ability to guide *how* the AI approaches your request — not just what it produces.

Sometimes specifying the approach is as important as specifying the output. You might want:
- A specific methodology or framework to be applied
- A particular order of operations
- Specific data sources or documents to be referenced
- A step-by-step breakdown rather than a single synthesised answer

**Example of weak Process Description:**
> *"Analyse this server log and tell me what is wrong."*

**Example of strong Process Description:**
> *"Analyse this server log by first identifying all ERROR and CRITICAL level entries, then grouping them by service, then identifying which service has the highest error frequency, and finally suggesting the three most likely root causes based on the error patterns. Present findings in that order."*

You have given the AI a clear methodology to follow — like a detailed runbook.

#### Sub-Concept 3: Performance Description

**Performance Description** is the ability to define how you want the AI to *behave* during the interaction — not just what it produces.

This is about shaping the style and nature of the AI's engagement with you:

- Should it ask clarifying questions before starting, or make reasonable assumptions and proceed?
- Should it challenge your ideas or support your direction?
- Should it give detailed explanations or concise answers?
- Should it think out loud (show its reasoning) or just give the final answer?
- What persona or expertise level should it adopt?

**Example of Performance Description:**
> *"You are a senior DevOps engineer reviewing my infrastructure design. Be direct and critical — point out weaknesses and risks I may have missed. Do not just validate my approach. Give concise, actionable feedback without lengthy preamble."*

This does not just ask Claude what to say — it shapes *how Claude engages with you*.

#### The Three Descriptions Work Together

| Description Type | Question It Answers | What to Include |
|-----------------|--------------------|--------------------|
| **Product Description** | What should Claude create? | Format, length, audience, tone, specific sections |
| **Process Description** | How should Claude approach the task? | Methodology, order, data sources, step-by-step guidance |
| **Performance Description** | How should Claude interact with me? | Persona, level of detail, challenging vs. supportive, explanation depth |

> **Key insight from the course:** *AI tools are not databases or vending machines. They are interactive systems that can behave differently in different contexts — much like people. You need to explain how you want the AI to behave to get the best results.*

---

### 📊 Key Concepts Snapshot

| Concept | Definition | Practical Example |
|---------|-----------|------------------|
| **Product Description** | Clearly defining what output you want | Specify format, length, audience, tone, required sections |
| **Process Description** | Guiding how the AI approaches the task | Provide methodology, order of steps, frameworks to apply |
| **Performance Description** | Defining the AI's interaction style | Set persona, level of challenge, detail vs. conciseness |
| **Context** | Background information the AI needs | Your role, the use case, relevant constraints and history |
| **Constraints** | Boundaries the AI must respect | Word limits, prohibited topics, required inclusions |
| **Explicit requirements** | Specific things the output must have or avoid | "Do not use gendered language", "Always include a risk section" |

---

### 🏢 Real-World Scenario

**Situation:** You are an IT project manager and need Claude to help you prepare for a vendor negotiation meeting for a new cloud storage contract.

**Product Description:**
*"Prepare a negotiation briefing document for a cloud storage contract discussion. The document should include: (1) our current usage and projected growth for 3 years, (2) key SLA requirements (99.99% uptime, RPO < 1 hour, RTO < 4 hours), (3) three negotiation leverage points, (4) acceptable fallback positions for price and SLA, and (5) questions to ask the vendor. Format as a structured document with clear section headings. Maximum 2 pages."*

**Process Description:**
*"First, identify the strongest negotiation leverage points based on our contract size and multi-year commitment. Then, structure the SLA requirements in order of business criticality. Present fallback positions only after making the case for our primary ask."*

**Performance Description:**
*"Act as an experienced IT procurement consultant who has negotiated dozens of enterprise cloud contracts. Be practical and commercial — focus on what actually works in vendor negotiations, not theoretical best practices. Keep language direct and business-focused."*

**Result:** Claude produces a document that is not just well-formatted but strategically structured, commercially realistic, and written in the voice of someone who actually knows this domain. The three layers of Description working together produce a dramatically better output than a vague single-line request.

---

### ⚠️ Watch Out For

**Trap 1: Stopping at Product Description only**
Most people only describe *what* they want (Product). Adding *how* (Process) and *how to interact* (Performance) dramatically improves output quality — but it requires a bit more upfront thinking.

**Trap 2: Assuming Claude will infer context you have not provided**
Claude cannot read your mind. It does not know your company's context, your project's history, your team's constraints, or your personal preferences unless you tell it. Every relevant detail that you leave out is a source of potential misalignment.

**Trap 3: Over-prompting on your first attempt**
Do not spend 30 minutes crafting the perfect prompt before seeing any output. Try a reasonable first draft, evaluate the output with Discernment, and refine. The Description → Discernment → Refine loop is faster and more effective than trying to perfect your prompt before you have seen anything.

**Trap 4: Forgetting that Performance Description can be updated mid-conversation**
If the AI's interaction style is not working for you, you can correct it at any point: *"Stop including so much background — just give me the key recommendation directly."* Description is not just for the first message.

---

### ✅ Quick Check

**Q1.** A developer asks Claude: *"Explain microservices architecture."* Claude gives a very basic explanation suitable for a beginner. The developer actually has 8 years of experience and wanted a deep technical discussion. Which type of Description was missing from the prompt?

- A) Product Description — the developer did not specify the format of the explanation
- B) Process Description — the developer did not specify the order in which concepts should be covered
- C) Performance Description — the developer did not specify the expected expertise level or interaction style
- D) All three types of Description were equally missing

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

This is primarily a **Performance Description** gap. The developer did not tell Claude about their expertise level, their prior knowledge, or how they wanted Claude to engage with them. Claude defaulted to a beginner-friendly explanation because it had no signal that a deeper, more technical discussion was expected. Adding something like *"I have 8 years of distributed systems experience — give me a technical, nuanced discussion covering tradeoffs, failure modes, and when NOT to use microservices"* would have produced a completely different output.

</details>

---

**Q2.** You want Claude to review a Python script for performance issues. Which prompt demonstrates the best combination of Product, Process, and Performance Description?

- A) *"Review this Python script."*
- B) *"Find bugs in this Python script and fix them."*
- C) *"Review this Python script for performance bottlenecks. First identify all O(n²) or worse operations, then check for unnecessary database calls in loops, then suggest specific optimisations with estimated impact. Present findings as a prioritised list. Be concise and technical — I am a senior Python developer."*
- D) *"You are a Python expert. Review my code."*

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

Option C demonstrates all three types of Description: **Product** (performance bottlenecks, prioritised list), **Process** (specific methodology: check O(n²) first, then database calls, then suggest optimisations with impact), and **Performance** (concise, technical, assumes senior developer background). Options A and B are vague. Option D only addresses Performance (barely) and leaves Product and Process undefined.

</details>

---

**Q3.** During a long conversation, Claude starts giving very lengthy, detailed responses when you actually need quick, direct answers to move fast. What should you do?

- A) Start a new conversation — you cannot change Claude's behaviour mid-conversation
- B) Use a different AI model that is more concise by default
- C) Apply Performance Description mid-conversation: tell Claude directly to be more concise and give direct answers without lengthy preamble
- D) Reduce the temperature setting to make Claude less verbose

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

**Performance Description can and should be applied mid-conversation.** Simply tell Claude: *"From now on, be concise. Give me direct answers without lengthy explanations unless I ask for them."* Claude will adjust immediately. You do not need to start over or switch models. This is one of the most practical and underused aspects of the Description competency — treating AI interaction as a dynamic, steerable conversation rather than a one-shot prompt.

</details>

---

[⬅ Previous: Lesson 4 — A Closer Look at Delegation](./Lesson-04-A-Closer-Look-at-Delegation.md) · [🏠 Course Home](./README.md) · [Next: Lesson 7 — Effective Prompting Techniques ➡](./Lesson-07-Effective-Prompting-Techniques.md)
