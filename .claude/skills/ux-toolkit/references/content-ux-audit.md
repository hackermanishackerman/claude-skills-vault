# Content & UX Writing Audit

Evaluate content strategy, UX writing, readability, and voice & tone consistency.

## Readability Assessment

### Reading Level Targets

| Audience | Target Grade | Flesch-Kincaid |
|----------|--------------|----------------|
| General public | Grade 6-8 | 60-70 |
| Professional | Grade 10-12 | 50-60 |
| Technical | Grade 12+ | 30-50 |
| Legal/Medical | Varies | Document clearly |

### Readability Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Grade level | Appropriate for target audience | Major |
| Sentence length | Average 15-20 words | Minor |
| Paragraph length | Max 3-4 sentences | Minor |
| Passive voice | < 10% of sentences | Minor |
| Jargon | Explained or avoided | Major |
| Acronyms | Expanded on first use | Minor |

### Plain Language Principles

```
❌ "Utilize the functionality"     → ✅ "Use the feature"
❌ "Prior to commencement"         → ✅ "Before starting"
❌ "In order to"                   → ✅ "To"
❌ "At this point in time"         → ✅ "Now"
❌ "Terminate the process"         → ✅ "End" or "Stop"
```

---

## Voice & Tone Audit

### Voice Attributes Matrix

Define and audit against brand voice:

| Attribute | We Are | We're Not | Example |
|-----------|--------|-----------|---------|
| Friendly | Warm, approachable | Overly casual, unprofessional | "Hi there!" not "Hey dude!" |
| Clear | Simple, direct | Dumbed down, condescending | "Select your plan" not "Pick stuff" |
| Confident | Assured, knowledgeable | Arrogant, dismissive | "This will work" not "Obviously..." |
| Helpful | Supportive, proactive | Pushy, annoying | "Need help?" not "You seem lost" |

### Tone Variations by Context

| Context | Tone Adjustment | Example |
|---------|-----------------|---------|
| Success | Celebratory, brief | "Done!" "Payment complete" |
| Error | Calm, helpful | "Something went wrong. Here's how to fix it." |
| Onboarding | Warm, encouraging | "Welcome! Let's get you set up." |
| Warning | Serious, clear | "This action cannot be undone." |
| Empty state | Helpful, actionable | "No results yet. Try a different search." |

### Voice Consistency Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Documented voice | Voice guidelines exist | Major |
| Consistent application | Same voice across product | Major |
| Appropriate tone shifts | Tone matches context | Minor |
| No personality clashes | UI doesn't feel disjointed | Minor |

---

## Microcopy Audit

### Button & CTA Copy

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Action-oriented | Starts with verb | Major |
| Specific | Describes outcome | Major |
| Concise | 1-3 words ideal | Minor |
| No ambiguity | Clear what happens | Major |

**Examples:**

```
❌ "Submit"        → ✅ "Create account"
❌ "OK"            → ✅ "Save changes"
❌ "Click here"    → ✅ "Download report"
❌ "Yes/No"        → ✅ "Delete / Keep"
```

### Form Labels & Placeholders

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Clear labels | Purpose obvious | Major |
| Placeholder != Label | Placeholder is example, not instruction | Major |
| Help text | Provided for complex fields | Minor |
| Error messages | Specific, actionable | Critical |

**Placeholder Guidelines:**

```
❌ Placeholder: "Email"           → Disappears, loses context
✅ Label: "Email" + Placeholder: "you@example.com"

❌ Placeholder: "Enter your password"
✅ Label: "Password" + Help: "Min 8 characters"
```

### Error Message Quality

| Quality | Bad Example | Good Example |
|---------|-------------|--------------|
| Specific | "Error" | "Email address is invalid" |
| Actionable | "Invalid input" | "Add an @ symbol to your email" |
| Human | "Error 422" | "That email is already registered. Log in instead?" |
| Blame-free | "You entered wrong data" | "Please check the phone number format" |

### Error Message Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| No codes | Human-readable message | Major |
| Specific location | Identifies which field | Major |
| Solution provided | Tells how to fix | Critical |
| Non-blaming | Doesn't shame user | Major |
| Persistent | Doesn't disappear too fast | Minor |

---

## Information Architecture Audit

### Navigation Labeling

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Descriptive labels | Purpose clear from name | Major |
| Consistent terminology | Same concepts = same words | Major |
| Scannable | Easy to find in list | Minor |
| No jargon | Understandable to new users | Major |

### Taxonomy Audit

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Logical grouping | Related items together | Major |
| Mutual exclusivity | Items don't overlap | Minor |
| Appropriate depth | Max 3-4 levels | Major |
| Mental model match | Matches user expectations | Major |

### Card Sorting Validation

```
If navigation structure was designed without user input:
1. Run open card sort with 5-8 users
2. Compare results to current IA
3. Flag mismatches as Major issues
```

---

## Inclusive Language Audit

### Gender & Identity

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Gender-neutral defaults | "They/them" or neutral terms | Major |
| Optional gender fields | Not required if unnecessary | Minor |
| Inclusive greetings | "Hello" not "Dear Sir/Madam" | Minor |
| Name flexibility | Supports preferred names | Minor |

**Examples:**

```
❌ "he/she"          → ✅ "they"
❌ "mankind"         → ✅ "humanity" / "people"
❌ "manpower"        → ✅ "workforce" / "staff"
❌ "guys"            → ✅ "everyone" / "folks" / "team"
```

### Cultural Sensitivity

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| No idioms | Or explained if used | Minor |
| Universal examples | Not culturally specific | Minor |
| Respectful imagery | Diverse, non-stereotypical | Major |
| Date/currency aware | Localized formats | Major |

### Accessibility in Content

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Alt text quality | Descriptive, not "image of..." | Major |
| Link text clarity | Describes destination, not "click here" | Major |
| Heading hierarchy | Logical structure | Major |
| List usage | For 3+ related items | Minor |

---

## Empty States & Edge Cases

### Empty State Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Explains why empty | Context provided | Major |
| Action provided | CTA to resolve | Major |
| Not blank | Visual interest/illustration | Minor |
| Encouraging tone | Not discouraging | Minor |

**Empty State Template:**

```markdown
[Illustration - optional]
[Headline - what's missing]
[Body - why it's empty]
[CTA - what to do next]

Example:
📭
No messages yet
Start a conversation with your team.
[Send a message]
```

### Loading State Copy

| State | Copy Approach | Example |
|-------|---------------|---------|
| Brief (<3s) | None or minimal | Spinner only |
| Medium (3-10s) | Reassurance | "Loading your data..." |
| Long (>10s) | Progress + context | "Processing... 3 of 10 items" |
| Background | Toast/notification | "We'll notify you when done" |

### Error Page Copy

| Page | Must Include | Example |
|------|--------------|---------|
| 404 | What happened, search/home link | "Page not found. Try searching or go home." |
| 500 | Apology, retry, support contact | "Something broke on our end. Try again or contact support." |
| Offline | Status, retry | "You're offline. Check your connection and try again." |
| Maintenance | Duration, updates | "Back in 30 minutes. Follow @status for updates." |

---

## Content Audit Process

### Step 1: Content Inventory

```
For each screen/page:
├── Page title
├── URL
├── Word count
├── Last updated
├── Content type (UI, help, marketing)
└── Issues found
```

### Step 2: Quality Assessment

| Dimension | Score 1-5 | Notes |
|-----------|-----------|-------|
| Accuracy | | Is content correct? |
| Clarity | | Is it understandable? |
| Completeness | | Is anything missing? |
| Consistency | | Does it match other content? |
| Findability | | Can users locate it? |

### Step 3: Gap Analysis

```
Questions to ask:
- What content is missing?
- What content is outdated?
- What content is redundant?
- What content is performing poorly?
```

---

## Localization Readiness

### Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| String externalization | No hardcoded strings | Critical |
| Text expansion room | 30-40% extra space | Major |
| No string concatenation | Full sentences in translations | Critical |
| Plural handling | Proper plural rules | Major |
| Date/time format | Locale-aware | Major |
| Number format | Locale-aware | Major |

### Translation-Friendly Patterns

```
❌ "You have " + count + " messages"
✅ "You have {count} messages" (with plural rules)

❌ "Welcome, " + firstName + "!"
✅ "Welcome, {name}!" (translator controls position)

❌ "Click here" (multiple uses)
✅ Unique, contextual strings for each use
```

---

## Audit Report Template

```markdown
# Content UX Audit Report

**Product:** [Name]
**Date:** [Date]
**Auditor:** [Name]

## Readability Summary

| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| Grade level | X | 6-8 | ✅/❌ |
| Avg sentence length | X words | 15-20 | ✅/❌ |
| Passive voice | X% | <10% | ✅/❌ |

## Voice & Tone

| Attribute | Consistent | Issues |
|-----------|------------|--------|
| Friendly | ☐ | |
| Clear | ☐ | |
| Helpful | ☐ | |

## Content Issues

| Location | Issue | Severity | Effort | Fix |
|----------|-------|----------|--------|-----|
| [page] | [desc] | Major | Low | [solution] |

## Recommendations

1. [Priority action]
2. [Enhancement]
```