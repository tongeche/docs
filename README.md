# TIBS documentation site

This repository contains the Mintlify documentation site for TIBS and Tisab.
It is being reworked from the Mintlify starter into a multi-purpose docs hub
for product documentation, API reference material, repository-derived docs, and
legal pages.

## Current scope

- Product documentation for core TIBS domains
- API and data-surface documentation
- Legal documentation such as privacy and terms
- Shared docs for multiple TIBS repositories

## Repo layout

- `docs.json`: Mintlify configuration
- `index.mdx`: landing page
- `quickstart.mdx`: role-based orientation
- `development.mdx`: contributor workflow
- `product/`: product and workflow pages
- `legal/`: legal document pages
- `api-reference/`: API overview and mapping
- `references/`: raw source material and working notes

## Development

```bash
npm i -g mint
mint dev
```

Preview the site at `http://localhost:3000`.

Validate links before pushing:

```bash
mint broken-links
```

## Content rules

- Remove starter content instead of adapting it blindly.
- Pull technical facts from the real source repositories.
- Do not publish draft legal pages as final legal documents.
- Keep one canonical page per topic and link to it from adjacent sections.
