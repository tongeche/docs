---
title: "VDC Surveyor Handover"
description: "Routing map and link targets for the surveyor platform engineer"
---

Last updated: 25 March 2026 13:24 WET

# VDC Surveyor Handover

This document maps the docs site hosted at `https://docs.tisabs.com` and the
routes the VDC surveyor platform should use when linking to it.

Use this as the source of truth when wiring links from the surveyor app or any
related service.

## Routing rules

- Use full URLs when linking from outside the docs site.
- Use relative paths only inside the docs site itself.
- Keep the route slugs stable where possible.
- If a page moves, update this handover first and then update the app links.
- For policy-sensitive flows, link to the broad policy page rather than a
  narrow subsection unless the narrower page is the intended destination.

## Core route map

| Area | Route | Full URL | When to use |
| --- | --- | --- | --- |
| Landing page | `/` | `https://docs.tisabs.com/` | Main entry point for users |
| First experience | `/quickstart` | `https://docs.tisabs.com/quickstart` | Task-based onboarding |
| Product overview | `/product/overview` | `https://docs.tisabs.com/product/overview` | High-level user experience map |
| Reports | `/product/reports` | `https://docs.tisabs.com/product/reports` | Reporting a concern |
| Incidents | `/product/incidents` | `https://docs.tisabs.com/product/incidents` | Viewing incident information |
| Vehicles | `/product/vehicles` | `https://docs.tisabs.com/product/vehicles` | Vehicle lookup and profile context |
| Feedback | `/product/feedback` | `https://docs.tisabs.com/product/feedback` | Ride feedback and service comments |
| Search | `/product/search` | `https://docs.tisabs.com/product/search` | Transport context search |
| Network | `/product/network` | `https://docs.tisabs.com/product/network` | Corridors, routes, and coverage |
| Surveyor | `/product/surveyor` | `https://docs.tisabs.com/product/surveyor` | Surveyor workflows and participant access |
| Learning | `/product/learning` | `https://docs.tisabs.com/product/learning` | Learning and readiness content |

## Legal links

| Area | Route | Full URL | When to use |
| --- | --- | --- | --- |
| Legal center | `/legal/index` | `https://docs.tisabs.com/legal/index` | Main legal landing page |
| Privacy policy | `/legal/privacy` | `https://docs.tisabs.com/legal/privacy` | Personal data and privacy questions |
| Content posting policy | `/legal/content-posting-policy` | `https://docs.tisabs.com/legal/content-posting-policy` | Reports, feedback, notes, ratings, and uploads |
| Child safety policy | `/legal/child-safety-protection` | `https://docs.tisabs.com/legal/child-safety-protection` | Minor-related or child-safety concerns |
| Reporting policy | `/legal/reporting-policy` | `https://docs.tisabs.com/legal/reporting-policy` | Incident and service report rules |
| Surveyor participation agreement | `/legal/surveyor-participation-agreement` | `https://docs.tisabs.com/legal/surveyor-participation-agreement` | Surveyor program access and expectations |
| Terms of service | `/legal/terms-of-service` | `https://docs.tisabs.com/legal/terms-of-service` | General service terms |
| Data processing | `/legal/data-processing` | `https://docs.tisabs.com/legal/data-processing` | Data handling and processing details |

## Technical links

| Area | Route | Full URL | When to use |
| --- | --- | --- | --- |
| API introduction | `/api-reference/introduction` | `https://docs.tisabs.com/api-reference/introduction` | Technical overview |
| Live interfaces | `/api-reference/live-interfaces` | `https://docs.tisabs.com/api-reference/live-interfaces` | Current implemented interfaces |
| Public app routes | `/api-reference/public-app-routes` | `https://docs.tisabs.com/api-reference/public-app-routes` | Public route inventory |
| Restricted operations routes | `/api-reference/restricted-operations-routes` | `https://docs.tisabs.com/api-reference/restricted-operations-routes` | Restricted and admin paths |
| Learning and auth | `/api-reference/learning-and-auth` | `https://docs.tisabs.com/api-reference/learning-and-auth` | Auth handover and learning flows |
| API domain map | `/api-reference/domain-map` | `https://docs.tisabs.com/api-reference/domain-map` | Cross-service domain mapping |
| Future public API draft | `/api-reference/future-public-api` | `https://docs.tisabs.com/api-reference/future-public-api` | Planned external contract shape |

## Repository links

| Area | Route | Full URL | When to use |
| --- | --- | --- | --- |
| Repositories hub | `/repositories` | `https://docs.tisabs.com/repositories` | Public service map |
| TIBS | `/repositories/tibs` | `https://docs.tisabs.com/repositories/tibs` | Main rider service |
| Survey operations | `/repositories/tibs-survey` | `https://docs.tisabs.com/repositories/tibs-survey` | Survey and operations service |
| Learning center | `/repositories/tibs-learning-center` | `https://docs.tisabs.com/repositories/tibs-learning-center` | Learning service |
| Shared sign-in | `/repositories/shared-auth` | `https://docs.tisabs.com/repositories/shared-auth` | Shared auth handover |

## Recommended app links

Use these labels when you want the surveyor app to point users into the docs:

- `Introducing TIBS` -> `https://docs.tisabs.com/`
- `Your First Experience` -> `https://docs.tisabs.com/quickstart`
- `Report a concern` -> `https://docs.tisabs.com/product/reports`
- `View privacy policy` -> `https://docs.tisabs.com/legal/privacy`
- `Read the posting rules` -> `https://docs.tisabs.com/legal/content-posting-policy`
- `Child safety policy` -> `https://docs.tisabs.com/legal/child-safety-protection`
- `Surveyor participation agreement` -> `https://docs.tisabs.com/legal/surveyor-participation-agreement`
- `Technical reference` -> `https://docs.tisabs.com/api-reference/introduction`

## Notes for future changes

- The old privacy route slug was replaced by `/legal/privacy`.
- If a page title changes, the route may stay the same, so prefer route-based
  linking over title-based linking.
- If the surveyor app needs a new link target, add it here first so the mapping
  stays in one place.
