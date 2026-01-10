# Design System Audit

Evaluate design system consistency, token usage, and component governance.

## Token Audit

### Design Token Categories

| Category | Examples | Purpose |
|----------|----------|---------|
| Color | `--color-primary`, `--color-error` | Brand & semantic colors |
| Typography | `--font-size-lg`, `--line-height-base` | Text styling |
| Spacing | `--space-4`, `--gap-md` | Layout consistency |
| Radius | `--radius-sm`, `--radius-full` | Border rounding |
| Shadow | `--shadow-sm`, `--shadow-lg` | Elevation & depth |
| Motion | `--duration-fast`, `--easing-default` | Animation timing |

### Token Governance Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Semantic naming | Tokens named by purpose, not value | Major |
| No hardcoded values | All values reference tokens | Major |
| Token documentation | Usage examples documented | Minor |
| Accessibility tokens | Contrast-aware token pairs defined | Critical |
| Deprecation policy | Clear upgrade paths for old tokens | Minor |
| Version control | Token changes tracked | Major |
| Single source of truth | Design ↔ Code sync mechanism | Major |

### Token Anti-Patterns

```
❌ color: #3B82F6;          → Use: var(--color-primary)
❌ font-size: 14px;         → Use: var(--font-size-sm)
❌ padding: 16px;           → Use: var(--space-4)
❌ margin-left: 8px;        → Use: margin-inline-start: var(--space-2)
```

---

## Component Consistency Audit

### Component Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Visual consistency | Same component = same appearance | Major |
| Behavioral consistency | Same interaction patterns | Major |
| Token usage | Components use design tokens, not raw values | Major |
| Accessibility built-in | A11y compliance at component level | Critical |
| Documentation | Props, states, variants documented | Minor |
| Code-design parity | Figma/design matches implementation | Major |
| Responsive behavior | Component adapts to viewport | Major |

### Component States Matrix

| Component | Default | Hover | Focus | Active | Disabled | Loading | Error |
|-----------|---------|-------|-------|--------|----------|---------|-------|
| Button | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| Input | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| Select | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ | ☐ |
| Checkbox | ☐ | ☐ | ☐ | ☐ | ☐ | - | ☐ |
| Card | ☐ | ☐ | ☐ | ☐ | - | ☐ | - |
| Link | ☐ | ☐ | ☐ | ☐ | ☐ | - | - |

### Variant Audit

| Component | Variants Defined | Consistent Naming | Documented |
|-----------|------------------|-------------------|------------|
| Button | primary, secondary, ghost, danger | ☐ | ☐ |
| Input | default, error, success, disabled | ☐ | ☐ |
| Badge | info, success, warning, error | ☐ | ☐ |

---

## Typography Scale Audit

### Scale Consistency

| Token | Size | Line Height | Use Case |
|-------|------|-------------|----------|
| `--text-xs` | 12px | 1.5 | Captions, labels |
| `--text-sm` | 14px | 1.5 | Secondary text |
| `--text-base` | 16px | 1.5 | Body text |
| `--text-lg` | 18px | 1.4 | Lead text |
| `--text-xl` | 20px | 1.4 | Subheadings |
| `--text-2xl` | 24px | 1.3 | Section headings |
| `--text-3xl` | 30px | 1.2 | Page headings |

### Typography Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Scale ratio | Consistent mathematical ratio (1.25, 1.333, etc.) | Minor |
| Mobile adjustments | Responsive type scale | Major |
| Font loading | FOUT/FOIT handled gracefully | Minor |
| Fallback fonts | System fonts defined as fallback | Minor |
| Variable fonts | Optimized weight ranges if used | Cosmetic |

---

## Spacing Scale Audit

### Spacing System

| Token | Value | Use Case |
|-------|-------|----------|
| `--space-1` | 4px | Tight grouping |
| `--space-2` | 8px | Related items |
| `--space-3` | 12px | Standard gap |
| `--space-4` | 16px | Component padding |
| `--space-6` | 24px | Section breaks |
| `--space-8` | 32px | Large sections |
| `--space-12` | 48px | Page sections |

### Spacing Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Consistent scale | Base unit (4px/8px) consistently applied | Major |
| Logical properties | Uses margin-inline, padding-block (RTL-safe) | Major |
| No magic numbers | All spacing uses tokens | Major |
| Responsive spacing | Scale adjusts for mobile | Minor |

---

## Color System Audit

### Semantic Color Mapping

| Purpose | Light Mode Token | Dark Mode Token |
|---------|------------------|-----------------|
| Primary action | `--color-primary` | `--color-primary-dark` |
| Background | `--color-bg` | `--color-bg-dark` |
| Text | `--color-text` | `--color-text-dark` |
| Error | `--color-error` | `--color-error-dark` |
| Success | `--color-success` | `--color-success-dark` |
| Warning | `--color-warning` | `--color-warning-dark` |
| Border | `--color-border` | `--color-border-dark` |

### Color Accessibility Pairs

| Pair | Minimum Contrast | Use |
|------|------------------|-----|
| Text on background | 4.5:1 | Normal text |
| Large text on background | 3:1 | Headings |
| UI components | 3:1 | Buttons, inputs |
| Focus indicators | 3:1 | Keyboard navigation |

### Color Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Semantic names | Colors named by purpose | Major |
| Contrast pairs | Pre-validated accessible combinations | Critical |
| Theme support | Light/dark mode tokens defined | Major |
| Color blindness | Not sole indicator of meaning | Critical |
| Hover/focus contrast | Interactive states maintain contrast | Major |

---

## Icon System Audit

### Icon Consistency

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Visual style | Consistent stroke width, corners | Minor |
| Size system | Standardized sizes (16, 20, 24px) | Minor |
| Touch targets | Min 44×44px hit area around icons | Major |
| Accessibility | Decorative icons hidden, meaningful labeled | Critical |
| Color inheritance | Icons inherit currentColor | Minor |

### Icon Usage

| Type | ARIA Treatment | Example |
|------|----------------|---------|
| Decorative | `aria-hidden="true"` | Icon next to label |
| Meaningful | `aria-label` or `<title>` | Standalone icon button |
| Status | Paired with visible text | Error icon + message |

---

## Component Documentation Audit

### Documentation Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Props documented | All props with types & descriptions | Major |
| Usage examples | Code snippets for common uses | Minor |
| Do/Don't guidance | Best practices with visual examples | Minor |
| Accessibility notes | A11y requirements per component | Major |
| Figma link | Design file reference | Minor |
| Changelog | Breaking changes documented | Major |

### Documentation Template

```markdown
## ComponentName

Brief description of the component.

### Props

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| variant | 'primary' \| 'secondary' | 'primary' | Visual variant |
| disabled | boolean | false | Disables interaction |

### Accessibility

- Role: `button` / `link` / etc.
- Keyboard: Tab to focus, Enter/Space to activate
- ARIA: Uses `aria-disabled` when disabled

### Examples

[Code examples]

### Do / Don't

✅ Use primary for main actions
❌ Don't use multiple primary buttons
```

---

## Design-Code Sync Audit

### Sync Checklist

| Check | Pass Criteria | Severity |
|-------|---------------|----------|
| Token parity | Design tool tokens match code tokens | Critical |
| Component parity | Figma components match coded components | Major |
| Naming consistency | Same names in design and code | Major |
| Version sync | Design and code versions aligned | Major |
| Change process | Updates flow both directions | Minor |

### Sync Tools

| Tool | Purpose |
|------|---------|
| Figma Tokens | Export design tokens to JSON |
| Style Dictionary | Transform tokens to platform formats |
| Storybook | Visual component documentation |
| Chromatic | Visual regression testing |

---

## Audit Report Template

```markdown
# Design System Audit Report

**System:** [Name]
**Version:** [Version]
**Date:** [Date]

## Token Audit Summary

| Category | Defined | Documented | Issues |
|----------|---------|------------|--------|
| Colors | X tokens | ☐ | X issues |
| Typography | X tokens | ☐ | X issues |
| Spacing | X tokens | ☐ | X issues |
| Motion | X tokens | ☐ | X issues |

## Component Audit Summary

| Component | States | A11y | Docs | Issues |
|-----------|--------|------|------|--------|
| Button | ✅/❌ | ✅/❌ | ✅/❌ | X |
| Input | ✅/❌ | ✅/❌ | ✅/❌ | X |

## Critical Issues

| Issue | Location | Impact | Fix |
|-------|----------|--------|-----|
| [desc] | [token/component] | [severity] | [solution] |

## Recommendations

1. [Priority action]
2. [Enhancement]
```