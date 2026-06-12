# Web Properties Fix Kit — Tobiloba Adeyemo

Generated 2026-06-12 from the audit fix spec and revamp plan. This kit contains every
**[CODE]**-tagged fix as a ready-to-apply artifact, plus checklists for everything that
can only be done in a platform dashboard ([DASH]) or needs a human decision ([DECISION]).

> **Why these are files and not applied changes:** this session only has write access to
> this one GitHub repository. The WordPress theme (tobilobaadeyemo.com) and the other
> GitHub repos (`tobilobaadeyemo/tobilobaadeyemo`, `ZenDay-AI-Guard`,
> `cri-assessment-tool`) are not reachable from here. Everything below is prepared so
> each fix is a copy-paste or a 2-minute dashboard task.
>
> **Scope note:** everything skunkworks-related is excluded from this kit by request.

## Contents

| Path | What it is | Where it goes |
|---|---|---|
| `tobilobaadeyemo.com/booking-links-fix.md` | Broken WhatsApp booking-link fix (P0) | WP admin / Elementor |
| `tobilobaadeyemo.com/seo-meta-fix.md` | Email leak removal + real meta descriptions (P0/P2) | WP SEO plugin |
| `tobilobaadeyemo.com/person-schema.jsonld` | JSON-LD Person schema (entity plan Phase 1) | WP header inject |
| `tobilobaadeyemo.com/about-page-copy.md` | Canonical bios (50/100/250 words) for About/#person page | WP page |
| `tobilobaadeyemo.com/dead-links-fix.md` | Every `#` link and what to wire it to (P2) | Elementor |
| `github/profile-README.md` | Profile README, ready to publish | new repo `tobilobaadeyemo/tobilobaadeyemo` |
| `github/zenday-ai-guard/README.md` | README scaffold (TODOs marked) | `ZenDay-AI-Guard` repo |
| `github/zenday-ai-guard/LICENSE` | MIT license, ready as-is | `ZenDay-AI-Guard` repo |
| `github/repo-hygiene.md` | Unpin forks, cri-assessment-tool, org cleanup | GitHub UI |
| `identity/canonical-identity.md` | The locked identity block + cert list template + LinkedIn checklist | everywhere |

## Execution order (matches the spec's priority)

**P0 — do first, ~30 minutes total:**
1. Fix the three broken booking links (`tobilobaadeyemo.com/booking-links-fix.md`). Every priced service currently has no working checkout.
2. Remove the Gmail address from the `twitter:data1` meta tag (`seo-meta-fix.md`).
3. Standardize the phone number everywhere — **verify the correct number first** (header and booking links currently differ by one digit).

**P0 — decisions (no code until these are made):**
- One title everywhere. The revamp plan locks this: **Cloud Security Engineer** (see `identity/canonical-identity.md`).
- Collapse the overlapping LinkedIn roles, restate the Skye Bank role, split certs into Earned vs In-Progress.

**P1 — trust signals:**
- Replace placeholder testimonials and demo client logos (WP admin) — or delete the sections.
- Fix or remove the broken newsletter form.

**P2 — polish:** dead links, footer, SEO meta, GitHub hygiene.

**Phase 1 entity work (after P0 convergence only):** inject `person-schema.jsonld`, publish the About page, standardize Credly URL, LinkedIn ID verification, `tobiloba@tobilobaadeyemo.com` mailbox.

> **Gate from the red-team review (non-negotiable):** do not do the entity/authority work
> (schema, press, Wikidata) until the P0 deletions are done. Adding authority on top of the
> current contradictions makes them more visible and more permanent, not less.
