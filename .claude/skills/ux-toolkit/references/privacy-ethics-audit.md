# Privacy & Ethics Audit

Evaluate dark patterns, consent management, and ethical design compliance (GDPR/DSA/CCPA).

## Dark Pattern Detection

### Deceptive Pattern Categories

| Category | Description | Severity |
|----------|-------------|----------|
| **Trick questions** | Confusing language that misleads | Critical |
| **Sneak into basket** | Adding items without consent | Critical |
| **Hidden costs** | Revealing fees late in checkout | Critical |
| **Roach motel** | Easy to get in, hard to get out | Critical |
| **Privacy zuckering** | Confusing privacy settings | Critical |
| **Misdirection** | Drawing attention away from important info | Major |
| **Confirm-shaming** | Guilting users into choices | Major |
| **Disguised ads** | Ads that look like content | Major |
| **Forced continuity** | Auto-renewal without clear notice | Major |
| **Friend spam** | Harvesting contacts without clear consent | Critical |
| **Bait and switch** | Promising one thing, delivering another | Critical |

### Dark Pattern Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| No confirm-shaming | Rejection copy is neutral | Major |
| No hidden costs | All fees shown before checkout | Critical |
| Easy cancellation | Same effort as signup | Critical |
| Clear opt-out | Rejecting as easy as accepting | Critical |
| No pre-checked boxes | All consent explicit | Critical |
| No misleading buttons | Visual weight doesn't manipulate | Major |
| No artificial urgency | Countdown timers are real | Major |
| No obstruction | Unsubscribe/delete not buried | Major |

### Confirm-Shaming Examples

```
❌ "No thanks, I don't want to save money"
❌ "I'll pass on this great deal"
❌ "No, I prefer to stay uninformed"

✅ "No thanks"
✅ "Not now"
✅ "Skip"
```

### Visual Manipulation

| Pattern | Bad Example | Good Example |
|---------|-------------|--------------|
| Button sizing | Accept: Large, Reject: Tiny | Same size |
| Color emphasis | Accept: Bright, Reject: Gray | Equal prominence |
| Positioning | Accept: Top, Reject: Hidden | Side by side |
| Contrast | Accept: High, Reject: Low | Equal contrast |

---

## Consent Management

### Cookie Consent Requirements (GDPR/DSA)

| Requirement | Pass Criteria | Severity |
|-------------|---------------|----------|
| Prior consent | No tracking before acceptance | Critical |
| Equal prominence | Accept/Reject same visibility | Critical |
| No pre-selection | All boxes unchecked by default | Critical |
| Granular choice | Can select specific purposes | Major |
| Easy withdrawal | Revoke as easy as grant | Critical |
| No cookie walls | Service available without tracking | Major |
| Persistent choice | Don't re-ask constantly | Minor |

### Consent Banner Audit

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| "Accept All" prominence | Not more prominent than "Reject All" | Critical |
| Clear language | No confusing terminology | Major |
| Purpose explanation | Why each cookie type needed | Major |
| Third-party disclosure | External trackers listed | Major |
| Settings access | Easy to change later | Minor |
| No dark patterns | No manipulation tactics | Critical |

### Compliant Banner Example

```
┌─────────────────────────────────────────────────────────┐
│ We use cookies                                          │
│                                                          │
│ We use cookies to improve your experience and for       │
│ analytics. You can accept all, reject all, or choose    │
│ specific types.                                          │
│                                                          │
│ [Reject All]    [Customize]    [Accept All]             │
│                                                          │
│ Learn more in our Privacy Policy                        │
└─────────────────────────────────────────────────────────┘

Note: All buttons same size, equal visual weight
```

### Non-Compliant Patterns

```
❌ Giant "Accept" button, tiny "More options" link
❌ "Accept" colored, "Reject" grayed out
❌ Pre-checked "Accept marketing" checkbox
❌ No reject option, only "Accept" or "Settings"
❌ Cookie wall: "Accept or leave"
❌ Re-prompting after rejection
```

---

## Data Minimization

### Collection Audit

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Necessity check | Only collect what's needed | Critical |
| Purpose explained | Why each field is required | Major |
| Optional clearly marked | Non-required fields labeled | Minor |
| No hidden collection | All data collection visible | Critical |
| Retention limits | Data not kept forever | Major |

### Form Field Analysis

```
For each form field, ask:
1. Is this field necessary for the feature?
2. Is it legally required?
3. What happens without it?
4. How long is it retained?
5. Who has access?
```

### Minimization Checklist

| Data Type | Necessary | Justified | Retention |
|-----------|-----------|-----------|-----------|
| Email | ✅/❌ | [reason] | [duration] |
| Phone | ✅/❌ | [reason] | [duration] |
| Address | ✅/❌ | [reason] | [duration] |
| DOB | ✅/❌ | [reason] | [duration] |
| Payment | ✅/❌ | [reason] | [duration] |

---

## User Rights (GDPR/CCPA)

### Rights Implementation Checklist

| Right | GDPR | CCPA | Implementation | Status |
|-------|------|------|----------------|--------|
| Access | Art. 15 | § 1798.100 | View personal data | ☐ |
| Deletion | Art. 17 | § 1798.105 | Delete account/data | ☐ |
| Portability | Art. 20 | - | Export data | ☐ |
| Rectification | Art. 16 | § 1798.106 | Edit personal data | ☐ |
| Objection | Art. 21 | - | Opt-out of processing | ☐ |
| Opt-out of sale | - | § 1798.120 | Do not sell toggle | ☐ |

### Right to Delete Audit

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Findable | Accessible from profile/settings | Major |
| Self-service | No email required | Major |
| Complete | All data actually deleted | Critical |
| Timely | Processed within legal limits | Major |
| Confirmation | User notified of completion | Minor |

### Account Deletion Flow

```
Ideal flow:
Settings → Account → Delete Account → Confirmation → Processed

Anti-patterns to avoid:
❌ Requires emailing support
❌ Hidden behind multiple menus
❌ Requires phone call
❌ Long waiting period without justification
❌ "Deactivate" instead of actual delete
```

---

## Privacy Settings UX

### Settings Accessibility

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Findable | 2-3 clicks from any page | Major |
| Understandable | Plain language, not legalese | Major |
| Actionable | Can change settings immediately | Major |
| Comprehensive | All privacy options in one place | Minor |
| Default-safe | Privacy-protective defaults | Major |

### Settings Organization

```
Privacy Settings
├── Data Collection
│   ├── Analytics
│   ├── Personalization
│   └── Third-party sharing
├── Communication
│   ├── Email preferences
│   ├── Push notifications
│   └── SMS preferences
├── Your Data
│   ├── Download your data
│   ├── Delete your data
│   └── View data we have
└── Security
    ├── Two-factor auth
    ├── Login history
    └── Connected apps
```

### Default Settings Audit

| Setting | Current Default | Privacy-Safe Default | Status |
|---------|-----------------|---------------------|--------|
| Analytics | ✅ On / ❌ Off | Off | ☐ |
| Marketing emails | ✅ On / ❌ Off | Off | ☐ |
| Personalization | ✅ On / ❌ Off | Off or Ask | ☐ |
| Third-party sharing | ✅ On / ❌ Off | Off | ☐ |

---

## Transparency Requirements

### Privacy Policy Accessibility

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Easy to find | Footer link on all pages | Minor |
| Readable | Not just legal jargon | Major |
| Layered | Summary + full detail | Minor |
| Up to date | Recent revision date | Major |
| Specific | Details actual practices | Major |

### Just-in-Time Notices

| Context | Notice Needed | Example |
|---------|---------------|---------|
| Data collection | Why + how used | "We use your email to send receipts" |
| Feature requiring permissions | Why needed | "Camera needed for video calls" |
| Third-party sharing | Who + why | "Shared with payment processor" |
| AI processing | How AI uses data | "AI uses your history to personalize" |

### Transparency Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| No hidden data collection | All collection visible/notified | Critical |
| Third-party disclosure | Partners/processors listed | Major |
| Processing purposes | All purposes explained | Major |
| Retention periods | How long data kept | Minor |
| International transfers | Cross-border data flows disclosed | Major |

---

## Ethical AI Considerations

### AI Ethics Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| No deceptive AI | Don't pretend AI is human | Critical |
| Bias monitoring | Check for discriminatory outputs | Critical |
| Human oversight | Human review for high-stakes | Critical |
| Opt-out available | Can avoid AI processing | Major |
| Explainability | AI decisions explained | Major |

### EU AI Act Considerations

| Risk Level | Examples | Requirements |
|------------|----------|--------------|
| Unacceptable | Social scoring, manipulation | Prohibited |
| High | Credit scoring, hiring | Strict oversight |
| Limited | Chatbots | Transparency |
| Minimal | Spam filters | None specific |

---

## Regulatory Compliance Matrix

### Requirements by Regulation

| Requirement | GDPR | DSA | CCPA | EAA |
|-------------|------|-----|------|-----|
| Cookie consent | ✅ | ✅ | ✅ | - |
| Data portability | ✅ | - | - | - |
| Right to delete | ✅ | - | ✅ | - |
| Opt-out of sale | - | - | ✅ | - |
| Dark pattern ban | ✅ | ✅ | - | - |
| Accessibility | - | - | - | ✅ |
| Algorithmic transparency | ✅ | ✅ | - | - |

### Compliance Deadlines

| Regulation | Effective Date | Scope |
|------------|----------------|-------|
| GDPR | May 2018 | EU residents |
| CCPA/CPRA | Jan 2023 | California residents |
| DSA | Feb 2024 | EU (platforms) |
| DMA | Mar 2024 | EU (gatekeepers) |
| EAA | Jun 2025 | EU (accessibility) |

---

## Children's Privacy (COPPA)

### If Targeting Under 13

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Parental consent | Verified before collection | Critical |
| Limited collection | Minimum necessary | Critical |
| No behavioral ads | No targeted advertising | Critical |
| Parental controls | Parents can review/delete | Critical |
| Age verification | Appropriate age gate | Major |

---

## Audit Report Template

```markdown
# Privacy & Ethics Audit Report

**Product:** [Name]
**Markets:** [EU/US/Global]
**Date:** [Date]

## Dark Pattern Assessment

| Pattern | Found | Location | Severity |
|---------|-------|----------|----------|
| Confirm-shaming | ✅/❌ | [page] | Critical |
| Hidden costs | ✅/❌ | [page] | Critical |
| Roach motel | ✅/❌ | [page] | Critical |

## Consent Compliance

| Requirement | Status | Issue |
|-------------|--------|-------|
| Equal prominence | ✅/❌ | |
| No pre-selection | ✅/❌ | |
| Easy withdrawal | ✅/❌ | |

## User Rights

| Right | Implemented | Accessible | Timely |
|-------|-------------|------------|--------|
| Access | ✅/❌ | ✅/❌ | ✅/❌ |
| Deletion | ✅/❌ | ✅/❌ | ✅/❌ |
| Portability | ✅/❌ | ✅/❌ | ✅/❌ |

## Issues Found

| Issue | Category | Regulation | Severity | Fix |
|-------|----------|------------|----------|-----|
| [desc] | [dark pattern/consent/rights] | [GDPR/DSA] | Critical | [solution] |

## Recommendations

1. [Priority action]
2. [Enhancement]
```