# FPESLL — 75 Seasons Strong campaign site

## What this repo is

One static page, `index.html`, destined for **give.fpesll.com**. It's the
fundraising microsite for the Fox Point–East Side Little League 75th-anniversary
capital campaign. No build step, no package manager: all CSS and JS are inline
in the single file, and Google Fonts is the only external dependency.

## The organization

- Fox Point–East Side Little League (FPESLL), Providence, RI. Founded 1952, so
  2027 is the 75th season. Registered 501(c)(3).
- Roughly 300 players a season across 15+ teams.
- Home field is Gano Field, in view of the Crook Point Bascule Bridge — the
  tilted steel lattice silhouette in the hero and in the diamond illustration is
  that bridge. It's a real local landmark and an intentional motif, not clip art.
- Campaign contact: Kat Dey, sponsor@fpesll.com.

## The campaign

- Called **75 Seasons Strong**. Goal is **$75,000**, closing around Opening Day 2027 (tentatively May 1).
- Funds three capital projects: batting cages ("Project Home Run," replacing
  cages destroyed in the 2026 winter storms, est. $24–38K), a dedicated bullpen
  ($5–12K), and scoreboards, AV and spectator upgrades ($5–15K).
- Sponsorship tiers map onto the bases: Single (any amount), Double ($1,000+),
  Triple ($2,500+), Home Run ($7,500+), Grand Slam ($20,000+). The benefit copy
  comes from the league's official one-pager — don't invent or embellish
  benefits; ask for the current one-pager if they need to change.

## Page structure

Notice bar → sticky nav → hero → stat strip → The Plan (3 cards) → interactive
diamond → progress → give → footer.

## The interactive diamond (the centerpiece — handle with care)

- Hand-authored inline SVG, `viewBox="0 0 800 660"`, composed as the view from
  behind home plate: home plate largest in the foreground, second base smallest
  at the back, bases drawn as foreshortened diamonds with drop shadows to sell
  the depth.
- Five `.hotspot` groups — first, second, third, pitcher's mound, home plate —
  map to the five tiers via `data-tier`. Hover, click, and Enter/Space all route
  through `select()`; the chip row under the detail panel calls the same thing.
- Tier names, prices, and benefit lists live in the `tiers` object in the inline
  script. Edit copy there, not in the markup.
- The gold fox silhouette near home plate is a deliberate placeholder for a
  wished-for animated mascot that runs the bases as tiers light up.

## Design decisions — these are intentional, don't "fix" them unless specifically directted to as part of a claude.md update.

- **Single-theme dark by design.** There is no light/dark switching; tokens are
  defined once on `:root`. This was a deliberate brand choice.
- Palette: dark navy grounds (`#0A1830`, `#0E2140`, `#132A4D`), `#81DCE8` as the
  prominent accent (buttons, links, active states, progress bar), `#E3B85A` gold
  as the secondary accent (eyebrow labels, stat figures).
- **FPESLL branding does not use green.** The greens inside the SVG are literal
  grass in an illustration, not brand color — don't propagate them into UI.
- Type: Anton (display, uppercase), Public Sans (body), Chivo Mono (figures).

## Known TODOs

1. The goal still reads **$50,000** in the hero, in The Plan copy, and in the
   progress card. It should be **$75,000**.
2. Progress figures ($14,750 raised, 29.5% bar) are placeholder sample data,
   labeled as such on the page.
3. The four channel targets in the progress section ($25K / $15K / $5K / $5K)
   were scoped to the old $50,000 goal and need rescoping.
4. The "Donate Online" button is deliberately disabled pending the giving
   platform (Zeffy) setup. 
5. The "Design mockup — not yet live" notice bar at the top must come off before
   launch.

## Constraints a new contributor won't guess

- Little League policy requires U.S. league **websites** to run on Sports
  Connect, and www.fpesll.com does. This page is a separate fundraising
  microsite at give.fpesll.com (Bluehost WordPress Choice Plus, Bluehost
  nameservers) — deliberately additive, not a replacement for the league site.
- Little League trademark rules: anything selling merchandise bearing LL marks
  needs approval from Little League International. Campaign branding leans on
  "Fox Point" and "75 Seasons Strong" rather than the Little League wordmark.
- A separate FPESLL design system is in progress (primary logo, Cooper Black
  headers, a commissioned fox character sheet). If it lands, reconcile this
  page's type and color to the design system rather than the reverse.

## Origin

Built conversationally in Claude and published as an artifact:
https://claude.ai/artifact/HYN1YedTRuK9c1jbpHpsYV

That artifact is still the published copy of this page. Once this repo is the
source of truth, make changes here first and treat the artifact as downstream.
