# Vision

> Working title: **Orbit** (the people in your orbit). Placeholder until we pick a name.
> Status: Draft v1, for review
> Owner: Areeb Hussain
> Last updated: 2026-10-16

## The one line

**Never lose touch with anyone who matters.**

Orbit is a personal relationship assistant. It watches your email, calendar, messages and meetings, builds a living picture of everyone you know, and tells you who to talk to, when, and what to say. You never forget a name, a promise or a person again.

## The problem

Every professional's most valuable asset is their relationships, and everyone manages them with nothing.

- You meet hundreds of people a year. Within a month, most are a name you half-remember and a face you don't.
- You say "let's stay in touch" and then don't, not from lack of care but because nothing reminds you.
- You promise to send someone an intro, a link, a deck, and forget it by the next meeting.
- You walk into a meeting with someone you met twice before and can't recall what you talked about.
- The person who could help you with the thing you're stuck on today is already in your contacts. You just don't know it.

The tools people use for this are the wrong shape. LinkedIn is a public network, not your private memory. CRMs (Salesforce, HubSpot) are built for sales pipelines, and they punish you with data entry. Personal CRMs (Clay, Dex, Folk, Monica) are better but still manual: you have to remember to log things, which is the exact thing you're bad at. Spreadsheets and Notes apps die after two weeks. Your contacts app is a phone book from 2005.

The result: relationships decay by default, and the cost is invisible. The intro you didn't get, the client who hired someone else, the friend who drifted.

## The insight

**The data already exists. Nobody has to type anything.**

Every interaction you have leaves a trace: an email thread, a calendar invite, a message, a photo of a business card, a LinkedIn connection. The relationship graph is sitting in your accounts, scattered across ten apps. The hard part was never storing it. The hard part is reading it all, understanding it, and knowing what to surface when.

That was impossible to do well until now. Language models can read a year of email and tell you "you promised Sara an intro to Tom on March 3rd and never sent it". They can summarize three past conversations into two lines before a meeting. They can draft the follow-up in your voice. The product that was always wanted but never buildable is now buildable, and nobody has built it properly yet.

**Orbit is zero-input by design.** You connect your accounts once. From then on, it reads, remembers and reminds. The only thing you ever do by hand is add a one-line note when you feel like it, and act on what it tells you.

## Who it's for

**First:** people whose livelihood depends on relationships, and who feel the pain weekly.

- **Founders**, who meet investors, candidates, advisors and customers constantly and lose track of all of them.
- **Salespeople and BD**, who have a CRM for the pipeline and nothing for the hundred people who aren't in it yet.
- **Freelancers and consultants**, whose next contract is always a former client or a referral.
- **Investors and recruiters**, whose entire job is remembering people.
- **Community builders, journalists, organizers**, who know everyone and can't keep it in their head.

**Then:** everyone. Everyone has relationships they'd rather not lose. The professional wedge is where the willingness to pay is sharpest, but the product is for anyone who's ever thought "I should reach out to them" and didn't.

## What the almost-perfect product feels like

A day with Orbit, a year from now.

**7:40 am.** Your morning brief: "You have 3 meetings today. At 10 you're seeing Priya Shah for the second time. Last time (April, coffee at Blue Bottle) she was raising a seed round and mentioned her co-founder was leaving. You promised to send her the hiring doc, which you did. Her round closed in June. Also, Dan Kim's new job started yesterday, and you haven't spoken since the conference. Here's a draft congratulations."

**10:05 am.** You walk into the meeting already knowing everything. Afterwards, you say nothing. Orbit reads the calendar event, sees the meeting happened, and later that day notices an email from Priya saying "great to see you, I'll send over the deck". It files that as a promise *she* made and will nudge you if it doesn't arrive.

**1:15 pm.** At lunch you meet someone new. You tap your phone to theirs, or they scan your code. Orbit records who, where, when, and that you were both at the "Founders Lunch" event. On the walk back you say into your phone: "Marcus, the guy with the hardware startup, might be a good fit for Lena's fund." Orbit transcribes it, attaches it to Marcus, and notes a possible intro to Lena.

**4:00 pm.** A gentle card: "You haven't talked to Amira in 5 months. You used to talk monthly. She posted that she's moving to Lisbon." One tap drafts a message, you edit one line, send. Three seconds.

**Friday.** The weekly review: 14 people you met this week, 3 promises you made (2 done, 1 waiting), 2 promises made to you, 4 people going quiet that you care about, and one thing Orbit noticed: "Four people in your network work at Stripe. You've been trying to reach their partnerships team. Jess is the closest and you talked last month."

**At no point did you fill in a form.**

## Principles

These decide product arguments. When two options conflict, the earlier principle wins.

1. **Zero input.** If the user has to type it, we failed. Every piece of data should come from a connected source, a tap, or a spoken sentence. Manual entry exists but is never required.
2. **Private by default.** This is your memory. It is not a network, not a feed, and never visible to anyone else unless you choose to share a specific thing. We do not sell, train on, or mine your data. The business model is that you pay us.
3. **Proactive, not a database.** The value is in what Orbit brings to you, not what you can look up. If a user only ever opens it to search, we've built a contacts app.
4. **Calm.** A few things that matter, at the right moment. One brief a day, one review a week, nudges only when something is actionable. The user should never feel nagged. Every nudge has "less of this" one tap away.
5. **Trust through transparency.** Every suggestion shows its reason ("because you emailed on March 3rd"). Every automated action is visible and reversible. Orbit never sends anything on your behalf without a tap.
6. **Fast and beautiful.** It should feel like the best-designed app on your phone. Instant, quiet, thoughtful. Design quality is a feature, not polish.
7. **Works alone, better together.** Full value with zero other users. Any network feature comes second and never gates the core.

## What we will not build

- **A social network.** No profiles for others to browse, no feed, no followers. Orbit is private.
- **A sales pipeline CRM.** No deals, stages, forecasts or team dashboards. Teams come later, and even then it's shared memory, not a pipeline.
- **A messaging app.** Orbit drafts; you send through the channel you already use.
- **An ads business.** Ever.

## Why now

1. **LLMs made zero-input possible.** Reading, understanding and summarizing unstructured communication at scale was science fiction in 2020 and a commodity API now.
2. **Relationships became more fragmented.** Remote work, more jobs per career, more tools per person. The graph got bigger and harder to hold in your head.
3. **Privacy expectations shifted.** People increasingly want a tool that's theirs, not a platform that monetizes them. A paid, private product is a position the big platforms can't take.
4. **The incumbents can't do it.** LinkedIn won't read your Gmail. Google won't build a product that admits Contacts is broken. Apple is years away. The personal CRM startups are manual-first and small.

## How it grows

Orbit has no cold-start problem: one person gets full value on day one. Growth comes from:

- **Every follow-up is a touchpoint.** Orbit's drafts are sent from the user's own email and messaging, so growth isn't viral by spam. It's viral by reputation: the user becomes the person who always remembers, always follows up, and people ask how.
- **In-person capture.** The tap-to-exchange and QR flows put Orbit in front of a new person at every meeting. The person who receives your details gets a beautiful page and a one-tap "save contact", and an invite that's optional, not pushy.
- **Shared memory (later).** A founder invites a co-founder to share the investor list. A team shares the people they all know. This is the one network feature that's both natural and non-gating.

## The long arc

**Year 1: the memory.** A private, automatic relationship assistant for individuals. Win on being the best-designed, most useful tool in the category, and charge for it.

**Year 2: the shared memory.** Small teams, with shared people and context, and warm introductions through your real network ("who do we know at X?"). Still private, still a tool.

**Year 3: the network that grew out of a tool.** By now, millions of people have their real relationship graph inside Orbit, with context LinkedIn has never had. Opt-in features emerge from that: a verified "we've worked together" layer, trust-based introductions across teams, a public profile that's optional and built from real history. The professional network of the earlier PRD becomes possible, but it arrives as an outgrowth of something people already love, not as an empty room asking to be filled.

Slack grew out of a game studio's internal tool. Notion grew out of a note-taking app. LinkedIn grew out of a résumé host. Networks grow out of tools. Tools don't grow out of networks.

## What success looks like

**12 months after launch:**

- People describe it to friends as "the app that remembers everyone for me".
- 100,000 people have connected at least one account. 20,000 pay.
- Day-30 retention over 50%, because an app that reads your email either becomes essential or gets disconnected, and we're built for essential.
- Users act on more than 30% of nudges. That's the number that proves it's proactive and calm, not noise.
- Not a single privacy incident, and a published transparency report.

## Open questions for the next docs

1. **Name.** "Orbit" is a placeholder. Needs a real name and domain.
2. **First platform.** Mobile-first PWA, native iOS first, or desktop web first? The morning brief and in-person capture argue for mobile. The deep-review argues for desktop. (Leaning: iOS native + web, with Android soon after.)
3. **Depth of email access.** Reading all email is the most valuable and most sensitive thing we do. We need a clear, honest answer on what's processed, where, and for how long, before writing a line of code.
4. **Pricing.** Free tier with limits, or a free trial then paid? A product this private may be better off with no free tier at all, so that the user knows exactly what the business is.
5. **The first 100 users.** Who are they, and how do we reach them?

## Document map

| Doc | Purpose | Status |
|---|---|---|
| `00-vision.md` | Why this exists, for whom, what it feels like, principles | This doc |
| `01-personas-and-jobs.md` | Who we serve and the jobs they hire us for | Next |
| `02-prd.md` | What v1 does, prioritized, with acceptance criteria | Next |
| `03-design-principles.md` | How it looks, feels and speaks | Planned |
| `04-privacy-and-trust.md` | Data handling, permissions, what we never do | Planned |
| `05-architecture.md` | Systems, data model, AI pipeline, integrations | Planned |
| `06-roadmap.md` | Milestones for Phase 1 | Planned |
| `07-go-to-market.md` | Launch plan, first 100 users, pricing | Planned |
| `archive/` | Earlier directions, kept for context | |
