# Gender Filter Paywall Audit — Random Video Chat Platforms

What 17 random video chat platforms charge for gender filtering, what they
say they charge, and where those two things disagree. Eleven platforms have a
gender filter. **None of them lets a new user switch it on for free.**

Audited 11 August 2026. Prices as displayed, in USD.

## Why this exists

"Gender filter" is one of the highest-intent search terms in this category,
and several platforms describe the feature inconsistently across their own
pages — listed free in a feature grid, restricted to premium in the FAQ two
scrolls down. This dataset records what each platform publishes, what its
purchase screen actually shows, and the gap between them, with a source per
row so the contradictions are checkable rather than asserted.

## Headline findings

- 11 of 17 platforms have a gender filter
- 0 let a new user use it without either paying or first earning credit
- 10 require payment outright
- 1 (Camloo) gates it behind an earnable in-app currency, and sells a shortcut
- Entry prices range from $4.89 to $99.99
- 2 platforms (Monkey, Azar) meter the filter as a counted consumable rather
  than unlocking it

## What this is — and isn't

Evidence quality varies by row and the `verification_method` column records
which is which:

- **`paywall-screenshot` (11 platforms)** — a live upgrade or purchase screen
  was opened and captured. Prices and gating on these rows are what the
  product itself displayed.
- **`public-pages` (6 platforms)** — the row reflects only what the platform
  publishes on its own site, including official help-center documentation.
  Not confirmed in-product.

A user account was created on each platform in order to reach upgrade and
purchase screens, since most do not expose pricing to logged-out visitors. No
purchase was completed and no card details were entered. All captures reflect
a logged-in session from a single geographic region; platforms may show
different offers to anonymous visitors or in other markets.

`steps_to_access_filter` is unresolved on every row — it is a click count and
was not measured in this pass.

Full column definitions, coverage gaps and limitations:
[`METHODOLOGY.md`](./METHODOLOGY.md)

## Data

[`data/gender-filter-audit.csv`](./data/gender-filter-audit.csv) — 17
platforms, 13 columns.

Platforms: Chatspin, Shagle, Chatrandom, Camgo, Flingster, Camsurf, Camloo,
Bazoocam, Joingy, OmeTV, Emerald Chat, CooMeet, LuckyCrush, Monkey, Uhmegle,
Azar, Chatroulette.

## The finding most worth checking

Five platforms — **Chatspin, Shagle, Chatrandom, Camgo and Flingster** —
present upgrade screens that are not merely similar but substantively the same
product. On four of the five, the gender filter slide carries an identical
sentence:

> "Use our gender filter to connect with women, men or couples more quickly
> and easily."

Same three-tier layout, same price points to the cent ($7.99 trial / $19.99
month / $14.99 per month on six months, rebilling at $89.94–$89.99), with one
observed variance: Camgo's trial rebills at $19.99 where its siblings rebill
at $29.99.

This is consistent with a single operator running five brands. Common
ownership is **not** confirmed here — WHOIS, shared analytics IDs, or the
legal entity named in each Terms of Service would settle it, and no such claim
is made in this dataset.

It matters for anyone deriving statistics from this data. A figure of the form
"N of 17 platforms paywall the filter" implies N independent pricing
decisions. Across this group of five, that assumption does not hold.

## Known open questions

- **Chatroulette** — a paid virtual currency ("Quids", $1.99 per 300) is
  confirmed by capture. Whether Quids unlock a gender filter is **not**
  established and is not asserted. Row is marked `partially-resolved`.
- **Camsurf** — recorded as offering no gender filter on the strength of its
  own FAQ. Not confirmed in-product; the absence may be stale documentation.
- **Azar** — filter and gating documented in Azar's own help center, but no
  in-product capture and no published gem prices. Primarily a mobile app; any
  pricing pass should test the iOS/Android build rather than the web property.
- **Monkey** — the tier comparison shows "150" against Filter-Gender with no
  unit stated. Whether that counts filter activations or in-app coins is
  unresolved.

## Disclosure

FlirtyVideoChat maintains a commercial affiliate relationship with CooMeet,
which is included as a subject in this dataset. No platform paid for
inclusion, placement, or favorable treatment, and no platform saw the data
before publication. CooMeet was audited using the same method and the same
evidentiary standard as every other row.

FreeCam Chatter, also operated by FlirtyVideoChat's owner, is deliberately
**excluded** from this dataset. Including a first-party platform in a
comparison presented as independent research — even with a disclosure flag —
would apply a different evidentiary standard to one row than to every
competitor. FreeCam Chatter also operates on a third-party embed rather than
independently built infrastructure, which would have meant double-counting a
service already present in the set under a different name.

## Companion article

Narrative write-up with the full comparison table and the source quotes:
https://flirtyvideochat.com/gender-filter-video-chat-paywall-audit/

## How to cite

> FlirtyVideoChat. (2026). *Gender Filter Paywall Audit — Random Video Chat
> Platforms* [Data set]. https://github.com/flirtyvideochat/gender-filter-audit

```bibtex
@misc{fvc_gender_filter_paywall_audit_2026,
  author = {FlirtyVideoChat},
  title  = {Gender Filter Paywall Audit: Random Video Chat Platforms},
  year   = {2026},
  url    = {https://github.com/flirtyvideochat/gender-filter-audit}
}
```

## License

Data and documentation are licensed under [CC BY 4.0](./LICENSE). Reuse is
permitted; attribution and a link back are required.

## Corrections and updates

This is a snapshot as of the `date_audited` on each row. Platform pricing and
copy change without notice, and several offers were time-limited or
discount-framed at the moment of capture.

Corrections are welcome — open an issue, or email
info@flirtyvideochat.com. Re-audits are tracked in commit history rather than
overwriting silently.
