---
name: inalp-artifacts
description: Rules for making claude.ai Artifacts for İnalp Akademi (and the Sungur İnşaat projects designed in the same language) - social posts and Instagram carousels, specs and briefs handed to another developer or their AI, and any shareable page. Use whenever someone asks for an artifact, a carousel, a post, a spec, a brief or a shareable page in or about the İnalp repo.
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
- **Read the repo's design before inventing one** when the repo is at hand:
  `app/globals.css` (tokens) and `app/[locale]/layout.tsx` (fonts).
- When the premium design skills are installed (`design-taste-frontend`, `impeccable`), load
  them for visual work such as posts and carousels.
- **Do not commit, push or start the dev server** for an artifact unless asked. An artifact is
  not a code change.

## 2. Visual language

Match the İnalp site so a post or page reads as the same brand.

| Role | Value |
| --- | --- |
| Headings | DM Serif Display. One phrase per heading set in *italic* as the emphasis. |
| Body | Inter (with `latin-ext`, for Turkish characters). |
| Hand-written accent | Caveat 700, sparingly: one note or label, never body copy. |
| Background (default) | `oklch(0.97 0.012 95)` |
| Cream / paper / sky | `oklch(0.96 0.02 88)` / `oklch(0.94 0.03 78)` / `oklch(0.93 0.035 260)` |
| Ink (dark sections) | `oklch(0.15 0.045 263)` |
| Text | `oklch(0.18 0.04 260)`, muted `oklch(0.42 0.03 260)` |
| Primary (navy) | `oklch(0.4 0.12 260)` |
| Accents | honey `oklch(0.78 0.13 75)`, sky `oklch(0.82 0.1 250)`, yellow `oklch(0.82 0.15 88)` |
| Hairlines | `oklch(0.82 0.025 88)`, 1px rules instead of boxes and heavy shadows |

- Thin rules, generous space, editorial layout. No gradient blobs, no glassmorphism, no emoji
  as decoration.
- A brand colour may be pulled from the client's own photo (for example warm façade lights as
  the honey accent) when it sits with the palette above.
- Check that a logo reads on the background it is placed on; use a light version on ink.

## 3. Language

- **Copy the audience reads** (posts, captions, slides, client-facing pages): Turkish, with
  correct characters (ç, ğ, ı, İ, ö, ş, ü).
- **Specs and briefs for developers or their AI**: English. Keep Turkish product terms and the
  exact Turkish strings the site sends (form labels, dropdown values) as they are.
- Code comments are always English.

## 4. Social posts and Instagram carousels

- Instagram carousel slides are **1080×1350 (4:5)**. Name the size when you hand it over.
- The page gives a **"ZIP indir"** button for all slides and a **PNG** button per slide.
  Render slides at their real pixel size, not a scaled screenshot.
- Put a **ready-to-copy caption** under the slides: the text, a map or contact link when one
  was given, and hashtags.
- Usual flow: cover (photo + logo + name) → intro → one slide per fact group (unit types,
  features) → closing slide with contact. Keep each slide to one idea.

## 5. Specs and briefs for another developer

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

## 6. Hand-over and sharing

- After publishing, give the link and a short summary in the user's language: what is on the
  page, the sizes, the buttons.
- **"Anyone with the link" may be blocked** by the account or workspace policy, and the agent
  cannot change sharing settings. When the reader is outside the account, also export the
  content to a file they can send: Markdown under `docs/` for specs (best format to feed an
  AI), or PDF/.docx if asked. Say which copy is the source of truth, and re-export when the
  artifact changes so they do not drift.
- Delete an artifact only when the user asks; deletion breaks the link for everyone and cannot
  be undone.
