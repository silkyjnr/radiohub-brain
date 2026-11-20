---
name: making-memories-meta-ads
description: Plan, write, build, launch-prep and review Facebook/Instagram (Meta) ads for Making Memories, Radio Hub's $799 family-story studio session. Covers account IDs, targeting, objective choice, creative and copy rules, the PAUSED-build workflow, and what has worked before. Use for any Making Memories ad work, including Christmas, Mother's Day and Father's Day pushes.
---

# Making Memories: Meta ads

Load `making-memories-brand` first for colours, fonts, logo and voice. Past results and learnings are in `references/past-performance.md`. **Read it before proposing anything** and add to it after every campaign.

## Hard rules

1. **Build everything PAUSED.** Campaign, ad set and ads. Never activate, raise a budget, or edit a live campaign without Cooper's explicit "yes" in chat.
2. Use the **RadioHub Media** ad account only (below). Never touch Fit Business Services.
3. **No fake people.** Real studio photos, real client footage (with permission), or AI variations of our real photos/backgrounds. Never AI-generated "clients" or invented testimonials.
4. Every ad has **one action** and links to the Making Memories page (or the voucher page) with UTM tags.
5. Before building, show Cooper the plan: objective, audience, budget, dates, each ad's creative plus copy. Build after he approves.

## Account facts

| Thing | Value |
|---|---|
| Ad account | RadioHub Media, `2028389834366573` (AUD, min daily budget $1.49) |
| Page | RadioHub Media, `725777784208212` |
| Instagram | look up with `ads_get_ig_accounts` before building, then record the ID here |
| Pixel/dataset | "Making Memories", `834947215699382` |
| Landing page | https://www.radiohub.com.au/makingmemoriesservices |

**Pixel status (20 Nov 2026):** only `PageView` fires. **No Lead or Purchase events.** That's why 2025's Sales campaigns reported no results.

## Choosing the objective

- **No booking/purchase event firing** (current state): use **Traffic** (`OUTCOME_TRAFFIC`), optimised for **landing page views**. Judge by cost per landing page view, then by bookings Cooper or France confirm manually (ask buyers "where did you hear about us?").
- **Once a Lead or Purchase event fires on the booking/voucher confirmation page:** switch to **Sales** (`OUTCOME_SALES`) optimising for that event. That's the real fix. Raise it whenever ads are discussed until it's done.
- **Instant-form Leads** (`OUTCOME_LEADS`) is an option when someone can call leads back within 24 hours. The 2025 test got CTR above 5% but only 1 lead from $33. The sample is too small to judge.

## Targeting defaults

- **Location:** Sydney, ~40 km radius around Alexandria NSW (sessions are in person). Australia only.
- **Age:** 30–65+ (the buyers are adult children and grandchildren, not the person being interviewed).
- **Audience:** start broad / Advantage+ audience. Interests are optional hints (family, parenting, genealogy/family history, gifts). With a small budget, **one ad set**. Don't split the money.
- **Placements:** Advantage+ placements, with vertical 9:16 versions for Stories/Reels.
- **Budget:** 2026 Christmas = **$25/day to 22 Dec** (~$800). One ad set, 3–4 ads max at this budget.

## Creative: what to make

From 2025 results: **video beat stills by a mile** (video $0.73 per click vs stills $2.50–$3.40). Lead with motion.

Priority order:
1. **Real session footage**: a family member asking a question, the loved one's answer, a laugh or tear. 15–30 s, captions burned in, hook in the first 2 s.
2. **Studio walkthrough video** from the new studio photos/videos (mics, lights, two chairs, warm). Shows "this is easy and comfortable".
3. **Navy-wash photo collage** still, per the brand guidelines: Great Vibes gold title plus one action.
4. **Gift voucher mock-up** still: the voucher in a gift context, for "give the gift" ads.

Formats: 1:1 or 4:5 for feed, 9:16 for Stories/Reels. Keep text off faces.

## Copy rules

- **Hook = a question a family member would ask:** "Dad, how did you and Mum meet?" / "Nan, what was Christmas like when you were little?"
- Say what they get, concretely: **1-hour guided session · our Alexandria studio · we bring the questions · edited highlight video · private link · $799.**
- Gift angle for Christmas: "The gift they'll never forget getting", "Book before Christmas, or give a gift voucher."
- Reassure: "No experience needed. We guide the whole conversation."
- One CTA. Use **Book Now** for sessions and **Learn More** / **Shop Now** for voucher pages. Never `BOOK_TRAVEL` (2025 mistake).
- Avoid guilt or mortality framing, clichés, all caps.
- Headline under ~40 characters. Primary text: the first 125 characters carry the message.

Templates:

```
Primary: "Mum, what's your favourite memory of us as kids?"
One hour in our Alexandria studio. You ask the questions, with our guide to help, and we turn it into a highlight video your family keeps forever. $799.
Headline: A family story to keep
CTA: Book Now
```

```
Primary: Stuck on what to give Dad this Christmas?
Give him an hour to tell his story. A guided conversation in our studio, edited into a video the whole family can watch. Book a session or give a gift voucher. $799.
Headline: The gift of their story
CTA: Learn More
```

## Build workflow (Meta Ads connector)

1. `ads_get_ad_entities` on `2028389834366573`: check nothing Making Memories is live or overlapping.
2. Upload images/videos (`ads_create_upload_url` / `ads_creative_upload_media`) from Drive downloads.
3. `ads_create_campaign`: status **PAUSED**, objective as above, no campaign budget (use ad set budget) unless asked.
4. `ads_create_ad_set`: **PAUSED**, daily budget, start/end dates, Sydney radius, age, optimisation goal.
5. `ads_create_creative` per ad: page `725777784208212`, link with UTMs `?utm_source=meta&utm_medium=paid&utm_campaign=mm_<season>_<year>&utm_content=<ad-name>`.
6. `ads_create_ad`: **PAUSED**.
7. `ads_get_ad_preview` for each ad. Show Cooper the previews plus a summary table.
8. Only on Cooper's yes: `ads_activate_entity`.
9. Record what was built (IDs, budget, dates, creative) in `references/past-performance.md` and commit.

Naming: `MM | <Season Year> | <Objective>` (campaign), `MM | Sydney 40km | 30-65` (ad set), `MM | <format> | <hook>` (ad).

## Reviewing results

Pull weekly: spend, impressions, CTR, cost per landing page view, frequency, plus bookings confirmed by the team. Pause ads with CTR under 1% after ~$40 spend, or frequency over 3. Move money to the best video. Write learnings into `references/past-performance.md`.
