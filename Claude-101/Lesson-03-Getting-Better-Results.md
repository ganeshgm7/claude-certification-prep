# Lesson 3 — Getting Better Results

> **Estimated time:** 15 minutes

---

### 📌 What Is This About?

This lesson is about troubleshooting. Every new Claude user hits a few common bumps — responses that are too generic, too long, wrong tone, wrong format, or confidently wrong facts. This lesson gives you a fix for each of these bumps, introduces the idea of **AI Fluency**, and shows you a simple way to test ("eval") how well Claude actually performs on the specific tasks that matter to you.

---

### 💡 Why Does This Matter?

If you don't know how to fix a bad response, you might give up on Claude too early — thinking "it's not good at this" when actually your prompt just needed a small tweak. Learning these fixes turns frustration into a quick, two-minute correction. And learning to "eval" Claude on your own work builds real trust — not blind trust, but *earned* trust based on evidence.

---

### 📖 The Explanation

#### Common challenges and how to fix them

| Challenge | What's Happening | Try This |
|---|---|---|
| **Response is too generic** | Your prompt didn't include enough context about your specific situation | Add details about audience, role, or constraints. Instead of "Write an email about the project delay," try: "Write an email to our enterprise client explaining that the software integration will be delayed by two weeks. They've been patient so far but this is the second delay. Keep it professional but apologetic." |
| **Response too long (or too short)** | Claude is guessing at the right length | Be explicit: "Give me a two-paragraph summary," "Keep this under 100 words," or "I need a comprehensive analysis — length isn't a concern." |
| **Didn't follow my format** | Claude understood *what* you want but not *how* to present it | Show, don't just tell. Give an example format, or describe the structure explicitly: "Use bullet points with bold headers for each section." |
| **Confident-sounding info that turned out wrong** | Claude occasionally generates plausible but incorrect information, especially with specific facts or niche topics | For high-stakes work, verify key facts independently. Ask Claude to cite sources or state its confidence level. Enable web search to ground responses in current information. |
| **Tone isn't right** | Claude defaults to helpful and professional, which may not match your needs | Describe the tone in plain language: "Make this more conversational" or "This should sound authoritative and formal." Give an example of the writing style you want. |

#### The iteration mindset

The biggest mental shift when working with Claude: **your first prompt rarely produces a perfect result — and that's okay.** Treat your initial prompt as the start of a conversation, not a one-shot request.

Effective Claude users:
- **Treat first drafts as starting points.** Review, identify what's working and what isn't, then refine.
- **Give specific feedback.** "Make it shorter" is fine, but "Cut the first two paragraphs and make the conclusion more action-oriented" is much better.
- **Know when to start fresh.** If a conversation has gone off track, sometimes a new chat with a clearer prompt is faster than trying to redirect the old one.

#### What is AI Fluency?

**AI Fluency** is the ability to collaborate effectively with AI tools — not just knowing which buttons to click, but developing the *judgement* to use AI well across different situations.

The **4D Framework for AI Fluency** (developed by Prof. Rick Dakan, Ringling College of Art and Design, and Prof. Joseph Feller, University College Cork) names four core competencies:

- **Delegation** — deciding what work should be done by humans, what by AI, and how to distribute tasks between them.
- **Description** — communicating effectively with AI systems — clearly defining outputs, guiding processes, specifying desired behaviour.
- **Discernment** — thoughtfully and critically evaluating AI outputs — quality, accuracy, appropriateness, areas to improve.
- **Diligence** — using AI responsibly and ethically — transparency and accountability for AI-assisted work.

You've already been practising these! The prompt framework from Lesson 2 (setting the stage, defining the task, specifying rules) is rooted in **Description**. The troubleshooting techniques in this lesson draw on **Discernment** and **Diligence**.

> **Good to know:** Anthropic's free AI Fluency course explores all four competencies in depth, with practical exercises.

#### Evaluating Claude for your workflows ("Evals")

As you use Claude more in your work, a natural question comes up: *how do I know if Claude is actually good at this particular task?* This is where **Discernment** becomes essential.

**Evals** (short for evaluations) are a systematic way to test how well Claude performs on tasks that matter to *you*. Running simple evals helps you:
- Understand where Claude adds the most value in your workflow.
- Identify tasks where you'll need to give more context or examples.
- Build confidence in Claude's outputs for recurring tasks.

**A simple eval approach — 4 steps:**
1. **Gather examples.** Collect 5–10 examples of a task you do regularly (emails, reports, analyses).
2. **Create test prompts.** Write prompts that would generate similar outputs, including the natural context you'd have while doing the work.
3. **Compare outputs.** Run your prompts and compare Claude's responses to your own examples: Does it capture the key information? Is the tone/style right? What's missing?
4. **Refine your approach.** Adjust prompts, add examples of "what good looks like," or identify where human review is essential.

#### Example — Using Claude for data analysis (the "delegation-diligence loop")

This example comes from a video (originally from the AI Fluency for Nonprofits course), but it applies to anyone working with data.

The core idea: build confidence in AI's analytical capability for **your specific work** by systematically testing it against data you already understand. This is called the **delegation-diligence loop**:

> Identify a specific task to delegate → find past data where you already completed that analysis (a known-answer test case) → work with AI to reproduce it, checking every response against what you already know → refine your prompt and test again. If AI matches your known results, you can trust it for similar future tasks. If it consistently doesn't, you've learned this isn't a task to delegate.

**Story — Rio, program director at Valley Veterans Services:**

Every quarter, Rio analyses program attendance alongside employment outcomes — participation rates, monthly changes, and whether attendance correlates with job placement success. This normally takes him hours. He wants to keep interpreting results himself but hand off the data-cleaning and formula work.

- He uses **last quarter's known data** as his test case (he already knows the "right answer").
- First prompt: *"I'm sharing attendance data and employment outcome data from our job training program last quarter. Please analyze the participation patterns across the three months and graph the correlations between attendance levels and employment success. I'm particularly interested in understanding whether consistent attendance predicts better job placement outcomes."*
- AI correctly found the attendance-placement correlation, but **missed** an insight about a combined housing-assistance + job-placement program. Rio refined his prompt (asked AI to pay attention to program type) — and on the retry, AI caught it.
- Rio also tested a harder ask (segmenting by enrollment date). AI could help even without explicit enrollment dates by inferring them — but Rio flagged this to cross-check later rather than trust it blindly. He noted: AI needs actual enrollment dates for cohort analysis, otherwise it infers them, which he doesn't want.
- **Result:** Rio now has a validated, repeatable approach for his quarterly reporting — plus clear notes on what context he must add himself each time. His ongoing diligence: sanity-check numbers, take accountability for the final report, and be transparent about AI's role if asked.
- **If you're not very data-savvy yourself:** AI can still help — bring your question to it like you would to a data-analyst teammate (e.g., "help me write this Excel formula" or "help me reformat this messy data"), and keep asking for clarifications so you can follow the process. Validation builds confidence, but it never removes your responsibility to check the results.

This testing approach works for any analytical task — donor analysis, budget forecasting, survey synthesis, outcome tracking. **Test first, validate what works, then apply with confidence — or learn what you shouldn't delegate.**

---

### 📊 Key Concepts Snapshot

| Term | Meaning | Why It Matters |
|------|---------|-----------------|
| **Iteration mindset** | Treating the first prompt as a conversation starter, not the final word | Saves you from giving up too early on a "bad" response |
| **AI Fluency** | The judgement to use AI well across situations, not just tool tricks | The overarching skill this whole course builds toward |
| **4D Framework** | Delegation, Description, Discernment, Diligence | A complete mental model for working with AI responsibly |
| **Evals** | A simple, repeatable way to test Claude on tasks that matter to you | Builds evidence-based trust instead of blind trust |
| **Delegation-diligence loop** | Test AI against data you already know the answer to, then refine | The practical, step-by-step way to run an eval on analytical work |

---

### 🏢 Real-World Scenario

**Situation:** Rio (program director, described above) wants to trust Claude with his quarterly attendance-vs-employment analysis, which normally eats up hours of his time.

**What he did:** Used last quarter's already-known data as a "test case," ran the analysis with Claude, checked every result against what he already knew, and refined his prompt each time a gap showed up (like asking Claude to consider "program type"). After 2-3 rounds, he had a validated, repeatable prompt he could trust for new data — along with clear notes on what extra context to always provide (like enrollment dates).

**The takeaway:** He didn't blindly trust Claude, and he didn't dismiss it after one imperfect answer either. He tested it like you'd test a new team member — with real work, checked against known answers.

---

### 🤔 Lesson Reflection

- Which of the common challenges above have you already run into? What will you try next time?
- Where in your work would a simple eval help you understand if Claude is a good fit for a recurring task?
- How might the 4D Framework help you think about your collaboration with Claude going forward?

---

### ⏭️ What's Next

In the next lesson, you'll explore the Claude desktop app and its three interaction modes: **Chat, Cowork, and Code.**
