# Clancy Prompts 🗣️

**Quick phrases that activate AI protection**

> These prompts work with any AI coding assistant. Say them naturally—the AI understands.

---

## 🚀 Session Management

### Starting a Session

```
"Read CLANCY.md before we start"
```
*Loads the framework into context*

```
"I'm working on [project]. Follow CLANCY.md rules."
```
*Context + protection in one phrase*

```
"What should you know before we start coding?"
```
*Prompts AI to ask for context and rules*

---

### Ending a Session

```
"Write a handover for the next session"
```
*Creates structured summary for continuity*

```
"Summarize what we did and what's left"
```
*Quick state capture*

```
"What would the next developer need to know?"
```
*Ensures knowledge transfer*

---

## 🛡️ The Protection Prompts

### Rule 1: The Deletion Rule

```
"Don't remove any existing functionality"
```
*Activates deletion protection*

```
"Whatever you do, preserve [specific feature]"
```
*Explicit protection for critical features*

```
"If you need to remove something, ask me first"
```
*Ensures approval before deletion*

---

### Rule 2: Show Your Work

```
"Show me proof this works"
```
*Demands verification evidence*

```
"Don't just say it works—verify it"
```
*Rejects unverified claims*

```
"What evidence do you have that this is working?"
```
*Prompts for specific proof*

---

### Rule 3: Watch the Build

```
"Watch the build output and tell me if anything fails"
```
*Ensures monitoring*

```
"Run this and read me the full output"
```
*Forces attention to results*

```
"Don't assume success—check the output"
```
*Prevents silent failures*

---

### Rule 4: No Skipping

```
"Complete the full checklist before we move on"
```
*Enforces thoroughness*

```
"What verification steps haven't we done yet?"
```
*Identifies gaps*

---

### Rule 5: Fix It Right

```
"Find the root cause, not just a workaround"
```
*Prevents band-aid fixes*

```
"What's the proper fix, not the quick fix?"
```
*Elevates solution quality*

```
"If this is a workaround, tell me why the real fix is blocked"
```
*Requires justification for shortcuts*

---

### Rule 6: Trust But Verify

```
"Is this library actively maintained?"
```
*Validates technology choices*

```
"When was this last updated?"
```
*Checks for staleness*

```
"Is there something already in the codebase that does this?"
```
*Prevents duplication*

---

### Rule 7: Check Every Screen

```
"Does this work on mobile?"
```
*Triggers responsive check*

```
"Show me how this looks at 375px width"
```
*Specific viewport verification*

```
"Check dark mode too"
```
*Ensures theme compatibility*

---

### Rule 8: Secrets Stay Secret

```
"Make sure no secrets are exposed"
```
*Activates credential vigilance*

```
"Use environment variables for that"
```
*Redirects hardcoded values*

---

### Rule 9: Test Before You Tell

```
"Verify this works before asking me to test"
```
*Sets verification expectation*

```
"Have you confirmed the build passes?"
```
*Checks self-verification*

---

### Rule 10: One Fix at a Time

```
"Try one thing, verify it, then move to the next"
```
*Enforces methodical approach*

```
"Revert that and try a different approach"
```
*Prevents layered fixes*

```
"What ONE change will test your hypothesis?"
```
*Forces minimal changes*

---

## 🔍 Investigation Prompts

### Debugging

```
"Don't fix anything yet. Just investigate."
```
*The Investigation-First Protocol*

```
"What do the logs say?"
```
*Directs to evidence*

```
"What changed since this last worked?"
```
*Activates "It Worked Before" heuristic*

```
"What's your hypothesis? How can we test it?"
```
*Structures debugging*

```
"Walk me through what happens when [action]"
```
*Traces execution flow*

---

### Understanding Code

```
"Explain this like I wrote it and forgot"
```
*Clear explanation*

```
"What is this actually doing vs what it looks like?"
```
*Catches hidden complexity*

```
"What could go wrong here?"
```
*Risk identification*

---

## ✅ Verification Prompts

### Before Merging

```
"What should I check before merging this?"
```
*Generates relevant checklist*

```
"What could break from this change?"
```
*Impact assessment*

```
"Are there any edge cases we haven't handled?"
```
*Completeness check*

---

### Specific Scenarios

```
"UI change checklist"
```
*Prompts: Mobile? Accessible? Loading states? Error states?*

```
"API change checklist"
```
*Prompts: Backwards compatible? Error handling? Auth?*

```
"Database change checklist"
```
*Prompts: Migration needed? Indexes? Rollback plan?*

---

## 💡 Power Phrases

### Combining Prompts

```
"Don't remove any features, but refactor [X] to use [Y]"
```
*Protection + instruction*

```
"Fix this but verify it works before telling me"
```
*Task + verification*

```
"Investigate first, then propose solutions"
```
*Sequence enforcement*

---

### Setting Context

```
"This is production code—be extra careful"
```
*Raises caution level*

```
"This is a prototype—move fast"
```
*Adjusts for speed*

```
"We're in debugging mode—investigate everything, fix nothing without asking"
```
*Session-wide behavior change*

---

### When AI Gets Stuck

```
"Start from first principles. What are we actually trying to achieve?"
```
*Resets thinking*

```
"What's the simplest thing that could possibly work?"
```
*Reduces complexity*

```
"Let's step back. What do we know for certain?"
```
*Grounds in facts*

---

### When AI Makes Mistakes

```
"Undo that. Let's think more carefully."
```
*Reset and retry*

```
"That removed functionality. Revert and try again."
```
*Explicit Rule 1 correction*

```
"That's a workaround. What's the real fix?"
```
*Rule 5 correction*

---

## 📋 Quick Reference

| Situation | Prompt |
|-----------|--------|
| **Start** | "Read CLANCY.md first" |
| **Protect** | "Don't remove any features" |
| **Investigate** | "Don't fix yet, just investigate" |
| **Verify** | "Show me proof this works" |
| **Debug** | "What changed since it worked?" |
| **Quality** | "What's the proper fix, not the quick fix?" |
| **Check** | "Does this work on mobile?" |
| **End** | "Write a handover" |

---

## 🎯 The Golden Phrases

If you remember nothing else, remember these:

1. **"Read CLANCY.md first"** — Session start
2. **"Don't remove any features"** — Protection
3. **"Don't fix yet, just investigate"** — Debugging
4. **"Show me proof it works"** — Verification
5. **"What changed since it worked?"** — The power heuristic

These five phrases prevent 80% of AI coding mistakes.

---

<p align="center">
  <em>Part of the <a href="https://github.com/scainet-enterprise/clancy">Clancy Framework</a></em><br>
  🛡️ Protected by Clancy v4.0
</p>
