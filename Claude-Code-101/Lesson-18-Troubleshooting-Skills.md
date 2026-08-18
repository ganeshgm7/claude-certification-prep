# Lesson 18 — Troubleshooting Skills

[⬅ Previous: Lesson 17 — Sharing Skills](./Lesson-17-Sharing-Skills.md) · [🏠 Course Home](./README.md) · [Next: Lesson 19 — MCP (Model Context Protocol) ➡](./Lesson-19-MCP-Model-Context-Protocol.md)

---

### 📌 What Is This About?

When skills don't work as expected, the problem usually falls into a few predictable categories. This final skills lesson walks through each one — from skills that don't trigger, to priority conflicts, to runtime failures — with a systematic troubleshooting approach and a quick checklist.

---

### 💡 Why Does This Matter?

A skill that silently fails to trigger, or gets shadowed by another skill, can quietly waste hours of "why isn't this working" confusion. Knowing exactly which category a problem falls into (and the standard fix for each) turns that into a two-minute correction.

---

### 📖 The Explanation

#### Use the Skills Validator
The first thing to try is the agent skills verifier command. Installation steps vary by operating system, but using `uv` is the easiest way to get it set up quickly. Once installed, either navigate to your skill directory or run the command from anywhere. The validator will catch structural problems before you spend time debugging other things.

#### Skill Doesn't Trigger
Your skill exists and passes validation, but Claude isn't using it when you expect. The cause is almost always the description.

Claude uses semantic matching, so your request needs to overlap with the description's meaning. If there's not enough overlap, no match. Here's what to do:
- Check your description against how you're actually phrasing requests.
- Add trigger phrases users would actually say.
- Test with variations like "help me profile this," "why is this slow?", "make this faster."
- If any variation fails to trigger, add those keywords to your description.

#### Skill Doesn't Load
If your skill doesn't appear when you ask Claude "what skills are available," check these structural requirements:
- The `SKILL.md` file must be inside a named directory, not at the skills root.
- The file name must be exactly `SKILL.md` — all caps on "SKILL", lowercase "md".

Run `claude --debug` to see loading errors. Look for messages mentioning your skill name. Sometimes this alone will point you straight to the problem.

#### Wrong Skill Gets Used
If Claude uses the wrong skill or seems confused between skills, your descriptions are probably too similar. Make them distinct. Being as specific as possible doesn't just help Claude decide when to use your skill — it also prevents conflicts with other similar-sounding skills.

#### Skill Priority Conflicts
If your personal skill is being ignored, an enterprise or higher-priority skill might have the same name. For example, if there's an enterprise "code-review" skill and you also have a personal "code-review" skill, the enterprise one wins every time. Your options:
1. Rename your skill to something more distinct (this is usually the easier path).
2. Talk to your admin about the enterprise skill.

![An enterprise skill taking priority over a personal skill with the same name](https://everpath-course-content.s3-accelerate.amazonaws.com/instructor%2Fa46l9irobhg0f5webscixp0bs%2Fpublic%2F1771527274%2FSkills6_12.1771527274623.png)

#### Plugin Skills Not Appearing
Installed a plugin but can't see its skills? Clear the cache, restart Claude Code, and reinstall. If skills still don't appear after that, the plugin structure might be wrong — this is when the validator tool really earns its keep.

#### Runtime Errors
The skill loads but fails during execution. A few common causes:
- **Missing dependencies** — if your skill uses external packages, they must be installed. Add dependency info to your skill description so Claude knows what's needed.
- **Permission issues** — scripts need execute permission. Run `chmod +x` on any scripts your skill references.
- **Path separators** — use forward slashes everywhere, even on Windows.

#### Quick Troubleshooting Checklist
- **Not triggering?** Improve your description and add trigger phrases.
- **Not loading?** Check your path, file name, and YAML syntax.
- **Wrong skill used?** Make descriptions more distinct from each other.
- **Being shadowed?** Check the priority hierarchy and rename if needed.
- **Plugin skills missing?** Clear cache and reinstall.
- **Runtime failure?** Check dependencies, permissions, and paths.

---

### 📊 Key Concepts Snapshot

| Symptom | Most Likely Cause | Fix |
|---|---|---|
| Skill doesn't trigger | Description doesn't semantically overlap with your request | Add real trigger phrases you'd actually say |
| Skill doesn't load | Wrong path/filename | Named directory + exact `SKILL.md`, check with `claude --debug` |
| Wrong skill used | Descriptions too similar | Make each description more distinct |
| Personal skill ignored | Priority conflict (enterprise wins) | Rename, or talk to your admin |
| Plugin skills missing | Cache / bad plugin structure | Clear cache, restart, reinstall; validate structure |
| Runtime error | Missing deps / permissions / path separators | Add deps to description, `chmod +x`, use forward slashes |

---

### 🏢 Real-World Scenario

**Situation:** You built a "performance-review" skill, but Claude never seems to use it, even when you ask "why is this slow?"

**Diagnosis:** Run the skills validator first to rule out structural issues. Since it passes, the cause is almost certainly the description not overlapping semantically with how you phrase requests. Add trigger phrases like "help me profile this" and "make this faster" to the description, and test again — now it activates reliably.

---

### 🤔 Lesson Reflection

- Have you encountered any of these troubleshooting scenarios in your own work? Which fix would have saved you the most time?
- How would you set up a process to validate skills before sharing them with your team?

---

### ⏭️ What's Next

**Course wrap-up (Agent Skills module):** you've now learned how to create, configure, share, and troubleshoot skills in Claude Code. The best skills come from real pain points — start with the instructions you find yourself repeating most often. Next up, the final module: **MCP** and **Hooks**.

---

[⬅ Previous: Lesson 17 — Sharing Skills](./Lesson-17-Sharing-Skills.md) · [🏠 Course Home](./README.md) · [Next: Lesson 19 — MCP (Model Context Protocol) ➡](./Lesson-19-MCP-Model-Context-Protocol.md)
