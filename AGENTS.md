# AGENTS.md

Maintainer notes for Awesome-Personal-Agents. The site is a [yaal](yaal/) contents/ instance, same pattern as [Awesome-Vibe-Coding](https://github.com/0xWelt/Awesome-Vibe-Coding).

## Positioning

This list records personal agents that can act on a person's digital life, and the tool stack around them: harnesses, life surfaces, extensions, memory, routines, identity and permissions, runtimes, and supporting tools.

In scope: products that take external actions for a person's life or affairs — connectors, skills, a browser, a computer, or a phone. Chat-only companions, enterprise contact-center bots, and a dump of the whole MCP ecosystem are out of scope.

## Boundary with Awesome-Vibe-Coding

[Awesome-Vibe-Coding](https://github.com/0xWelt/Awesome-Vibe-Coding) is the AI coding stack: coding harnesses, gh/Vercel-class coding platforms, and coding-oriented MCP servers and skills. Leave those there.

Personal harnesses belong here: Grok Bot, ChatGPT with connectors and computer use, Claude Cowork and computer use, and similar products. Do not list Claude Code, GitHub Copilot, Gemini CLI, or other coding harnesses. Do not re-list the MCP protocol or the Agent Skills standard as entries; mention them in prose when a product uses them. A dual-use life surface (mail, calendar) can be added later with a life-oriented description. Do not copy AVC entries into this repo.

## contents/ conventions

- One markdown file per tool under `contents/<category>/` or `contents/<category>/<subcategory>/`.
- Every folder has `_meta.md` with YAML `title:` and a short English description in the body.
- Tool frontmatter is `name` and `link`. Optional `tags` are short labels. Do not add a `command` field.
- Links are official and canonical. Strip UTM, referral, and affiliate parameters.
- English throughout. Keep entries factual. Do not invent features, plan limits, or URLs.
- If a product spans categories, pick one primary home — usually how most people launch it — and mention other modes in the body.
- Harness entries use the same labels so they stay comparable: **Runtime**, **Acts on**, **Extensions**, **Notes**.
- Do not add this repo as a submodule of the Awesome meta repo, and do not edit yaal's own README, from a contents PR.

## Commits

Use [Conventional Commits](https://www.conventionalcommits.org/): `type(scope): description`. A Chinese description is fine; English is fine.

## Toolchain

This repo consumes the `yaal` submodule (Vite+). From `yaal/`:

- `vp install` — install dependencies
- `vp run dev` — development server
- `vp run build` — production build (`yaal/out`)
- `vp run parse-readme` — regenerate site data from `contents/`
- `vp check` — format, lint, and type-check

GitHub Pages is deployed by `.github/workflows/smart-deploy.yml` when `README.md`, `contents/`, `yaal.config.yaml`, the `yaal` submodule, or the workflows change on `main`. Renovate updates the nested `yaal` submodule (`renovate.json`).
