# P0 — Fix the three broken "Book now" links

## The bug
All three priced services (R2,800 / R3,200 / R3,500) link to:

```
https://tobilobaadeyemo.com/wa.me/+2763067221
```

This is a WhatsApp link pasted as a *relative* URL, so it resolves onto your own domain
and lands on a 404. It is also **one digit short** of the header phone number and includes
a `+`, which `wa.me` does not accept.

## ⚠️ Verify the number first
- Header shows: `+27630672211` (11 digits after +27… i.e. `27630672211`)
- Booking links show: `+2763067221` (one digit short)

Confirm which is your real WhatsApp number before applying. The fix below assumes the
**header** number is correct.

## The fix
In Elementor, edit each of the three "Book now" buttons and replace the Link URL with:

```
https://wa.me/27630672211
```

Rules for `wa.me` links: international format, digits only — **no `+`, no spaces, no leading zeros**.

Optional but recommended — pre-fill the message so you know which service the lead wants:

```
https://wa.me/27630672211?text=Hi%20Tobiloba%2C%20I%27d%20like%20to%20book%20the%20R2%2C800%20audit
https://wa.me/27630672211?text=Hi%20Tobiloba%2C%20I%27d%20like%20to%20book%20the%20R3%2C200%20service
https://wa.me/27630672211?text=Hi%20Tobiloba%2C%20I%27d%20like%20to%20book%20the%20R3%2C500%20service
```

(Adjust the service names in the `text=` parameter to match the actual card titles.)

## How to verify
1. Open each pricing card on the live site.
2. Click "Book now" — it must open WhatsApp (app or web.whatsapp.com) with your chat.
3. Test from a phone too; `wa.me` behaves differently on mobile.

## Also standardize the number everywhere
Once verified, make the phone number byte-identical in: site header, booking links,
footer (if present), LinkedIn contact info, skunkworks.africa contact page, and any
business listings.
