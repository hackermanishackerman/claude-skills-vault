# Accessibility (A11Y) Inspector

WCAG 2.2 compliance & inclusive design review.

> **Updated**: This reference covers WCAG 2.2 (October 2023), including all 9 new success criteria.

## WCAG 2.2 Compliance Levels

| Level | Requirement | Target |
|-------|-------------|--------|
| A | Minimum accessibility | Baseline |
| AA | Acceptable accessibility | **Standard target** |
| AAA | Enhanced accessibility | Ideal for specific audiences |

---

## WCAG 2.2 New Success Criteria

> Published October 2023. These 9 criteria are additions to WCAG 2.1.

### Level A New Criteria

#### 3.2.6 Consistent Help

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Help location | Help mechanism in consistent location | A | Manual |
| Cross-page consistency | Same position across related pages | A | Manual |

**Implementation:**
- Place help (contact, chat, FAQ) in same location across all pages
- Common patterns: footer, persistent header link, floating button

#### 3.3.7 Redundant Entry

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| No repeat entry | Don't require same info twice in process | A | Manual |
| Auto-populate | Previously entered data available | A | Manual |

**Implementation:**
- Auto-fill billing from shipping address
- Remember user preferences in multi-step forms
- Session storage for form data

### Level AA New Criteria

#### 2.4.11 Focus Not Obscured (Minimum)

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Focus visible | At least part of focused element visible | AA | Manual |
| Not hidden by sticky | Sticky headers/footers don't fully hide focus | AA | Manual |
| Not hidden by modals | Background focus not obscured by overlays | AA | Manual |

**Common Violations:**
```
❌ Sticky header covers focused nav item
❌ Cookie banner hides focused form field
❌ Floating chat widget covers focused button
```

**Fix Patterns:**
```css
/* Ensure scroll position accounts for sticky elements */
html { scroll-padding-top: 80px; }

/* Or use scroll-margin on focusable elements */
:focus { scroll-margin-top: 80px; }
```

#### 2.5.7 Dragging Movements

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Single-pointer alternative | Drag operations have click alternative | AA | Manual |
| No drag required | Essential function achievable without dragging | AA | Manual |

**Requires Alternatives For:**
- Drag-and-drop file uploads (+ click to select)
- Slider controls (+ text input or buttons)
- Sortable lists (+ move up/down buttons)
- Map panning (+ directional buttons)
- Canvas drawing (+ alternative input)

**Implementation Example:**
```html
<!-- Slider with buttons -->
<button aria-label="Decrease">-</button>
<input type="range" />
<button aria-label="Increase">+</button>

<!-- Or with text input -->
<input type="number" />
```

#### 2.5.8 Target Size (Minimum)

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Minimum 24×24 CSS px | Interactive targets meet minimum | AA | Manual |
| Spacing exception | Targets <24px have sufficient spacing | AA | Manual |
| Inline exception | Inline text links exempt | AA | Manual |

**Size Requirements (Stricter than 2.1):**
| WCAG Version | AA Requirement | AAA Requirement |
|--------------|----------------|-----------------|
| 2.1 | None | 44×44px |
| 2.2 | 24×24px | 44×44px |

**Exceptions:**
- Inline links within text paragraphs
- User-customized targets
- Essential smaller presentation
- Targets with 24px+ spacing between

#### 3.3.8 Accessible Authentication (Minimum)

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| No cognitive function test | Login doesn't require memory/transcription | AA | Manual |
| Object recognition allowed | Picture selection OK | AA | Manual |
| Personal content allowed | Identify your own content OK | AA | Manual |

**Prohibited:**
```
❌ Type this CAPTCHA text
❌ Remember and re-type your password
❌ Solve this puzzle
❌ Transcribe distorted audio
```

**Allowed:**
```
✅ Password managers (copy-paste enabled)
✅ Biometric authentication (fingerprint, face)
✅ Magic link / email verification
✅ "Select all images with cats" (object recognition)
✅ SSO / OAuth (delegated authentication)
✅ Hardware keys / FIDO2
```

### Level AAA New Criteria

#### 2.4.12 Focus Not Obscured (Enhanced)

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Focus fully visible | No part of focus indicator hidden | AAA | Manual |

**Stricter than 2.4.11:** Entire focused element must be visible, not just part.

#### 2.4.13 Focus Appearance

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Focus indicator size | ≥2px perimeter | AAA | Manual |
| Focus contrast | 3:1 against adjacent colors | AAA | Manual |
| Focus change area | ≥ outline of unfocused + 2px | AAA | Manual |

**Implementation:**
```css
:focus-visible {
  outline: 3px solid #005fcc;
  outline-offset: 2px;
}
```

#### 3.3.9 Accessible Authentication (Enhanced)

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| No cognitive tests at all | No object recognition either | AAA | Manual |

**Stricter than 3.3.8:** Even object recognition (image selection) prohibited.

---

## WCAG 2.2 Quick Checklist

| Criterion | ID | Level | Status |
|-----------|-------|-------|--------|
| Consistent Help | 3.2.6 | A | ☐ |
| Redundant Entry | 3.3.7 | A | ☐ |
| Focus Not Obscured (Min) | 2.4.11 | AA | ☐ |
| Dragging Movements | 2.5.7 | AA | ☐ |
| Target Size (Min) | 2.5.8 | AA | ☐ |
| Accessible Auth (Min) | 3.3.8 | AA | ☐ |
| Focus Not Obscured (Enhanced) | 2.4.12 | AAA | ☐ |
| Focus Appearance | 2.4.13 | AAA | ☐ |
| Accessible Auth (Enhanced) | 3.3.9 | AAA | ☐ |

---

## WCAG 2.2 Removed Criterion

**4.1.1 Parsing** has been removed in WCAG 2.2. Modern browsers and assistive technologies handle parsing errors, making this criterion obsolete.

---

## Perceivable (WCAG 1.x)

### 1.1 Text Alternatives

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Images have alt text | Descriptive, not "image of" | A | axe-core |
| Decorative images | `alt=""` or CSS background | A | Manual |
| Complex images | Long description available | A | Manual |
| Icons w/ meaning | Accessible name provided | A | axe-core |
| Form inputs | Labels or aria-label | A | axe-core |

### 1.2 Time-Based Media

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Video captions | Synchronized captions | A | Manual |
| Audio description | For visual-only content | A | Manual |
| Transcript | Text alternative available | A | Manual |
| No auto-play audio | Or mute control visible | A | Manual |

### 1.3 Adaptable

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Semantic HTML | Proper heading hierarchy | A | axe-core |
| Reading order | Logical DOM order | A | Manual |
| Landmark regions | header, nav, main, footer | A | axe-core |
| Tables | Headers w/ `<th>` scope | A | axe-core |
| Lists | Proper `<ul>`, `<ol>`, `<dl>` | A | axe-core |

### 1.4 Distinguishable

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Color contrast (text) | 4.5:1 normal, 3:1 large | AA | Contrast checker |
| Color contrast (UI) | 3:1 for controls | AA | Contrast checker |
| Color not sole indicator | Shape/text also used | A | Manual |
| Text resize | 200% w/o loss | AA | Browser zoom |
| Text spacing | Adjustable w/o breaking | AA | Manual |
| Reflow | No horiz scroll at 320px | AA | Responsive test |

---

## Operable (WCAG 2.x)

### 2.1 Keyboard Accessible

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| All functionality | Operable via keyboard | A | Manual |
| No keyboard trap | Can Tab away from all elements | A | Manual |
| Visible focus | Clear focus indicator | AA | Manual |
| Focus order | Logical tab sequence | A | Manual |
| Skip links | Skip to main content | A | Manual |
| Shortcut keys | Documented, not conflicting | A | Manual |

**Keyboard Navigation Protocol:**
```
1. Tab through entire page
2. Verify focus visible on each element
3. Test Enter/Space activation
4. Test Escape for overlays
5. Test Arrow keys in menus
6. Verify no dead ends
```

### 2.2 Enough Time

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Session timeout | Warning + extend option | A | Manual |
| Moving content | Pause, stop, hide controls | A | Manual |
| Auto-updating | User-controlled refresh | A | Manual |
| No time limits | Or adjustable + warned | A | Manual |

### 2.3 Seizures & Physical

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| No flashing >3Hz | Avoid seizure triggers | A | Manual |
| Reduced motion | `prefers-reduced-motion` | AAA | Code review |
| Animation toggle | User can disable | AAA | Manual |

### 2.4 Navigable

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Page titles | Descriptive `<title>` | A | axe-core |
| Focus order | Logical sequence | A | Manual |
| Link purpose | Clear from text | A | Manual |
| Multiple ways | Search, nav, sitemap | AA | Manual |
| Headings | Descriptive, hierarchical | AA | axe-core |
| Focus visible | 2px+ visible indicator | AA | Manual |

### 2.5 Input Modalities

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Touch target size | Min 44×44px | AAA | Manual |
| Pointer gestures | Single-point alternative | A | Manual |
| Pointer cancellation | Undo/abort on release | A | Manual |
| Motion actuation | Non-motion alternative | A | Manual |

---

## Understandable (WCAG 3.x)

### 3.1 Readable

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Page language | `lang` attr on `<html>` | A | axe-core |
| Part language | `lang` on foreign text | AA | Manual |
| Unusual words | Glossary available | AAA | Manual |
| Abbreviations | Expanded on first use | AAA | Manual |

### 3.2 Predictable

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| No focus change | Focus doesn't auto-move | A | Manual |
| No input change | Changing input = no submission | A | Manual |
| Consistent nav | Same order across pages | AA | Manual |
| Consistent ID | Same components = same name | AA | Manual |

### 3.3 Input Assistance

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Error identification | Errors described in text | A | Manual |
| Labels/instructions | Present before input | A | axe-core |
| Error suggestion | How to fix described | AA | Manual |
| Error prevention | Confirm destructive actions | AA | Manual |

---

## Robust (WCAG 4.x)

### 4.1 Compatible

| Check | Criteria | Level | Tool |
|-------|----------|-------|------|
| Valid HTML | No major parsing errors | A | W3C validator |
| Name, role, value | ARIA properly applied | A | axe-core |
| Status messages | `aria-live` for dynamic | AA | Manual |

---

## Screen Reader Compatibility

### ARIA Implementation

| Pattern | Required ARIA | Example |
|---------|---------------|---------|
| Button (non-`<button>`) | `role="button"` + keyboard | `<div role="button" tabindex="0">` |
| Modal dialog | `role="dialog"` + `aria-modal="true"` + focus trap | Dialog component |
| Tab panel | `role="tablist"`, `role="tab"`, `role="tabpanel"` | Tabs component |
| Dropdown menu | `aria-expanded`, `aria-haspopup` | Menu button |
| Live region | `aria-live="polite"` or `"assertive"` | Notifications |
| Loading state | `aria-busy="true"` | Skeleton loader |

### Screen Reader Testing

```
1. Enable screen reader (NVDA/JAWS/VoiceOver)
2. Navigate via headings (H key)
3. Navigate via landmarks (D key)
4. Navigate via links (K key)
5. Fill forms, verify label reading
6. Test dynamic content updates
7. Verify error announcements
```

---

## Color Contrast Requirements

| Content Type | AA Ratio | AAA Ratio |
|--------------|----------|-----------|
| Normal text (<18pt/14pt bold) | 4.5:1 | 7:1 |
| Large text (≥18pt/14pt bold) | 3:1 | 4.5:1 |
| UI components & graphics | 3:1 | 3:1 |
| Decorative/logos | No req | No req |

### Contrast Checker Script

```bash
python3 scripts/check_contrast.py --fg "#333333" --bg "#FFFFFF"
# Output: Ratio 12.63:1 ✅ Passes AA & AAA
```

---

## Focus Management

### Focus States Checklist

| State | Requirement |
|-------|-------------|
| Visible | 2px+ outline or equivalent |
| High contrast | 3:1 against adjacent |
| Consistent | Same style across UI |
| No outline removal | Never `outline: none` w/o replacement |
| Focus ring | `:focus-visible` for keyboard only |

### Focus Trap Pattern (Modals)

```javascript
// Required for modal dialogs
1. Move focus to modal on open
2. Trap Tab within modal
3. Return focus to trigger on close
4. Close on Escape key
```

---

## Form Accessibility

### Label Requirements

| Input Type | Labeling Method |
|------------|-----------------|
| Text fields | `<label for="">` or `aria-labelledby` |
| Radio/checkbox groups | `<fieldset>` + `<legend>` |
| Required fields | `aria-required="true"` or `required` |
| Error states | `aria-invalid="true"` + `aria-describedby` |

### Error Announcement

```html
<input aria-invalid="true" aria-describedby="error-msg">
<div id="error-msg" role="alert">Password must be 8+ chars</div>
```

---

## Tools Integration

| Tool | Purpose | Usage |
|------|---------|-------|
| axe-core | Automated testing | `npm run axe` or browser extension |
| Lighthouse | A11y audit | Chrome DevTools → Audits |
| WAVE | Visual overlay | Browser extension |
| NVDA | Screen reader (Windows) | Free download |
| VoiceOver | Screen reader (Mac) | Cmd+F5 |
| Contrast Checker | Color ratios | `scripts/check_contrast.py` |

---

## Audit Report Template

```markdown
# A11Y Audit Report

**Product:** [Name]
**WCAG Target:** AA
**Date:** [Date]

## Summary

| Principle | Pass | Fail | N/A |
|-----------|------|------|-----|
| Perceivable | X | X | X |
| Operable | X | X | X |
| Understandable | X | X | X |
| Robust | X | X | X |

## Critical Issues (Must Fix)

| Issue | WCAG | Location | Fix |
|-------|------|----------|-----|
| [desc] | [criterion] | [page/component] | [solution] |

## Recommendations

1. [Priority fix]
2. [Enhancement]
```
