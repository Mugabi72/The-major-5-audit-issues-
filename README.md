The-major-5-audit-issues-
This repository contains the major five  audit issues  that i  have identified while interacting with the wed sites, explaining who is affected and the barriers, and a recommended possible, practical improvement to solve the identified issues
 The Major 5 Audit Issues: Notes

You didn't list your five issues, so these notes cover the five most common ones found in website audits (accessibility and usability). Swap in your own findings where they differ.

How to structure each issue
For every issue, state: **What it is → Who is affected → Barrier → Recommended fix → Standard (e.g., WCAG)**


1. Poor colour contrast and tiny text
- **Who is affected:** Users with low vision or colour blindness, older adults, anyone on a phone in sunlight.
- **Barrier:** Light grey text on white or small fonts make content hard or impossible to read.
- **Fix:** Use a contrast ratio of at least 4.5:1 for body text, allow text resizing, and use a base font of 16px or larger.
- **Standard:** WCAG 1.4.3 (Contrast), 1.4.4 (Resize Text)

2. Missing alt text on images
- Who is affected:** Blind and low-vision users who rely on screen readers, and users on slow connections where images fail to load.
- Barrier:** The screen reader says "image" or reads a file name, so meaning is lost.
- Fix: Add short, meaningful alt text to informative images, and use empty alt (`alt=""`) for decorative ones.
- Standard:WCAG 1.1.1 (Non-text Content)

3. Poor keyboard navigation and no focus indicators
- Who is affected: Users with motor impairments, screen-reader users, and anyone who can't use a mouse.
- Barrier: Menus, buttons, and forms can't be reached or operated using Tab/Enter, and the user can't see where they are on the page.
- Fix:  Make all interactive elements keyboard-accessible, keep a visible focus outline, and use a logical tab order.
- Standard: WCAG 2.1.1 (Keyboard), 2.4.7 (Focus Visible)

4. Confusing forms and unclear error messages
- Who is affected: Everyone, especially first-time users, people with cognitive disabilities, and non-native language speakers.
- Barrier: Missing labels, vague errors like "Invalid input," and forms that clear when an error occurs lead to abandonment.
- Fix: Use visible labels, give specific error messages ("Enter a valid email, e.g. name@mail.com"), and keep entered data when errors occur.
- Standard: WCAG 3.3.1 (Error Identification), 3.3.2 (Labels or Instructions)

 5. Poor mobile responsiveness and slow loading
- Who is affected: Mobile users, users on low bandwidth or expensive data (very relevant in Uganda), and low-end device owners.
- Barrier: Content overflows the screen, buttons are too small to tap, and heavy images cause long load times.
- Fix: Use responsive layouts, compress and lazy-load images, make tap targets at least 44×44px, and minimise scripts.
- Standard: WCAG 1.4.10 (Reflow), 2.5.5 (Target Size)

---
 Tips for your README
- Open with a 2–3 line **purpose statement** (what you audited, how, and when).
- Name the websites you tested and the tools you used (e.g., WAVE, Lighthouse, keyboard-only testing).
- Use a summary table (Issue | Affected group | Barrier | Fix) for quick reading.
- Add screenshots as evidence for each issue.
- End with a short conclusion on which issue has the highest impact and should be fixed first.

If you share your actual five issues and the websites you audited, I can tailor this into a finished README or a Word document.
 Here is extra material you can add to your audit notes, in the same structure.

## 6. Summary table (for the README)

| # | Issue | Who is affected | Barrier | Fix | WCAG |
|---|---|---|---|---|---|
| 1 | Poor contrast, tiny text | Low vision, colour blind, older adults | Text is hard to read | 4.5:1 contrast, 16px+ font | 1.4.3, 1.4.4 |
| 2 | Missing alt text | Blind and low-vision users | Image meaning lost | Meaningful `alt`, empty `alt=""` for decoration | 1.1.1 |
| 3 | Poor keyboard navigation | Motor impaired, screen-reader users | Cannot reach or see focus | Keyboard access, visible focus | 2.1.1, 2.4.7 |
| 4 | Confusing forms and errors | Everyone, cognitive disabilities | Users abandon forms | Labels, specific errors, keep data | 3.3.1, 3.3.2 |
| 5 | Poor mobile and slow loading | Mobile, low-bandwidth users | Overflow, small buttons, long loads | Responsive layout, compress images | 1.4.10, 2.5.5 |

## 7. Background: what is a website audit?
A website audit is a systematic check of a site against a standard to find problems and recommend fixes. An **accessibility and usability audit** checks whether all people, including those with disabilities, can use the site.
- **WCAG** (Web Content Accessibility Guidelines) is the international standard, built on four principles: **POUR**.
  - **Perceivable:** users can see or hear the content (contrast, alt text).
  - **Operable:** users can navigate and use controls (keyboard, target size).
  - **Understandable:** content and behaviour are clear (forms, errors).
  - **Robust:** works with assistive technologies and different devices.
- **Conformance levels:** A (minimum), AA (the usual target), AAA (highest).

## 8. Audit method and tools

| Tool or method | What it checks |
|---|---|
| **WAVE** | Flags missing alt text, low contrast, missing labels |
| **Lighthouse** (Chrome DevTools) | Accessibility, performance and best-practice scores |
| **axe DevTools** | Detailed accessibility violations with fixes |
| **Colour Contrast Analyser** | Exact contrast ratios |
| **Keyboard-only test** | Tab, Shift+Tab, Enter, Esc through the whole page |
| **Screen reader** (NVDA, VoiceOver, TalkBack) | What blind users actually hear |
| **Device emulation** | Mobile layout in browser DevTools |
| **Network throttling** (Slow 3G) | Load time on poor connections |

**Steps followed:** choose pages, run automated tools, test manually, record findings with screenshots, rate severity, recommend fixes.

## 9. Issue-by-issue extras

**Issue 1: Contrast and text size**
- Large text (18pt or 14pt bold) needs only 3:1.
- Never use colour alone to convey meaning (e.g. red for errors with no text or icon).
- Example fix: change `#999` text on white (about 2.8:1) to `#595959` (about 7:1).

**Issue 2: Alt text**
- Good: `alt="Students queuing at the UCU library"`. Bad: `alt="image1.jpg"`.
- Complex images (charts) need a longer text description nearby.
- Images that are links should describe the destination, not the picture.
```html
<img src="logo.png" alt="UCU home page">
<img src="divider.png" alt="">
```

**Issue 3: Keyboard and focus**
- Never remove the outline with `outline: none` unless you add a replacement.
- Add a "Skip to main content" link at the top for keyboard users.
- Avoid keyboard traps, where focus enters a pop-up and cannot leave.
```css
a:focus, button:focus { outline: 3px solid #005fcc; outline-offset: 2px; }
```

**Issue 4: Forms and errors**
- Link each label to its input with `for` and `id`.
- Mark required fields clearly and explain formats before the user types.
- Show the error next to the field, and say how to fix it.
```html
<label for="email">Email address</label>
<input id="email" type="email" required aria-describedby="email-help">
<span id="email-help">Example: name@mail.com</span>
```

**Issue 5: Mobile and speed**
- Add the viewport tag: `<meta name="viewport" content="width=device-width, initial-scale=1">`.
- Use modern formats (WebP) and `loading="lazy"` on images.
- Uganda context: data is costly and many users are on mobile, so a lighter page is also cheaper to use.
- Aim for a load time under 3 seconds.

## 10. Severity rating

| Level | Meaning | Example |
|---|---|---|
| **Critical** | Blocks users completely | Form cannot be submitted by keyboard |
| **High** | Serious difficulty | Missing alt on key images |
| **Medium** | Causes frustration | Vague error messages |
| **Low** | Minor inconvenience | Small spacing problems |

Suggested priority: fix keyboard access and forms first (they block tasks), then alt text, contrast and mobile speed.

## 11. Template for recording each finding
```
Issue:
Page / website:
Description:
Who is affected:
Barrier:
Evidence (screenshot):
Severity:
Recommended fix:
WCAG criterion:
```

## 12. Benefits of fixing these issues
- Reaches more users, including people with disabilities.
- Improves SEO, since alt text, headings and speed help search ranking.
- Reduces legal and reputational risk.
- Better usability and higher conversion for all users.

## 13. Conclusion (sample wording)
"The audit found five major barriers: poor contrast, missing alt text, weak keyboard navigation, confusing forms and poor mobile performance. Keyboard access and forms have the highest impact because they stop users from completing tasks. Fixing all five would make the sites more inclusive, faster and easier to use."

## 14. Likely exam questions
1. **What is a website audit?** A systematic review of a site against a standard to find problems and suggest fixes.
2. **What does POUR stand for?** Perceivable, Operable, Understandable, Robust.
3. **What contrast ratio does WCAG AA require for body text?** 4.5:1.
4. **When should alt text be empty?** For purely decorative images.
5. **Why does keyboard accessibility matter?** Many users cannot use a mouse and rely on Tab and Enter.
6. **Name three audit tools.** WAVE, Lighthouse, axe DevTools.

## 15. Key terms
- **Accessibility:** designing so people with disabilities can use the site.
- **Assistive technology:** tools such as screen readers.
- **Screen reader:** software that reads page content aloud.
- **Focus indicator:** the visible outline showing the active element.
- **Responsive design:** layouts that adapt to any screen size.
- **Lazy loading:** loading images only when they are about to be seen.

Share your real five issues and the sites you audited, and I can turn this into a finished README or a Word document.


Here are more sections that continue from section 15 in the same structure.

## 16. Other common issues (use as extras or swap-ins)

| Issue | Who is affected | Fix | WCAG |
|---|---|---|---|
| Poor heading structure (skipped levels, bold text used as headings) | Screen-reader users | Use one `<h1>`, then `<h2>`, `<h3>` in order | 1.3.1, 2.4.6 |
| Vague link text ("click here", "read more") | Screen-reader and cognitive users | Use descriptive text, e.g. "Download the 2026 fee structure" | 2.4.4 |
| No captions or transcripts for video/audio | Deaf and hard-of-hearing users | Add captions and a transcript | 1.2.1, 1.2.2 |
| Missing page title or language attribute | Screen-reader users | Unique `<title>` and `<html lang="en">` | 2.4.2, 3.1.1 |
| Auto-playing media, moving banners | Users with attention or vestibular issues | Allow pause/stop, avoid autoplay | 2.2.2 |
| Session timeouts without warning | Slow readers, motor-impaired users | Warn and allow extension | 2.2.1 |

17. Useful ARIA basics
- **First rule of ARIA:** use native HTML (`<button>`, `<nav>`) before adding ARIA.
- `aria-label` gives a name to icon-only buttons.
- `aria-live="polite"` announces dynamic messages such as form errors.
- `role="alert"` is used for urgent messages.

```html
<button aria-label="Open menu"><svg>…</svg></button>
<div role="alert">Password must be at least 8 characters.</div>
```

## 18. Landmarks and structure
Use `<header>`, `<nav>`, `<main>`, `<footer>` so screen-reader users can jump between page regions.

```html
<a href="#main" class="skip-link">Skip to main content</a>
<main id="main"> … </main>
```

## 19. Quick manual test checklist
- [ ] Can I complete the main task using only the keyboard?
- [ ] Is the focus outline always visible?
- [ ] Do all informative images have meaningful alt text?
- [ ] Does text zoom to 200% without breaking the layout?
- [ ] Is contrast at least 4.5:1 for body text?
- [ ] Do form errors say what went wrong and how to fix it?
- [ ] Does the page work at 320px width (phone)?
- [ ] Does the page load in under 3 seconds on Slow 3G?

## 20. Example finding (filled-in template)
```
Issue: Missing alt text on images
Page / website: Home page – News section
Description: Five news thumbnails have no alt attribute; the screen reader reads "image1.jpg".
Who is affected: Blind and low-vision users
Barrier: News meaning is lost
Evidence: Screenshot of WAVE report (Figure 2)
Severity: High
Recommended fix: Add alt="Students receiving certificates at graduation"
WCAG criterion: 1.1.1 Non-text Content
```

## 21. Prioritised action plan

| Priority | Action | Effort | Impact |
|---|---|---|---|
| 1 | Fix keyboard access and focus | Medium | Very high |
| 2 | Improve form labels and errors | Low | High |
| 3 | Add alt text | Low | High |
| 4 | Fix contrast and text size | Low | Medium |
| 5 | Optimise images and mobile layout | Medium | High (Uganda data costs) |

## 22. Limitations of the audit
- Automated tools catch only about 30–40% of issues, so manual testing is essential.
- Only a sample of pages was tested.
- Testing was not done with real users with disabilities.
- Sites change over time, so results reflect the date of testing.

## 23. Recommendations beyond fixes
- Include accessibility in design and development from the start, not as an afterthought.
- Train content editors on alt text and headings.
- Re-test after every major update.
- Publish an accessibility statement with a contact for feedback.

## 24. More likely exam questions
1. Differentiate WCAG levels A, AA and AAA.** A is the minimum, AA is the usual target, AAA is the highest and not always achievable.
2. Why do automated tools alone fail?** They cannot judge meaning, such as whether alt text is accurate.
3. What is a keyboard trap?** Focus enters an element and the user cannot leave it with the keyboard.
4. Give two benefits of accessible sites to a business.** Wider audience and better SEO.
5. What is a skip link?** A hidden link that lets keyboard users jump past the menu to the main content.
6. Why is page speed an accessibility issue in Uganda?** Data is costly and bandwidth is limited, so heavy pages exclude users.

25. More key terms
- ARIA:** attributes that add accessibility information to elements.
- Landmark:** a page region (`main`, `nav`) that assistive tools can jump to.
- Alt text:** a text alternative describing an image.
- Keyboard trap:** focus gets stuck in an element.
- Severity rating:** how seriously an issue affects users.
- Conformance:** meeting a WCAG level.

26. References
- W3C, *Web Content Accessibility Guidelines (WCAG) 2.2*, w3.org/TR/WCAG22
- WebAIM, *WCAG 2 Checklist*, webaim.org
- Google, *Lighthouse documentation*, developer.chrome.com

I can merge everything (sections 1–26) into one finished README or a Word document. If you give me the five real issues and the websites you audited, I'll tailor it to them.


