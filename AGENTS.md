# Processor documentation instructions

## About this project

- This is the public documentation site for Processor, built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Product source lives in the sibling `../rss-processor` repository
- Screenshots and `schema.graphql` are generated in the application repository and copied here

## Terminology

- Use **Processor** as the product name.
- Use **RSS processor** only for the feed-processing subsystem.
- Use **FreshRSS**, **Ollama**, **Qdrant**, **GraphQL**, **WebSub**, and **Atom** with their official capitalization.

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise — one idea per sentence
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Start UI pages with one frame containing theme-aware light and dark screenshots; use `block dark:hidden` for light and `hidden dark:block` for dark
- Describe prerequisites, permissions, primary workflows, failure states, and operational notes

## Content boundaries

- Document current behavior verified against source, tests, schema, and environment examples.
- Do not publish historical plans, code reviews, or migration-status notes.
- Do not expose credentials, feed signing tokens, WebSub secrets, or private callback data.
- Keep the GraphQL schema generated; edit source SDL in the application repository instead.
