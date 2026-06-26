# P2 — Every dead `#` link on tobilobaadeyemo.com and what to do with it

Rule of thumb: a link to `#` is worse than no link — it breaks trust on a trust-selling
site. For each item: wire it to a real destination or **remove the link** until the
destination exists. All edits in Elementor.

## Hero / primary CTAs
| Element | Currently | Do this |
|---|---|---|
| `AUDIT MY TRUST GAPS` button | `#` | Point to the WhatsApp booking link (`https://wa.me/27630672211?text=...`) or a real intake form (Tally/Google Form takes 15 min to make). Until then, remove the button. |
| `DOWNLOAD PROOF PORTFOLIO` button | `#` | Only keep if a real portfolio PDF exists — upload it to Media Library and link the file. No PDF → remove the button (a dead "proof" button is the worst offender on the page). |

## Career section — five "Read More" links
Financial / Creative / Operational / Supply Chain / Digital Systems cards all link to `#`.

- No detail pages exist yet → **remove the "Read More" links** (keep the cards).
- Long-term: each card becomes a short case study page; that's also where real
  employment dates go (must reconcile with LinkedIn to the month).
- Note: the "Financial" card currently reframes the Skye Bank teller role as
  "Control & Compliance Engineering" — per the P0 decisions, restate it honestly when
  touching this section.

## Footer
| Link | Do this |
|---|---|
| `About` | Point to `/about/` (created in `about-page-copy.md`). |
| `Case Study` | Remove until at least one case study exists. |
| `Services` | Anchor-link to the pricing section (`/#services` or the section's CSS ID). |
| `Tech Nation` | Unclear what this is — remove unless it has a real destination. |
| 5 social icons | Wire to the canonical profiles: LinkedIn, GitHub, Credly (+ X/Instagram only if actively maintained). Delete unused icons. |
| `Privacy Policy` | Compliance basic — generate a policy (WP plugins: Complianz / WP AutoTerms), publish at `/privacy-policy/`, link it. |
| `Terms` | Same — publish at `/terms/`, link it. You sell priced services; terms are not optional. |

## Verify
Crawl the site after edits (free: https://www.drlinkcheck.com or Screaming Frog) — target
is zero links whose href is `#` and zero 404s.
