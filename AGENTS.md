# AGENTS.md

Maintainer notes for Awesome-Personal-Agents. The site is a [yaal](yaal/) contents/ instance, same pattern as [Awesome-Vibe-Coding](https://github.com/0xWelt/Awesome-Vibe-Coding).

## Positioning

This list records named personal agents that can act on a person's digital life, and the tool stack around them: harnesses, life surfaces, extensions, memory, routines, identity and permissions, runtimes, and supporting tools.

## Inclusion rule

Include a product only if it is a named personal agent that can act on a person's behalf over time: its own computer or persistent runtime, connectors or apps, background work, and approval for sensitive actions.

Do not list a general chat product as an entry, even if it has tools, connectors, computer use, or a Cowork or Work mode:

- ChatGPT, the assistant, is not an entry. The personal agent is Dots.
- Claude, and Claude Cowork, are not entries. The personal agent is Claude Duet, a separate app.
- Gemini, the assistant, is not an entry. Google's earlier named agent, Gemini Spark, was renamed Task and now sits in the Gemini app as a chat/task toggle. Do not add a file titled Gemini, and do not add Task unless Google again ships it as a distinct personal-agent product under its own name.
- Microsoft Copilot and Microsoft 365 Copilot are not entries unless a distinctly named personal-agent product in this class exists. Do not invent one.
- An agentic browser, such as Perplexity Comet, is not this class.

Chat-only companions, enterprise contact-center bots, and a dump of the whole MCP ecosystem are also out of scope.

## Boundary with Awesome-Vibe-Coding

[Awesome-Vibe-Coding](https://github.com/0xWelt/Awesome-Vibe-Coding) is the AI coding stack: coding harnesses, gh/Vercel-class coding platforms, and coding-oriented MCP servers and skills. Leave those there. Claude Code, Gemini CLI, and GitHub Copilot stay in AVC.

Personal-agent products belong here: Grok Bot, Dots, Claude Duet, Muse, and similar named agents. Do not re-list the MCP protocol or the Agent Skills standard as entries; mention them in prose when a product uses them. A dual-use life surface (mail, calendar) can be added later with a life-oriented description. Do not copy AVC entries into this repo.

## contents/ conventions

- One markdown file per tool under `contents/<category>/` or `contents/<category>/<subcategory>/`.
- Every folder has `_meta.md` with YAML `title:` and a short English description in the body.
- Tool frontmatter is `name` and `link`. Optional `tags` are short labels. Do not add a `command` field.
- Links are official and canonical. Strip UTM, referral, and affiliate parameters.
- English throughout. Keep entries factual. Do not invent features, plan limits, or URLs.
- If a product spans categories, pick one primary home — how people launch that product — and mention other modes in the body. Dots stays Dots even when people open it inside ChatGPT. Claude Duet is its own app, not an entry under Claude. Do not put a general chat assistant in `contents/harnesses/chat-products-with-tools/`.
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
