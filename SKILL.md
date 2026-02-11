---
name: fonts
description: "Personal font reference and setup helper. Use when discussing typography, choosing fonts for a project, setting up font imports, or when the user is starting a new project and needs to pick typefaces."
---

# Font Selection & Setup

You have access to the user's curated font list in `fonts.md` (in this skill's directory). Read it before responding to any font-related question.

## Rules

1. **Never auto-select fonts.** Always present relevant options from the list and let the user decide. No exceptions.
2. **Ask about project context first** when invoked directly via `/fonts` — what's the vibe? audience? medium (marketing site, app UI, editorial, docs)?
3. **Respect preference ordering.** Fonts are listed in order of how likely the user is to reach for them. Surface higher-ranked fonts first when multiple fit the context.
4. **Use tags to guide recommendations.** Each font is tagged `heading`, `body`, or both. Match recommendations to the role the user needs filled. If they need a body font, don't suggest heading-only fonts.
5. **Once the user picks a font, just do the setup.** Don't ask for confirmation — detect the project's stack and automatically:
   - Add the correct import method based on the font's source:
     - **Google Fonts**: `<link>` tag, CSS `@import`, or `next/font/google` depending on stack
     - **Fontshare**: CSS `@import` from their CDN, or provide download link for self-hosting
     - **Uncut / Collletttivo**: Provide the download URL and set up `@font-face` declarations for self-hosting
   - Set up CSS custom properties or `font-family` declarations
   - Handle framework specifics (e.g., `next/font` for Next.js, global CSS for Vite, Tailwind config, etc.)
   - For non-Google fonts that require manual download, include the download link prominently

## Presentation

When presenting font options, keep it scannable:
- Font name, classification (serif/sans), and a short vibe description
- What it's tagged for (heading, body, or both)
- Source (Google Fonts, Fontshare, Uncut, Collletttivo) — this affects setup complexity

Don't dump the entire list. Filter to what's relevant based on the user's stated needs and context.
