# Design Audit — Current Site vs. Nordic Template vs. What Your Positioning Needs

**Scope:** Designs only, per request. Engineering/stack critique (Astro vs. WordPress, GSAP/Lenis,
etc.) is deliberately held for the next round — flagged at the end.

**Method & honesty caveat:** This environment's network proxy blocks both
`nordic-template-supply.webflow.io` and `tobilobaadeyemo.com` (403 on the tunnel), so I could not
take fresh screenshots of either. This audit is built from: (a) the concrete design inventory of
your current site in the 2026-06-12 fix spec, and (b) the Nordic design characteristics described in
your own stack write-up plus the template's known genre. Where I'm reasoning from genre rather than a
pixel I've seen, I say so. Re-run this with live screenshots before committing budget.

---

## The headline conclusion (read this first)

**Nordic is a creative-studio/agency template. You are repositioning as a cloud-security engineer.
Those two things want opposite design languages, and copying Nordic wholesale would actively fight the
identity you just spent this whole project converging on.**

- Nordic's job is to make a **creative studio look expensive and expressive** — dark canvas, dramatic
  motion, custom cursor, oversized type, "Move your mouse —" play. It sells *taste and vibe.*
- A cloud-security trust brand sells the opposite signals: **clarity, evidence, restraint, legibility,
  speed, accessibility.** A buyer paying for a security audit is reassured by precision, not by a
  cursor that does tricks.

So the right answer to "what's better where" is **not** "Nordic, all of it." It's: **steal Nordic's
craft-level fundamentals (grid discipline, whitespace, type quality, restrained motion, a real work
grid) and reject its theatrics (heavy custom-cursor gimmicks, motion that delays content, drama-over-
substance dark mode).** Your current site has the opposite problem — it reaches for premium signals
(big claims, ratings, logos) without the craft underneath, and most of those signals are fake
placeholders. The synthesis below is the target.

---

## What's what — three design profiles side by side

| Dimension | Current site (WordPress/Elementor) | Nordic template (per your write-up + genre) | What your positioning actually needs |
|---|---|---|---|
| **Genre** | Generic "consultant/agency" Elementor demo, lightly reskinned | Premium creative studio / motion-forward agency | Credible technical professional — "trust infrastructure," not "vibe" |
| **Integrity of content** | Placeholder testimonials (`avatar-john.png`), demo client logos (`logo-luminous`…), unbacked "4.9/5 from 100+ Reviews" | Template demo content (also placeholder, but *honestly* so — it's a template) | 100% real, verifiable proof or nothing. This is the whole brand. |
| **Layout** | Card-stack sections ("phases": Financial/Creative/Operational/Supply Chain/Digital Systems) | Disciplined editorial grid, generous gutters, work-led | Clean grid, evidence-led, scannable |
| **Color** | Unknown live, but Elementor-default-ish | Dark, minimal, high-contrast accent | Either restrained dark *or* clean light — pick for legibility, not drama |
| **Typography** | Theme default; "Architect" display claims oversell | Crisp large-scale sans display, strong weight contrast | Crisp sans, real hierarchy, **headline claims it can back up** |
| **Motion** | Minimal/none of note; a *broken* newsletter form | Scroll-reveal timelines, staggered fades, counters, custom cursor, hover physics | Restrained, fast, purposeful — motion that reveals content, never gates it |
| **Imagery** | Placeholder avatars/logos | Polished photography / showreel video / abstract | Real headshot (the canonical one), real screenshots, real press logos |
| **Social proof** | Fake (the core sin) | N/A (template) | Real press (Businessday, Guardian NG), real CompTIA partner badge, real certs |
| **Navigation** | Footer links mostly dead (`#`) | Clean sticky/minimal nav, works | Few links, all live, including Privacy/Terms |
| **Mood** | Inflated — "Architect," "decade," 4.9/5 | Confident, expressive, premium | Precise, evidence-first, quietly confident |

---

## What is better WHERE — element by element verdicts

For each, the winner and *why*, plus what to actually do.

**1. Grid & whitespace → Nordic wins, adopt it.**
Nordic's editorial restraint (wide margins, few elements per viewport, strong alignment) is exactly
what reads as "professional and trustworthy." Your current card-stack of five "career phases" is busy
and dilutes focus. *Do:* adopt Nordic-style spacing and a strict grid; cut the five-phase card wall
down to one clear "what I do" statement + a real work grid.

**2. Typography quality → Nordic's approach wins; your *claims* must change.**
Big crisp sans display type is good and transfers directly. But Nordic uses huge type to project
*expressive confidence*; you must use it to state a claim you can defend. A giant "Systems Verification
Architect" is the failure mode — big type magnifies an unsupported title. *Do:* large type, but on the
canonical headline ("Cloud Security Engineer | Identity & Cloud Platform Security"), never on inflation.

**3. Custom cursor / "Move your mouse —" / hover physics → Current site wins by absence; reject Nordic here.**
This is the single clearest "better where" call. For a creative studio, a custom cursor signals craft.
For a security buyer, it's friction and gimmickry that *undercuts* the trust message, hurts
accessibility, and adds JS weight. *Do:* skip it entirely. This is a feature you should be glad to not
copy.

**4. Scroll-reveal / staggered animation → Split decision.**
Subtle fade-up-on-scroll: keep, it's tasteful and cheap. Heavy scroll-driven *timelines* that hold
content hostage until you scroll "just right": reject — they delay the evidence a buyer came for. *Do:*
one restrained reveal pattern, fast (≤300ms), `prefers-reduced-motion` respected, content readable even
with JS off.

**5. Dark, dramatic canvas → Neutral; decide on legibility, not vibe.**
Nordic's dark mode is a mood choice. It can work for security ("ops/terminal" connotation) *if* contrast
and legibility are airtight. It backfires if it's drama covering thin content. *Do:* if dark, hold WCAG
AA contrast everywhere and keep it clean; otherwise a crisp light theme reads more "trustworthy
professional." Either beats the current placeholder-laden look.

**6. Work / case-study grid → Nordic wins hard, but you must fill it with truth.**
Nordic's "Works" grid is the best single thing to borrow — it's how you replace fake testimonials with
real proof. *Do:* build a real case-study grid: the China-Africa press, a ZenDay-AI-Guard write-up, an
anonymized IAM/audit teardown. Empty is fine; fake is not. This directly executes the P0 "replace fake
social proof with real press" item.

**7. Social proof blocks → Current site loses catastrophically; neither template fixes it.**
Your "4.9/5 from 100+ Reviews" + `avatar-john.png` + demo logos is the highest-severity *design* problem
because it's design *and* a credibility lie. No template solves this — only real content does. *Do:*
delete the rating + fake avatars now; replace with real press logos and the CompTIA Delivery Partner
badge. (This overlaps the P0 work already in the kit.)

**8. Navigation & footer → Both should be functional; you currently fail, Nordic passes.**
Dead `#` footer links and missing Privacy/Terms are a trust tax on a trust brand. Nordic-style minimal
working nav is the bar. *Do:* few links, all live, Privacy + Terms published (already in `dead-links-fix.md`).

**9. Forms (newsletter / contact / booking) → Both must work; you currently ship a broken one.**
A newsletter form that errors "Input Invalid" on load is worse than no form. Nordic's contact/modal
patterns are fine to emulate visually. *Do:* fix or remove the form; wire the booking CTAs to the real
`wa.me` link (already in `booking-links-fix.md`).

---

## The core strategic design tension (the real decision)

You're being pulled toward Nordic because it *looks* expensive. But the expensive look it sells is
**"creative studio with taste."** Your converged identity is **"founder-operator turned cloud-security
engineer."** There's a real overlap — the founder/creative origin story is part of your authority — but
the *current service* you're selling (security audits, IAM, trust) is bought on evidence and precision.

Three honest options:

- **A — Full Nordic clone.** Maximum visual wow, fastest "premium" hit. *Risk:* it dresses a security
  professional as a creative agency; a technical buyer may read it as style-over-substance, and it
  amplifies any remaining inflation. Worst fit for the trust positioning.
- **B — Nordic fundamentals, security restraint (recommended).** Borrow grid, whitespace, type quality,
  the work grid, and *subtle* motion. Drop the cursor, the heavy timelines, the drama. Result reads
  "precise, modern, credible" — premium *and* on-message.
- **C — Pure utilitarian/docs aesthetic.** Maximum trust signal, minimum flash. *Risk:* undersells the
  founder/creative half of the hybrid identity; can read as junior.

**Recommendation: B.** It's the only one that satisfies both halves of the locked identity — premium
enough to honor the founder/creative authority, restrained enough to be believed as a security engineer.
It also happens to be the cheapest to maintain and the fastest to load.

---

## Target design direction (the synthesis to build toward)

1. **Light-leaning, high-contrast, lots of whitespace** (or disciplined dark if you test it and contrast
   holds). Legibility over mood.
2. **One crisp sans family**, strong size hierarchy, display type reserved for the canonical headline.
3. **Evidence-first page order:** headline + one-line frame → real proof (press logos, CompTIA badge,
   certs) → what I do (one clear block, not five cards) → real work grid → clear single CTA → working
   contact. Proof *before* pitch.
4. **Motion budget:** one subtle scroll-reveal, fast, reduced-motion-safe. No custom cursor. No timeline
   that gates content.
5. **Zero placeholders.** Every face, logo, number, and quote is real and verifiable, or the section is
   cut. This is the brand, not a detail.
6. **Real headshot, identical everywhere** (also an entity-graph signal from the revamp plan).

This direction is template-agnostic: it can be built in Astro (per your stack) *or* achieved by fixing
the existing WordPress site. That build/stack decision is round two.

---

## What's next (you said designs only — here's the queued round)

When you're ready, round two is the **engineering/stack audit** of your pasted Astro proposal:
- Astro + React islands + Tailwind + GSAP + Lenis + Motion One + Content Layer + Fontsource/Lucide —
  what's right, what's redundant (e.g. Motion One *and* GSAP *and* Framer Motion is three animation libs
  doing overlapping jobs), and what's overkill for a 5-page professional site.
- Astro rebuild **vs.** fixing the current WordPress/Elementor site — cost, SEO/entity continuity (you
  have a `sameAs` spine and schema plan riding on the current domain), and migration risk.
- How the JSON-LD Person schema, canonical bios, and About/#person page (already in this kit) map onto
  whichever stack wins.

Say the word and I'll run that round.
