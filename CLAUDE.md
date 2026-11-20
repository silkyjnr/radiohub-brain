# Radio Hub — Second Brain

This repo is the shared brain for RadioHub Media. Everyone (Sydney and the Philippines team) clones it and works from it with Claude. If you learn something about how we work, our clients, our brands or what performs, **write it here** (update this file, a skill, or a doc), commit, and push. Chat history is not memory; this repo is.

## Who we are

- **RadioHub Media** (trading as Radio Hub), https://www.radiohub.com.au
- Boutique media company in **Alexandria, Sydney**. Founded **2014** by **Cooper Silk** and **Craig Markham**.
- We make **podcasts, vodcasts, video and graphic design**, mostly for business clients.
- Brand line: **"Plan. Produce. Perform."**
- **France Siopongco** leads our creative and admin team of about **20 in the Philippines**.
- We have **new studios** in Alexandria (photos in Drive, see below).

## Current priority (Nov–Dec 2026)

**More bookings for the podcast studio, starting with Making Memories before Christmas.**

- Ads budget agreed: **$25/day to 22 Dec 2026** (~$800), on Meta (Facebook and Instagram).
- Offer: book a **session before Christmas**, or buy a **gift voucher** to redeem in the new year.
- Every new ad is built **PAUSED**. Cooper reviews it before anything spends.

## Brands

| Brand | What it is | Skill |
|---|---|---|
| RadioHub Media | The parent business: podcast/video production for businesses | `.claude/skills/radiohub-brand` |
| Making Memories | Family story recording in our studio. $799. "A guided conversation. A family story to keep." | `.claude/skills/making-memories-brand` |

### Making Memories in one paragraph

A family books a **one-hour guided session** in our studio. One family member interviews a loved one (usually a parent or grandparent) from a **tailored question set**, and we edit it into a **highlight video** they keep, delivered on a **private link**. **$799.** Most buyers are **adult children and grandchildren giving it as a gift**, so **Christmas is our big moment** (Mother's Day and Father's Day are the next ones).
Page: https://www.radiohub.com.au/makingmemoriesservices

## Skills (how we do repeat jobs)

Claude loads these automatically when the task matches. Add a new one whenever we do a job twice.

- `radiohub-brand`: RadioHub Media colours, fonts, logo rules, voice.
- `making-memories-brand`: Making Memories colours, fonts, logo rules, layouts, voice.
- `making-memories-meta-ads`: planning, writing, building and reviewing Making Memories ads on Facebook/Instagram, including what has and hasn't worked.

## Where things live

**Google Drive** (connected through the Google Drive connector):

| What | Drive folder ID |
|---|---|
| Making Memories brand folder (guidelines PDF, LOGO.png, Studio Photos, Previous AD Images, NEW ADS) | `1fuR3biAW7H1cFmaKL9Q5RJDjDvphAy4Z` |
| RadioHub Media brand folder (guidelines PDF, light and dark logos, New Studio) | `1boRF0wB0-UCChDklD0UdagQIvrzu0_eJ` |
| New Studio raw photos and videos (HEIC/MOV) | `1TVIJT6DH2UKaMds82rZQYOQKqj42Rpqa` |

File-level IDs are in each brand skill.

**Meta** (connected through the Meta Ads connector):

- Ad account: **RadioHub Media**, `2028389834366573` (AUD). Use this one for Making Memories.
  - Other accounts the login can see: `365675180562482` "RadioHub" (USD, old), `10151223254711019` (personal, empty), `2378335789336576` Fit Business Services (**not ours to touch** for Radio Hub work).
- Facebook Page: **RadioHub Media**, `725777784208212` (lead-ads terms accepted).
- Pixel/dataset: **"Making Memories"**, `834947215699382`, browser pixel plus Conversions API (server events deduped, match quality 6.1/10). Up to 20 Nov 2026 it had only recorded **PageView**: no Lead or Purchase events, so Meta couldn't see bookings. Cooper submitted a test form at ~3:55 pm 20 Nov and the pixel fired then; confirm in Events Manager whether a Lead event came through.
  - Two other pixels in the business ("RadioHub Pixel" `1010379871254663`, "RadioHub Media Pixel" `802214036057708`) have **never fired**. Ignore them or delete them.
- **Website:** radiohub.com.au runs on **Squarespace**, with two Google Tag Manager containers (`GTM-WN9BDT`, `GTM-TD2PRVPG`). The Making Memories page code only contains `fbq('init')` and `fbq('track','PageView')`. Its form shows an inline "Thank you!" with no separate thank-you page, so a Lead event has to come from a GTM tag on form submit (or Squarespace's Meta integration).

**Higgsfield** (if connected): makes image/video variations from our **real** studio photos. Never pass off AI-generated people as real clients.

## How we work (rules for Claude and for people)

1. **Nothing spends without Cooper's OK.** Build campaigns, ad sets and ads **PAUSED**. Never activate, raise budgets or change live campaigns without an explicit yes in chat.
2. **Use real assets first.** Real studio photos and real client footage beat stock. AI variations are fine for backgrounds and layout tests, not fake testimonials.
3. **Stay on brand.** Load the brand skill before making anything visual or written for a brand.
4. **Write it down.** After a campaign or a learning, update the relevant skill's references (e.g. `making-memories-meta-ads/references/past-performance.md`).
5. **Privacy.** Don't commit client personal details, passwords, API keys or payment info. Client names only with permission.
6. **Commits:** small, plain-English messages ("Add Christmas 2026 ad results"). Push when it's worth keeping.

## Team

- **Cooper Silk**: co-founder. Final say on ads, spend and brand.
- **Craig Markham**: co-founder.
- **France Siopongco**: leads creative and admin (Philippines team, ~20 people).

## Open questions / to-do

- [ ] Add booking tracking: fire a **Lead** or **Purchase** pixel event on the Making Memories booking/checkout confirmation page so ads can optimise for bookings, not clicks.
- [ ] Confirm the gift voucher purchase flow and URL.
- [ ] Two 2025 campaigns ("Making Memories Black Friday", "New Sales Campaign") are still ACTIVE at campaign level with every ad paused ($0 spend). Tidy up once the 2026 campaign is live.
