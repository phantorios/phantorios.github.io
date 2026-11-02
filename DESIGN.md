# DESIGN.md

Direction for `phantorios.github.io`.

This file is the brief the page is built against. antislop is a filter: it removes
slop, it does not supply direction. Without this file the page is a draft, not a
deliverable. Every decision below has a reason (R-31).

## Design Read

Reading this as an engineer's professional record for hiring managers and senior
technical leads, in a well-set technical document style, dial ENERGY 2 / RHYTHM 3 / MOTION 1.

## Dials

| Dial | Value | Why |
| --- | --- | --- |
| ENERGY | 2 (balanced) | The audience is enterprise and platform teams in the Netherlands and EU, reading to decide on an interview. Agency-grade spectacle would misfire, but a GOV.UK-flat page would erase the person. |
| RHYTHM | 3 (asymmetric) | The content genuinely has three shapes: one flagship case study, a few short project entries, a chronological career spine, and a flat specification table. Forcing all four into one card grid would flatten real hierarchy (R-14, R-05). |
| MOTION | 2 (one entrance, then hover and focus only) | A recruiter scans and leaves in under a minute, so nothing may delay reading: no scroll reveals, no staging. One entrance on the headline is worth it because the name is the page's focal point and the reveal states that. Everything after it is hover and focus only. |

## Identity motif

The run record: a continuous vertical rule down the left of the page, with each
section hung off it at a tick, numbered in the order it is read. It comes from the
work itself (build pipelines, deployment history, workload identity) and it is
executed as typography and spacing rather than a fake terminal window, which R-06
forbids as costume.

The motif repeats three times and no more: the section tick, the career spine, and
the trust chain in the flagship project.

## Typography

| Role | Typeface | Why |
| --- | --- | --- |
| Display | Archivo, weight 800, tight tracking | Grotesque with industrial proportions. Not the model default roster (Inter, Geist, Space Grotesk). Reads as signage, which suits an engineer's name as the page's largest element. |
| Body | IBM Plex Sans | Humanist with slightly technical details, stays legible at 15 to 17px, and pairs by design with Plex Mono. |
| Metadata | IBM Plex Mono, 12 to 13px | Restricted to real metadata only: stage numbers, dates, stack names, counts. Never used as decoration on headings. |

Monospace is a tool here, not an aesthetic. If a string is not real metadata, it is
not in mono.

## Colour

Three complete palettes, not one light and one dark. The page carries no photography,
so the ground itself has to do the work that images would otherwise do: the paper is
tinted, not white, and the dark scheme is a cold ground with warm text rather than
terminal black (R-29: two or three core values plus one accent, per palette).

| Token | Paper | Slate | Ink | Use |
| --- | --- | --- | --- | --- |
| paper | `#F4EEE2` | `#E9EEF1` | `#0C1113` | Page ground. Ecru, porcelain, cold ink. |
| ink | `#1A1611` | `#0E1A22` | `#EDE6D9` | Body and display text. |
| muted | `#5C5245` | `#4A5C68` | `#99A3A6` | Secondary text and metadata. |
| rule | `#DCD2BF` | `#CBD7DE` | `#232C30` | Hairlines and field borders. |
| wash | `#EDE4D3` | `#DFE7EC` | `#121A1D` | Margin band, inputs, status label. A tint of the ground, not a new hue. |
| accent | `#A83E12` | `#0B5C8A` | `#FF8C5A` | One accent per palette: primary action, current role, focus ring, link hover. |
| on-accent | `#FFFFFF` | `#FFFFFF` | `#0C1113` | Label colour on an accent fill. Changes with the palette so the pair stays legible. |

Measured contrast, all passing WCAG AA at 4.5:1 for body text:

| Pair | Paper | Slate | Ink |
| --- | --- | --- | --- |
| body text on ground | 15.58 | 15.10 | 15.31 |
| muted text on ground | 6.61 | 5.94 | 7.37 |
| accent text on ground | 5.40 | 6.17 | 8.28 |
| accent on wash | 4.95 | 5.76 | 7.68 |
| label on accent fill | 6.24 | 7.21 | 8.28 |

The accent is one hue per palette and it does not appear on headings, icons, list
markers, borders, or decorative dots. The tinted margin band is what carries colour
across the page; the accent stays a signal.

## Motion

MOTION 2 allows exactly one entrance. The headline is revealed by a horizontal clip
wipe and the three blocks under it rise in sequence, 100ms apart, so the eye is led
from the name to the lede to the actions in the order they should be read. It runs
once, for 0.92s, and never repeats, loops, or reacts to scroll.

The purpose is hierarchy, not decoration: the name is the page's focal point and the
wipe says so. `prefers-reduced-motion` removes the animation and the clip entirely,
so the content is identical without it.

What this direction still refuses: scroll-triggered reveals, parallax, hover lift,
floating, pulse, and any animation on a second element of the same kind.

## Voice

Plain declarative sentences. Real numbers only, with provenance the reader can
check. No marketing adjectives. Where a claim exists, the artefact that proves it
is one click away. Sentences end rather than trail off (R-02: no em dashes).

## What this direction refuses

Deliberately excluded, with the rule that excludes each:

- Eyebrow badge above the H1 restating the headline (ui skill, R-09)
- Decorative status dots and pulsing markers (ui skill, R-19)
- Emoji as icons (R-04)
- Arrows on every button (R-08)
- Language proficiency percentage bars, which invent data (R-17)
- Pill-shaped chips for technology names (R-11, R-09); technology is set as text
- Shadows on every card (R-12); hairline rules carry elevation instead
- Glassmorphism on the navigation (R-10)
- Uppercase tracked-out labels as section furniture (R-06)

## Decisions log

| Decision | Reason |
| --- | --- |
| Name is the H1, not a tagline | The page's subject is a person. A tagline as H1 makes the largest type say nothing checkable. |
| Flagship project gets full width, the second gets one column | They are not equals: one has an architecture and documented decisions, the other is a playable prototype. Equal cards would misrepresent that (R-14). |
| Career presented as a dated spine | Dates and employers are the strongest verifiable evidence on the page. A spine shows them at a glance. |
| Contact form validates before opening the mail client | R-27: a control that shows no error and no success state is unfinished. |
| No résumé preview image | Honest placeholder avoided; the PDF is the artefact, linked directly. |
| Three palettes instead of one light/dark pair | With no photography on the page, the ground has to carry the identity. A near-white or pure black page left nothing to look at, so there are three moods of the same document: ecru paper, porcelain slate, cold ink. |
| Headline wipes in once | The single entrance MOTION 2 allows. It names the focal point and the staggered rise sets reading order. Removed entirely, including the clip, under reduced motion. |
