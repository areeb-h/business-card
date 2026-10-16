# Product Requirements: Professional Network Platform

> Status: **Draft v0.2**, for review
> Owner: Areeb Hussain
> Last updated: 2026-10-16
> Supersedes v0.1 (digital business card scope)

## 1. Summary

A professional network that does everything LinkedIn and its neighbors do, but better: a profile that proves what you've done instead of listing it, connections that remember how you met and keep the relationship alive, and a social layer that feels like talking to peers rather than performing for an algorithm. Every feature the incumbents offer exists here, with a cleaner, faster and more respectful experience.

**One-line positioning:** the professional network that works for you, not for the feed.

**Why people will switch:** LinkedIn is where everyone is, but almost no one likes being there. The profile is a résumé, the feed is engagement bait, connections are a number, and the UI is slow and cluttered. We win by being the place that's pleasant to use every day, and by making it easy to bring your existing network along (import, instant share, mutual discovery).

## 2. Competitive baseline

What the incumbents offer, and how we do each one better. "Parity" means we must have it. "Edge" is the improvement.

| Area | LinkedIn | Others (Bento, Read.cv, Polywork, Blinq/Popl) | Parity we must ship | Our edge |
|---|---|---|---|---|
| **Profile** | Résumé-style: experience, education, skills, about, featured, recommendations | Read.cv: clean design; Polywork: multi-hat badges; Bento: link grid | All LinkedIn sections, plus a clean design | Proof-of-work showcase, verified facts, a "now" status, expressive themes, video/voice intro |
| **Connections** | Mutual requests, 1st/2nd/3rd degree, "People you may know" | Blinq/Popl: scan to connect, with notes | Requests, degrees, suggestions, contact import | Context on every connection (where, when, notes), scan-to-connect, smart follow-up reminders, zero spam |
| **Feed and posts** | Algorithmic feed, posts, articles, polls, reactions, comments, reposts, newsletters | Polywork: highlights | Posts, images, video, polls, reactions, comments, reposts | Chronological by default, structured updates that become proof of work, no engagement counters on display, strong mute/filter controls |
| **Messaging** | DMs, InMail, group chats, voice/video notes, read receipts | Mostly none | 1:1 and group DMs, media, voice notes | Message requests that need acceptance, intro requests, snooze, no InMail spam |
| **Search and discovery** | People, jobs, companies, posts, with boolean filters | Minimal | People, companies, posts, skills, location | Search by proof (skills with evidence), availability, "open to", with natural-language search |
| **Jobs and opportunities** | Job board, Easy Apply, "Open to work", recruiter tools | Read.cv: simple job board | Job listings, apply, "open to" signals | Opportunities include freelance, collaboration and advising, with transparent pay and no ghosting (status is always visible) |
| **Companies** | Company pages, followers, employees, jobs | None | Company pages, employees and jobs | Verified employees, with culture and tech stack sections |
| **Endorsements** | Skill endorsements, recommendations | None | Both | Attestations are from people who actually worked with you (verified overlap) |
| **Sharing** | Profile URL, QR code | Blinq/Popl: QR, NFC, wallet pass, vCard, lead capture | QR, URL | NFC, Apple/Google Wallet, one-tap vCard, OG previews, lead capture |
| **Notifications** | Noisy, engagement-driven | Minimal | Full notification system | Digest mode, with only things that need you, and no "X viewed your profile" bait |
| **Analytics** | Profile views, post impressions, search appearances | Blinq: taps and saves | Views, impressions, link clicks | Source breakdown, privacy-friendly and useful for follow-up |
| **Groups and events** | Groups, events, live audio | None | Groups and events (Phase 3) | Small, moderated communities |
| **Learning and premium** | LinkedIn Learning, Premium, Sales Navigator | None | Out of scope for v1 | Pro tier focused on verification and tools, not on gating basic features |

## 3. Goals and non-goals

### Goals
1. **Parity.** Nobody leaves because something they rely on is missing.
2. **Better UI/UX.** Faster, cleaner and calmer than every incumbent, with world-class mobile.
3. **Proof over claims.** Profiles show evidence, and facts can be verified.
4. **Relationships, not numbers.** Connections have context and stay alive.
5. **Daily value without manipulation.** People come back because it's useful, not because it's addictive.

### Non-goals (v1)
- Paid learning content
- Recruiter sales tools (Sales Navigator-style)
- Advertising
- Native mobile apps (v1 is a responsive web app and PWA; native comes in Phase 3)

## 4. Target users

Broad from day one, like LinkedIn. Early marketing focuses on the three personas most likely to switch.

| Persona | Pain with LinkedIn | What wins them |
|---|---|---|
| **Builder** (dev, designer, PM) | A résumé can't show the work | Proof-of-work profile, linked GitHub/Dribbble, verified skills |
| **Independent** (freelancer, consultant, founder) | Needs leads, not likes | Lead capture, availability status, opportunities with transparent pay |
| **Connector** (sales, BD, community, recruiter) | Loses track of who they met | Scan-to-connect, connection context, follow-up reminders |
| **Everyone else** | The feed is exhausting | Calm chronological feed, digest notifications, clean UI |

## 5. Product pillars and functional requirements

Priority: **P0** is required for Phase 1, **P1** for Phase 2, and **P2** for Phase 3. See §12 for phasing.

### 5.1 Profile

| ID | Requirement | Pri | Better than LinkedIn because |
|---|---|---|---|
| PR1 | Core identity: name, pronouns, headline, photo, cover, location, languages, bio (markdown) | P0 | Bio supports formatting and sounds human |
| PR2 | **Now** block: what I'm working on, availability (open to work, freelance, advising, collaboration, not open), updated with one tap | P0 | Living profile, not a static résumé |
| PR3 | Experience, education, certifications, volunteering, publications, patents, honors (full LinkedIn section parity) | P0 | Each entry can attach proof (links, media, attestations) |
| PR4 | **Showcase**: projects, case studies, code repos, designs, writing, talks, products, each with media, links and a role description | P0 | Shown, not listed, with rich media and embeds |
| PR5 | **Skills with evidence**: each skill links to showcase items and attestations, and skills without evidence are shown lighter | P0 | Endorsements become meaningful |
| PR6 | Video intro (≤60 s) and voice note (≤30 s) | P1 | Expressive and personal |
| PR7 | Themes: 6+ curated themes, accent color, font pairs, light and dark mode, with a contrast guard | P0 | Expression, with accessibility guaranteed |
| PR8 | Section reorder, show and hide, and custom sections | P0 | Your profile, your structure |
| PR9 | Linked accounts: GitHub, Dribbble, Behance, YouTube, Substack, personal domain, with auto-synced content and ownership proof | P1 | Proof of work pulls itself in |
| PR10 | Multiple "hats" (for example Engineer + Angel investor + Podcaster) shown as badges | P1 | Polywork-style multi-identity |
| PR11 | Profile completeness guidance that recommends adding proof, not just filling fields | P0 | Nudges toward quality |
| PR12 | Import from LinkedIn (data export ZIP upload and OAuth basics) and from a résumé PDF (AI-parsed) | P0 | Switching takes 2 minutes |
| PR13 | Public URL `site.com/{username}`, custom domain (Pro), and per-section visibility (public, connections, private) | P0 | Granular privacy |

### 5.2 Verification and trust

| ID | Requirement | Pri |
|---|---|---|
| V1 | **Work email verification**: confirm an @company.com address to verify current or past employment, with the badge shown on the entry | P0 |
| V2 | **Peer attestation**: a connection with verified overlap (same company, overlapping dates) confirms "we worked together" and can write a recommendation | P0 |
| V3 | **Linked account verification**: ownership of GitHub, a domain, or others, proven by OAuth or a DNS/meta tag | P1 |
| V4 | Education verification via .edu email or an attestation by a classmate | P1 |
| V5 | Identity verification (government ID through a provider such as Persona or Stripe Identity) as a Pro feature with a badge | P2 |
| V6 | Verification is visible but never shaming: unverified facts are simply unbadged | P0 |

### 5.3 Connections

| ID | Requirement | Pri | Better than LinkedIn because |
|---|---|---|---|
| C1 | Mutual connection requests with an optional note, and requests expire after 30 days | P0 | No request graveyard |
| C2 | **Scan-to-connect**: QR or NFC in person creates a pending or instant connection and records where and when | P0 | Meeting becomes a connection automatically |
| C3 | **Connection context**: where we met, when, tags, private notes and a follow-up date, on every connection | P0 | A personal CRM built in |
| C4 | Contact import (Google, Apple, CSV) that matches existing users and invites the rest, opt-in and never silent | P0 | Bring your network along |
| C5 | Degrees of connection (1st, 2nd, 3rd) and mutual connections shown | P0 | Parity |
| C6 | "People you may know", based on real signals (mutuals, same company, same event) with a one-tap "why?" | P1 | Transparent suggestions |
| C7 | **Smart reminders**: follow up after meeting, "you haven't spoken in 6 months", job-change and milestone alerts, configurable or off | P0 | Keeps relationships alive |
| C8 | **Warm intro requests**: ask a mutual to introduce you, with a draft message, and they accept or decline privately | P1 | Trust-based networking |
| C9 | Follow (one-way) for public figures and companies, separate from connections | P1 | Parity, kept distinct |
| C10 | Request rate limits, spam detection and a per-user "who can request me" setting (anyone, 2nd degree, nobody) | P0 | Zero recruiter spam |
| C11 | Block, mute and report, and remove a connection silently | P0 | Safety |

### 5.4 Social: feed and posts

| ID | Requirement | Pri | Better than LinkedIn because |
|---|---|---|---|
| S1 | **Structured updates**: shipped, started, launched, learned, looking for, milestone, each one attaching to the profile timeline as proof of work | P0 | Posts build your profile instead of disappearing |
| S2 | Free-form posts: text (markdown), images (up to 10), video, link previews, polls, documents (PDF carousel) | P0 | Parity |
| S3 | Long-form articles with a clean editor, and newsletters (subscribe to a person) | P1 | Parity |
| S4 | **Chronological feed of connections and follows by default**, with an optional "for you" tab that explains why each item is shown | P0 | You control the feed |
| S5 | Reactions (small set), comments (threaded), reposts with comment, bookmarks | P0 | Parity, with counts de-emphasized (visible on tap, not in the feed) |
| S6 | Feed controls: mute person, mute topic, hide reposts, "fewer like this", and a snooze for 24 hours | P0 | Calm by design |
| S7 | **Asks**: a post type where you request something specific (an intro, a hire, feedback, a co-founder) and connections can respond or vouch for someone | P1 | A primitive LinkedIn lacks |
| S8 | Mentions, hashtags and topic follows | P0 | Parity |
| S9 | Drafts, scheduling and edit history | P1 | Parity, done right |
| S10 | Post analytics for the author (reach, saves, profile visits from the post) | P1 | Parity |
| S11 | Content moderation: report, auto-detection for spam, a human review queue and community guidelines | P0 | Required for a social platform |

### 5.5 Messaging

| ID | Requirement | Pri | Better than LinkedIn because |
|---|---|---|---|
| M1 | 1:1 messaging between connections with text, images, files, links, voice notes and reactions | P0 | Parity |
| M2 | **Message requests** from non-connections go to a separate inbox and need acceptance, with the first message limited to one and no follow-ups until accepted | P0 | No cold-pitch flood |
| M3 | Group conversations (up to 50) | P1 | Parity |
| M4 | Read receipts and typing indicators, each one optional | P1 | Your choice |
| M5 | Snooze, archive, pin, search and a "needs reply" filter | P1 | Inbox zero friendly |
| M6 | Intro threads: when a warm intro is accepted, a three-way thread opens automatically | P1 | Connects to C8 |
| M7 | Real-time delivery (WebSocket), push and email fallback, end-to-end encryption is a P2 consideration | P0 | Parity |

### 5.6 Search and discovery

| ID | Requirement | Pri |
|---|---|---|
| D1 | Universal search: people, companies, posts, skills, locations, with typeahead | P0 |
| D2 | People filters: location, company, school, skills (with evidence), availability, "open to", degree of connection, language | P0 |
| D3 | Natural-language search ("React devs in Berlin open to freelance") | P1 |
| D4 | Searchable only if the user opts in; profile and search visibility settings | P0 |
| D5 | Explore page: curated people and showcases by topic, with no engagement-based ranking | P1 |

### 5.7 Opportunities (jobs and more)

| ID | Requirement | Pri | Better than LinkedIn because |
|---|---|---|---|
| O1 | Opportunity listings: full-time, contract, freelance, advising, co-founder, collaboration, speaking | P1 | Beyond "jobs" |
| O2 | Required fields: compensation range, location/remote policy, process timeline | P1 | Transparent by default |
| O3 | One-tap apply with the profile, with optional answers, and the applicant always sees status (viewed, in review, closed), so there is no ghosting | P1 | Respect for applicants |
| O4 | "Open to" signals visible to the right audience (everyone, recruiters only, connections only) | P0 | Parity, with control |
| O5 | Company and individual posters, with posting limits and fees for companies (revenue) | P1 | |
| O6 | Saved searches and alerts | P2 | Parity |

### 5.8 Companies

| ID | Requirement | Pri |
|---|---|---|
| CO1 | Company pages: logo, description, website, size, locations, tech stack and culture sections, with followers | P1 |
| CO2 | Verified employees (via V1 work email), shown on the page | P1 |
| CO3 | Company posts and opportunities | P1 |
| CO4 | Admin roles and claim flow for existing companies | P1 |

### 5.9 Sharing and in-person

| ID | Requirement | Pri |
|---|---|---|
| SH1 | QR code (branded, with PNG and SVG download), always available from the home screen in two taps and offline in the PWA | P0 |
| SH2 | One-tap **Save contact** (vCard) with photo and all public contact methods | P0 |
| SH3 | Native share sheet, copy link, rich OG previews for every profile and post | P0 |
| SH4 | Apple Wallet and Google Wallet pass with the QR code | P1 |
| SH5 | NFC guide and URL for tags and cards | P1 |
| SH6 | **Lead capture** on the public profile for visitors without an account ("share your details back"), with spam protection | P0 |
| SH7 | Email signature generator | P2 |

### 5.10 Notifications

| ID | Requirement | Pri |
|---|---|---|
| N1 | In-app, push (PWA) and email notifications, per-type controls, and quiet hours | P0 |
| N2 | **Digest mode**: a daily or weekly summary instead of real-time, which is the default for non-urgent types | P0 |
| N3 | Urgent types (messages, connection requests, intro requests, reminders) are the only real-time ones by default | P0 |
| N4 | No engagement bait: no "X viewed your profile", "trending in your network" or "congratulate Y" | P0 |

### 5.11 Analytics (for the user)

| ID | Requirement | Pri |
|---|---|---|
| AN1 | Profile views, unique visitors, link clicks, vCard saves, QR scans, search appearances, post reach | P0 |
| AN2 | Source breakdown (QR, NFC, link, wallet, search, feed), device, country | P1 |
| AN3 | Who viewed (opt-in and symmetric: you see them only if you also show yourself) | P1 |
| AN4 | Privacy-friendly: no third-party trackers, hashed IPs | P0 |

### 5.12 Groups and events

| ID | Requirement | Pri |
|---|---|---|
| G1 | Groups: small, moderated, with posts and member lists, and a cap on size for quality | P2 |
| G2 | Events: create, RSVP, attendee list, and "event mode" that tags every scan-to-connect with the event | P2 |

### 5.13 Account, privacy and settings

| ID | Requirement | Pri |
|---|---|---|
| AC1 | Sign up and log in with Google, LinkedIn, Apple, and an email magic link, plus passkeys | P0 |
| AC2 | Username claim and change (with a redirect) | P0 |
| AC3 | Visibility controls per section, per post audience (public, connections, custom) | P0 |
| AC4 | Data export (full JSON ZIP) and account deletion within 30 days (GDPR and CCPA) | P0 |
| AC5 | Two-factor authentication | P1 |
| AC6 | Pro subscription management (Stripe) | P1 |

## 6. UI/UX principles

These are requirements, not aspirations. Design reviews check against them.

1. **Fast.** Every screen interactive in under 1 s on a mid-range phone. Optimistic UI everywhere. No loading spinners for navigations, only skeletons.
2. **Calm.** One accent color, generous whitespace, no red badges unless something needs you. Counters are secondary and de-emphasized.
3. **Mobile first, desktop great.** Design every flow on a 375 px screen first. Desktop uses the space for a two or three-column layout, never just a stretched phone screen.
4. **Two taps to the thing you do most.** QR code, new update, and inbox are always reachable in two taps.
5. **Keyboard and screen-reader complete.** WCAG 2.2 AA. Command palette (⌘K) on desktop for everything.
6. **Respectful defaults.** Chronological feed, digest notifications, no dark patterns, every nudge has a "turn this off" link right there.
7. **Expressive but consistent.** Users customize their profile; the app chrome stays the same, so it always feels familiar.
8. **Motion with purpose.** Transitions explain where things went. Everything respects `prefers-reduced-motion`.
9. **Empty states teach.** Every empty screen shows what to do next and why it's worth doing.
10. **Design system from day one.** Tokens, components and patterns documented in Storybook, so every screen is built from the same parts.

## 7. Non-functional requirements

- **Performance:** public profile LCP under 1.5 s on 4G, served from the edge. App shell under 200 KB JS. Core Web Vitals green.
- **Scale target (v1):** 1 M users, 10 M connections, 100 M events, with an architecture that doesn't need a rewrite to reach 10 M users.
- **Availability:** 99.9%, with multi-region reads for profiles.
- **Security:** OWASP ASVS level 2, upload scanning, EXIF stripping, rate limits on every public and write endpoint, CSRF, CSP, and a bug bounty at launch.
- **Privacy:** GDPR and CCPA, a privacy policy in plain language, data minimization, encryption at rest, and a documented retention policy.
- **Trust and safety:** reporting on every object, a moderation queue with SLAs, automated spam and abuse detection, a blocking model that's enforced in every query.
- **Accessibility:** WCAG 2.2 AA, audited before launch.
- **Internationalization:** English at launch, with the i18n framework and RTL support in place from the start.
- **Observability:** tracing, error tracking, product analytics (self-hosted PostHog or similar, privacy-first).

## 8. Tech stack

| Layer | Choice | Why |
|---|---|---|
| Web app | **Next.js (App Router) + TypeScript + React** | SSR/ISR for fast public profiles and SEO, and one codebase for the app and marketing |
| Styling and components | **Tailwind CSS** + **shadcn/ui** (Radix) + CSS variable tokens, documented in **Storybook** | Accessible primitives we own, and themes as token sets |
| Animation | Framer Motion | Purposeful motion, with reduced-motion support |
| API | **tRPC** for the app, with a public REST API later | End-to-end types |
| Auth | **Auth.js** (Google, LinkedIn, Apple, magic link, passkeys) | Covers every method |
| Database | **PostgreSQL** (Neon or Supabase) + **Drizzle ORM** | Relational data with strong typing |
| Search | **Meilisearch** or Typesense, with pgvector for semantic and natural-language search | Fast typeahead and NL search |
| Real time | WebSockets via **Pusher/Ably** or a self-hosted Soketi, with Postgres LISTEN/NOTIFY as a fallback | Messaging and notifications |
| Queues and jobs | **Inngest** or BullMQ on Redis (Upstash) | Reminders, digests, imports, media processing |
| Storage and media | **Cloudflare R2** + image resizing at the edge, Mux for video | Avatars, showcases, video intros |
| Email | Resend | Magic links, digests, notifications |
| Push | Web Push (VAPID) | PWA notifications |
| Payments | Stripe | Pro tier and company postings |
| Verification | Email domain checks in-house, Persona or Stripe Identity for ID (Phase 3) | |
| QR, OG and vCard | `qrcode`, `@vercel/og`, a custom vCard builder | |
| Wallet | `passkit-generator` and the Google Wallet API | |
| Bot protection | Cloudflare Turnstile + rate limiting | |
| AI | Claude API for résumé parsing, bio help, NL search query rewriting, and spam classification | |
| Hosting | **Vercel** for the web, with managed Postgres, Redis and search | Fast to start, with a clear path to self-hosting |
| Mobile (Phase 3) | React Native (Expo), sharing the API and design tokens | |
| Testing | Vitest, Playwright, and Storybook interaction tests | |

## 9. Data model (high level)

```
User            id, email, createdAt, plan, settings(JSON)
Profile         id, userId, username, displayName, pronouns, headline, bio, avatarUrl, coverUrl,
                location, languages[], nowStatus, availability[], themeKey, accentColor, fontPair,
                visibility, searchable, customDomain
ProfileSection  id, profileId, type, title, order, visible
Experience      id, profileId, company(companyId?), title, start, end, description, verifiedVia
Education       id, profileId, school, degree, field, start, end, verifiedVia
Showcase        id, profileId, type, title, description, media[], links[], role, skills[]
Skill           id, profileId, name, evidence[] (showcaseIds, attestationIds)
Attestation     id, fromProfileId, toProfileId, type (worked_together|skill|recommendation),
                overlapVerified, text, createdAt
LinkedAccount   id, profileId, provider, handle, verified, lastSyncAt
Connection      id, aId, bId, status (pending|accepted), requestedBy, note, createdAt,
                metWhere, metWhen, metSource (scan|nfc|request|import|event)
ConnectionMeta  connectionId, ownerId, tags[], privateNote, followUpAt, lastContactAt
Follow          followerId, targetType (profile|company), targetId
IntroRequest    id, requesterId, viaId, targetId, message, status
Post            id, authorId, type (update|post|article|ask|poll), body, media[], audience, parentId,
                repostOfId, createdAt, editedAt
Reaction        postId, profileId, type
Comment         id, postId, authorId, parentId, body
Bookmark        profileId, postId
Conversation    id, type (dm|group|intro), createdAt
Participant     conversationId, profileId, role, lastReadAt, muted, archived
Message         id, conversationId, senderId, body, media[], createdAt
Company         id, slug, name, logo, description, website, size, locations[], verifiedDomain
CompanyAdmin    companyId, profileId, role
Opportunity     id, posterType, posterId, type, title, description, compRange, location, remote,
                processTimeline, status
Application     id, opportunityId, profileId, answers, status, statusUpdatedAt
Lead            id, profileId, name, email, phone, company, note, consentAt, source
Notification    id, profileId, type, payload, readAt, deliveredVia[]
Event           id, profileId, type, target, source, device, country, visitorHash, createdAt
Report          id, reporterId, targetType, targetId, reason, status
Block           blockerId, blockedId
```

## 10. Key screens

1. **Landing** with a live example profile and "Claim your username"
2. **Onboarding**: claim username, import (LinkedIn/résumé/contacts), choose a theme, add your first proof
3. **Home** (feed): chronological, with a "for you" tab and a composer at the top
4. **Profile** (public and edit mode with inline editing and live preview)
5. **Showcase editor**
6. **Connections**: list with context, filters, reminders, and the "met recently" view
7. **Scan / Share**: QR, scanner, wallet, NFC, vCard
8. **Inbox**: messages, requests, intros
9. **Search and explore**
10. **Opportunities**: browse, post, applications
11. **Company page**
12. **Notifications** with digest settings
13. **Analytics**
14. **Settings**: account, privacy, visibility, verification, Pro
15. **Moderation console** (internal)

## 11. Trust, safety and cold start

**Trust and safety (a launch requirement, not a later one):** community guidelines, report flows on every object, a moderation queue with a 24-hour SLA, automated spam and abuse classification, rate limits, a blocking model enforced in every query, age minimum (16+), and a transparency page.

**Cold start:** a social network with no one on it is worthless, so launch has a plan:
1. **Profile-first value.** The profile, sharing, lead capture and connection CRM are fully useful with zero other users. People get value on day one.
2. **Import everything.** LinkedIn export, résumé PDF, and contacts, so switching costs minutes.
3. **Invite-driven growth.** Scan-to-connect with a non-user sends them a profile and an invite. Every QR scan is an acquisition channel.
4. **Seed communities.** Launch with 3–5 communities (for example a city's tech scene or a design community) that are invited together, so their first feed isn't empty.
5. **Waitlist with usernames.** Claiming a username early is the hook.

## 12. Phasing

| Phase | Theme | Ships |
|---|---|---|
| **Phase 1: Profile + Network** | Useful alone, and better than LinkedIn's profile | Auth, onboarding, imports, full profile with showcase and skills-with-evidence, themes, verification (email, peer), connections with context, scan-to-connect, reminders, QR/vCard/share, lead capture, structured updates and posts with a chronological feed, basic messaging with requests, notifications with digest, analytics, search (people), moderation basics, design system |
| **Phase 2: Social + Opportunities** | Daily use | Articles and newsletters, asks, warm intros, group messaging, NL search and explore, opportunities and applications, company pages, linked-account sync, wallet passes, NFC, "who viewed" (symmetric), Pro tier |
| **Phase 3: Scale** | Everyone | Groups, events, native apps, identity verification, public API, custom domains, saved searches, enterprise and team features |

Phase 1 is large. Expect a small team to need 4–6 months for a solid build. The milestone breakdown within Phase 1 comes in the next planning doc.

## 13. Business model

- **Free:** full profile, connections, feed, messaging, sharing, and basic analytics. Nothing people need daily is paywalled.
- **Pro (individuals):** custom domain, advanced analytics, identity verification badge, priority intros, video intro, advanced reminders, and no platform branding on the public profile.
- **Companies:** opportunity postings beyond a free quota, verified company pages with extra sections, and team pages.
- **Never:** ads, selling data, or paywalling messaging to connections.

## 14. Success metrics

| Metric | Target at 6 months post-launch |
|---|---|
| Profile completeness with at least one proof item | 60% of active users |
| Day-30 retention | 40% |
| Weekly active / monthly active | 50% |
| Connections with context filled in | 50% of connections |
| Spam reports per 1,000 messages | under 1 |
| Public profile LCP (p75, mobile) | under 1.5 s |
| NPS | over 50 |

## 15. Open questions

1. **Product name and domain.** Needed before the landing page and username URLs.
2. **Team and timeline.** Who's building this, and what is the target launch date? That decides how Phase 1 is cut.
3. **LinkedIn import.** Their API is restricted. The data export ZIP works but is manual. Is that acceptable for v1?
4. **Messaging encryption.** End-to-end would be a differentiator but blocks server-side spam detection. Which matters more?
5. **Company postings pricing.** Flat fee per post, or a subscription?
6. **Seed communities.** Which 3–5 communities do we launch with?
7. **Apple Developer account** ($99/yr) for Wallet passes and Sign in with Apple. Is it OK to get now?
8. **Moderation staffing.** Who reviews the queue at launch?
