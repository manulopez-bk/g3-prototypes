# G3 Design Kit — Juguetería (v1)

Handoff package from Claude Code → Claude Design for the Grupo +3 toy store site.

**Live prototype (works in Venezuela):** https://manulopez-bk.github.io/g3-prototypes/
**Visual asset catalog:** open `catalog.html` (or https://manulopez-bk.github.io/g3-prototypes/kit/)

## The vision

Minimal Apple base + **mid-century atomic-age retro-futurism** ("Fantastic Four" retro).
Ringed planets, finned rockets, happy atoms, Calder mobiles, starbursts. Fluid vector,
**never pixelated**. Fun for kids, calm for parents: a few choreographed show-stopper
moments on a quiet cream ground.

**Division of labor:** Claude Design owns static composition + motion storyboards
("the rocket launches here, it should feel bouncy"). Motion itself is code —
SVG + CSS springs + SMIL orbits — owned by Claude Code. No video, no image-model
output in the shipped site.

## Working palette (MCM)

| Token | Hex | Role |
|---|---|---|
| paper | `#F7F0E1` | warm cream ground |
| ink | `#2B2320` | warm near-black text |
| orange | `#E2622B` | primary accent (burnt) |
| teal | `#1F7A72` | secondary |
| mustard | `#E8A33D` | rings, highlights |
| coral | `#E98C6B` | soft accent |
| navy | `#16233F` | night/space band |

**Corporate brand palette** (from the report suite): blue `#3A497D`, orange `#FF8C15`,
white `#FFFDFD`. The all-blue mark (blue disc, white glyph) is approved on cream.
⚠️ Open decision: corporate orange (bright) vs MCM burnt orange — harmonize at the real drop.

## Type

Display & labels: **Futura** (fallback Century Gothic) — caps kickers at +0.24em tracking.
Body: **Avenir Next**. Wordmark lockup: two lines, letter-justified to equal width:
`G R U P O` / `+ T R E S` (see prototype header).

## Motion system (spec for storyboards)

- Spring curve: `cubic-bezier(.34,1.56,.64,1)` — everything bounces like a wind-up toy
- `float` 5.5s ease-in-out (planets), `sway` 4.5s (mobile), `bob` 3.2s (car), `tw` 3.4s twinkle (stars)
- Orbits: SMIL `animateMotion` along ellipse paths (hero rocket 14s, electrons 6/8.5/11s)
- Interactions: squash-stretch `boing` + starburst confetti on tap; cards lift with spring on hover
- Scroll: one-shot reveals (opacity+26px rise); rocket launch on section entry
- `prefers-reduced-motion`: all motion off, content fully visible

## Illustration quality bar ("the planet standard")

Every drawing ships with: base fill + darker shadow tone + lighter highlight arc +
detail dots + soft ground shadow ellipse. **No bare lines-and-circles primitives.**

## Contents

- `assets/` — 12 approved static SVGs (celestial set, age icons, product spots, all-blue G3 mark)
- `assets/planeta-heroe-animado.svg` + `assets/atomo-cohete-animado.svg` — the two hero
  scenes with their animation EMBEDDED in the file (CSS keyframes + SMIL orbits). They play
  in any browser and even as `<img>` embeds — no JavaScript. The tap-to-boing interaction
  is site behavior, not in the asset.
- `alternativas-0-3/` — 3 candidate replacements for the 0–3 mobile (reads a bit
  Christmas-ornament): pull-along duck, shape blocks, rattle. Pick or remix.
- `tokens.css` — palette, type, motion tokens as CSS custom properties + keyframes
- `catalog.html` — visual index of everything (self-contained)
