# Contribute to the documentation

This repository is the shared documentation site for TIBS and Tisab. Use it to
publish stable product docs, API docs, repository-derived reference material,
and legal pages.

## Local workflow

1. Install the Mintlify CLI: `npm i -g mint`
2. Run the site locally from the repo root: `mint dev`
3. Preview changes at `http://localhost:3000`
4. Validate links before pushing: `mint broken-links`

## What to document here

- Product workflows that should be understandable without reading code
- API boundaries, contracts, and integration notes
- Cross-repo concepts that deserve one canonical explanation
- Approved legal documents and clearly marked legal drafts

## What not to document here

- Leftover Mintlify starter examples
- Speculative technical behavior not verified from source repos
- Final legal claims that have not been reviewed and approved
- Internal-only notes presented as public guidance

## Writing rules

- Use active voice and second person
- Keep sentences concise
- Prefer repo-derived facts over assumptions
- Keep one canonical page per topic and link to it
- Mark draft legal content clearly
