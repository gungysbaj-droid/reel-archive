---
id: "r13"
url: "https://www.instagram.com/reel/DcWQCQdN28T/"
creator: "Peter Griffin AI (@petergriffin.ai)"
title: "Five Claude Code plugins for better-looking websites"
saved: "2026-10-11"
item_ids: [94, 95, 96, 97, 98]
---

# Five Claude Code plugins for better-looking websites

AI-tools creator Peter Griffin AI rounds up "5 Claude Code Plugins That Make Your Websites Look 10x Better" (posted 2026-08-22), pitched at people whose Claude Code sites "still look like generic AI-generated templates", with a comment-DESIGN-for-the-links call to action - the visible comments are readers typing "Design". The five it names are Claude Code skills/plugins: TasteSkill for design taste, Web Design Guidelines for UI audits, AwesomeDesign for a design system, ImageToCode for turning design references into code, and Playwright CLI for opening the built site, screenshotting it and catching broken UI. Each is verified below at its canonical home. Links checked 2026-10-11.

## 94. TasteSkill - anti-slop frontend skills

Kind: website
Collection: claude-code-plugins
Creator: Leonxlnx

Open-source SKILL.md pack billed as "The Anti-Slop Frontend Framework for AI Agents": design-taste skills that steer Claude Code, Cursor and Codex away from boilerplate-looking UI (layout, typography, motion, spacing), plus image-generation skills for reference boards. Installs with `npx skills add`. The reel's first pick; matches its "apply better design taste using premium references" description.

- GitHub: https://github.com/Leonxlnx/taste-skill
- Writeup: https://dev.to/wonderlab/open-source-project-of-the-day-89-taste-skill-give-your-ai-agent-good-design-taste-10l0

## 95. Web Design Guidelines - UI audit checklist (Vercel Labs)

Kind: website
Collection: claude-code-plugins
Creator: Vercel Labs

Vercel Labs' web-interface-guidelines repo: a living, framework-agnostic list of interface decisions (interactions, focus, forms, animation) whose command.md Claude Code skills wrap to audit a UI against modern design principles and catch weak areas before shipping. Matches the reel's "audits your UI" description.

- GitHub: https://github.com/vercel-labs/web-interface-guidelines
- Guidelines: https://vercel.com/design/guidelines

## 96. AwesomeDesign - directory of DESIGN.md files

Kind: website
Collection: claude-code-plugins
Creator: AwesomeDesign

Directory of real public DESIGN.md files for coding agents (74 in the catalog at check time, from Anthropic's Claude to Vercel, Supabase and Linear): colors, typography, spacing and component specs an agent reads as its design system, matching the reel's "complete design system covering colors, typography, spacing, buttons". Sister site getdesign.md generates a private DESIGN.md from your own site.

- Directory: https://awesomedesign.store
- Generate your own: https://getdesign.md

## 97. ImageToCode - design image to frontend code

Kind: website
Collection: claude-code-plugins
Creator: Leonxlnx

The image-to-code skill inside the taste-skill repo: forces an image-first workflow - generate or supply a design reference, analyze its palette, type, spacing and layout, then implement the frontend to match, with rules against cropped boards and card-spam cliches. Matches the reel's "turns design references into usable code". Install: `npx skills add leonxlnx/taste-skill --skill "image-to-code"`.

- Skill folder: https://github.com/Leonxlnx/taste-skill/tree/main/skills/image-to-code-skill

## 98. Playwright CLI - browser screenshots for coding agents

Kind: website
Collection: claude-code-plugins
Creator: Playwright (Microsoft)

Playwright's official CLI for coding agents: token-efficient browser control (open, type, snapshot, screenshot) so Claude can open the site it built, capture screenshots and catch broken UI, matching the reel's fifth pick. The docs include a Claude Code skill install (`playwright-cli install --skills`).

- Docs: https://playwright.dev/docs/getting-started-cli
