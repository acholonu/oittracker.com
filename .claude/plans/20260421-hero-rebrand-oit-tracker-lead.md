# Hero rebrand: lead with "OIT Tracker", demote "OIT Simplified." to eyebrow

> **Rename this file on approval** to `.claude/plans/20260421-oittracker-site-hero-rebrand.md` per the `YYYYMMDD-<goal>.md` naming convention (memory preference — the current name was system-generated).
>
> **Where this plan actually lives for execution**: the change is in a *different* repo (`~/Documents/Repos/oittracker.com`), which already has its own `.claude/plans/` convention. Recommend copying this plan into that repo after approval so the decision lives next to the code. We keep a copy here as cross-repo decision history.

## Context

`oittracker.com/index.html:347` reads `<h1>OIT Simplified</h1>` at 3.25rem / weight 700 / white. The product name "OIT Tracker" appears in the hero only as a 1rem nav wordmark (line 332) and in the phone-mockup alt text (line 364). A first-time visitor sees the tagline *before* they see the app's name, which weakens brand recognition for App Store search, word-of-mouth recall, and the in-page SEO signal.

The ask is to swap the hierarchy: make **OIT Tracker** the dominant hero heading and keep **OIT Simplified.** as a tagline byline *above* it. The sentiment stays; the brand leads.

User selections (AskUserQuestion, 2026-04-21):
- **Placement**: eyebrow kicker *above* the H1
- **Phrasing**: `OIT Simplified.` (exact wording, with trailing period)

## Current state (verified against local clone)

Repo: `~/Documents/Repos/oittracker.com`, branch `main`, clean working tree, HEAD at `cdc3d9d`.

Relevant lines in `index.html` (single-file HTML/CSS, inline `<style>`):

| Line | Element | Current value |
|---|---|---|
| 6 | `<title>` | `OIT Tracker — Oral Immunotherapy, Simplified` — leave |
| 10 | `og:title` | `OIT Tracker — Oral Immunotherapy, Simplified` — leave |
| 87–92 | `.hero-icon` CSS | 64×64, 1.5rem `margin-bottom` — leave |
| 93–96 | `.hero h1` CSS | 3.25rem, weight 700, white, `margin-bottom: 1.25rem` — leave (re-used by new H1) |
| 266, 289, 311, 319 | responsive `.hero h1` | 2.5 / 2 / 1.75 / 1.5rem at 960 / 768 / 640 / 390 breakpoints — leave |
| 332 | Nav wordmark `<span>OIT Tracker</span>` | leave |
| 344–358 | Hero copy block | **modify** (see below) |
| 364 | Phone-mockup `alt` | mentions "OIT Made Simple" — leave (describes the literal screenshot) |

Previews (`previews/a-screenshot-swap.html:278`, `b-hero-mockup.html:301`, `c-full-polish.html:332`) also contain `<h1>OIT Simplified</h1>`, but these are *frozen reference snapshots* from the variant review — Variant C was promoted to `index.html` in commit `1bb5fd1`. **Previews stay untouched.** Rationale: they document the evaluation that happened, not the current live design. Modifying them would rewrite history.

## Recommended approach

Exactly one file changes: `~/Documents/Repos/oittracker.com/index.html`. Two edits: markup swap in the hero, one new CSS rule.

### Edit 1 — markup, lines 346–347

Current (line 346–347):

```html
<img class="hero-icon" src="assets/images/icon.png" alt="" width="64" height="64">
<h1>OIT Simplified</h1>
```

New:

```html
<img class="hero-icon" src="assets/images/icon.png" alt="" width="64" height="64">
<p class="hero-eyebrow">OIT Simplified.</p>
<h1>OIT Tracker</h1>
```

Notes:
- `<p>` (not `<h2>`) for the eyebrow — it is decorative brand copy, not a content heading. The document outline stays clean: one `<h1>` per page, `<h2>` reserved for section headings ("Everything in one place", "Get notified when we launch").
- `.subtitle` on line 348–350 and everything else in the hero are unchanged.
- Because `.hero-icon` already has `margin-bottom: 1.5rem`, the icon still sits above the eyebrow with proper spacing.

### Edit 2 — CSS, insert after line 96 (after the `.hero h1` rule)

```css
.hero-eyebrow {
  font-size: 0.8125rem;
  font-weight: 600;
  color: var(--teal);
  letter-spacing: 0.12em;
  text-transform: uppercase;
  margin-bottom: 0.875rem;
}
```

Rationale for the tokens (all reused from the existing design vocabulary):
- `var(--teal)` + uppercase + letter-spacing matches `.nav-links a` (line ~60), `.badge` (line ~170), and `.trust-meta` (line ~240).
- 0.8125rem aligns with nav links and badge — a clear accent that does not compete with the 3.25rem H1.
- 0.875rem `margin-bottom` sits between the eyebrow and the H1 without introducing a visible gap.

### Responsive — probably nothing, possibly one small addition

No new media-query entries are required: `rem`-based sizing scales with the root. After manually checking each breakpoint in DevTools, *only if* the eyebrow feels oversized at ≤480px (where the H1 drops to 1.75rem), add one line inside the existing `@media (max-width: 480px)` block (near line 311):

```css
.hero-eyebrow { font-size: 0.75rem; margin-bottom: 0.625rem; }
```

Do not add this preemptively — verify visually first. The 1.15fr/1fr grid collapses to a single centered column at ≤768px (line 282–287), so the eyebrow will inherit `text-align: center` automatically.

### Out of scope (close out before stretch)

Explicitly *not* doing in this PR — ship the hero swap, then revisit based on real feedback:
- Previews directory (`previews/*.html`) — archived snapshots, leave alone.
- Harmonizing site tagline ("OIT Simplified.") with the in-app onboarding tagline ("OIT Made Simple") — pre-existing inconsistency, separate copy pass.
- Rewording the showcase `<h2>` ("Everything in one place") or CTA/trust sections.
- Adding a second "OIT Tracker" mention to the subtitle.

## Files to change

| File | Repo | Change |
|---|---|---|
| `index.html` | `acholonu/oittracker.com` (local: `~/Documents/Repos/oittracker.com`) | 1 markup swap (lines 346–347) + 1 new CSS rule after line 96. ~10 lines touched total. |

No changes in this repo (`oit`).

## Subagent strategy

- **Phase 1 (exploration)**: used one `Explore` subagent — justified because the site's location was unknown and required a repo-wide sweep.
- **Phase 2 onwards**: no subagents. Justification: the change is ~10 lines in a single HTML file. Parallel decomposition would cost more context than it saves, and there are no independent work streams. A `code-reviewer` subagent on the final diff is optional but not planned.

## Regression prevention strategy

1. **Visual check across breakpoints** before commit — Chrome DevTools device toolbar at 390, 480, 640, 768, 960, 1024, 1140+:
   - Eyebrow renders without wrapping and does not overlap the hero icon.
   - H1 "OIT Tracker" is visually dominant.
   - Phone-mockup column stays aligned (1.15fr/1fr grid at ≥960, single column ≤768).
   - At ≤768, eyebrow + H1 + subtitle are centered together.
2. **Document outline**: confirm exactly one `<h1>` remains on the page and it reads `OIT Tracker`. Quick check: `Grep '<h1' index.html` should return one hit in the hero.
3. **Social preview**: OG title/description and favicon are untouched — pre-verify with `curl -sI https://oittracker.com` post-deploy shows unchanged `Content-Type`, and [opengraph.xyz](https://www.opengraph.xyz/) still renders the Twitter/iMessage preview correctly.
4. **HTML validity**: optional [validator.w3.org](https://validator.w3.org/) sanity check after deploy — the `<p>` eyebrow does not introduce outline issues.
5. **No test suite exists** for this Jekyll site; regression surface is purely visual. Change is isolated to one hero section, does not touch JS (Kit form, IntersectionObserver) or the `legal-sync.yml` pipeline that syncs from this repo.

## Verification plan (end-to-end)

Run locally from the site repo:

```bash
# From ~/Documents/Repos/oittracker.com
bundle exec jekyll serve   # http://127.0.0.1:4000
```

Then:
1. Open `http://127.0.0.1:4000` in Chrome.
2. Confirm the hero reads, top to bottom: 64×64 icon → small teal uppercase **OIT SIMPLIFIED.** → large white **OIT Tracker** → subtitle → Notify Me + App Store placeholder.
3. Resize through DevTools device-toolbar widths (390, 480, 640, 768, 960, 1024, 1200) and confirm nothing overlaps, wraps awkwardly, or breaks alignment with the phone mockup.
4. View source: `grep -c '<h1' index.html` should return `1`, and `grep 'OIT Tracker' index.html | grep '<h1>'` should match.
5. Commit on `main`, push, wait ~1–2 min for GitHub Pages to redeploy, re-verify at `https://oittracker.com`.

If `bundle exec jekyll serve` isn't wired up locally, opening `index.html` via `file://` in Chrome is sufficient for this change — it's a pure HTML/CSS edit, no Liquid templating in the hero.

## Follow-ups (not blocking)

- **Ticket**: file an issue in `acholonu/oittracker.com` titled "Site hero: lead with 'OIT Tracker', demote 'OIT Simplified.' to eyebrow", link this plan file. Per project convention all plans get comment-linked to their ticket.
- **Copy harmonization pass** (future): decide whether the in-app onboarding's "OIT Made Simple" and the site's "OIT Simplified." should converge.
- **Previews review**: once the new hero is live and validated, decide whether to delete the archived variant previews entirely or freshen them to match — separate call.
