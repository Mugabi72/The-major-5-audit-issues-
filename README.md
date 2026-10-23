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
