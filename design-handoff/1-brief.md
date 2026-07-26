# ACC Redesign Brief

## What this is
A personal student dashboard for one user — Michael Maxwell, MWCC. Single HTML file, vanilla JS, localStorage, deployed on Netlify. The logic is done. This is a UI redesign only.

## The problem with the current design
- Feels like a webpage, not a tool
- Big empty cards stacked in a column
- Tiny bottom nav, too many tabs, no hierarchy
- Everything is the same visual weight — nothing signals urgency
- Wastes space, no focus

## The user
- ADHD — calm, focused, low cognitive load is non-negotiable
- Studies on his phone from 6:45–9:30 PM
- Needs to open the app and know his one next action in under 2 seconds
- No shame states — overdue is flagged clearly, never scolding

## Design rules (non-negotiable)
1. One clear next action always visible on open
2. Mobile-first — phone is the real device, desktop is the scale-up
3. Low cognitive load — hierarchy through size and restrained color, not clutter

---

## Color
- Base: neutral slate
- Single accent: warm amber (#D98A3D dark / #C77D2E light)
- Status: desaturated red for overdue, desaturated orange for due-soon — they signal, they do not shout
- 90% of the UI is neutral gray. Color is rare and meaningful.
- Ship both light and dark modes with a toggle. Persist choice in localStorage.
- Dark base: ~#14161a. Light base: ~#F4F5F7.

## Typography
- Space Grotesk for UI
- JetBrains Mono for numbers and dates
- Push size contrast hard: large stat numbers, tight uppercase micro-labels, comfortable body

---

## Layout

### Mobile (default)
- Clean top header: date, greeting, mode toggle, most urgent item as a hero row
- Bottom tab bar, 5 items max, overflow menu for the rest
- Content stacks in priority order

### Desktop 900px+
- Bottom bar becomes a collapsible left sidebar (icon + label, collapses to icon only)
- Dashboard goes two-column where it helps

---

## Home / Dashboard
Open here every time. Top to bottom:
1. Header with date, greeting, mode toggle, and the single most urgent item with a jump button
2. Three-stat row: Overdue / Due Soon / Done — big mono numbers, small labels
3. Priority list — single-line rows: status dot · course tag · title · due date
4. Course grade summary — one compact row per course, grade + risk pill
5. Quick Launch — Blackboard, MyEconLab, Claude, Netlify, MWCC Portal, Salem State

No section header that just restates what is under it. No decorative padding.

---

## Courses + Tutor Mode
Five courses: SOC 205, ECO 101, POL 211, BIO 109, PSY 240.

Each course card shows: code + name, professor, current grade, risk pill, next deadline.

Each card has a **Tutor** button. Tutor Mode expands the card in place and shows:
- **Practice Quizzes** — uses the existing quiz engine (see file 2). Filter to this course.
- **Study Resources** — uses existing STUDY_RESOURCES array. Filter to this course.
- **Key Terms** — new KEY_TERMS structure (see file 2). Scrollable term/definition list. Filter to this course.
- **Flashcards** — generated from KEY_TERMS. Tap to flip. Filter to this course.
- **Study Checklist** — 4 placeholder checkable items for this course.

---

## Navigation
Dashboard · Assignments · Courses · Planner · Files · Contacts · Settings

Study folds into course cards as Tutor Mode — no standalone Study nav item needed, but the underlying functions stay in the file.

---

## Feel
Linear or Things, not a school portal. Calm, focused, every element earns its place. Something he opens every night and immediately knows what to do.

---

## Deliver
One complete index.html. All CSS in style. All JS in script. No dependencies beyond Google Fonts and existing manifest.json / sw.js references. Ready for Claude Code to wire and Netlify to deploy.
