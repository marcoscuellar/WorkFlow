# AI at Work — Christian's Day

A self-contained landing page that demonstrates how an AI operating layer supports a
business owner through one real working day. No build step, no dependencies: open
`christian-ai-day-final-v3.html` in a browser.

## Files

| File | Purpose |
|---|---|
| `christian-ai-day-final-v3.html` | The page. HTML, CSS and JS in one file. |
| `CLAUDE_CODE_HANDOVER_AI_AT_WORK.md` | The specification this build is verified against. |
| `vercel.json` | Serves the page at `/` without renaming it. |

## Deploying

There is no build step. The repo root is the static output, and `vercel.json` rewrites
`/` to `christian-ai-day-final-v3.html` so the page loads at the bare domain.

On Vercel, the project needs **no framework preset and no build command** — "Other" with
the output directory left empty. Check too that the project's *production branch* matches
this repo's default branch, otherwise pushes here only produce preview deployments.

## Preserved baseline

Commit `318acf7` holds the prototype exactly as it was delivered, before any QA work.
Diff against it to review every change:

```
git diff 318acf7 -- christian-ai-day-final-v3.html
```

## Structure

Three choreographed product demos, and no more (per the spec):

1. **Morning planning** — a scrambling headline resolves into the day's operating plan.
2. **Contractor workflow** — a submission is checked, then payment is approved.
3. **Meeting preparation** — a trace runs, then the pre-meeting brief assembles.

Remaining capabilities are editorial rows (situation → AI solution → finished output),
followed by the product positioning section.

Every demo autoplays once when it scrolls into view and stays manually triggerable for
presentation use. Section 01 also has a replay control.

## How the scramble works

Each character sits in its own cell, sized to the advance width of that character's
*resolved* glyph and expressed in `em` so it scales with the clamped font size. Line
breaks are therefore fixed by the final sentence, and a random glyph can never reflow
the block. Each cell also draws only from glyphs narrow enough to fit inside it, so
random characters cannot spill over their neighbours.

Cells are measured after `document.fonts.ready` so the widths match Archivo rather than
the fallback face. Spaces and punctuation never scramble. On activation, characters lock
progressively from left to right behind a short accent-coloured wavefront; the sentence
holds for ~260 ms before the plan takes over.

## Accessibility

- Reduced motion is a first-class path: the same scroll triggers fire, every delay is
  zero, and each demo simply presents its finished, legible state.
- The scrambling text is `aria-hidden`; a visually hidden sentence carries the real
  content to screen readers.
- All controls are real buttons with a visible `:focus-visible` ring, and every demo can
  be driven from the keyboard.
- Body copy meets WCAG AA against its actual background.

## Content guardrails

The workflows are simulated. Nothing here connects to live email, calendar, payment or
document systems, and no money moves — the page demonstrates preparation and approval,
with Christian as the decision-maker. Business data is realistic but fictional.

## QA

Verified in Chromium at 320, 390, 768, 1280 and 1600 px, plus a reduced-motion pass at
desktop and phone widths: no console errors, no horizontal overflow, no contrast
failures, and the palette is strictly black, white and blue (`#4DA3FF`).
