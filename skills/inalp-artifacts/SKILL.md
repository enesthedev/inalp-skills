---
name: inalp-artifacts
description: Rules and brand kit for making claude.ai Artifacts for İnalp Akademi (and the Sungur İnşaat projects designed in the same language) - social posts and Instagram carousels, specs and briefs handed to another developer or their AI, and any shareable page. Ships the logo, tutor photos, university crests and site content. Use whenever someone asks for an artifact, a carousel, a post, a spec, a brief or a shareable page for İnalp, or needs İnalp's logo, tutors or brand assets.
---

# İnalp artifacts

How to build and hand over an Artifact for İnalp. The platform's own artifact rules
(quickstart, `artifact-design`, theming, size limits) still apply; this skill adds the
project's taste, language and hand-over habits on top.

## 1. Before building

- **Use only facts you were given.** Square metres, room counts, features, prices, dates,
  endpoints: take them from the brief, the pasted chat or the repo. Never fill a gap with a
  plausible number; ask, or leave the slot out.
- **Use the supplied photos and logo.** Draw everything else yourself in HTML/CSS, SVG or
  canvas. No AI-generated imagery.
- **Start from the kit** (section 3) for the logo, tutors, crests, contact details and brand
  tokens. When the İnalp repo itself is at hand and newer, its `app/globals.css` and `data/`
  win.
- When the premium design skills are installed (`design-taste-frontend`, `impeccable`), load
  them for visual work such as posts and carousels.
- **Do not commit, push or start the dev server** for an artifact unless asked. An artifact is
  not a code change.

## 2. Visual language

Match the İnalp site so a post or page reads as the same brand. Full tokens, font link and
logo rules: `references/brand.md`.

- DM Serif Display headings with one *italic* phrase each, Inter body, Caveat 700 for at most
  one hand-written note.
- Light grounds (`oklch(0.97 0.012 95)`, cream, paper, sky), navy primary
  `oklch(0.4 0.12 260)`, ink `oklch(0.15 0.045 263)` for dark sections, honey/sky/yellow accents.
- Thin rules, generous space, editorial layout. No gradient blobs, no glassmorphism, no emoji
  as decoration.
- A brand colour may be pulled from the client's own photo (for example warm façade lights as
  the honey accent) when it sits with the palette above.

## 3. Kit

Everything below ships with this skill; paths are relative to the skill folder. Start with
`references/kit-index.md`: contact details, every tutor (name, city, university, rank, photo
path) and every crest in one table.

| Need | Where |
| --- | --- |
| Logo | `assets/brand/wordmark.html` (icon + wordmark, three grounds), `inalp-ikon.png`, `og-logo.png`, `favicon.svg` |
| Tutor photos | `assets/tutors/<city>/<slug>.jpg`, portrait, 1400px long edge |
| University crests | `assets/universities/*.png` |
| Contact, Instagram | `references/data/settings.json` |
| Tutors, testimonials, programs, FAQ, roles, cities | `references/data/*.json` |
| Brand tokens and logo rules | `references/brand.md` |

- **Put files into the artifact**: upload them as the artifact's own assets, or inline small
  ones as data URIs. Never hotlink GitHub raw URLs.
- **Keep facts attached to their person.** A tutor photo goes only with that tutor's own name,
  university, city and rank from `tutors.json`. Testimonials are quoted verbatim with the name
  exactly as given ("Z. Köroğlu"). Never invent a tutor, a rank, a quote or a price.
- **Prices and packages** come from `programs.json`; check its notes before quoting a number.
- Read only the files the task needs; the JSONs can be long.

## 4. Language

- **Copy the audience reads** (posts, captions, slides, client-facing pages): Turkish, with
  correct characters (ç, ğ, ı, İ, ö, ş, ü).
- **Specs and briefs for developers or their AI**: English. Keep Turkish product terms and the
  exact Turkish strings the site sends (form labels, dropdown values) as they are.
- Code comments are always English.

## 5. Social posts and Instagram carousels

- Instagram carousel slides are **1080×1350 (4:5)**. Name the size when you hand it over.
- The page gives a **"ZIP indir"** button for all slides and a **PNG** button per slide.
  Render slides at their real pixel size, not a scaled screenshot.
- Put a **ready-to-copy caption** under the slides: the text, a map or contact link when one
  was given, and hashtags.
- Usual flow: cover (photo + logo + name) → intro → one slide per fact group (unit types,
  features) → closing slide with contact. Keep each slide to one idea.

## 6. Specs and briefs for another developer

Typical case: forms live in this site, the endpoints live in another app, and the reader has
**no access to this source code**.

- Write it **as a product person**: what each form or endpoint is for, who meets it and where,
  and what has to be true before it goes live.
- Make it **the whole contract on its own**: every field, its type, whether it is required,
  and the **exact strings** behind every dropdown or radio.
- Open with a status table (endpoint, form, where the visitor meets it, status) and a date.
  Update the status when things go live instead of rewriting the document.
- Say what already works and use it as the model for the rest ("same auth, same transport,
  same failure behaviour, different fields").

## 7. Hand-over and sharing

- After publishing, give the link and a short summary in the user's language: what is on the
  page, the sizes, the buttons.
- **"Anyone with the link" may be blocked** by the account or workspace policy, and the agent
  cannot change sharing settings. When the reader is outside the account, also export the
  content to a file they can send: Markdown under `docs/` for specs (best format to feed an
  AI), or PDF/.docx if asked. Say which copy is the source of truth, and re-export when the
  artifact changes so they do not drift.
- Delete an artifact only when the user asks; deletion breaks the link for everyone and cannot
  be undone.
