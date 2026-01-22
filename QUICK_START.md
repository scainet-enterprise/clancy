# Quick Start: 5 Minutes to Better AI Coding

## Step 1: Add Clancy to Your Project (30 seconds)

**Option A: Download directly**
```bash
curl -o CLANCY.md https://raw.githubusercontent.com/scainet-enterprise/clancy/main/CLANCY.md
```

**Option B: Copy from GitHub**
1. Go to [CLANCY.md](https://github.com/scainet-enterprise/clancy/blob/main/CLANCY.md)
2. Click "Raw"
3. Save to your project root

**Option C: Clone the whole thing**
```bash
git clone https://github.com/scainet-enterprise/clancy.git
cp clancy/CLANCY.md /path/to/your/project/
```

## Step 2: Load the Framework (10 seconds)

At the start of your AI coding session, say:

> "Read CLANCY.md before we begin"

That's it. Your AI now knows:
- Never remove functionality without permission
- Verify everything before claiming success
- Watch for build/deploy failures
- Follow checklists for each change type
- Find root causes, not workarounds

## Step 3: Use the Magic Phrases (ongoing)

**Before changes:**
> "What could break if we do this?"

**During debugging:**
> "Don't fix anything yet. Just investigate."

**Before merging:**
> "Show me proof this works"

**End of session:**
> "Write a handover for the next agent"

See [CLANCY_PROMPTS.md](CLANCY_PROMPTS.md) for the full list.

---

## What Just Happened?

You've installed a governance layer for your AI coding assistant. Here's what changes:

### Before Clancy
```
You: "Fix this bug"
AI: "Fixed!" (removes a feature to make it "work")
You: 😱 (discovers in production)
```

### After Clancy
```
You: "Fix this bug"
AI: "I see two options that preserve the existing feature..."
You: 😊 (chooses the right approach)
```

---

## Verify It's Working

After loading CLANCY.md, ask your AI:

> "What's Rule 1 in the Clancy framework?"

It should answer something like: "Never remove functionality without explicit agreement."

If it doesn't know, re-load the file or ensure it's in the AI's context.

---

## Customize for Your Project

Replace the placeholders in CLANCY.md:

| Placeholder | Replace With |
|-------------|--------------|
| `{{PROJECT_NAME}}` | Your project name |
| `{{DOCUMENT_OWNER}}` | Your name |
| `{{DOCUMENT_CREATED_DATE}}` | When you added it |
| `{{DOCUMENT_LAST_UPDATED}}` | Today's date |

Optional but recommended for team use.

---

## Next Steps

1. **Read the full framework** - CLANCY.md has deep wisdom in ~2,000 lines
2. **Learn the prompts** - CLANCY_PROMPTS.md has phrases for every situation
3. **Check the incident report** - See why Rule 1 exists (INCIDENT_REPORT_EXAMPLE.md)

---

## Need More Power?

For teams and enterprises, check out the full [Agent Excellence Framework](https://scainet.io/framework):
- npm package with CLI tools
- GitHub Actions automation
- Dashboard for cross-repo tracking
- HUMAN Protocol (semantic commands)

---

<p align="center">
  <strong>You're all set! 🚀</strong><br>
  Questions? <a href="https://github.com/scainet-enterprise/clancy/issues">Open an issue</a>
</p>
