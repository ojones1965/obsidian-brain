# Obsidian Jarvis Rules

This repository is an Obsidian knowledge vault. Markdown files in this vault are the human-readable, durable source of truth.

## Core behavior

- Before answering questions about prior decisions, technical setups, projects, people, preferences, research, or work already documented here, search the vault first.
- Read the smallest useful set of relevant notes before drawing conclusions.
- In responses based on vault content, cite relevant relative note paths.
- Separate documented facts from inference, recommendations, and open questions.
- If the vault does not contain the answer, say so plainly. Do not invent a decision, date, source, measurement, configuration, task status, or completion claim.
- Preserve existing folder layout, filenames, frontmatter conventions, tags, writing style, and internal link conventions.
- Use Obsidian wikilinks such as `[[Project Name]]` only for existing notes or notes explicitly intended to be created.

## Vault layout

```text
_config/              vault rules, guidelines, agent instructions
_archive/             inactive material, closed projects, old decisions
Inbox/Drafts/         default AI write location; watch for refiling
Daily/                daily notes
Projects/             active projects
Reference/            reference material
People/               contacts and relationships
Areas/                ongoing areas of responsibility
Decisions/            decision records and ADRs
Templates/            note templates
SimpleBrain/raw/      machine-generated research drafts (see below)
```

## Low-trust source: `SimpleBrain/raw/`

- Notes in `SimpleBrain/raw/` are unreviewed research drafts produced by a local LLM (their frontmatter says `source: ... unreviewed draft`, and some are marked `truncated: true`).
- Treat them as background research, never as the user's decisions, preferences, or confirmed facts.
- When citing them, label them as unreviewed machine drafts. Flag truncation when present.
- Do not edit, move, or delete files there; an external pipeline may manage that folder.

## Access boundaries

- Read permitted Markdown notes as needed for a user request.
- Treat paths with names such as `Private`, `Personal`, `Confidential`, `Credentials`, `Secrets`, `Financial`, `Medical`, or `Legal` as out of scope unless the user explicitly names the file or folder and asks to use it.
- Never place passwords, tokens, API keys, private keys, credentials, sensitive personal data, or secrets into the vault.

## Write policy

- Default write location: `Inbox/Drafts/`.
- Create a new draft there when the user asks for a note, summary, capture, plan, decision record, project brief, weekly review, or organization output, unless they name a different destination.
- Do not overwrite, rename, move, delete, archive, merge, or substantially revise an existing note without explicit user approval.
- Do not make bulk edits, mass-link notes, modify dashboards, update indexes, or reorganize folders without an explicit plan and approval.
- When in doubt, generate a dry run or create a separate draft rather than changing canonical material.

## Draft metadata

For a new AI-created draft, begin with:

```yaml
---
created: YYYY-MM-DD
updated: YYYY-MM-DD
source: claude-code-jarvis
status: draft
tags: [ai-draft]
---
```

Use the actual current date in ISO format. Keep any user-required existing frontmatter keys as well.

Filename convention: `YYYY-MM-DD - Descriptive Title.md`. Starting structure: `Templates/AI Draft.md`.

## Draft composition

- Use clear, searchable titles and filenames.
- Capture original source links, file paths, dates, commands, measurements, assumptions, and constraints when available.
- For technical notes, distinguish observed state, proposed configuration, implementation steps, validation, risks, and rollback plan when relevant.
- For decision records, include context, options considered, decision, rationale, consequences, and open questions.
- For project notes, include current status, decisions, next actions, blockers, and related notes.
- Avoid duplicate notes. Before creating a draft, search for materially overlapping existing notes.

## Retrieval workflow

1. Identify likely relevant folders, filenames, tags, headings, and wikilinks.
2. Search exact terms first, then aliases, abbreviations, component names, and related concepts.
3. Prefer decision records, current project notes, primary technical notes, and newer dated records over secondary summaries.
4. When sources conflict, describe the conflict and prioritize an explicitly recorded decision or a newer authoritative source.
5. List the relative paths consulted in the final response under a `Vault evidence` heading.

## Weekly review

- Read daily notes in the requested range and relevant active project notes.
- Write the review as a draft in `Inbox/Drafts/`.
- Report completed work only where documented. Never mark tasks complete based on inference.

## Completion protocol

After creating a draft, report:

1. The exact relative path created.
2. A concise summary of the material written.
3. Related existing notes that may warrant linking, review, or a future update.
4. Any uncertainty, assumptions, or source gaps.
5. A request for explicit approval before promoting, moving, or merging the draft into a canonical location.
