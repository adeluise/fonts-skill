# fonts-skill

An opinionated Claude Code skill for picking and setting up typefaces. Surfaces a curated font list, asks about your project context with interactive prompts, and handles the full setup — imports, CSS custom properties, framework config.

## Install

Clone directly into your Claude Code skills directory:

```sh
mkdir -p ~/.claude/skills
git clone https://github.com/adeluise/fonts-skill.git ~/.claude/skills/fonts
```

Or, if you already have it cloned elsewhere, symlink it:

```sh
mkdir -p ~/.claude/skills
ln -s /path/to/fonts-skill ~/.claude/skills/fonts
```

## Usage

Invoke the skill directly:

```
/fonts
```

You'll get prompts to select:

1. **Project type** — marketing site, SaaS app, editorial/blog, portfolio
2. **Vibe** — clean/minimal, bold/expressive, editorial/serious, friendly/warm
3. **Role** — full pairing, headings only, body only

Pick from the chips or choose "Other" to type your own answer.

The skill filters down to 2–4 font recommendations presented as selectable options. Once you pick, it detects your stack and sets everything up automatically — no confirmation step.

You can also trigger it naturally in conversation:

```
I need a font pairing for a marketing landing page
```

## What's in the list

10 hand-picked typefaces:

| Font | Classification | Source | Tags |
|------|---------------|--------|------|
| Newsreader | Serif | Google Fonts | heading, body |
| Nyght Serif | Serif | Uncut | heading |
| Zodiak | Serif | Fontshare | heading, body |
| Prociono | Serif | Google Fonts | heading |
| Satoshi | Sans | Fontshare | heading, body |
| Geist | Sans | Google Fonts | heading, body |
| Bricolage Grotesque | Sans | Google Fonts | heading |
| Epilogue | Sans | Google Fonts | heading |
| Uncut Sans | Sans | Uncut | body |
| Apfel Grotezk | Sans | Collletttivo | heading |

## Customizing

Edit `fonts.md` to add, remove, or reorder fonts. The skill reads this file every time it's invoked — no restart needed. Follow the existing table format and tag fonts with `heading`, `body`, or both.
