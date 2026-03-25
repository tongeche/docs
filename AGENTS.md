# Documentation project instructions

## About this project

- This is a documentation site built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Configuration lives in `docs.json`
- Run `mint dev` to preview locally
- Run `mint broken-links` to check links
- The site is intended to cover product docs, API docs, legal docs, and
  repository-derived docs for TIBS

## Terminology

- Use `TIBS` for the product or platform
- Use `Tisab` for the company when the company is the legal actor
- Use `documentation site` or `docs site`, not `starter kit`
- Use `legal documents` for approved policy or contractual pages
- Use `draft legal page` for placeholders that still need review

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise; one idea per sentence is preferred
- Use sentence case for headings
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- Prefer repo-derived facts over assumptions
- Keep internal working notes out of public-facing docs unless they are clearly
  marked as reference material

## Content boundaries

- Do not keep Mintlify starter examples in published navigation
- Do not invent legal obligations, privacy claims, compliance status, or
  retention periods
- Do not treat a placeholder page as final legal text
- Restricted admin functionality can be documented, but must be labeled
  internal or restricted when applicable
