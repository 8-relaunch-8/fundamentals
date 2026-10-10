# Conventions

The rules that keep the knowledge base consistent. Short on purpose.

## Languages

- **English** for structure and documentation: folder names, file names, front matter keys, READMEs at the root and in `practices/`, `cheatsheets/`, `errors/`, `tools/`, `journal/`.
- **French** for the knowledge itself: the content of concept, error, practice and cheatsheet pages, domain introductions and glossaries. Every concept also gives its English term.

## Where things go

| I want to write down… | It goes in… |
|---|---|
| a term seen in passing, to handle later | `INBOX.md` |
| a concept (a word, an idea) | `knowledge/<domain>/<concept>.md` |
| an error and its fix | `errors/` |
| a way of working, a checklist | `practices/` |
| commands, shortcuts | `cheatsheets/` |
| my day, my doubts, a project's status | `journal/` (private) |
| an idea for the knowledge base itself | `IDEAS.md` |

## One concept, one page

- File names are in English, lowercase, with hyphens: `single-source-of-truth.md`.
- A page is never renamed or moved, because that breaks every link pointing to it.
- A concept with subtopics can get its own subfolder inside its domain, created only when needed.

## Links

- Use standard relative Markdown links: `[Compiler](../programming-languages/compiler.md)`. They work in Zed, Obsidian and on GitHub.
- No `[[…]]` wikilinks: GitHub cannot render them.
- Links between pages are the backbone of the knowledge base: every page should link to at least one related page in « Voir aussi », including pages in other domains.

## Front matter

| Key | Content |
|---|---|
| `title` | the concept's name in French |
| `english` | the English term, always |
| `domain` | the domain folder name |
| `status` | `draft`, `reviewed` or `verified` (see below) |
| `tags` | cross-domain themes, in English: `[performance, memory]` |
| `encountered` | where I came across it: `[Pixiety J16, CS50 week 2]` |
| `verified_with` | the reference source used for verification, with the date |
| `created`, `updated` | dates in YYYY-MM-DD format |

A page never stores its domain group (theoretical foundations, application areas…): the group is derived from the domain, as listed in the README.

## Statuses: human in the loop

- **draft**: the page is written (often by Claude) but not reviewed yet.
- **reviewed**: I have read it, I understand it, it looks correct to me.
- **verified**: it has been checked against a reference source, cited in `verified_with` and in « Sources ».

A page can be downgraded if a mistake is found in it. That is normal: it shows the knowledge base is alive.

## Writing

- The « En bref » line is a single sentence, with no undefined jargon: it feeds the glossary.
- Code examples are in JavaScript, TypeScript or Rust, whichever suits the topic best.
- No analogies by default: only when they genuinely help.
- Never copy a source: rephrase it in your own words, and cite it.

## Generated sections

Glossaries are produced by `tools/generate.mjs`. Everything between `glossary:start` and `glossary:end` is rewritten each time the script runs: do not edit it by hand.
