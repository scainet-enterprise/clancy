# Clancy Prompts 🗣️

**Simple phrases that guide AI coding assistants**

These prompts leverage the Clancy framework without requiring you to memorize rules or sections. Just say them naturally - any modern AI coding assistant (Cursor, Copilot, Claude, etc.) will understand.

---

## 🚀 Session Management

### Starting Fresh
```
"Read CLANCY.md before we begin"
```
*Loads the framework into context*

```
"I'm working on [project]. What should you know first?"
```
*AI will ask for relevant files and context*

### Ending a Session
```
"Write a handover for the next agent"
```
*Creates structured summary of work done and remaining tasks*

```
"What would you tell the next developer about this session?"
```
*Quick summary of decisions made and why*

---

## 🛡️ Safety Prompts

### Before Making Changes
```
"What could break if we do this?"
```
*Forces consideration of side effects before action*

```
"Show me what you're about to change before you change it"
```
*Preview changes without applying them*

### Preventing Feature Removal
```
"Whatever you do, don't remove any existing features"
```
*Activates Rule 1 protection*

```
"This feature must keep working: [describe feature]"
```
*Explicit protection for specific functionality*

### After Making Changes
```
"Did anything else break when you made that change?"
```
*Triggers cross-impact verification*

---

## 🔍 Investigation Prompts

### Debugging
```
"Don't fix anything yet. Just investigate and tell me what you find."
```
*Investigation-First Protocol - prevents premature "fixes"*

```
"What's the root cause, not just the symptom?"
```
*Prevents workarounds (Rule 5)*

```
"Walk me through what happens when [action]"
```
*Traces execution flow to understand behavior*

### Understanding Code
```
"Explain this code like I wrote it yesterday and forgot"
```
*Clear explanation of existing code*

```
"What is this actually doing vs what it looks like it's doing?"
```
*Catches misleading variable names or hidden complexity*

---

## ✅ Verification Prompts

### Quality Check
```
"Before you call this done, verify it actually works"
```
*Triggers Rule 2 - no claiming success without evidence*

```
"Show me proof this works"
```
*Explicit request for verification evidence*

### Build & Deploy
```
"Watch the output and tell me if anything fails"
```
*Activates Rule 3 - monitor all operations*

```
"Run the tests and interpret the results"
```
*Full test verification, not just "tests pass"*

---

## 🏗️ Architecture Prompts

### Before New Code
```
"Does this pattern already exist in the codebase?"
```
*Prevents duplicate implementations*

```
"What's the standard way to do [X] in this project?"
```
*Follows existing conventions*

### Technology Decisions
```
"Is this library/framework still maintained?"
```
*Rule 6 - validate technology choices*

```
"What's the simplest solution that actually works?"
```
*Prevents over-engineering*

---

## 📋 Checklist Prompts

### General
```
"What should I check before merging this?"
```
*Generates relevant checklist for the change type*

### Specific Scenarios
```
"UI change checklist"
```
- Works on mobile?
- Accessible?
- Dark/light mode?
- Loading states?
- Error states?

```
"API change checklist"
```
- Backwards compatible?
- Error handling?
- Auth checked?
- Rate limiting?

```
"Database change checklist"
```
- Migration needed?
- Indexes correct?
- Rollback possible?

---

## 💡 Pro Tips

### Combine Prompts
```
"Don't remove any features, but refactor [X] to use [Y]"
```

### Be Explicit About Risk Tolerance
```
"This is production code, be extra careful"
"This is a prototype, move fast"
```

### When AI Gets Stuck
```
"Start from first principles. What are we actually trying to achieve?"
```

### When AI Makes Mistakes
```
"Undo that. Let's think through this more carefully."
```

---

## 🔮 Context-Setting Phrases

These establish ongoing behavior, not just single actions:

```
"From now on, always show me changes before applying them"
```

```
"For this session, assume I want thorough explanations"
```

```
"We're in debugging mode - investigate everything, fix nothing without asking"
```

---

## Quick Reference Card

| Situation | Prompt |
|-----------|--------|
| Start | "Read CLANCY.md first" |
| Investigate | "Don't fix, just investigate" |
| Before change | "What could break?" |
| Verify | "Show me proof this works" |
| Protect feature | "Don't remove [X]" |
| End session | "Write a handover" |

---

<p align="center">
  <em>Part of the <a href="https://github.com/scainet-enterprise/clancy">Clancy Framework</a></em><br>
  More at <a href="https://scainet.io/clancy">scainet.io/clancy</a>
</p>
