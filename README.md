# Clancy 🛡️

**The AI Coding Guardian**

> One file. 10 rules. Protect your code from AI mistakes.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-4.0-blue.svg)](CLANCY.md)
[![Works With](https://img.shields.io/badge/works%20with-Cursor%20%7C%20VS%20Code%20%7C%20Claude%20%7C%20Copilot-green.svg)](#tool-setup)

---

## The Problem

AI coding assistants are powerful but make predictable mistakes:
- **Remove features** while "fixing" bugs
- **Claim success** without verification
- **Implement workarounds** instead of real fixes
- **Lose context** between sessions

These mistakes cost developers hours. Every week.

## The Solution

**Clancy** is a battle-tested framework that prevents these failures. Drop one file into your project, tell your AI to read it, and watch the quality of AI assistance transform.

---

## Quick Start (30 Seconds)

### 1. Get the file

```bash
curl -O https://raw.githubusercontent.com/scainet-enterprise/clancy/main/CLANCY.md
```

Or just copy [CLANCY.md](CLANCY.md) to your project root.

### 2. Tell your AI

> "Read CLANCY.md before we start working."

### 3. You're protected

The AI now follows 10 rules that prevent the most common failures.

---

## The 10 Rules

| # | Name | What It Prevents |
|---|------|------------------|
| 1 | **The Deletion Rule** | AI removing features to "fix" bugs |
| 2 | **Show Your Work** | Unverified "it should work now" claims |
| 3 | **Watch the Build** | Silent deployment failures |
| 4 | **No Skipping** | Missed verification steps |
| 5 | **Fix It Right** | Workarounds that become tech debt |
| 6 | **Trust But Verify** | Deprecated/nonexistent dependencies |
| 7 | **Check Every Screen** | Broken mobile experiences |
| 8 | **Secrets Stay Secret** | Leaked API keys and credentials |
| 9 | **Test Before You Tell** | Wasted time testing broken builds |
| 10 | **One Fix at a Time** | Layered fixes that become unmaintainable |

Each rule exists because someone learned it the hard way. [Read the full guide →](CLANCY.md)

---

## Tool Setup

Clancy works with any AI coding assistant. Here's how to get the best results:

### Cursor (Recommended)

**Option A: Project Rules**
1. Copy `CLANCY.md` to your project root
2. The AI will see it in context automatically

**Option B: System-Wide**
1. Open Settings → Features → Rules for AI
2. Add: "Always read and follow CLANCY.md when present in a project"

**Recommended Settings:**
- ✅ Enable terminal command execution
- ✅ Allow file creation and modification
- ✅ Enable codebase indexing
- ✅ Allow running build commands

*For maximum effectiveness, ensure Cursor has the permissions to actually verify builds and run tests.*

---

### VS Code + Continue

1. Copy `CLANCY.md` to your project root
2. In Continue settings, add to system prompt:
   ```
   When working on code, follow the rules in CLANCY.md if present.
   ```

**Recommended Extensions:**
- Continue (AI assistant)
- GitLens (for change tracking)

---

### Claude (Direct / Claude.ai)

**For Projects:**
1. Create a Project in Claude
2. Add `CLANCY.md` to the project knowledge
3. Start conversations within the project

**For Quick Sessions:**
1. Copy-paste the [Quick Reference Card](CLANCY.md#quick-reference-card)
2. Or tell Claude: "I'll share my coding standards first" and paste CLANCY.md

---

### GitHub Copilot Chat

1. Copy `CLANCY.md` to your project root
2. Reference it explicitly: "@workspace explain CLANCY.md"
3. In conversations: "Following CLANCY.md rules, help me..."

---

### Windsurf

1. Copy `CLANCY.md` to your project root  
2. Windsurf will index it automatically
3. Reference it: "According to CLANCY.md..."

---

### Aider (CLI)

```bash
# Add CLANCY.md to chat context
aider --read CLANCY.md your_files.py

# Or in session
/read CLANCY.md
```

---

### Other Tools

The pattern works with any AI that can read files:
1. Get CLANCY.md into the AI's context
2. Tell it to follow the rules
3. Watch the quality improve

---

## Permission Recommendations

### For Solo Developers / Trusted Environments

Give the AI **full permissions**. Clancy's verification rules only work if the AI can actually:
- Run builds
- Execute tests
- Check command output
- Verify deployments

**Why?** An AI with read-only access can follow "don't remove features" but can't follow "verify the build passes."

### For Teams / Shared Environments

Balance permissions with your security needs:
- ✅ Read all files
- ✅ Write to actively edited files
- ⚠️ Terminal access (case-by-case)
- ❌ Full system access

### Minimum Viable Permissions

If you can't grant full access, ensure the AI can at least:
- Read all project files
- Write to files you're editing
- See terminal output (even without execute)

> **The 80/20:** Most of Clancy's value comes from the rules themselves. Full permissions just let the AI verify instead of asking you to verify.

---

## The Prompts

Quick phrases that activate Clancy behaviors:

| Situation | Say This |
|-----------|----------|
| **Start session** | "Read CLANCY.md first" |
| **Protect feature** | "Don't remove any existing functionality" |
| **Debug carefully** | "Don't fix yet, just investigate" |
| **Verify work** | "Show me proof this works" |
| **End session** | "Write a handover for the next session" |
| **When concerned** | "What could break if we do this?" |

See [CLANCY_PROMPTS.md](CLANCY_PROMPTS.md) for the complete list.

---

## What's Included

| File | For | Purpose |
|------|-----|---------|
| [CLANCY.md](CLANCY.md) | AI Agents | The 10 rules, heuristics, checklists |
| [README.md](README.md) | Humans | Setup guide, tool configuration |
| [CLANCY_PROMPTS.md](CLANCY_PROMPTS.md) | Humans | Quick phrases for common situations |

---

## Works Even Better with Forge

**Clancy** is the knowledge—rules that any AI can follow.

**[Forge](https://scainet.io/forge)** is the enforcement—rules that are always active.

| | Clancy | Forge Light | Forge Pro |
|-|--------|-------------|-----------|
| **Price** | Free | Free | Paid |
| **Rules** | Manual load | System-level | System-level |
| **Engine** | Clancy.md | Clancy.md | Chazwazza |
| **Features** | 10 rules | Auto-enforcement | Enterprise |

*Forge Light launches with Clancy.md embedded at the system level. No more "read CLANCY.md first"—it's always on.*

[Join the Forge waitlist →](https://scainet.io/forge)

---

## Need Enterprise Features?

**[Chazwazza](https://scainet.io/framework)** is Clancy's big sibling:

- 📦 **npm package** with CLI tools
- 🔄 **Cross-repo sync** for teams
- 📊 **Dashboard** for visibility
- 🎯 **Modules** for platform-specific rules
- 🤖 **HUMAN Protocol** for natural language commands
- 📈 **Learning flow** that improves over time

Clancy is the free foundation. Chazwazza is the enterprise evolution.

[Learn more →](https://scainet.io/framework)

---

## Why "Clancy"?

Named after characters known for simple wisdom and doing the right thing when it matters. Clancy keeps things straightforward—one file, clear rules, immediate impact.

---

## Contributing

Found a rule that prevents AI failures? Open a PR.

The best contributions come from real incidents:
- What happened?
- What rule would have prevented it?
- How should the rule be phrased?

---

## License

MIT License — Use freely, improve openly.

---

## What People Are Saying

> "Rule 1 alone saved us from three production incidents this month."  
> — *Startup CTO*

> "I paste 'don't fix yet, just investigate' into every debugging thread now."  
> — *Senior Developer*

> "The AI stopped removing my features. That's literally all I needed."  
> — *Solo Founder*

---

<p align="center">
  <strong>🛡️ Protected by Clancy</strong><br>
  <em>The AI Coding Guardian</em><br><br>
  <a href="https://scainet.io/clancy">Website</a> •
  <a href="https://scainet.io/framework">Enterprise</a> •
  <a href="https://scainet.io/forge">Forge</a> •
  <a href="https://github.com/scainet-enterprise/clancy/issues">Issues</a>
</p>

---

*Built with care by [SCAINET](https://scainet.io) — AI-Native Product Studio*
