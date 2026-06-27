# API Security Controls Matrix

An interactive reference document mapping the [NCSC's seven HTTP API security pillars](https://www.ncsc.gov.uk/collection/securing-http-based-apis) against UK Government Security Classification Policy (GSCP) 2023 tiers — from PUBLIC through to TOP SECRET.

Deployed at **[api.govassure.uk](https://api.govassure.uk)**.

## What's in it

- **Seven NCSC pillars** — secure development, authentication & authorisation, data in transit, input validation, DoS mitigation, logging & monitoring, limiting exposure
- **Five GSCP tiers** — PUBLIC, OFFICIAL, OFFICIAL-SENSITIVE, SECRET, TOP SECRET
- **Cumulative controls** — each tier inherits all controls from the tier below
- **BFF / Facade overlay** — additional controls for Backend-for-Frontend and aggregation layer architectures
- **By Classification view** — all controls applicable at a chosen tier across all seven pillars at once
- **Escalation matrix** — quick-reference summary across six key control dimensions

## Sources

| Source | Version |
|--------|---------|
| NCSC Securing HTTP-based APIs | April 2025 |
| Government Security Classifications Policy (GSCP) | 2023 |
| NCSC Cyber Assessment Framework (CAF) | 4.0 |
| Good Practice Guide 13 (GPG 13) — Protective Monitoring | Current |
| Cyber Essentials / Cyber Essentials Plus | Current |
| OWASP API Security Top 10 | Current |

## Tech

Single-file static HTML — no build step, no dependencies to install.

- [GOV.UK Frontend](https://frontend.design-system.service.gov.uk/) 5.4.1 (loaded from CDN)
- Vanilla JavaScript for interactivity
- All content and logic in `index.html`

## Deployment

Hosted on [Vercel](https://vercel.com) as a static site. `vercel.json` configures security headers and routing.

To deploy your own instance:

1. Fork this repo
2. Import it into Vercel
3. Add your custom domain in Vercel project settings
4. Point your domain's DNS CNAME to `cname.vercel-dns.com`

## Updating content

All controls, assurance statements, and metadata live in the `PILLARS`, `ESCALATION`, `TIER_META`, and `SOURCES` constants near the top of the `<script>` block in `index.html`. No framework knowledge required — edit the data objects and commit.

## Licence

Content available under the [Open Government Licence v3.0](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/).
