# Happy Hour App: Foundation Plan

Oct 5, 2026 · @Ant

Singapore-first happy hour app: a cheap-pint map as the base layer, "where to go tonight" (deal plus vibe) as the reason to choose us, alerts third. Beer first, cocktails later.

## How to use this doc

- Each section: short points, then **Open questions** for us both to answer. Add your thoughts inline.
- Confidence tags: **\[Certain\]** = evidence, **\[Likely\]** = strong inference, **\[Guessing\]** = filling gaps.
- Ratings: **Impact** H/M/L, **Effort** S/M/L, **Viral** 1 to 5 (5 = people share it without being asked).
- Ranking rule: highest impact and lowest effort first; viral potential breaks ties.

**Decided so far**

- Goal: mix of passion/community and portfolio/venture bet.
- Launch: Singapore only.
- Jobs, in order: cheap pint now (base layer), where to go tonight (headline), alerts (retention).
- Data: scrape plus crowd, a new data source (not the LootSG pipeline), plus venue submissions and hand-seeding.
- Incentives: status, utility and bar rewards, introduced in that order.
- Platform: native app wanted for UX. Proposed: Expo (React Native) plus web share pages.
- Timeline: none fixed. Proposed: one validation milestone (see Success metrics).

## 1. Research: market and competitors

Centmap is a strong, actively shipping, price-first competitor in Singapore. It already has most "obvious" features. Its gap is reach, not product. \[Certain\]

| Player | What it is | Strengths | Gaps we can exploit |
| --- | --- | --- | --- |
| [Centmap](https://apps.apple.com/si/app/centmap/id6469340143) | Live beer price map. SG, London, HK. Free, iOS + [web](https://centmap.app/) | Live price on pins, 12-hour time slider, filter by beer and size, XP + leaderboard for editors, auto-filled bar hours. Updated v1.5.4 this week | Too few App Store ratings to show a score (small user base \[Likely\]). Price-only: no vibe, no "where should our group go". No visible monetisation. Spread across 3+ cities |
| [The Happiest Hour](https://apps.apple.com/au/app/the-happiest-hour-pub-finder/id414453120) | Australian pub and happy hour finder. 1,000+ pubs, 50k+ community ([site](https://thehappiesthour.com/)) | 4.5 stars from 486 ratings. What / where / when search. Venues list themselves. Trivia and events | Not in SG. Reviewers flag weak suburb coverage and a slow map |
| Listicles: [City Nomads](https://citynomads.com/happy-hours-in-singapore-best-bars-restaurants-for-cheap-beers-cocktails-and-drink-deals/), [Zula](https://zula.sg/happy-hour-deals/), [BK Magazine](https://www.bkmagazine.com/nightlife/best-happy-hours-singapore/), [Time Out](https://www.timeout.com/singapore/bars-and-pubs/cheapest-happy-hours-in-singapore), [Urban List](https://www.theurbanlist.com/singapore/a-list/singapore-best-happy-hours) | Editorial "best 25 to 49 happy hours" | SEO traffic, trusted names, good for seeding | Static, go stale within months, no map, no "open now" |
| Google Maps / Instagram | Where people really check | Everyone already uses them | Happy hour info is buried in photos and stories, rarely structured |

**What this means** \[Likely\]

- We can't win on "price map + gamification". Centmap has it. We win on the **decision** (where to go tonight, with whom) and **distribution** (sharing into group chats).
- Centmap's small rating count suggests the SG market isn't locked up yet.

**Open questions**

- Have you used Centmap? What annoyed you? (Your own pain is the best research we have.)
- Who else should we tear down? Candidates: Burpple, Chope, The Entertainer, 1-for-1 Telegram channels.
- Should we do 5 to 10 quick interviews with drinker friends before building? I'd say yes.

## 2. Problem statements

The core problem: in Singapore, a beer costs S$15+ at full price, and the info that would save you money is scattered, stale and hard to act on as a group. \[Likely\]

**Drinkers**

1. "I don't know which deal near me is on **right now**, or when it ends." (cheap pint now)
2. "Our group can't agree where to go. Cheap isn't enough, it needs the right vibe." (where to go tonight)
3. "I've shown up and the deal changed. I don't trust listicles." (trust / freshness)
4. "I only find deals by accident on Instagram." (discovery / alerts)

**Bars**

1. "Our 5 to 8pm is empty, and Instagram posts don't fill it."
2. "Listings about us are wrong, and we can't fix them."
3. "Paid platforms (Chope, Entertainer) take a cut or ask for discounts we can't afford." \[Guessing\]

**Contributors**

1. "I know the best spots and want credit for it."
2. "Updating an app is a chore with no payoff."

**Open questions**

- Which drinker problem hurts most? My bet: #2 (group decision) is the most painful, #1 is the most frequent.
- Who is the primary user: expat professionals, local young adults, or tourists? It changes vibe tags, pricing tolerance and marketing channels.
- Is the bar problem real enough that they'd pay? Needs 5 bar owner conversations to find out.

## 3. Where current apps fall short

The biggest gap is that every option answers "where is it cheap" and none answers "where should **we** go tonight". \[Likely\]

| Gap | Who has it | Impact if we fix it | Effort |
| --- | --- | --- | --- |
| No group decision flow (share options, vote, pick) | All | H | M |
| No vibe layer (rooftop, sports on, quiet, date, big group, dog-friendly) | Centmap, listicles | H | M |
| No visible freshness ("verified 2 days ago") | Listicles, likely others \[Guessing\] | H | S |
| Shared links don't drive installs or look good in WhatsApp | Centmap partly (web map) \[Guessing\] | H | S |
| Price-only, ignores value (pint size, beer quality, bar snacks) | Centmap shows size; others don't | M | S |
| Weak suburb / heartland coverage | The Happiest Hour (per reviews) | M | M |
| No reason for bars to keep listings fresh | All | M | M |

**Open questions**

- Which of these would make **you** switch from Centmap?
- Is "heartland coverage" (coffeeshops, kopitiam beer towers) an underserved angle? Cheap Tiger towers could be a fun, viral niche. \[Guessing\]
- I've inferred some gaps from store listings, not hands-on use. Can you test Centmap for a week and log the friction?

## 4. Positioning and moat

**Draft positioning:** "The fastest way for your group to pick a bar tonight, with the best deal on." Centmap tells you a price. We help you make a plan.

A moat is what stops a competitor copying you. Features get copied in weeks. These are harder to copy, ranked by strength:

| Moat | Why it's hard to copy | Effort | Strength |
| --- | --- | --- | --- |
| Freshest data in SG (verify loop + bar self-updates) | Takes months of community habit to build | L | High |
| Group chat distribution (share, vote, pick) | Network effect: every shared plan recruits new users | M | High |
| Vibe tags from real visitors | Subjective data only locals can give | M | Medium |
| Bar relationships (exclusive app-only deals) | Takes time and trust; also a revenue base | L | Medium-High |
| Brand and taste (it feels fun, local, Singaporean) | Hard to fake, easy to underrate | M | Medium |

**Tradeoffs**

- Focusing on SG only means a smaller market, but it's the only way to get data density. Thin data in many cities is the classic killer. \[Likely\]
- Exclusive bar deals make money but can hurt neutrality. Users must trust that rankings aren't paid.

**Open questions**

- Do we lean into being proudly Singaporean (Singlish copy, kopitiam towers) or neutral and expat-friendly?
- One-line positioning: which word should we own? "Tonight", "together", or "cheapest"?
- Would you ever partner with Centmap (they do price data, we do decisions) rather than compete?

## 5. Data and freshness strategy

Fresh data is the product. Every deal shows when it was last confirmed, and stale deals fade out automatically. \[Likely\]

**Sources, ranked by impact vs effort**

| Source | Gives us | Impact | Effort | Risk |
| --- | --- | --- | --- | --- |
| Hand-seed 100 to 150 bars yourself (CBD, Tanjong Pagar, Clarke Quay, Holland V, Robertson) | High-quality first map | H | M | Your time |
| Google Places API for search-to-add (name, location, hours, photos) | Fast, low-friction adding | H | S | Cost per call; terms limit what we can store long term \[Likely\] |
| Listicles (City Nomads, Zula, BK, Time Out) as leads | 100+ deal leads quickly | M | S | Often outdated; treat as "unverified" |
| Apify on bar Instagram / Google reviews mentioning "happy hour" | Ongoing leads | M | M | Platform terms; noisy; needs AI cleanup |
| Photo of a menu or board, AI extracts prices | Very low-effort contributions | H | M | Extraction errors, needs review |
| Bars self-submit and update | Most accurate | H | L (needs bar adoption) | Slow to start |

**Freshness mechanics**

- "Still true?" one-tap check when someone opens a bar near it during happy hour.
- Freshness badge: green (verified < 14 days), amber (< 60), grey (older, flagged).
- Conflicting reports: newest verified wins, with photo evidence weighted higher.

**Open questions**

- Will you commit to hand-seeding the first 100 bars? It's the single best quality investment.
- Budget for Google Places and Apify? Both cost money at scale; need a monthly cap.
- How do we stop spam or bad edits? Trusted-editor levels (like Centmap) vs moderation queue?

## 6. Contributor loop and incentives

Make contributing take under 10 seconds and feel like status, not admin. Introduce rewards in three stages. \[Likely\]

| Stage | Incentive | Examples | When |
| --- | --- | --- | --- |
| 1 | Utility | Contributors unlock alerts, saved lists, early access to new deals | Day 1 |
| 2 | Status | Scout ranks, "Mayor of Tanjong Pagar", streaks, monthly leaderboard, badge on shared plans | Day 1 |
| 3 | Real rewards | Free pint for top scouts, funded by partner bars | After 10+ bar partners |

**Tradeoffs**

- Leaderboards attract gaming (fake updates for points). Points should come from **confirmed** edits, not raw edits.
- Status works for a small core (maybe 1 to 5% of users \[Guessing\]). Utility is what gets everyone else to tap "still true?".

**Open questions**

- Is your own friend group a credible first 20 scouts? Who are your 5 most "I know a spot" friends?
- Should scouts be local-neighbourhood based (own an area) or global (one leaderboard)? Neighbourhood ownership is more viral. \[Guessing\]
- Do we show contributor names on deals ("found by @ant")? Good for status, some may want privacy.

## 7. Feature backlog (ranked)

Top of the list: the "Happening now" map plus a shareable plan link. Together they cover the base job and the growth engine. Sorted by impact, then lowest effort, then viral score.

| # | Feature | Job | Impact | Effort | Viral (1-5) | Why viral (or not) |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | "Happening now" map: live deals, countdown ("ends in 40 min"), price on pin | Cheap pint | H | M | 2 | Useful, not shareable on its own |
| 2 | Shareable bar / plan link with rich WhatsApp preview | Tonight | H | S | 5 | Every share is free marketing into group chats |
| 3 | Freshness badge + "still true?" tap | Trust | H | S | 1 | Invisible but makes everything else trusted |
| 4 | Search-to-add bar + snap a menu photo | Contribute | H | M | 2 | Feeds the data engine |
| 5 | Group vote: send 3 bars, friends vote, app picks | Tonight | H | M | 5 | Brings non-users in to vote; core differentiator |
| 6 | Vibe filters (rooftop, sports on, quiet, big group, date) | Tonight | H | M | 3 | Makes lists people want to share |
| 7 | "Cheapest pint in SG" live leaderboard | Cheap pint | M | S | 5 | Screenshot bait; great for TikTok / Reddit r/singapore |
| 8 | Scout ranks, neighbourhood mayors | Contribute | M | S | 4 | People brag about status |
| 9 | Follow a bar + deal alerts | Alerts | M | M | 2 | Retention, not growth |
| 10 | Happy hour crawl builder (route 3 bars by time) | Tonight | M | M | 4 | Shareable weekend plan |
| 11 | Monthly "SG Pint Index" (average pint price by area) | Brand | M | S | 5 | Press and social bait once data exists |
| 12 | Bar dashboard: claim listing, post deals | Bars | M | L | 1 | Revenue and freshness later |
| 13 | Cocktails | Expand | M | M | 3 | Phase 3 |

**Open questions**

- Agree #2 and #5 (share + vote) are the true differentiators to protect? If yes, they ship in MVP.
- Any feature you've seen elsewhere and loved that's missing here?
- "SG Pint Index" needs enough data to be credible. How many bars before we publish? I'd say 200+.

## 8. MVP scope and phases

The MVP is Phase 1 plus the share link. Each later phase starts only once the previous gate is hit. Gate numbers are proposals for us to agree on.

**Roadmap (diagram in the doc, text copy here)**

| Phase | Scope | Gate to next phase |
| --- | --- | --- |
| 1: Cheap pint now | Live map, countdown timers; bar page + share link; freshness badge, "still true?"; search-to-add, menu photo; scout points, basic ranks | 150 verified bars; 20 non-friend scouts |
| 2: Where tonight | Group vote (3 bars, pick 1); vibe filters; cheapest pint leaderboard; follow a bar + alerts; happy hour crawl builder | 1 in 4 plans shared; week-4 retention 20%+ |
| 3: Bars and money | Bar claims + deal posting; app-only partner deals; scout rewards (free pints); SG Pint Index; cocktails | 10+ paying bars; then consider a 2nd city |

Group vote sits in Phase 2 because it needs enough bars to be worth voting on. If you'd rather lead with the differentiator, it's the first thing to pull forward.

**Phase 0: validate before code (proposed)**

- [x] Use Centmap for a week; log friction
- [x] 10 drinker interviews (how does your group pick a bar?)
- [ ] 5 bar owner chats (would you post deals? pay?)
- [ ] Hand-seed 100 bars in a spreadsheet
- [ ] Clickable prototype of map + share + vote

**Open questions**

- Pull group vote into the MVP, or keep it in Phase 2?
- Are the gates the right ones? What number would make you say "this is working"?
- What do we explicitly NOT build in v1? (My list: accounts beyond basic sign-in, reviews, food deals, cocktails.)

## 9. UI/UX principles and brand

The test for every screen: can someone standing on Amoy Street find a deal and send it to their group in under 10 seconds?

**Principles**

1. **Map opens instantly, no sign-up wall.** Ask for an account only when someone contributes or votes.
2. **Time is the main filter.** Default view is "now", with a slider to "later tonight" (Centmap has this too, so it's table stakes).
3. **One thumb.** Key actions in the bottom third of the screen.
4. **Trust is visible.** Freshness, price, pint size and who verified it, at a glance.
5. **Delight in small doses.** Haptics on a vote, a fizz animation on "deal found", playful empty states.
6. **Dark mode first.** People use it in dim bars at night. \[Likely\]

**Brand directions (pick one)**

| Direction | Feel | Fits |
| --- | --- | --- |
| Playful local | Singlish copy, bright colours, kopitiam warmth | Locals, social sharing |
| Clean premium | Muted, editorial, Monocle-like | Expats, date nights |
| Night neon | Dark UI, glowing pins, bar-sign type | Night use, strongest visual identity |

**Name ideas** (unchecked for trademarks and domains)

- Pint Lah, Shiok Hour, Last Call, Tapped, Cheers SG, HoppyHour, Golden Hour, Dibs, Round On Me, Kampong Pint

**Open questions**

- Which brand direction? My lean: night neon with a dash of playful local copy.
- Which 2 or 3 names do you like? I'll check domains and App Store clashes.
- Any apps whose UI you love (e.g. Airbnb map, Citymapper, Strava)? They set the design bar.

## 10. Tech stack (proposed)

Expo (React Native) for iOS, Android and web from one codebase, with Supabase as the backend. Fast to build, cheap at small scale. \[Likely\]

| Layer | Choice | Why | Alternative |
| --- | --- | --- | --- |
| App | Expo + Expo Router | Native feel, push alerts, also builds web share pages | Native Swift/Kotlin (slower, 2 codebases) |
| Maps | Mapbox (custom dark style) | Best-looking custom maps for a strong brand | Google Maps (familiar, less stylable) |
| Backend + DB | Supabase (Postgres + PostGIS, auth, storage) | "Bars within 1 km open now" is a simple geo query | Firebase (weaker for geo queries) |
| Venue lookup | Google Places API | Search-to-add with auto-filled hours | Foursquare Places |
| Menu photo to prices | Claude vision API | Read a menu board photo into structured deals | Manual entry only |
| Lead scraping | Apify (Instagram, Google reviews) | Ongoing deal leads | Manual tips |
| Share previews | Web route per bar / plan with Open Graph images | Rich previews in WhatsApp and Telegram |  |
| Analytics | PostHog | Funnels, retention, feature flags | Amplitude |

**Tradeoffs**

- Expo is a tiny step below fully native for very heavy map animation. Fine for this app. \[Likely\]
- Mapbox and Google Places both bill by usage. Cache our own data; call Google only when adding a bar.

**Open questions**

- Will you build it yourself with Claude, or bring in a developer or designer?
- Monthly budget cap for APIs and hosting while pre-revenue? (S$50? S$200?)
- iOS first, or both stores from launch? SG skews iPhone \[Guessing\]; both is little extra work with Expo.

## 11. Monetisation

Don't charge drinkers. Bars pay to fill quiet hours, once we can prove we send them people. \[Likely\]

| Option | Who pays | Impact | Effort | Tradeoff |
| --- | --- | --- | --- | --- |
| Featured / boosted deals (clearly labelled) | Bars | H | S | Can erode trust if not marked as ads |
| Claimed listing + deal dashboard (subscription) | Bars | M | M | Needs proof of footfall first |
| App-only flash deals ("first 20 pints S$6") | Bars, we take a fee | H | L | Needs redemption tracking |
| Brewery / distributor sponsorship (e.g. a beer brand's "week") | Brands | M | S | Alcohol ad rules; brand fit |
| Pro tier for users (unlimited alerts, crawl planner) | Drinkers | L | M | Small market; slows growth |

**Open questions**

- Does Singapore regulate alcohol promotion in apps? Needs a quick legal check before any paid placements.
- What counts as proof for a bar: tracked check-ins, redeemed codes, or views?
- Is revenue a Phase 3 problem (my view), or do you want early signal to justify the time?

## 12. Success metrics

North star (the one number that best shows the app is working): **weekly plans shared**. It captures data quality, the "tonight" job and growth in one number. \[Likely\]

| Metric | What it tells us | Proposed target |
| --- | --- | --- |
| Verified bars (< 14 days) | Data freshness | 150 by end of Phase 1 |
| Non-friend contributors | Community is real, not just your mates | 20 by end of Phase 1 |
| Share rate (plans shared / active users) | Viral engine works | 1 in 4 |
| Invite conversion (vote link opened to install) | Sharing brings in users | 10%+ \[Guessing\] |
| Week-4 retention | People come back | 20%+ |
| "Still true?" confirmations per week | Freshness loop is alive | Rising week on week |

**Open questions**

- Agree on weekly plans shared as the north star?
- Set a check-in date for the Phase 1 gate even without a fixed timeline? I'd suggest 8 weeks after first build.

## 13. Risks

The biggest risk is the data going stale after launch. That kills these apps more than anything else. \[Likely\]

| Risk | Likelihood | Impact | Mitigation |
| --- | --- | --- | --- |
| Data goes stale after the launch buzz | High | High | Freshness decay, "still true?" taps, bar self-updates |
| Centmap copies group vote / vibes | Medium | Medium | Win on speed, brand and SG density; they're spread across cities |
| Cold start: empty map, no contributors | High | High | Hand-seed 100+ bars before launch |
| Building forever, never launching | Medium | High | Phase gates and an 8-week check-in |
| Alcohol advertising rules / app store age limits | Medium | Medium | 18+ age gate, legal check before paid deals |
| Scraping breaks platform terms | Medium | Medium | Scraping only for leads; store our own verified data |
| API costs grow with usage | Low | Medium | Budget caps, caching |

**Open questions**

- Which risk worries you most?
- What would make you stop or pivot? Worth deciding now, while there's no sunk cost.

## 14. Decisions log

| Date | Decision | Status |
| --- | --- | --- |
| 5 Oct 2026 | Launch in Singapore only | Agreed |
| 5 Oct 2026 | Cheap-pint map as base, "where to go tonight" as headline | Agreed |
| 5 Oct 2026 | Beer first, cocktails in Phase 3 | Agreed |
| 5 Oct 2026 | Scrape + crowd + venue submit + hand-seed; not the LootSG pipeline | Agreed |
| 5 Oct 2026 | Incentives: utility, status, then bar rewards | Agreed |
| 5 Oct 2026 | Expo (React Native) + web share pages | Proposed |
| 5 Oct 2026 | Name and brand direction | Open |

## Sources

- [Centmap website](https://centmap.app/) and [App Store listing](https://apps.apple.com/si/app/centmap/id6469340143)
- [The Happiest Hour website](https://thehappiesthour.com/) and [App Store listing](https://apps.apple.com/au/app/the-happiest-hour-pub-finder/id414453120)
- SG listicles: [City Nomads](https://citynomads.com/happy-hours-in-singapore-best-bars-restaurants-for-cheap-beers-cocktails-and-drink-deals/), [Zula](https://zula.sg/happy-hour-deals/), [BK Magazine](https://www.bkmagazine.com/nightlife/best-happy-hours-singapore/), [Time Out](https://www.timeout.com/singapore/bars-and-pubs/cheapest-happy-hours-in-singapore), [Urban List](https://www.theurbanlist.com/singapore/a-list/singapore-best-happy-hours)
