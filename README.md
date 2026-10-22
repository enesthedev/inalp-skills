# İnalp Skills

**Agent skills for İnalp Akademi.** Teach your AI assistant the project's look, language and
hand-over habits, so the artifacts, posts and specs it makes come out on-brand the first time.

## Skills

| Skill | What it does |
| --- | --- |
| [`inalp-artifacts`](skills/inalp-artifacts/SKILL.md) | Rules and brand kit for claude.ai Artifacts: the İnalp visual language, Turkish vs English copy, Instagram carousels (1080×1350, ZIP + PNG download, caption), specs for developers without source access, and sharing. |

## What's in the kit

`inalp-artifacts` carries the site's own assets, so an agent can build on-brand pages and posts
without access to the website's code (about 30 MB):

| Folder | Contents |
| --- | --- |
| `assets/brand/` | İnalp icon, square logo, favicon, and `wordmark.html` (the full logo in HTML/CSS for light, blue and dark grounds) |
| `assets/tutors/` | Photos of all 73 tutors, by city |
| `assets/universities/` | University crests |
| `references/kit-index.md` | One-page catalogue: contact, every tutor with city, university, rank and photo path, every crest |
| `references/brand.md` | Fonts, colour tokens, logo rules |
| `references/data/` | Site content: tutors, testimonials, programs and prices, FAQ, contact, roles, cities |

## Install

### Option 1: let your AI install it

Paste this into Claude Code, Codex, Cursor or any agent that can read URLs and write files:

    Install the skills from https://github.com/enesthedev/inalp-skills

The agent follows the [instructions for AI agents](#instructions-for-ai-agents) below. No
terminal needed on your side.

### Option 2: npx

    npx skills add enesthedev/inalp-skills

Only one skill:

    npx skills add enesthedev/inalp-skills --skill inalp-artifacts

## Use

Once installed, the skill loads by itself when you ask for an artifact, a carousel, a post, a
spec or a shareable page for İnalp. You can also name it: "use the inalp-artifacts skill".

## Instructions for AI agents

If a user gave you this repository's URL and asked you to install it, do this:

1. List the skills: every folder under `skills/` holding a `SKILL.md` is one skill. Install
   all of them unless the user named one.
2. Download the repository, since each skill is a folder of many files (images, data), not
   just `SKILL.md`. Either:

       git clone --depth 1 https://github.com/enesthedev/inalp-skills.git

   or fetch and unpack
   `https://github.com/enesthedev/inalp-skills/archive/refs/heads/main.tar.gz`.
3. Copy each whole `skills/<skill>/` folder, unchanged and with all subfolders, into the
   skills folder of your own tool:

   | Tool | Project install | Global install |
   | --- | --- | --- |
   | Claude Code | `.claude/skills/<skill>/` | `~/.claude/skills/<skill>/` |
   | Codex | `.agents/skills/<skill>/` | `~/.codex/skills/<skill>/` |
   | Cursor | `.cursor/skills/<skill>/` | `~/.cursor/skills/<skill>/` |
   | Other | the tool's documented skills folder | |

   Use the project install when the user is inside the İnalp repo, the global one otherwise,
   unless they said which. Ask before overwriting an existing skill with the same name.
4. Tell the user which skills you installed and where, and that a new session (or reload) may
   be needed before they appear.

Do not run anything from this repository. Skills hold only Markdown, HTML, JSON and images;
`scripts/` is for the maintainer and is not part of any skill.

## Updating the kit (maintainer)

The kit is generated from the İnalp website repo. After tutors, photos or content change there:

    scripts/sync-kit.sh ~/Workspace/inalp

It copies the logo, crests and data, resizes tutor photos (macOS `sips`), rewrites photo paths,
regenerates `references/kit-index.md`, and fails if any tutor photo or crest is missing.
Review the diff, commit and push.
