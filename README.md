# Processor documentation

The [Mintlify](https://mintlify.com) site for [Processor](https://github.com/bludesign/processor), a self-hosted RSS processing and semantic-grouping application.

## Structure

| Path | Contents |
| --- | --- |
| `docs.json` | Branding, navigation, GraphQL reference, navbar, and footer |
| `processing/` | Dashboard workflows, feeds, folders, grouping, and statistics |
| `services/` | FreshRSS, Ollama, Qdrant, and WebSub |
| `administration/` | Setup, authentication, users, profile, JWT, and posts |
| `reference/` | Architecture, configuration, APIs, database, hosting, and development |
| `images/light/`, `images/dark/` | Playwright desktop captures, one pair per documented route |
| `schema.graphql` | Generated runtime GraphQL schema |

## Local preview

Install the [Mintlify CLI](https://www.npmjs.com/package/mint) to preview your documentation changes locally. To install, use the following command:

```
npm i -g mint
```

Run the following command at the root of your documentation, where your `docs.json` is located:

```
mint dev
```

Open `http://localhost:3000`.

Run the quality checks before publishing:

```bash
mint validate
mint broken-links --check-anchors
mint a11y
```

If `/opt/homebrew/bin/mint` reports Swift Package Manager usage, call the npm-installed Mintlify binary by its full path. Both tools use the same executable name.

## Publishing generated artifacts

Run these commands from the sibling application repository:

```bash
npm run screenshots
npm run screenshots:copy -- ../processor-docs
npm run schema:copy -- ../processor-docs
```

The screenshot copy publishes only desktop light and dark PNGs. Mobile captures remain in the application repository for responsive verification.

## Writing pages

Every page uses YAML frontmatter with `title` and `description`. UI pages open with one screenshot frame that automatically switches assets with the documentation theme, then explain prerequisites, permissions, controls, workflows, errors, and operational notes. Put both images inside the frame using `className="block dark:hidden"` for the light asset and `className="hidden dark:block"` for the dark asset. Register every page in `docs.json`; unregistered pages remain hidden.

## Publishing changes

The Mintlify GitHub app deploys changes to `https://processor.mintlify.app` from the default branch.

## License

MIT. See [`LICENSE`](LICENSE).
