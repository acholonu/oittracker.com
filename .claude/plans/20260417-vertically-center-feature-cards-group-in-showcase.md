# Vertically Center Feature Cards Group in Showcase Grid

## Context

The feature cards in the showcase section share a grid row with the phone mockup. The phone image drives the row height, which is taller than the 8 cards need. Currently the cards pack to the top (`align-content` defaults to `start`), leaving empty space below the last row of cards. The user wants the card group centered vertically alongside the phone.

UX reviewer confirmed this is the correct approach — cards keep their natural height with icon top-aligned to title text (`flex-start`), while the group as a whole centers in the available vertical space.

## Change

**File:** `/Users/ujones/Dropbox/My Mac (Drs-MacBook-Pro.local)/Documents/Repos/oittracker.com/index.html`

Add `align-content: center` to the `.features` grid (line ~289):

```css
/* Before */
.features {
  grid-column: 2;
  grid-row: 1;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.625rem 0.875rem;
}

/* After */
.features {
  grid-column: 2;
  grid-row: 1;
  display: grid;
  grid-template-columns: 1fr 1fr;
  align-content: center;
  gap: 0.625rem 0.875rem;
}
```

One CSS property, zero HTML changes.

## Why this works

- `.features` is stretched to match the phone mockup height by the parent `.showcase-grid`
- `align-content: center` distributes the extra vertical space evenly above and below the card rows
- Cards keep natural height (no dead space inside card backgrounds)
- At mobile breakpoints (768px and below), the phone and cards are in separate rows — no extra space to center within, so this becomes a no-op

## Subagent Strategy

No subagents needed — single CSS property addition.

## Regression Prevention

No automated tests for the marketing site. Manual verification only.

## Verification

1. Open `index.html` in browser at desktop width (>960px)
2. Confirm the 2x4 card grid is vertically centered alongside the phone mockup
3. Confirm icons remain top-aligned with their title text
4. Resize to 768px — cards should stack below phone, no visual change
5. Resize to 640px, 480px, 390px — no regressions
