# İnalp brand reference

Taken from the site's `app/globals.css` and `app/[locale]/layout.tsx`.

## Fonts (Google Fonts, always with `latin-ext` for Turkish)

| Role | Font |
| --- | --- |
| Headings | DM Serif Display 400, normal + italic. One phrase per heading in *italic* as the emphasis. |
| Body | Inter |
| Hand-written accent | Caveat 700, sparingly: one note or label, never body copy. |

    <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@700&family=DM+Serif+Display:ital@0;1&family=Inter:wght@400;500;600;700&display=swap&subset=latin-ext" rel="stylesheet">

## Colours

| Token | Value | Use |
| --- | --- | --- |
| `--background` | `oklch(0.97 0.012 95)` | default page ground |
| `--background-cream` | `oklch(0.96 0.02 88)` | warm section ground |
| `--background-paper` | `oklch(0.94 0.03 78)` | paper section ground |
| `--background-sky` | `oklch(0.93 0.035 260)` | cool section ground |
| `--background-ink` | `oklch(0.15 0.045 263)` | dark (night) sections |
| `--foreground` | `oklch(0.18 0.04 260)` | text |
| `--muted-foreground` | `oklch(0.42 0.03 260)` | secondary text |
| `--primary` | `oklch(0.4 0.12 260)` | navy, buttons and brand blue |
| `--primary-foreground` | `oklch(0.98 0 0)` | text on primary |
| `--accent` | `oklch(0.82 0.15 88)` | yellow accent |
| `--accent-honey` | `oklch(0.78 0.13 75)` | warm accent |
| `--accent-sky` | `oklch(0.82 0.1 250)` | cool accent |
| `--hairline` | `oklch(0.82 0.025 88)` | 1px rules |
| `--radius` | `0.875rem` | corner radius |

## Layout

- Thin rules, generous space, editorial layout. No gradient blobs, no glassmorphism, no emoji
  as decoration.
- A colour may be pulled from a supplied photo when it sits with the palette above.

## Logo

- Use `assets/brand/wordmark.html`: icon + "İnalp" (Inter bold) with "Akademi" (Caveat bold)
  overlapping its descender.
- The stroke on "Akademi" must be the colour of the ground it sits on. Pick the variant by
  ground: `dark` on the light page ground, `light` on primary blue, `ink` on the night ground.
- On ink, the icon tile gets a faint hairline ring so its blue does not merge with the ground.
- The icon alone (`inalp-ikon.png`) works for avatars and small marks; `og-logo.png` is the
  mark on its tile for square covers.
- Never recolour, stretch or redraw the icon.
