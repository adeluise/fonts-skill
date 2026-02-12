---
name: fonts
description: "Personal font reference and setup helper. Use when discussing typography, choosing fonts for a project, setting up font imports, or when the user is starting a new project and needs to pick typefaces."
---

# Font Selection & Setup

You have access to the user's curated font list in `fonts.md` (in this skill's directory). Read it before responding to any font-related question.

## Rules

0. **Do not explore or scan the project until the user has chosen a font.** Read only `fonts.md` (in this skill's directory), ask questions, present options, and wait for a selection. Only investigate the project's stack/framework when it's time to do the actual setup.
1. **Never auto-select fonts.** Always present relevant options from the list and let the user decide. No exceptions.
2. **Ask about project context first** when invoked directly via `/fonts`. Use `AskUserQuestion` with up to 3 questions in a single call:
   - **Project type** (header: "Project") — options: "marketing site", "SaaS app", "editorial/blog", "portfolio"
   - **Vibe** (header: "Vibe") — options: "clean/minimal", "bold/expressive", "editorial/serious", "friendly/warm"
   - **Role needed** (header: "Role") — options: "full pairing", "headings only", "body only"
   The user can always pick "Other" (auto-included) for free-text input.
3. **Use tags to guide recommendations.** Each font is tagged `heading`, `body`, or both. Match recommendations to the role the user needs filled. If they need a body font, don't suggest heading-only fonts.
5. **Once the user picks a font, just do the setup.** Don't ask for confirmation — detect the project's stack and automatically:
   - Add the correct import method based on the font's source:
     - **Google Fonts**: `<link>` tag, CSS `@import`, or `next/font/google` depending on stack
     - **Fontshare**: CSS `@import` from their CDN, or provide download link for self-hosting
     - **Uncut / Collletttivo**: Provide the download URL and set up `@font-face` declarations for self-hosting
   - Set up CSS custom properties or `font-family` declarations
   - Handle framework specifics (e.g., `next/font` for Next.js, global CSS for Vite, Tailwind config, etc.)
   - For non-Google fonts that require manual download, include the download link prominently

## Presentation

After filtering the font list to what's relevant, present the top 2–4 candidates using `AskUserQuestion`:
- Each option's **label** = font name or pairing name (e.g. "Bricolage Grotesque + Satoshi")
- Each option's **description** = short vibe + source + tags (e.g. "Bold geometric sans · Fontshare · heading + body")
- If presenting pairings, describe both the heading and body font in the description
- Use a single question with header "Font" (or "Pairing" when showing pairs)

Don't dump the entire list. Filter to what's relevant based on the user's stated needs and context.
