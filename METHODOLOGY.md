# Methodology

## How this audit was conducted

Public pages were read as static documents on 2026-08-11. A user account was
then created on each platform in order to reach upgrade and purchase screens,
since most do not expose pricing to logged-out visitors. Prices were captured
from a single geographic region and may differ elsewhere.

## What is verified and what is not

Rows are not equally evidenced, and the `verification_method` column records
which is which on every row.

- **`paywall-screenshot` (11 platforms)** — a live upgrade or purchase screen
  was opened and captured. Prices and feature gating on these rows reflect
  what the product itself displayed.
- **`public-pages` (6 platforms)** — the row reflects only what the platform
  publishes on its own site, including official help-center documentation.
  These claims have not been confirmed in-product.

`steps_to_access_filter` is unresolved on every row. It is a click count from
landing to active filter use and was not measured in this pass.

## Platforms covered (17)

Chatspin, Shagle, Chatrandom, Camgo, Flingster, Camsurf, Camloo, Bazoocam,
Joingy, OmeTV, Emerald Chat, CooMeet, LuckyCrush, Monkey, Uhmegle, Azar,
Chatroulette.

FreeCam Chatter is deliberately not included — see the Disclosure section of
the README.

## Fields

| Column | Description |
|---|---|
| `platform_name` | Platform under audit |
| `gender_filter_offered` | yes / no / unverified / `partially-resolved` — the latter meaning some element is confirmed but the filter link itself is not (see Chatroulette) |
| `filter_type` | self-reported / id-verified / none / unverified |
| `pricing_model` | free / freemium / paywalled / `activity-gated` / unverified — `activity-gated` means the filter is locked behind an in-app currency or activity threshold that can be earned free or purchased (see Camloo) |
| `price_usd_monthly` | Monthly price as displayed, blank if none published or captured |
| `price_usd_one_time` | One-time or package price as displayed, blank if none |
| `steps_to_access_filter` | Click count from landing to active filter use — not measured in this pass; unverified on every row |
| `signup_required` | yes / no / unverified |
| `payment_required_before_preview` | `no` where the filter's existence is visible before payment is requested; yes/unverified otherwise |
| `date_audited` | ISO date (YYYY-MM-DD) |
| `notes` | Verbatim-sourced findings, contradictions and context |
| `source_url` | The page the row's claims were read from |
| `verification_method` | `paywall-screenshot` or `public-pages` |

## Coverage gaps

- **Chatroulette** — a paid virtual currency ("Quids", $1.99 per 300) is
  confirmed by capture. Whether Quids unlock a gender filter is **not**
  established and is not asserted here. Recorded as `partially-resolved`.
- **Azar** — the filter and its gating are documented in Azar's own Help
  Center, but no in-product paywall was captured and Azar publishes no gem
  prices, so no figure is recorded. The web property gates all content behind
  a Yoti selfie-based age estimation before anything loads, which is why the
  domain returns no crawlable content. Azar is primarily a mobile app; any
  pricing pass should test the iOS/Android build.
- **Camsurf, OmeTV, Bazoocam, Joingy, Uhmegle** — all recorded as offering no
  gender filter based on their own published statements. None of those
  absences was confirmed in-product. OmeTV maintains a refund page, implying
  paid elements not documented on its homepage.
- **Monkey** — the Plus tier's pricing was captured; the Plus+ tier, which
  removes the gender filter cap, was not priced in the capture. The tier
  comparison shows "150" against Filter-Gender with no unit stated, so whether
  that denotes filter activations or an in-app coin balance is unresolved.

## Sample independence

Five platforms — Chatspin, Shagle, Chatrandom, Camgo and Flingster — present
upgrade screens that are not merely similar but substantively the same
product: the same feature carousel, the same three-tier layout, and, on four
of the five, the gender filter slide reproduced word for word:

> "Use our gender filter to connect with women, men or couples more quickly
> and easily."

Price points align to the cent across the group ($7.99 trial / $19.99 month /
$14.99 per month on six months, rebilling at $89.94–$89.99), with one
observed variance: Camgo's trial rebills at $19.99 where its siblings rebill
at $29.99.

This is consistent with a single operator running five brands. Common
ownership has not been confirmed through corporate records, and no such claim
is made. It is stated here because any statistic of the form "N of 17
platforms" implies N independent decisions, and that assumption does not hold
across this group.

## Limitations

- Single-point-in-time snapshot per platform; offers and prices change
- Prices captured from a single geographic region; at least one platform
  displayed live local-currency conversion at checkout
- Several offers were time-limited or discount-framed at the moment of
  capture, most visibly CooMeet's countdown pricing, so a visitor arriving
  later may be shown different figures
- All captures reflect a logged-in session; platforms may present different
  offers to anonymous visitors
- CooMeet's in-product pricing differs from the pricing published in its own
  FAQ; both are recorded in the row's notes
- Two platforms meter the gender filter as a counted consumable rather than
  unlocking it outright (Monkey, Azar); a per-use allowance is not directly
  comparable to an unlimited subscription feature
