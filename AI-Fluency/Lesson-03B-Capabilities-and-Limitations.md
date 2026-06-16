# Lesson 3B — Capabilities & Limitations of Generative AI

---

### 📌 What Is This About?

This lesson is your practical guide to knowing what LLMs like Claude genuinely do well — and where they fall short. Think of it as getting to know a new colleague: understanding their strengths and limitations helps you work with them more effectively, assign the right tasks, and know when to step in.

---

### 💡 Why Does This Matter?

In IT, we are very comfortable with the concept that every system has a purpose and a limit. A Redis cache is excellent for fast key-value lookups but is not the right tool for complex relational queries. Knowing this prevents the wrong tool being chosen for the wrong job.

The same principle applies to LLMs. Knowing Claude's real strengths prevents under-use. Knowing its real limitations prevents over-reliance and the professional embarrassment of shipping AI-generated output that turns out to be wrong.

---

### 📖 The Story

#### What LLMs Do Remarkably Well

**1. Language Tasks — Their Core Strength**

LLMs excel at anything involving language. This includes:
- **Writing and drafting** — emails, reports, documentation, release notes, SOPs
- **Summarisation** — condensing long documents into clear summaries
- **Translation** — between languages (quality has improved dramatically)
- **Explanation** — breaking down complex topics for different audiences
- **Tone and style adjustment** — rewriting formal content casually, or vice versa

What is particularly impressive is the ability to shift between completely different domains without any additional training. The same Claude instance that helps you debug Python code can explain quantum computing concepts, draft a project proposal, and then discuss ITIL service management — all in the same session.

**2. Maintaining Conversational Context**

Within a single context window, LLMs can maintain the thread of a conversation with remarkable coherence. If you mention your project deadline early in a conversation, Claude will remember and reference it later — much like a human colleague would. This makes extended brainstorming and iterative work genuinely productive.

**3. In-Context Learning**

One of the most powerful features of modern LLMs is their ability to **adapt to new tasks based on instructions or examples in your prompt** — without requiring any additional training.

If you give Claude three examples of how you want something formatted, it will follow that pattern for all subsequent outputs. This is called **few-shot prompting** (covered in depth in Lesson 7) and it is one of the most practical skills in the AI Fluency toolkit.

**4. Connecting to External Tools**

Many modern LLM deployments — including Claude — can be connected to external tools like web search, code execution environments, file systems, and APIs. This dramatically expands what they can help with, allowing them to access real-time information and take real-world actions.

#### Where LLMs Have Real Limitations

**Limitation 1: Knowledge Cutoff Date**

LLMs are trained on data up to a specific date — the **knowledge cutoff**. After that date, the model has no built-in knowledge of world events, new software versions, regulatory changes, or anything else.

> **Example:** A model with a cutoff of late 2024 will not know about software vulnerabilities discovered in 2025 unless you tell it, or it has access to a web search tool.

Think of it as a brilliant colleague who has been completely offline since a specific date — knowledgeable about everything up to that point, but unaware of anything since.

**Solution:** Use models with web search capability, or explicitly provide recent information in your prompts.

**Limitation 2: Hallucination**

**Hallucination** is one of the most important limitations to understand. It refers to the tendency of LLMs to generate content that is **confidently stated but factually incorrect** — fabricated references, wrong statistics, invented names, plausible-sounding but false claims.

This happens because LLMs generate text based on statistical patterns, not from verified factual retrieval. The model is not checking a database — it is generating the most statistically likely continuation. Sometimes the most statistically likely continuation is wrong.

> **Fact check:** Hallucination is a well-documented, extensively researched limitation of current LLMs. It is sometimes called "confabulation" in technical literature. Research by Anthropic, Google, and OpenAI acknowledges this as an ongoing challenge being addressed through techniques like RLHF, constitutional AI, and better retrieval-augmented systems. It has not been "solved" as of the knowledge cutoff for this document.

> **IT Parallel:** Imagine a junior developer who writes documentation that sounds completely authoritative but contains several subtle errors. You cannot blindly trust it — you need to review it with domain knowledge.

**Limitation 3: Context Window Constraints**

As covered in Lesson 3A, the context window is finite. For very long documents, extended analyses, or multi-session projects, you need to manage what information is in the context window deliberately.

**Limitation 4: Non-Determinism (Variability)**

Unlike traditional software that produces identical outputs for identical inputs, LLMs are **non-deterministic** — ask the same question twice and you may get different responses.

This stems from the probabilistic nature of text generation. The model makes probability-based decisions about what word comes next — and those probabilities can be tuned via a parameter called **temperature**:

- **Low temperature (e.g., 0.1):** More deterministic, conservative, consistent responses. Good for factual tasks, code generation, and structured outputs.
- **High temperature (e.g., 1.0+):** More creative, varied, unpredictable responses. Good for brainstorming, creative writing, generating diverse ideas.

> **Fact check:** Temperature is a standard parameter in LLM APIs including Anthropic's Claude API. It controls the randomness of token selection. A temperature of 0 makes the model always pick the highest-probability next token (fully deterministic). Most production API deployments use a temperature between 0 and 1.

**Limitation 5: Complex Multi-Step Reasoning**

Historically, LLMs have struggled with tasks requiring precise multi-step logical or mathematical reasoning — problems where getting step 3 wrong makes step 4 and 5 also wrong.

However, this is an area of rapid improvement. **Extended thinking models** (also called reasoning models) are specifically designed to work through problems step by step before responding, showing significant improvement in these areas. Claude's extended thinking capability is an example of this.

**Limitation 6: Limited Access to Specific Data Sources**

Even when connected to tools, an LLM may not have access to your company's internal systems, proprietary databases, or specialised domain information. It is like having a brilliant consultant who cannot access your internal systems — their ability to help on specific questions is limited regardless of their general intelligence.

**The Future Direction: RAG and Beyond**

Researchers are actively addressing LLM limitations through techniques like:
- **Retrieval Augmented Generation (RAG):** Connecting the model to external knowledge bases so it can retrieve accurate, up-to-date information before generating a response. This directly addresses the knowledge cutoff and hallucination problems.
- **Tool use and function calling:** Allowing models to invoke APIs, run code, and interact with external systems in real time.
- **Better reasoning models:** Extended thinking capabilities that perform step-by-step reasoning before committing to an answer.

---

### 📊 Key Concepts Snapshot

| Capability / Limitation | What It Means | Practical Takeaway |
|------------------------|--------------|-------------------|
| **Language fluency** | Excellent at writing, summarising, translating, explaining | Delegate language tasks confidently |
| **In-context learning** | Adapts to new tasks from examples in the prompt | Use few-shot examples for style and format consistency |
| **Tool connectivity** | Can access web, APIs, code execution | Check what tools are connected before assuming limitations |
| **Knowledge cutoff** | No knowledge of events after training date | Provide recent info explicitly, or use web search |
| **Hallucination** | Can generate confident but false information | Always verify factual claims, especially in high-stakes contexts |
| **Non-determinism** | Same input may give different outputs | Use temperature settings; review outputs before using |
| **Temperature** | Controls randomness of output generation | Low temp for accuracy, high temp for creativity |
| **Context window limits** | Finite working memory per conversation | Plan context usage for long documents or conversations |
| **Complex reasoning** | Historically weak; improving with reasoning models | Break complex problems into steps; verify multi-step logic |
| **RAG** | Retrieval Augmented Generation — connects AI to external knowledge | Key technique for enterprise AI applications |

---

### 🏢 Real-World Scenario

**Situation:** Your company is building a Claude-powered security advisory tool. Employees can ask questions like *"What is the current best practice for zero-trust network architecture?"* and *"Is CVE-2024-XXXXX relevant to our stack?"*

**Applying knowledge of capabilities and limitations:**

**Knowledge cutoff issue:** Security is a rapidly evolving field. A question about a specific CVE disclosed after Claude's training cutoff will not return useful information without web search. **Solution:** Connect Claude to a web search tool or a curated security intelligence feed via RAG.

**Hallucination risk:** If a user asks *"How many organisations were affected by the Log4Shell vulnerability?"* Claude might generate a plausible-sounding number that is not accurate. **Solution:** For factual, numerical questions, always instruct Claude to cite sources or acknowledge uncertainty. Build a Discernment step into your workflow.

**Temperature setting:** For security advisories, you want **low temperature** — consistent, accurate, conservative responses. This is not a context for creative variability. Set temperature to 0.1–0.3 in your API configuration.

**Context window planning:** If you want Claude to be aware of your company's specific technology stack and security policies, include those in the system prompt — and monitor that they stay within the context window as conversations get long.

**Result:** A well-designed system that leverages Claude's strengths while actively compensating for its known limitations.

---

### ⚠️ Watch Out For

**Trap 1: Trusting Claude on recent events without verification**
If a user asks about something that happened recently, Claude may either say it does not know (good) or generate a plausible-sounding but inaccurate answer (dangerous). Always verify time-sensitive factual claims.

**Trap 2: Treating hallucinations as rare edge cases**
Hallucinations are more common than most users expect, especially for very specific facts (exact statistics, specific dates, specific names, citations). The more specific and verifiable the claim, the more you should verify it independently.

**Trap 3: Using high temperature for accuracy-critical tasks**
If you are using the API and have left temperature at default (or worse, set it high for a "creative" use case), you are getting more variable outputs than needed. For structured, factual tasks, lower the temperature.

**Trap 4: Assuming Claude knows your internal systems**
Claude has no knowledge of your company's infrastructure, policies, code, or data unless you explicitly provide it in the prompt or connect it via integrations. Do not assume it has context it does not have.

---

### ✅ Quick Check

**Q1.** An engineer asks Claude to confirm whether a specific software library has a known security vulnerability, and Claude confidently provides detailed CVE information — but the library was released three months after Claude's training cutoff. What has most likely occurred?

- A) Claude retrieved inaccurate information from a connected database
- B) Claude hallucinated a plausible-sounding but potentially inaccurate CVE response based on statistical patterns
- C) Claude's context window was exceeded, causing it to generate random output
- D) The temperature setting was too high, causing excessive creativity in the response

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: B**

This is a classic **hallucination** scenario, compounded by the **knowledge cutoff** limitation. The library did not exist during Claude's training, so the model has no real knowledge of it. However, because it has learned patterns about how CVE descriptions are written, it can generate something that *sounds* authoritative and specific — but is fabricated. This is exactly why Discernment is so critical, especially for security-related queries where accuracy is non-negotiable.

</details>

---

**Q2.** You are building a customer-facing chatbot using Claude API. For answering FAQs consistently, you want every user asking the same question to get essentially the same answer. Which API parameter should you adjust, and in which direction?

- A) Increase temperature to ensure diverse, creative responses
- B) Decrease temperature (set low, e.g., 0.1–0.2) to make responses more deterministic and consistent
- C) Increase context window size to ensure all FAQ content fits
- D) Decrease max_tokens to prevent the model from generating unnecessary text

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: B**

**Temperature** controls the randomness of text generation. For FAQ-style, accuracy-focused responses where consistency is important, you want a **low temperature** (close to 0). This makes the model more deterministic — it will consistently pick the highest-probability next token rather than introducing variability. High temperature is appropriate for creative writing or brainstorming where diversity of response is actually desirable.

</details>

---

**Q3.** What is Retrieval Augmented Generation (RAG), and what core LLM limitations does it primarily address?

- A) A fine-tuning technique that makes the model more accurate; it addresses hallucination by retraining the model on verified data
- B) A technique that connects the model to external knowledge sources at inference time; it addresses the knowledge cutoff and hallucination limitations
- C) A method of compressing the context window to allow longer documents; it addresses context window limitations
- D) A training technique that increases the number of model parameters; it addresses complex reasoning limitations

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: B**

**RAG (Retrieval Augmented Generation)** is a technique where, before generating a response, the system retrieves relevant, accurate, and up-to-date information from an external knowledge base (such as a company's internal documents, a live database, or a curated knowledge store) and provides it to the model as context. This addresses two major limitations: (1) the **knowledge cutoff** — RAG can provide current information regardless of training date; and (2) **hallucination** — grounding responses in retrieved factual content reduces the model's tendency to fabricate information.

</details>
