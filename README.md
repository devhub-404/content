# DevHub 404 Content

Repository-driven content for the DevHub 404 ecosystem. The application
consumes this repository as the `content` Git submodule; it is not application
code and should be changed in this repository before the application updates
the submodule reference.

## Content collections

| Collection | Purpose |
| --- | --- |
| `cheatsheets/` | Concise references organized by technical topic |
| `codex/` | Structured entries for technologies and concepts |
| `roadmaps/` | Progressive learning paths with outcomes and checkpoints |

There is intentionally no `tools/` collection in this repository. DevHub
Tools are executable product capabilities and will be implemented directly in
the main DevHub application, together with a coherent interface. Tool changes
are not accepted as content contributions here for now.

The consuming application loads these collections as Astro content. The
corresponding schemas and rendering integration live in the application's
`apps/client/src/content.config.ts` and client features.

## File format

Content files are Markdown with YAML frontmatter. All collections use these
common fields:

```yaml
title: "Entry title"
description: "Short description"
category: topic
tags: [tag-one, tag-two]
order: 10
status: published
```

Roadmaps additionally require `level`, `goal`, `prerequisites`, `outcomes`,
and `stages`. Codex entries require `topic`, `base`, `links`, `visualGuide`,
and `metadata`. The exact schemas are authoritative in the application's
`content.config.ts`.

## Writing content

- Write in English, which is the repository standard.
- Keep one subject or learning path per file.
- Prefer precise explanations, practical examples, and links to authoritative
  sources.
- Keep frontmatter valid and consistent with the collection schema.
- Do not add credentials, private data, or unverifiable claims.
- Update an existing entry instead of creating a duplicate.

Content is educational and repository-driven. It is separate from user-authored
Articles, Questions, Answers, Projects, and other content published through
the platform. Tools are also separate: they belong to the application's
implementation and product interface, not to this repository's content
collections.

## Contribution workflow

Changes to Cheatsheets, Codex and Roadmaps are made in this repository and
reviewed here first:

```bash
git switch -c docs/short-description
# edit the Markdown content
git add .
git commit -m "docs(content): update entry"
git push -u origin docs/short-description
```

After the content change is accepted, update the submodule reference in the
application repository:

```bash
cd ../app
git add content
git commit -m "chore(content): update content submodule"
```

The application PR must point to the accepted content commit. Do not edit a
second copy under `app/apps/client/src/content`; the submodule is the source
of truth once the integration is in place.

## Verification

Run the application checks from the app repository:

```bash
cd ../app
pnpm check
pnpm build
```

Astro validates frontmatter and collection schemas during these checks.
