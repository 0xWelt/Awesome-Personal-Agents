# AGENTS.md

Maintainer notes for Awesome-Personal-Agents. The site is a [yaal](yaal/) contents/ instance, same pattern as [Awesome-Vibe-Coding](https://github.com/0xWelt/Awesome-Vibe-Coding).

## Positioning

This list records named personal agents only. Group them by how they actually run, given the entries that exist today:

- Vendor cloud: named personal-agent products whose persistent runtime is provided by the vendor, including desktop apps and separately named products. File them under `contents/vendor-cloud/`.
- Self-hosted: named personal agents you run yourself on a machine or gateway you control. File them under `contents/self-hosted/`.

Desktop apps and separately named products share vendor-cloud. Grok Bot and Dots are both in that category.

## Inclusion rule

Include a product only if it is a named personal agent that can act on a person's behalf over time. It needs a persistent runtime, connectors or tools, background or unattended work, and some approval or policy control. The runtime can be a computer in the vendor's cloud, or a machine you control plus a gateway or service that stays up.

The list covers both:

- Vendor cloud personal-agent products, such as Grok Bot, Dots, Claude Duet, Muse, and Manus. File those under `contents/vendor-cloud/`.
- Self-hosted, local-computer, always-on agents you run yourself, such as OpenClaw and Hermes Agent. File those under `contents/self-hosted/`. They can run shell or code on that machine; record them here as personal agents, not as coding harnesses.

Do not list a general chat product as an entry, even if it has tools, connectors, computer use, or a Cowork or Work mode:

- ChatGPT, the assistant, is not an entry. The personal agent is Dots.
- Claude, and Claude Cowork, are not entries. The personal agent is Claude Duet, a separate app.
- Gemini, the assistant, is not an entry. Google's earlier named agent, Gemini Spark, was renamed Task and now sits in the Gemini app as a chat/task toggle. Do not add a file titled Gemini, and do not add Task unless Google again ships it as a distinct personal-agent product under its own name.
- Microsoft Copilot and Microsoft 365 Copilot are not entries unless a distinctly named personal-agent product in this class exists. Do not invent one.
- An agentic browser, such as Perplexity Comet, is not this class.

Chat-only companions, enterprise contact-center bots, and a dump of the whole MCP ecosystem are also out of scope.

## Boundary with Awesome-Vibe-Coding

[Awesome-Vibe-Coding](https://github.com/0xWelt/Awesome-Vibe-Coding) is the AI coding stack: coding harnesses, gh/Vercel-class coding platforms, and coding-oriented MCP servers and skills. Leave those there. Claude Code, Gemini CLI, and GitHub Copilot stay in AVC.

Personal-agent products belong here: vendor cloud agents such as Grok Bot, Dots, Claude Duet, and Muse, and self-hosted agents such as OpenClaw and Hermes Agent. Do not re-list the MCP protocol or the Agent Skills standard as entries; mention them in prose when a product uses them. Do not copy AVC entries into this repo. Claude Code, Codex, and Gemini CLI stay in AVC even if a self-hosted personal agent can also run code.

## Life-surface services

Life-surface services do not get folders in this list. If they belong anywhere, they belong in [Awesome-Agent-Services](https://github.com/0xWelt/Awesome-Agent-Services).

## Taxonomy maintenance

Categories must reflect currently listed entries only. Do not reserve empty categories for types that do not exist yet. Whenever you add a new item, re-evaluate whether the current taxonomy still makes sense: if the item does not fit cleanly, create a new category and put it there; if existing categories are unclear, redundant, empty, or broken by the new item, adjust them in the same change and migrate existing entries. Do not keep empty "might need later" categories.

## contents/ conventions

- One markdown file per tool under `contents/<category>/`. The categories that exist today are `contents/vendor-cloud/` and `contents/self-hosted/`.
- Every folder has `_meta.md` with YAML `title:` and a short English description in the body.
- Tool frontmatter is `name` and `link`. Optional `tags` are short labels. Do not add a `command` field.
- Links are official and canonical. Strip UTM, referral, or affiliate parameters.
- English throughout. Keep entries factual. Do not invent features, plan limits, or URLs.
- If a product spans categories, file it by who provides the persistent runtime, and mention other modes in the body. Dots stays Dots even when people open it inside ChatGPT. Claude Duet is its own app, not an entry under Claude. Do not add a general chat assistant as an entry.
- Entries use the same labels so they stay comparable: **Runtime**, **Acts on**, **Extensions**, **Notes**.
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
