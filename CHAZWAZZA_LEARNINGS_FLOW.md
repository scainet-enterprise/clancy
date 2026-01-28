# Learnings Flow: Chazwazza → Clancy

**Date:** January 24, 2026  
**Chazwazza Version:** 4.5.0  
**Clancy Version:** 3.6  
**Purpose:** Identify valuable learnings to incorporate into Clancy.md

---

## Executive Summary

Clancy.md is SCAINET's free, open-source AI coding framework. It exists to:
1. Provide value to the community without cost
2. Demonstrate SCAINET's expertise in AI governance
3. Serve as a funnel to Chazwazza for teams needing more

**Philosophy:** Clancy should be **complete enough to be useful** but **simple enough to be one file**.

This document identifies learnings from Chazwazza that should flow to Clancy, while respecting the intentional complexity gap.

---

## Table of Contents

1. [What Clancy Has vs Chazwazza](#what-clancy-has-vs-chazwazza)
2. [Recommended Updates to Clancy](#recommended-updates-to-clancy)
3. [What Should NOT Flow to Clancy](#what-should-not-flow-to-clancy)
4. [Implementation Plan](#implementation-plan)

---

## What Clancy Has vs Chazwazza

### Current Clancy (v3.6)
| Feature | Present |
|---------|---------|
| 6 Non-Negotiable Rules | ✅ |
| Mandatory Checklists (Pre/Post/Build) | ✅ |
| Investigation Pattern | ✅ |
| RCA Methodology | ✅ |
| Platform Gotchas (Windows) | ✅ |
| Response Signature | ✅ (basic) |
| Simple Prompts | ✅ (separate file) |
| Total Lines | ~2,400 |
| Total Files | 4 |

### Current Chazwazza (v4.5.0)
| Feature | Present |
|---------|---------|
| 10 Non-Negotiable Rules | ✅ |
| HUMAN Protocol Commands | ✅ |
| MDC Specification | ✅ |
| Modular Architecture (FLA) | ✅ |
| CLI Tooling | ✅ |
| Version Management | ✅ |
| Dashboard Integration | ✅ |
| Cross-Repo Sync | ✅ |
| Platform/Service Modules | ✅ |
| Response Signature (enhanced) | ✅ |
| Total Lines | 15,000+ |
| Total Files | 50+ |

---

## Recommended Updates to Clancy

### 1. Add Rules 7-10 (HIGH PRIORITY)

**Current:** Clancy has Rules 1-6.  
**Gap:** Rules 7-10 from Chazwazza are valuable and simple.

**Add to CLANCY.md §1.2:**

```markdown
#### Rule 7: Visual Output Validation

**ALWAYS verify visual output matches intent.**

When making UI changes:
1. Check all viewport sizes (mobile, tablet, desktop)
2. Verify dark/light mode if applicable
3. Test interactive states (hover, focus, active)
4. Confirm animations complete properly

---

#### Rule 8: Credential & Secret Handling

**NEVER hardcode or expose secrets.**

| ❌ NEVER | ✅ ALWAYS |
|----------|----------|
| Commit secrets to git | Use environment variables |
| Log sensitive values | Log sanitized/masked values |
| Hardcode API keys | Reference from secure config |

---

#### Rule 9: Self-Verification Protocol

**Before asking user to test, verify yourself:**

1. Build completes without errors
2. Lint passes
3. Application runs (verify with process check)
4. Core functionality accessible
5. No console errors on page load

---

#### Rule 10: One Solution Principle

**Implement ONE solution at a time.**

When debugging:
- Try one hypothesis
- Verify result
- If failed, REVERT before trying next
- Never layer multiple attempts
```

**Benefit:** +4 valuable rules | **Effort:** Copy-paste | **Risk:** None

---

### 2. Enhance Response Signature Format (MEDIUM PRIORITY)

**Current Clancy:**
```
🔧 Clancy.md v1.0 | Rules active: 1, 2, 4
```

**Proposed (matching Chazwazza simplicity):**
```
🔧 Clancy.md v3.7 | Session: Active | Rules: 1-10
```

**Add rule reference when protection triggered:**
```
🔧 Clancy.md v3.7 | ⚠️ Rule 1 active (removal prevented)
```

**Benefit:** Clearer communication | **Effort:** Minimal | **Risk:** None

---

### 3. Add "It Worked Before" Heuristic (HIGH PRIORITY)

This is one of the most powerful debugging patterns from Chazwazza.

**Add to CLANCY.md §5.3 (or new §5.4):**

```markdown
### 5.X The "It Worked Before" Heuristic

**When something worked before and doesn't now, the root cause is in what changed.**

This is one of the most powerful debugging heuristics. If a feature worked yesterday and doesn't today:

```
DO NOT:
❌ Assume the original implementation was flawed
❌ Add workaround code to "fix" it
❌ Rewrite the feature

DO:
✅ Identify exactly what changed between working and broken states
✅ Review: commits, config changes, environment changes, deployments
✅ Test by reverting changes one at a time
✅ Focus investigation on the delta, not the whole system
```

**Real-World Application:**

| Scenario | Wrong Approach | Correct Approach |
|----------|----------------|------------------|
| Auth stopped working after deploy | Add retry logic and error handlers | Check what changed in deployment (env vars, config) |
| API fails in production, works locally | Rewrite API client | Compare environments systematically |
| Feature broken after upgrade | Assume framework bug | Test minimal reproduction, check breaking changes |
```

**Benefit:** Critical debugging skill | **Effort:** Low | **Risk:** None

---

### 4. Add Database Document ID Handling (MEDIUM PRIORITY)

This is a subtle but common bug that catches developers.

**Add to CLANCY.md §9 (new subsection):**

```markdown
### 9.X Database Document ID Handling

**Critical Pattern:** When reading documents from document databases (Firestore, MongoDB), ensure the document ID is not overwritten by stored data.

```typescript
// ❌ WRONG - id gets overwritten by spread
return { id: doc.id, ...doc.data() };

// ✅ CORRECT - spread first, then override id  
return { ...doc.data(), id: doc.id };
```

**Why This Order Matters:**

```typescript
// Document: ID="db-abc123", Data={id:"TASK-001", title:"..."}

// WRONG - Database ID lost!
{ id: doc.id, ...doc.data() } → { id: "TASK-001", title: "..." }

// CORRECT - Database ID preserved
{ ...doc.data(), id: doc.id } → { id: "db-abc123", title: "..." }
```

**Symptoms of This Bug:**
- "No document to update" errors
- "Document not found" after successful query
- Batch updates affecting wrong records
```

**Benefit:** Prevents hours of debugging | **Effort:** Low | **Risk:** None

---

### 5. Add Debug-First Deployment Pattern (MEDIUM PRIORITY)

**Add to CLANCY.md §10 (deployment section):**

```markdown
### 10.X Debug-First Deployment Pattern

**When debugging production issues, deploy LOGGING first, not fixes.**

```
DEPLOYMENT 1: DIAGNOSTIC
├── Add console.log at key points
├── NO functional changes
├── Deploy
└── Reproduce error, capture logs

LOCAL ANALYSIS:
├── Analyze captured logs
├── Identify FIRST failure point
└── Form evidence-based hypothesis

DEPLOYMENT 2: FIX
├── Single, targeted fix based on evidence
├── Keep diagnostic logging
├── Deploy
└── Verify fix, then remove extra logging
```

**Why This Matters:**

| Wrong Approach | Result |
|----------------|--------|
| Guess → Fix → Deploy → Fail → Guess again | 3-5 deployment cycles |
| Log → Analyze → Fix → Deploy | 2 deployment cycles |

Every deployment cycle costs time. Investigation-first is always faster.
```

**Benefit:** Faster fixes | **Effort:** Low | **Risk:** None

---

### 6. Enhance Platform Gotchas (LOW PRIORITY)

Clancy already has Windows/PowerShell gotchas. Consider adding:

**Add macOS/Linux section:**

```markdown
#### macOS / Linux Bash

| Issue | Cause | Prevention |
|-------|-------|------------|
| File permissions | Different default umask | `chmod +x script.sh` after creation |
| Case sensitivity | Linux is case-sensitive | Always match exact case in imports |
| Locale issues | Different system locales | Set `LC_ALL=C` for consistent behavior |
```

**Benefit:** Cross-platform coverage | **Effort:** Low | **Risk:** None

---

### 7. Add Conditional View Rendering Pattern (LOW PRIORITY)

**Add to CLANCY.md §8 (Technical Excellence):**

```markdown
### 8.X Conditional View Rendering Pattern

**When UI changes based on filter state, document the expected behavior BEFORE implementing.**

Use a state-view matrix:

| Filter State | View Type | Rationale |
|--------------|-----------|-----------|
| All/Default | Grouped | Overview of all groups |
| Category selected | Filtered grouped | Still showing hierarchy |
| Specific item | Flat list | Drill-down detail |
| Search active | Flat list | Search results are flat |

**Key Principle:**
> Grouped views = overview. Flat views = detail.
> When the user drills down, give them the detail view.
```

**Benefit:** Clearer UI implementation | **Effort:** Low | **Risk:** None

---

### 8. Update Version Number (CRITICAL)

**Update all version references:**
- Header: v3.6 → v3.7
- Document control table
- Response signature examples
- README badges

**Benefit:** Accuracy | **Effort:** Find/replace | **Risk:** None

---

## What Should NOT Flow to Clancy

These features are intentionally Chazwazza-only:

| Feature | Why Not in Clancy |
|---------|-------------------|
| **CLI Tooling** | Adds complexity, requires npm install |
| **HUMAN Protocol** | Requires configuration files |
| **MDC Format** | Overhead for single-file users |
| **Modular Architecture** | Defeats one-file simplicity |
| **Version Management** | Needs infrastructure |
| **Dashboard Integration** | Enterprise feature |
| **Cross-Repo Sync** | Enterprise feature |
| **Learning Flow Tags** | Enterprise feature |
| **Action Items YAML** | Adds file complexity |

**Key Principle:** If it requires a second file or external tool, it belongs in Chazwazza.

---

## Implementation Plan

### Phase 1: Immediate Updates (CLANCY.md v3.7)

1. **Add Rules 7-10** (copy from Chazwazza, ~100 lines)
2. **Add "It Worked Before" Heuristic** (copy, ~40 lines)
3. **Update response signature format** (minor edit)
4. **Update version to 3.7** (find/replace)

**Total Effort:** 1-2 hours  
**Lines Added:** ~150

### Phase 2: Secondary Updates (CLANCY.md v3.8)

1. **Add Database ID Handling** (~30 lines)
2. **Add Debug-First Deployment** (~40 lines)
3. **Enhance Platform Gotchas** (~20 lines)
4. **Add Conditional View Rendering** (~25 lines)

**Total Effort:** 1-2 hours  
**Lines Added:** ~115

### Phase 3: Documentation Updates

1. **Update CLANCY_PROMPTS.md** with rules 7-10 references
2. **Update README.md** with new version and features
3. **Add changelog entry** for v3.7 and v3.8

---

## Changelog Entries (Draft)

```markdown
## [3.8] - [DATE]

### Added
- Database Document ID Handling pattern (§9.X)
- Debug-First Deployment Pattern (§10.X)
- Conditional View Rendering Pattern (§8.X)
- macOS/Linux platform gotchas (§5.6)

## [3.7] - [DATE]

### Added
- Rule 7: Visual Output Validation
- Rule 8: Credential & Secret Handling
- Rule 9: Self-Verification Protocol
- Rule 10: One Solution Principle
- "It Worked Before" Heuristic (§5.X)
- Enhanced response signature format

### Changed
- Response signature now includes session status
- Rule count updated from 6 to 10
```

---

## Summary

| Category | Items to Flow | Lines | Priority |
|----------|---------------|-------|----------|
| Rules | 4 new rules (7-10) | ~100 | HIGH |
| Debugging | "It Worked Before" | ~40 | HIGH |
| Signature | Enhanced format | ~10 | MEDIUM |
| Technical | Database ID | ~30 | MEDIUM |
| Deployment | Debug-First | ~40 | MEDIUM |
| Platform | macOS/Linux | ~20 | LOW |
| UI | Conditional Views | ~25 | LOW |
| **Total** | **7 items** | **~265** | — |

**Net Effect:** Clancy grows from ~2,400 to ~2,665 lines (+11%) while gaining significant value from Chazwazza battle-testing.

---

*This document serves as the bridge between enterprise learnings and open-source distribution.*

---

⚡ AEF v4.5.0 | HUMAN v1.0 | Session: Continuing | Tasks: 1 pending
