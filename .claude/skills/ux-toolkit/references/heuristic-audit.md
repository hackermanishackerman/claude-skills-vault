# UX Heuristic Audit

Systematic evaluation using Nielsen's 10 Usability Heuristics + modern UX methodologies.

> **Enhanced**: This reference now includes Cognitive Walkthrough, OOUX, JTBD, and other modern evaluation frameworks beyond Nielsen's 1994 heuristics.

## Nielsen's 10 Heuristics Checklist

### H1: Visibility of System Status

System keeps users informed through timely feedback.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Loading indicators | Progress shown for actions >1s | 🟠 Major |
| Form submission feedback | Success/error msg displayed | 🔴 Critical |
| Upload progress | % or time remaining shown | 🟠 Major |
| Navigation state | Current location highlighted | 🟡 Minor |
| Save status | Auto-save indicator present | 🟡 Minor |
| Processing state | Disabled state + spinner during ops | 🟠 Major |

**Questions:**
- Does user know what's happening at all times?
- Is feedback immediate (<100ms) or delayed w/ indicator?
- Are async operations clearly communicated?

---

### H2: Match Between System & Real World

System speaks user's language w/ familiar concepts.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Terminology | Uses domain-appropriate language | 🟠 Major |
| Icons | Universally recognized symbols | 🟡 Minor |
| Metaphors | Real-world analogs (folder, trash) | 🟡 Minor |
| Date/time formats | Locale-appropriate display | 🟡 Minor |
| Currency/numbers | Correct symbols & separators | 🟠 Major |
| Error messages | Plain language, not codes | 🔴 Critical |

**Questions:**
- Would a non-technical user understand all labels?
- Are industry-standard terms used correctly?
- Do icons match mental models?

---

### H3: User Control & Freedom

Users can undo, redo, and escape from states.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Undo action | Available for destructive ops | 🔴 Critical |
| Cancel operation | Exit modals/flows easily | 🟠 Major |
| Back navigation | Works as expected | 🟠 Major |
| Clear/reset forms | Single action to clear | 🟡 Minor |
| Escape key support | Closes modals/overlays | 🟡 Minor |
| Edit after submit | Modify submitted data | 🟠 Major |

**Questions:**
- Can user recover from mistakes w/o data loss?
- Is there always a clear exit?
- Can user change their mind?

---

### H4: Consistency & Standards

Follow platform conventions & internal patterns.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Button styles | Primary/secondary consistent | 🟡 Minor |
| Link behavior | Standard colors & underlines | 🟡 Minor |
| Form patterns | Same layout across app | 🟠 Major |
| Terminology | Same words for same concepts | 🟠 Major |
| Icon usage | Same icons = same actions | 🟠 Major |
| Navigation | Consistent placement & behavior | 🟠 Major |

**Questions:**
- Does similar content look similar?
- Are platform conventions followed?
- Is internal consistency maintained?

---

### H5: Error Prevention

Prevent problems before they occur.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Confirmation dialogs | Present for destructive actions | 🔴 Critical |
| Input validation | Real-time format checking | 🟠 Major |
| Disabled states | Unavailable options greyed out | 🟡 Minor |
| Autosave | Prevent data loss | 🟠 Major |
| Smart defaults | Sensible pre-filled values | 🟡 Minor |
| Constraint feedback | Show limits before hitting | 🟡 Minor |

**Questions:**
- Are slips prevented via constraints?
- Are dangerous actions safeguarded?
- Does system guide toward valid input?

---

### H6: Recognition vs Recall

Minimize memory load w/ visible options & cues.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Visible navigation | All options accessible | 🟠 Major |
| Recent items | Quick access to history | 🟡 Minor |
| Autocomplete | Suggestions for inputs | 🟡 Minor |
| Contextual help | Info where needed | 🟡 Minor |
| Breadcrumbs | Path visible in hierarchy | 🟡 Minor |
| Labels on icons | Text accompanies icons | 🟡 Minor |

**Questions:**
- Can user operate w/o memorizing?
- Are instructions visible when needed?
- Does UI prompt next actions?

---

### H7: Flexibility & Efficiency

Support both novice & expert users.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Keyboard shortcuts | Power user accelerators | 🟡 Minor |
| Customization | User preferences supported | 🟡 Minor |
| Batch operations | Multi-select + bulk actions | 🟡 Minor |
| Search/filter | Quick data access | 🟠 Major |
| Defaults | Skip steps for common paths | 🟡 Minor |
| Templates | Pre-built starting points | ⚪ Cosmetic |

**Questions:**
- Can experts work faster?
- Are common tasks streamlined?
- Is personalization available?

---

### H8: Aesthetic & Minimalist Design

Show only relevant information.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Visual hierarchy | Important elements prominent | 🟠 Major |
| Content density | Appropriate whitespace | 🟡 Minor |
| Progressive disclosure | Details on demand | 🟡 Minor |
| Noise reduction | No decorative clutter | ⚪ Cosmetic |
| Focused CTAs | Clear primary actions | 🟠 Major |
| Consistent styling | Unified visual language | 🟡 Minor |

**Questions:**
- Is every element necessary?
- Can user focus on primary task?
- Is content scannable?

---

### H9: Error Recovery

Help users recognize, diagnose & recover from errors.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Clear error message | Explains what went wrong | 🔴 Critical |
| Solution provided | Tells how to fix | 🔴 Critical |
| Non-destructive | Preserves user input | 🔴 Critical |
| Error location | Highlights problem field | 🟠 Major |
| Retry option | Easy to try again | 🟠 Major |
| Support path | Contact/help available | 🟡 Minor |

**Questions:**
- Does user understand what failed?
- Is recovery path clear?
- Is data preserved after error?

---

### H10: Help & Documentation

Provide accessible help when needed.

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Contextual help | Tooltips, inline hints | 🟡 Minor |
| Search docs | Searchable help content | 🟡 Minor |
| FAQ available | Common questions answered | ⚪ Cosmetic |
| Onboarding | New user guidance | 🟡 Minor |
| Task-focused | Steps for specific goals | 🟡 Minor |
| Accessible | Help reachable from any screen | 🟡 Minor |

**Questions:**
- Is help findable when needed?
- Are instructions task-oriented?
- Can user self-serve?

---

## Audit Report Template

```markdown
# Heuristic Audit Report

**Product:** [Name]
**Version:** [Version]
**Date:** [Date]
**Auditor:** [Name]

## Executive Summary

- Total issues: X
- 🔴 Critical: X
- 🟠 Major: X
- 🟡 Minor: X
- ⚪ Cosmetic: X

## Findings by Heuristic

### H1: Visibility of System Status
| Issue | Location | Severity | Recommendation |
|-------|----------|----------|----------------|
| [desc] | [screen/component] | 🔴/🟠/🟡/⚪ | [fix] |

[Repeat for H2-H10]

## Priority Actions

1. [Critical fix 1]
2. [Critical fix 2]
3. [Major fix 1]
```

---

## Severity Classification

| Level | Definition | Example |
|-------|------------|---------|
| 🔴 Critical | Prevents task completion | No error msg on failed payment |
| 🟠 Major | Causes significant delay/confusion | No loading indicator on slow op |
| 🟡 Minor | Causes minor friction | Inconsistent button styling |
| ⚪ Cosmetic | Polish/preference issue | Suboptimal whitespace |

## Remediation Priority

```
1. Critical → Fix before release
2. Major    → Fix in current sprint
3. Minor    → Next sprint backlog
4. Cosmetic → Nice-to-have backlog
```

---

## Modern UX Methodologies

Beyond Nielsen's 10, use these complementary evaluation frameworks.

### Cognitive Walkthrough

Step-by-step evaluation of task completion probability.

**For each step in a user flow, answer:**

| Question | Focus | Issue if No |
|----------|-------|-------------|
| 1. Will user try to achieve this effect? | Goal visibility | User doesn't know this is possible |
| 2. Will user notice the control? | Discoverability | Control is hidden or unclear |
| 3. Will user associate control with effect? | Signifiers | Control doesn't indicate its function |
| 4. After action, will user understand feedback? | Feedback | Success/failure unclear |

**Cognitive Walkthrough Template:**

```markdown
## Flow: [Task Name]

### Step 1: [Action]
| Question | Answer | Issue |
|----------|--------|-------|
| Try to achieve? | Yes/No | |
| Notice control? | Yes/No | |
| Associate with effect? | Yes/No | |
| Understand feedback? | Yes/No | |

**Severity:** Critical/Major/Minor
**Fix:** [Remediation]
```

---

### Object-Oriented UX (OOUX)

Audit content as objects (nouns) before actions (verbs).

**OOUX Checklist:**

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Objects identified | Key nouns (User, Project, Task) defined | Major |
| Consistent naming | Same object = same word everywhere | Major |
| Clear relationships | How objects relate is obvious | Minor |
| Actions follow objects | Verbs attached to correct nouns | Major |

**OOUX Audit Questions:**

```
1. What are the core objects in this system?
2. Is each object named consistently?
3. Are object relationships clear to users?
4. Do actions logically belong to their objects?
5. Can users find an object before acting on it?
```

**Example Issue:**

```
❌ "Projects" in nav, "Workspaces" in sidebar, "Spaces" in modal
   → Same object, three names

✅ "Projects" consistently everywhere
```

---

### Jobs to be Done (JTBD)

Evaluate features against user's actual job stories.

**Job Story Format:**

```
When [situation], I want to [motivation], so I can [expected outcome].
```

**JTBD Audit Questions:**

| Question | Focus |
|----------|-------|
| What job is the user trying to accomplish? | Core motivation |
| Does this feature help them complete that job? | Feature relevance |
| What's the user's measure of success? | Outcome definition |
| Are we solving the job or just a task? | Solution depth |

**JTBD Checklist:**

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Job identified | Feature maps to real user job | Critical |
| Outcome measurable | Success criteria clear | Major |
| Job story validated | Tested with actual users | Major |
| Competing solutions | Understood what user would do otherwise | Minor |

**Example:**

```
Feature: "Export to CSV"

Bad framing: "User wants to download data"
JTBD framing: "When I need to present metrics to my boss,
              I want to export clean data to Excel,
              so I can build a report they'll understand."

→ This reframes the feature: maybe we need formatted Excel, not raw CSV
```

---

### Six Minds Framework

Evaluate against six cognitive processing domains.

| Mind | Function | Audit Focus |
|------|----------|-------------|
| **Vision** | Visual processing | Hierarchy, contrast, grouping |
| **Attention** | Focus direction | CTAs, distractions, flow |
| **Wayfinding** | Navigation | Orientation, paths, landmarks |
| **Language** | Text comprehension | Copy, labels, instructions |
| **Memory** | Recall & recognition | Cognitive load, familiarity |
| **Emotion** | Affective response | Trust, delight, frustration |

**Six Minds Checklist:**

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Visual hierarchy | Important elements prominent | Major |
| Attention directed | User knows where to look | Major |
| Navigation clear | User knows where they are | Major |
| Language accessible | Copy is understandable | Major |
| Memory supported | Recognition over recall | Minor |
| Emotion positive | No frustration triggers | Minor |

---

### Baymard Heuristics (E-commerce)

For shopping and checkout flows, use Baymard Institute's weighted guidelines.

**Key Baymard Categories:**

| Category | Focus Areas |
|----------|-------------|
| Homepage & Category | Navigation, filters, sorting |
| Product Page | Images, descriptions, reviews |
| Cart | Edit quantity, save for later |
| Checkout | Guest checkout, form design, payment |
| Account | Registration, order history |
| Mobile | Touch targets, mobile-specific patterns |

**Baymard Severity Weighting:**

| Severity | User Impact | Weight |
|----------|-------------|--------|
| Critical | 50%+ abandon task | 5× |
| Significant | 10-50% friction | 3× |
| Minor | <10% friction | 1× |

**Priority = Severity × Frequency**

---

### Gestalt Principles Audit

Evaluate visual design against perceptual grouping.

| Principle | Description | Violation Example |
|-----------|-------------|-------------------|
| **Proximity** | Close items = related | Form labels far from inputs |
| **Similarity** | Similar items = grouped | Buttons styled inconsistently |
| **Continuity** | Eye follows lines | Misaligned elements |
| **Closure** | Mind completes shapes | Broken visual containers |
| **Figure-Ground** | Distinguish foreground | Modal doesn't stand out |
| **Common Fate** | Moving together = grouped | Unrelated items animate together |

**Gestalt Checklist:**

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Related items grouped | Proximity shows relationship | Major |
| Similar function = similar style | Buttons, links consistent | Major |
| Visual flow | Eye moves logically | Minor |
| Clear containers | Groups visually bounded | Minor |
| Foreground distinct | Primary content stands out | Major |

---

### Fitts's Law Audit

Evaluate target sizes and distances.

**Fitts's Law:**
```
Time to target = a + b × log₂(2D/W)

Where:
D = Distance to target
W = Width of target
```

**Practical Application:**

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Primary actions large | Bigger than secondary | Major |
| Frequent actions accessible | Close to start position | Minor |
| Edge/corner targets | Utilize screen edges | Cosmetic |
| Touch targets sized | Min 44×44px | Major |
| Destructive actions distant | Away from safe actions | Major |

**Anti-Patterns:**

```
❌ Small delete button next to large save button
❌ Confirmation dialog buttons same size
❌ Primary action buried in menu
```

---

### Hick's Law Audit

Evaluate decision complexity.

**Hick's Law:**
```
Time to decide = a + b × log₂(n+1)

Where:
n = Number of choices
```

**Practical Application:**

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Limited options | 7±2 items per group | Major |
| Clear hierarchy | Primary action obvious | Major |
| Progressive disclosure | Details on demand | Minor |
| Smart defaults | Reduce required decisions | Minor |
| Categorization | Group related options | Minor |

**Anti-Patterns:**

```
❌ 20+ items in dropdown without grouping
❌ 10 buttons of equal prominence
❌ All form fields visible at once
```

---

## Combined Audit Approach

For comprehensive evaluation, combine methodologies:

| Methodology | Best For | When to Use |
|-------------|----------|-------------|
| Nielsen's 10 | Broad usability | Every audit |
| Cognitive Walkthrough | New features, flows | Complex flows, onboarding |
| OOUX | Information architecture | Content-heavy apps |
| JTBD | Feature validation | Product strategy |
| Six Minds | Overall UX quality | Comprehensive audits |
| Baymard | E-commerce | Shopping experiences |
| Gestalt | Visual design | UI polish phase |
| Fitts's/Hick's | Interaction efficiency | Optimization phase |

**Recommended Combination:**

```
1. Start with Nielsen's 10 (baseline)
2. Add Cognitive Walkthrough for critical flows
3. Use OOUX for content/IA issues
4. Apply Gestalt for visual concerns
5. Validate with JTBD for feature relevance
```
