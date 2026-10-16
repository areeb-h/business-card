# Product Requirements: Digital Business Card Platform

> Status: **Draft v0.1**, for review
> Owner: Areeb Hussain
> Last updated: 2026-10-16

## 1. Summary

A web platform where any professional can create a modern, shareable digital business card in a few minutes. It is a lighter, faster and more personal alternative to LinkedIn for first impressions. You share the card with a QR code, an NFC tap, a link or a wallet pass. The person receiving it can save the contact in one tap and share their own details back. The owner sees who viewed the card and what got attention.

**Positioning:** LinkedIn is a social network, but this is about the moment two people meet. It should be the fastest way to say "here's who I am" and to remember who you met.

## 2. Goals and non-goals

### Goals
1. Let anyone create a polished public card in **under 3 minutes**.
2. Make sharing and saving a contact **one action** (scan, tap or click).
3. Turn card views into **two-way connections** through lead capture.
4. Show owners **useful analytics** about their card.
5. Look great on mobile first, in light and dark mode.

### Non-goals (v1)
- A social feed, posts, likes or follower graphs
- Messaging or chat between users
- Job listings or recruiting tools
- Team or company admin accounts (planned for later, see §11)
- Native mobile apps. v1 is a responsive web app and PWA.

## 3. Target users

| Persona | Need |
|---|---|
| **Freelancer / consultant** | Showcase work, get booked, and capture leads at events |
| **Sales / BD professional** | Share contact details instantly and follow up with the people they met |
| **Job seeker / student** | Have a modern profile that's easier to share than a résumé |
| **Founder / creator** | Have one link for all their projects, socials and booking |

## 4. User stories

**Owner**
- As a new user, I sign up with Google, LinkedIn or an email magic link and pick a unique username (`site.com/areeb`).
- I can fill in my name, headline, photo, company, location, bio and contact methods.
- I can add social links and choose their order.
- I can add showcase sections: projects, testimonials, a booking link, custom links and media.
- I can choose a theme, accent color and font, and preview the card live while I edit.
- I can download or print my QR code, add my card to Apple or Google Wallet, and write it to an NFC tag.
- I can see views, link clicks, contact saves and captured leads over time.
- I can export my leads as CSV.
- I can hide sections, unpublish my card or delete my account.

**Visitor (no account needed)**
- When I open a card, it loads fast and works well on my phone.
- I can tap **Save contact** to download a vCard straight into my phone's contacts.
- I can tap **Share my details back** to leave my name, email, phone and a note for the owner.
- I can tap any contact method (call, email, WhatsApp, map) to open it in the right app.
- I can switch between light and dark mode, or it follows my system setting.

## 5. Functional requirements

Priority levels: **P0** is required for MVP, **P1** should be in v1, **P2** is later.

### 5.1 Accounts and auth
| ID | Requirement | Pri |
|---|---|---|
| A1 | Sign up and log in with Google OAuth, LinkedIn OAuth, or an email magic link | P0 |
| A2 | Username claim with validation (3–30 chars, lowercase, unique, reserved words blocked) | P0 |
| A3 | Change username, with redirects from the old URL for 90 days | P1 |
| A4 | Delete account and all data (GDPR) | P0 |
| A5 | Import profile data from LinkedIn on sign-up (name, headline, photo) | P1 |

### 5.2 Profile and card content
| ID | Requirement | Pri |
|---|---|---|
| P1 | Core fields: name, pronouns (optional), headline, company, location, bio (≤300 chars) | P0 |
| P2 | Avatar upload with crop. Optional cover image. | P0 |
| P3 | Contact methods: email, phone, website, WhatsApp, address. Each one can be shown or hidden. | P0 |
| P4 | Social links (LinkedIn, GitHub, X, Instagram, YouTube, Behance, Dribbble and more) with auto-detected icons and drag-to-reorder | P0 |
| P5 | **Showcase sections:** Projects (title, image, link, description), Testimonials, Booking link (Calendly/Cal.com), Custom links, Media embed (YouTube, PDF résumé) | P1 |
| P6 | Reorder, show and hide sections | P1 |
| P7 | Live preview in the editor, side by side on desktop and as a toggle on mobile | P0 |

### 5.3 Themes and customization
| ID | Requirement | Pri |
|---|---|---|
| T1 | 4–6 curated themes (for example Minimal, Bold, Glass, Classic, Gradient) | P0 |
| T2 | Custom accent color and a choice from 6–8 font pairs | P0 |
| T3 | Every theme supports light and dark mode. Visitors follow their system setting and can toggle it. | P0 |
| T4 | Subtle entrance and hover animations that respect `prefers-reduced-motion` | P0 |
| T5 | Automatic contrast check so a custom color can't make text unreadable | P1 |

### 5.4 Sharing
| ID | Requirement | Pri |
|---|---|---|
| S1 | Public card at `site.com/{username}` | P0 |
| S2 | QR code generator with the accent color and optional center logo, downloadable as PNG and SVG | P0 |
| S3 | **Save contact:** a vCard 3.0/4.0 download with photo, all contact fields and the card URL | P0 |
| S4 | Native share sheet (Web Share API), with copy link as a fallback | P0 |
| S5 | Rich link previews: Open Graph image generated for each card | P0 |
| S6 | **Apple Wallet pass** (.pkpass) and **Google Wallet pass** that show the QR code | P1 |
| S7 | NFC: instructions and URL for writing to any NTAG213/215 tag or card | P1 |
| S8 | Downloadable "email signature" HTML snippet | P2 |
| S9 | Custom domains | P2 |

### 5.5 Lead capture
| ID | Requirement | Pri |
|---|---|---|
| L1 | A "Share my details back" form on the public card with name (required), email or phone (one required), company, note, and a consent checkbox | P0 |
| L2 | Spam protection: rate limiting, a honeypot field, and Cloudflare Turnstile | P0 |
| L3 | Leads inbox in the dashboard with search, a tag for where we met, and notes | P0 |
| L4 | Email notification to the owner for each new lead (can be switched off) | P1 |
| L5 | CSV export, and saving a lead as a vCard | P1 |
| L6 | The owner can turn lead capture off | P0 |

### 5.6 Analytics
| ID | Requirement | Pri |
|---|---|---|
| N1 | Track card views, unique visitors, link clicks for each link, vCard saves, QR scans (via a `?src=qr` param) and leads | P0 |
| N2 | Dashboard with a 7/30/90-day chart and a top links table | P0 |
| N3 | Breakdown by source (QR, NFC, link, wallet), device and country | P1 |
| N4 | Privacy-friendly: no third-party trackers or cookies for visitors; hash IPs and use them only for unique counts | P0 |

## 6. Non-functional requirements

- **Performance:** public card LCP under 1.5 s on 4G, JS for the card page under 50 KB, and the card served statically or from the edge cache.
- **Accessibility:** WCAG 2.1 AA, including keyboard navigation, alt text and color contrast.
- **SEO:** cards can be indexed by default, with a per-user `noindex` option.
- **Privacy and compliance:** GDPR-ready, with data export, deletion, a lead consent record and a privacy policy.
- **Security:** OWASP basics, upload validation (type and size, stripping EXIF location data), rate-limited public endpoints and CSRF protection.
- **Reliability:** 99.9% uptime target and daily database backups.
- **Responsive:** 320px and up, mobile-first design.
- **PWA:** the owner can install the dashboard and open their own QR code offline.

## 7. Proposed tech stack

| Layer | Choice | Why |
|---|---|---|
| Framework | **Next.js (App Router) + TypeScript** | SSR/ISR for fast, SEO-friendly public cards, with the API and the app in one codebase |
| Styling | **Tailwind CSS** + CSS variables for themes | Themes become sets of tokens, and dark mode comes almost for free |
| UI components | shadcn/ui (Radix) | Accessible primitives that we own the code for |
| Animation | Framer Motion | Polished motion that respects reduced-motion |
| Auth | **Auth.js** with Google, LinkedIn and an email magic link (Resend) | Covers all three sign-in methods |
| Database | **PostgreSQL** (Neon or Supabase) + **Drizzle ORM** | Relational data, typed queries, and free tiers to start |
| File storage | Cloudflare R2 or Supabase Storage | Avatars and project images |
| Email | Resend | Magic links and lead notifications |
| QR / OG / vCard | `qrcode`, `@vercel/og`, a custom vCard builder | Lightweight and run on the server |
| Wallet passes | `passkit-generator` (Apple) and the Google Wallet API | Needs an Apple Developer account (see §10) |
| Bot protection | Cloudflare Turnstile + Upstash rate limiting | Protects the lead form |
| Hosting | **Vercel** | Zero-config Next.js deploys, edge caching and preview deploys |
| Testing | Vitest (unit) + Playwright (e2e) | |

## 8. Data model (draft)

```
User        id, email, name, createdAt
Profile     id, userId, username (unique), displayName, pronouns, headline,
            company, location, bio, avatarUrl, coverUrl, published, noindex
Theme       profileId, themeKey, accentColor, fontPair, defaultMode
ContactItem id, profileId, type (email|phone|website|whatsapp|address), value, visible, order
SocialLink  id, profileId, platform, url, order
Section     id, profileId, type (projects|testimonials|booking|links|media), title, visible, order, data (JSON)
Lead        id, profileId, name, email, phone, company, note, tag, consentAt, source, createdAt
Event       id, profileId, type (view|click|save|scan|lead), target, source, device, country, visitorHash, createdAt
```

## 9. Key screens

1. **Landing page**: the value proposition, an example card and a "Claim your username" input
2. **Sign up / log in**
3. **Onboarding**: claim a username, then basic info, then a theme (3 steps that can be skipped)
4. **Editor**: form on the left, live preview on the right, with tabs for Profile, Links, Sections and Design
5. **Share**: QR code, wallet passes, NFC, copy link and email signature
6. **Leads**: inbox table with a detail drawer and export
7. **Analytics**: charts and a breakdown
8. **Settings**: account, username, privacy and delete account
9. **Public card**: `/{username}`

## 10. Open questions

1. **Product name and domain.** Do we keep "business-card" or pick a brand name?
2. **Monetization.** Free with a Pro tier for custom domains, advanced analytics, more themes and removing the branding? Or free for now?
3. **Apple Wallet passes** need a paid Apple Developer account ($99/yr). Do we want them in v1 or later?
4. **Physical NFC cards.** Will we sell or ship them, or only support tags people buy themselves?
5. **Languages.** English only for v1, or RTL and multi-language support?
6. **LinkedIn OAuth** needs an approved LinkedIn app. Is that OK, or should v1 launch with Google and email only?

## 11. Future (post-v1)

- Team and company accounts with shared branding and admin-managed employee cards
- CRM integrations (HubSpot, Salesforce, Google Contacts sync)
- AI help: write my bio, and summarize the leads I met at an event
- Event mode, which tags every lead captured during a named event
- Native iOS and Android apps with home-screen widgets for the QR code
- A paper-card scanner (OCR) that turns paper cards into leads

## 12. MVP milestones

| # | Milestone | Includes |
|---|---|---|
| M1 | Foundations | Repo setup, auth, database schema, username claim |
| M2 | Card editor | Profile fields, contact and social links, live preview, themes, dark mode |
| M3 | Public card and sharing | `/{username}`, vCard, QR code, OG image, share sheet, animations |
| M4 | Leads | Capture form, spam protection, inbox, CSV export |
| M5 | Analytics | Event tracking and dashboard |
| M6 | Polish and launch | Accessibility pass, performance, landing page, privacy policy, deploy |
| M7 (v1.1) | Showcase and wallet | Showcase sections, Apple/Google Wallet passes, NFC guide |
