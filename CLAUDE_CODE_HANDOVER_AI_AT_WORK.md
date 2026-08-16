# Claude Code Handover — “AI at Work” Landing Page

## 1. Mission

Build a polished, responsive landing page that demonstrates how AI can support a busy business owner named **Christian** throughout a workday.

This is **not** a generic AI feature list and **not** a literal storyboard. Each major section should feel like a premium product highlight. The progression through Christian’s day is the invisible narrative structure.

The page uses choreographed motion to demonstrate future AI workflows without requiring live integrations in this version.

## 2. Current Files

- `christian-ai-day-final-v3.html` — latest working prototype; use this as the primary implementation reference.
- `upload/out_index.html` — the user’s original ŌLLIN MAIZ site; use only as a visual and interaction reference. Do not overwrite it.

The current prototype is a self-contained HTML/CSS/JavaScript file.

## 3. Locked Decisions

### Audience and character

- Primary viewer: business owner / prospective client.
- Demonstration character: **Christian**.
- The page should make Christian think, “This understands my work and can take real operational weight off my plate.”

### Visual direction

- Performance-tech identity stays.
- Editorial presentation: oversized typography, numbered section rails, technical micro-labels, thin rules, disciplined spacing, and product UI as the centerpiece.
- Palette is strictly **black, white, and blue**.
- Current blue: `#4DA3FF`.
- Do not use lime, volt, green, yellow, orange, or amber. The volt accent inherited from MAIZ was accidental.
- Typeface pairing: Archivo + IBM Plex Mono.
- Dark interfaces should feel precise and premium, not like a generic SaaS dashboard.

### Experience structure

There are exactly **three live/choreographed product demonstrations**:

1. Morning planning
2. Contractor submissions and payment approval
3. First-meeting preparation

Do not build a separate live simulation for every remaining AI capability. The remaining capabilities should be concise editorial rows using:

`Situation / Problem → AI solution → Finished output`

The page ends by presenting the overall product: an AI operating layer built around Christian’s business.

### Motion philosophy

- Motion is how the page demonstrates functionality before real integrations exist.
- Each product demo should autoplay once when it enters the viewport.
- Manual controls should remain available for replay or presentation use.
- Animations must be purposeful: inputs are read, checked, organized, and transformed into finished work.
- Support `prefers-reduced-motion`.
- Avoid decorative motion that does not explain the workflow.

## 4. Page Architecture

### Hero

Purpose: establish that the visitor will watch AI work through a real business day.

Current direction:

> YOUR DAY.  
> WORKING WITH YOU.

Supporting idea:

> Not another list of things AI could do. Watch the work leave Christian’s plate.

Keep the hero shorter than the MAIZ hero so Section 01 appears quickly.

---

### 01 — Morning Planning

Headline:

> EVERYTHING THAT MATTERS.  
> IN THE RIGHT ORDER.

Core interaction:

1. Display one large editorial block of scrambling characters.
2. The scramble must resemble the controlled text behavior in this reference: <https://examples.motion.dev/react/scramble-text>.
3. Do **not** use floating chaos cards. The characters themselves scramble.
4. The scramble remains visibly active until the transformation runs; it must not finish before the visitor reaches it.
5. On viewport entry, or when “Organize my day” is clicked, characters progressively resolve.
6. The text then transitions into a beautiful daily plan.

Scrambled source content:

> 17 unread emails. 3 approvals. 6 meetings. 2 conflicts. 1 overdue invoice.

Resolved plan:

- Greeting: “Good morning, Christian.”
- Date: Tuesday, August 18.
- Highest-impact work appears first:
  - Approve Lakeshore estimate.
  - Prepare for Rivera meeting.
  - Resolve Invoice #1048.
- Below: a clean, time-based calendar.
- Include subtle intelligence labels such as “Protected,” “Brief ready,” and “Travel added.”

Closing idea:

> Everything that matters. In the right order.

Acceptance criteria:

- Scramble is unmistakably visible.
- It does not look like random floating notifications.
- Transition ends in a calm, legible, high-execution plan.
- Replay works.

---

### 02 — Contractor Workflow

Headline:

> THEY SUBMIT THE WORK.  
> YOU APPROVE THE PAYMENT.

Purpose: demonstrate a custom operational system that replaces texted time cards, emailed screenshots, manual calculations, and missing information.

Important language:

- Refer to 1099 workers as **contractors**, not employees.

Choreographed workflow:

1. Contractor submits weekly work through a clean portal.
2. Submission includes contractor, project, week ending, hours, receipts, and work description.
3. System visibly checks the submission.
4. Christian sees a weekly payout/approval view.
5. AI flags one exception that needs judgment.
6. Ready payments move to approved.
7. End state confirms records updated and contractors notified.

Example data:

- Jordan Reed — Lakeshore — 19.5 hours — $1,365.
- Maya Torres — Rivera — 24 hours — $1,440.
- Anthony Lewis — Oak Street — 17 hours — $1,020.
- Weekly total — $3,825 / 60.5 hours.

Trust principle:

> AI prepares, checks, and organizes the payment. Christian retains approval.

This is a simulated workflow. Do not imply that funds are actually transferred.

---

### 03 — First Meeting Preparation

Headline:

> WALK INTO THE ROOM.  
> ALREADY PREPARED.

Purpose: show AI preparing Christian for his first meeting, rather than adding another generic feature description.

Prompt shown in the interface:

> Prepare me for my 10:30 Rivera meeting.

Choreographed workflow:

1. Prompt activates automatically on viewport entry or by button.
2. A visible trace runs in sequence:
   - 18 emails reviewed.
   - Original proposal located.
   - Two previous meetings summarized.
   - Open commitments checked.
   - Timeline risk identified.
3. The final pre-meeting brief assembles visibly.

Brief content:

- **What changed:** Requested launch date moved forward by nine days.
- **What is at risk:** Final design approval is outstanding and blocks production.
- **Recommended position:** Offer the accelerated timeline only if Rivera approves final design by Wednesday at noon.
- **Talking points:** confirm why the date moved, establish the approval gate, leave with one owner and one deadline for every open item.

Trust principle:

> AI reconstructs the context. Christian leads the conversation.

---

### 04 — Remaining Capabilities

Do not create additional full simulations. Use elegant editorial rows with four columns on desktop and a readable stacked treatment on mobile:

| Domain | Situation / Problem | AI Solution | Finished Output |
|---|---|---|---|
| Docs & Proposals | Ideas live in scattered notes, voice memos, and old documents. | AI structures the material, drafts the document, and adapts it to Christian’s voice. | Client-ready proposal |
| Strategy & Synthesis | Daily execution leaves little time to research options or think ahead. | AI compares competitors, tests scenarios, and organizes evidence behind a decision. | Decision roadmap |
| Follow-through | Decisions disappear across meetings, messages, and informal promises. | AI captures commitments, assigns next steps, and prepares follow-ups. | Action plan |

Rows should reveal sequentially on scroll. They should feel editorial, not like a spreadsheet pasted into a website.

---

### Final Product Section

Positioning:

> NOT MORE SOFTWARE.  
> A WORKING OPERATING LAYER.

Supporting copy:

> One connected AI system that helps Christian plan the day, run repeatable workflows, enter meetings prepared, and turn unfinished information into finished work.

Three product principles:

1. Sees the full day.
2. Prepares the work.
3. Keeps Christian in control.

Do not end with a generic “AI saves time” message. End with the feeling that the system understands how Christian’s business operates.

## 5. Motion Specification

### Global

- Use `IntersectionObserver` or the framework equivalent to trigger each section once.
- Keep manual triggers enabled after autoplay.
- Use easing similar to `cubic-bezier(.18,.85,.24,1)` for major reveals.
- Prefer opacity, transform, filter, and direct text updates for performance.
- Do not animate layout properties unnecessarily.

### Scramble

- Continuous visible scrambling before activation.
- On activation, progressively lock characters from left to right.
- Preserve spaces and punctuation.
- After all characters resolve, wait approximately 200–300 ms, then transition to the calendar.
- If Motion+ is licensed in the target project, use its `ScrambleText` component.
- If Motion+ is not licensed, implement equivalent behavior locally; do not copy proprietary source.

### Contractor demo

- Submission state: idle → checking → submitted.
- Approval view: records appear checked; one exception remains visible.
- Approval state should visibly complete without suggesting a real payment occurred.

### Meeting demo

- Trace lines reveal at roughly 350–450 ms intervals.
- Brief remains blurred/dim until the trace completes.
- Final brief resolves sharply and becomes fully readable.

### Static rows

- Stagger rows by roughly 100–150 ms.
- Keep motion understated so it does not compete with the three live demos.

## 6. Responsive Requirements

- Mobile-first QA is mandatory because the original MAIZ references were reviewed on a phone.
- Numbered rail collapses above section content on narrow screens.
- Priority cards stack vertically.
- Calendar retains readable times and event names; optional metadata pills can hide on very small screens.
- Contractor submission and approval views stack.
- Meeting trace appears above the finished brief.
- Capability rows become two-column or stacked cards.
- No horizontal overflow.

## 7. Accessibility

- All controls require accessible labels.
- Keyboard activation must work.
- Do not place interactive elements inside `aria-hidden` containers.
- Dynamic finished states should be understandable without animation.
- Respect `prefers-reduced-motion`; show final legible content instead of scrambling indefinitely.
- Maintain sufficient contrast for blue text and borders on black.

## 8. Content and Claim Guardrails

- Time-saved figures are estimates until Christian confirms actual workload. Label them as estimates or omit them from the primary experience.
- Do not claim live email, calendar, payment, or document integrations in this prototype.
- Do not imply AI autonomously sends money, emails, or external messages.
- Demonstrate preparation and approval; Christian remains the decision-maker.
- Use realistic business data, but keep it fictional/non-sensitive.

## 9. Definition of Done

- Black/white/blue palette only.
- Three and only three major live demos.
- Scrambler clearly matches the user’s Motion reference in spirit and behavior.
- All demos autoplay on scroll and can be manually triggered/replayed.
- Remaining capabilities use the concise problem → solution → output structure.
- Final product positioning is present.
- Responsive at desktop, tablet, and phone widths.
- Reduced-motion mode works.
- No console errors.
- No accidental lime/amber/volt values remain.
- Original `upload/out_index.html` remains untouched.

## 10. Immediate Claude Code Task

1. Open and run `christian-ai-day-final-v3.html`.
2. Verify the current implementation against this specification.
3. Fix the scramble so its behavior is clearly visible and faithful to the Motion reference.
4. Perform responsive visual QA, especially on mobile.
5. Refine spacing, timing, and state transitions without changing the locked structure or palette.
6. Preserve a reviewable version before any framework migration.

