# Lesson 7 — Effective Prompting Techniques (Deep Dive)

---

### 📌 What Is This About?

This lesson is the practical hands-on companion to the Description competency. It introduces **six foundational prompting techniques** that translate the Description competency into concrete, actionable skills. It also covers the iterative nature of prompting and the "secret weapon" of asking Claude to help improve your own prompts.

---

### 💡 Why Does This Matter?

Description as a concept is important — but you need practical techniques to implement it. This lesson gives you a concrete toolkit: six techniques that work across different AI systems and are grounded in how LLMs actually process information. Think of this as your prompt engineering fundamentals course — not the fad-based "10 magic prompts" variety, but the deep principles that stay relevant as models evolve.

---

### 📖 The Story

Prompting is simply the practical application of the Description competency. It is about clearly communicating what you want, how you want it done, and how you want to interact with your AI assistant throughout the process.

> *"Think of prompting like explaining a task to a helpful new colleague who is eager to assist but needs clear directions and expectation-setting to do their best work."*

#### Technique 1: Give Claude Context

The most fundamental technique is being specific and clear about:
- **What you want** — the actual task
- **Why you want it** — the purpose and how it will be used
- **Who you are** — your background, expertise level, and role

**Weak prompt:**
> *"Tell me about cloud security."*

**Stronger prompt with context:**
> *"Explain the top 5 cloud security misconfigurations that lead to data breaches in AWS environments. I am an IT infrastructure engineer preparing a security awareness presentation for our development team, who are intermediate-level AWS users. Include a real-world example for each misconfiguration."*

The second prompt tells Claude: the topic (cloud security misconfigs), the scope (AWS, top 5), the audience for the final output (developers), the audience's knowledge level (intermediate AWS), the format needed (5 items with examples), and the purpose (security awareness presentation).

#### Technique 2: Show Examples of What "Good" Looks Like

Sometimes showing is better than telling. Providing examples of the output style, format, or tone you are looking for is extremely effective. This is called **few-shot prompting** (or **N-shot prompting** where N is the number of examples provided).

**Example of few-shot prompting:**
> *"Convert technical terms to plain language for a non-technical audience. Here are two examples:*
> *Technical: 'The API endpoint returns a 503 status code.' Plain: 'The service is temporarily unavailable — try again in a few minutes.'*
> *Technical: 'The database query is experiencing deadlock.' Plain: 'Two parts of the system are waiting for each other and neither can proceed — a restart will fix it.'*
> *Now convert this: 'The microservice is experiencing cascading failures due to circuit breaker activation.'"*

> **Fact check:** Few-shot prompting is a well-established and empirically validated technique in LLM research. The original GPT-3 paper (Brown et al., 2020) demonstrated that providing just a few examples in the prompt (in-context learning) allows models to generalise to new tasks without any weight updates. This remains one of the most practical and powerful prompting techniques.

**Practical tip:** When providing examples, try to cover diverse cases — different styles, edge cases, or variations — so Claude understands the full range of the pattern you want it to follow.

#### Technique 3: Specify Output Constraints

Be explicit about the boundaries and format of the output you need:
- Length (maximum word count, number of bullet points, number of pages)
- Format (table, numbered list, prose, JSON, Markdown)
- Coding language (Python, JavaScript, SQL)
- What to include and explicitly what to exclude
- Specific structural elements required

**Example:**
> *"Create an API endpoint specification. Output as a JSON object with these fields: endpoint_name, method, path, request_body_schema, response_schema, and error_codes. Keep descriptions under 50 words each. Include only the POST /users endpoint."*

This leaves no ambiguity about format, length, or scope.

#### Technique 4: Break Complex Tasks into Steps

For complicated requests, listing out the steps you want Claude to follow ensures it approaches the problem in the way you intend. This is related to **chain-of-thought prompting** — guiding the AI's reasoning process.

**Weak prompt:**
> *"Analyse our Q4 infrastructure costs and make recommendations."*

**Stronger prompt with step breakdown:**
> *"Analyse our Q4 infrastructure costs by following these steps:*
> *1. First, categorise all costs by service type (compute, storage, network, support)*
> *2. Then, identify the top 3 cost drivers by absolute spend*
> *3. Next, compare Q4 spend against Q3 for each service type and flag any increase above 20%*
> *4. Finally, suggest three specific cost optimisation actions with estimated savings for each*
> *Present your analysis in the same order as these steps."*

This is essentially providing a runbook for Claude to follow.

> **Fact check:** Chain-of-thought prompting was formally studied in a 2022 paper by Google Brain researchers (Wei et al., "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models"). It was shown to significantly improve LLM performance on complex reasoning tasks by explicitly guiding the model to reason step by step rather than producing an immediate answer. Modern reasoning models (like Claude's extended thinking mode) perform this chain-of-thought internally by default, but explicit step guidance still helps for domain-specific workflows.

#### Technique 5: Ask Claude to Think First

For complex problems, explicitly tell Claude to think through the problem before responding. This produces more considered, accurate answers.

**Example:**
> *"Before answering, think through the problem carefully. Consider the different factors involved, potential edge cases, and tradeoffs. Then provide your recommendation with reasoning."*

> **Important nuance:** The course makes a subtle but important point — ask Claude to think *before* acting, not *after*. Asking it to "explain your thinking" after it has already given an answer is different from asking it to *think first* before answering. The former is post-hoc rationalisation; the latter genuinely improves the quality of the output.

Modern reasoning models (like Claude's extended thinking mode) do this by default. But for standard models, this explicit instruction makes a real difference.

#### Technique 6: Define Claude's Role, Style, or Tone

Specify who you want Claude to be during the interaction. This shapes not just the content but the entire approach.

**Examples:**
- *"Act as a senior security consultant with 15 years of experience in enterprise architecture..."*
- *"You are an IT change manager reviewing this RFC for completeness and risk..."*
- *"Respond as a patient, non-technical explainer helping a business executive understand technical concepts..."*

This can dramatically change the depth, perspective, and style of the response.

#### The Secret Weapon: Ask Claude to Improve Your Prompt

When you are not sure how to phrase your request, use this meta-technique: ask Claude to help you write a better prompt.

**Example:**
> *"I am trying to get you to help me analyse system performance logs to identify the root cause of intermittent latency spikes. I am not sure how to phrase my request to get the most useful output. Can you help me craft an effective prompt for this, including what context I should provide and what format the output should take?"*

This is particularly powerful when you are working in a new domain or trying to get Claude to produce something you can describe in words but cannot easily structure into a prompt.

#### Iteration Is Key

**Effective prompting is iterative.** Your first attempt will not always yield the perfect result — and that is completely expected. When a response is not what you need:

- Add more specificity or context
- Provide examples of your desired output
- Break the task into smaller steps
- Try a different framing or combination of techniques
- Ask for variations: *"Give me three different versions of this"*
- Request a different format: *"Instead of prose, present this as a comparison table"*
- Check Claude's confidence on factual claims: *"How confident are you about this? Are there any parts you are uncertain about?"*
- Reset the conversation: Sometimes starting fresh gives better results than trying to correct a conversation that has gone off track

---

### 📊 Key Concepts Snapshot

| Technique | What It Does | When to Use |
|-----------|-------------|------------|
| **Give Context** | Tells Claude the who, what, why, and how of your request | Always — this is the foundation |
| **Show Examples (Few-shot)** | Demonstrates the format or style through examples | When style is hard to describe in words |
| **Specify Output Constraints** | Defines format, length, structure, and boundaries | When you have specific formatting requirements |
| **Break into Steps** | Provides a methodology for Claude to follow | For complex, multi-step analysis or workflows |
| **Ask Claude to Think First** | Encourages deliberate reasoning before responding | For complex problems requiring careful analysis |
| **Define Role/Tone** | Sets persona, expertise level, and interaction style | When you need a specific perspective or communication style |
| **Ask Claude to Improve Your Prompt** | Uses Claude to help craft better instructions | When you are unsure how to structure your request |

**Common patterns that consistently work well:**
- Start with a clear task overview statement
- Include format specifications and examples
- Set explicit constraints and requirements
- Provide rich, relevant background information

**Common mistakes to avoid:**
- Assuming Claude can read your mind
- Overloading one prompt with multiple unrelated tasks
- Being vague about what success looks like
- Not providing feedback on previous responses

---

### 🏢 Real-World Scenario

**Situation:** You need Claude to help you write a post-incident review (PIR) document for a production outage that occurred last night.

**Using all 6 techniques:**

*"You are a senior SRE (Site Reliability Engineer) with extensive experience writing post-incident reviews following Google's SRE methodology. [Role/Tone]*

*Write a Post-Incident Review document for a production API outage that lasted 47 minutes last night. [Product Description]*

*Follow this structure: [Step breakdown]*
1. Incident Summary (2-3 sentences)
2. Timeline of events with timestamps
3. Root Cause Analysis (use the 5-Whys method)
4. Impact Assessment (users affected, SLA impact, revenue impact if known)
5. Contributing Factors
6. Action Items (categorised as: Immediate / Short-term / Long-term)
7. Lessons Learned

*Before writing, think through each section and what information would make each section most useful for the on-call team going forward. [Think first]*

*Keep the tone professional and blameless — focus on systems and processes, not individuals. Maximum 2 pages. Use headers for each section. [Output constraints]*

*Here is an example of the tone and level of detail I want for the Root Cause Analysis section: [Example follows...]*"*

**Result:** A structured, professionally written PIR document that follows industry best practice, uses the right methodology, maintains the right tone, and is immediately usable — generated in seconds rather than the 45–60 minutes it typically takes to draft manually.

---

### ⚠️ Watch Out For

**Trap 1: Treating prompting as a one-time formula**
There is no magic prompt that works for everything. Effective prompting is a skill built through iteration and experimentation. What works for one task may need adjustment for another.

**Trap 2: Using few-shot examples that are too similar**
When providing examples, use examples that cover the full diversity of your use case — different styles, different edge cases. Giving three identical-looking examples teaches Claude too narrow a pattern.

**Trap 3: Asking Claude to think "after" instead of "before"**
Saying *"Explain your reasoning"* after Claude has given an answer is not the same as saying *"Think carefully before answering."* The former asks for post-hoc justification; the latter genuinely improves reasoning quality.

**Trap 4: Not resetting when a conversation goes off track**
If Claude has gotten confused or developed an incorrect frame for your request, sometimes it is faster to start a fresh conversation with an improved prompt than to keep trying to correct the existing conversation.

---

### ✅ Quick Check

**Q1.** You are writing a prompt to get Claude to generate test cases for a new REST API. You provide two example test cases showing the format you want (method, endpoint, test description, expected result). What prompting technique are you using?

- A) Chain-of-thought prompting — you are showing Claude the reasoning steps
- B) Few-shot prompting — you are providing examples of the desired output format for Claude to emulate
- C) Process Description — you are guiding how Claude approaches the task
- D) Performance Description — you are defining Claude's interaction style

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: B**

This is **few-shot prompting** (also called N-shot prompting). You are providing concrete examples of what the output should look like so Claude can understand the exact format and style you need. This is one of the most effective techniques when the format is easier to demonstrate than to describe in words. Note that it also overlaps with Product Description (defining what you want), but the specific technique of using examples is few-shot prompting.

</details>

---

**Q2.** You ask Claude to analyse a complex security incident and then say: *"Show me your thinking before giving me the final answer."* According to the course, what is the issue with this approach?

- A) There is no issue — asking Claude to show its reasoning is always beneficial
- B) Claude cannot explain its reasoning — this request will be ignored
- C) You asked Claude to explain its thinking *after* it has already committed to an answer — this produces post-hoc rationalisation rather than genuinely improved reasoning. You should ask it to think *before* answering.
- D) This approach only works with reasoning models, not standard Claude

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

The course makes an important distinction: asking Claude to *think first* (before generating the response) genuinely improves output quality because the thinking shapes the answer. Asking Claude to *explain its thinking after* the response is already given produces a rationalisation of a decision already made — the reasoning is reconstructed, not generative. The correct approach is: *"Before answering, think through this carefully, considering [factors]. Then provide your recommendation."*

</details>

---

**Q3.** After three attempts at prompting Claude, you are still not getting the structured output you need for a monthly compliance report, but you cannot quite articulate why. What is the most effective next step?

- A) Switch to a different AI model — Claude is not suitable for compliance reports
- B) Write a longer, more detailed prompt covering every possible scenario
- C) Ask Claude directly: describe your goal and the problem you are having, and ask it to help you craft a better prompt for this specific task
- D) Reduce temperature to get more consistent outputs

<details>
<summary>👉 Click to reveal answer</summary>

**Correct Answer: C**

The **"ask Claude to improve your prompt"** technique is the secret weapon for exactly this situation. When you know what you want but cannot figure out how to ask for it, describe your goal and your challenge to Claude and ask it to help you craft a better prompt. Claude can ask clarifying questions, suggest relevant context to include, and propose a structured prompt template. This is often faster and more effective than continuing to iterate on a poorly structured prompt on your own.

</details>
