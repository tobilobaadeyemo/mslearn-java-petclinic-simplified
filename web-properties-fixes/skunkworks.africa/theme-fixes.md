# skunkworks.africa — Shopify theme fixes

All of these are editable in Shopify admin → Online Store → Themes → **Edit code** (or
pull the theme locally with `shopify theme pull` and I can apply them directly in a
future session if the theme is added to a repo I can access).

## P1 — Remove Google AdSense from the storefront [CODE]
The storefront outputs:

```html
<meta name="google-adsense-account" content="ca-pub-9270041066336676">
```

Running third-party ads on your own commerce store cheapens it and competes with your own
checkout.

1. In **Edit code**, open `layout/theme.liquid` and search for `adsense` and `ca-pub-9270041066336676`.
2. Delete the meta tag and any accompanying `<script>` loading `adsbygoogle.js`.
3. Also check Shopify admin → Online Store → Preferences → "Google Analytics / additional
   scripts", and any installed AdSense/ads app under Apps — the snippet may be injected
   from there rather than the theme.

## P1 — "Authorized Reseller Partners" logos are blank placeholder SVGs [CODE/DASH]
The partner row renders gradient-placeholder SVGs instead of logos.

1. In the theme customizer, find the logo-list/brands section on the homepage and upload
   the real logos: Microsoft, Adobe, Sage, Google, CompTIA.
2. **CompTIA first** — you are a CompTIA Delivery Partner (public, verifiable); that's
   real credibility currently hidden behind a blank placeholder.
3. ⚠️ [DECISION] "Authorized Reseller" is a legally meaningful claim. Before publishing
   each logo, confirm the authorization is current and that the partner's brand
   guidelines permit logo display. Where you can't confirm, soften the heading (e.g.
   "Technologies we work with") instead of claiming authorization.

## P2 — Placeholder "Title" headings in the contact block [CODE]
The "Not ready to decide?" section shows the literal default text `Title` where headings
should be.

1. Theme customizer → locate the contact/multicolumn section near the footer.
2. Each column's "Heading" field is empty/default. Set real headings, e.g.
   "Email us" / "Call us" / "Visit us" (match whatever the columns actually contain).

## P2 — Typo [CODE]
Search the theme/sections for the string:

```
Let is know!
```

Replace with:

```
Let us know!
```

It's most likely in a section's customizer text field rather than a `.liquid` file —
check the same contact block first.

## [DASH] — Dashboard-only items (not theme code)
- **Payments:** PayPal is the only visible method. Add a SA card gateway (Yoco, Payfast,
  or Peach) and/or EFT in Settings → Payments. Single-method checkout is a conversion leak.
- **Markets/currency:** the region selector lists ~30 countries all forced to ZAR. In
  Settings → Markets, either enable per-market currency or restrict to the regions you
  actually serve (recommended: South Africa + the markets you genuinely fulfil).
