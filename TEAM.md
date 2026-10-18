# Sales Team — AI Agents Division

Zubair's AI sales team. Runs his client acquisition end-to-end for every active business.
Built 2026-10-01 on his order: "ek AI agents ki sales team banao jo mere har business idea waghera sab kuch handle kare, client lae."

## Businesses served (active)
1. **PharmaReg AI** — AI regulatory-compliance audits for pharma manufacturers (DRAP-first, GCC later)
2. **AI Automation Agency** — WhatsApp AI automation for PK e-commerce; WhatsApp AI assistants for Gulf (Dubai) real estate
3. **GEO Visibility Portal** — client self-serve AI-search visibility tool (GSC + GBP + WordPress connect; daily ChatGPT/Perplexity/Gemini mention checks + reports). In-portal AI agent does onboarding/support/dealing; pricing/commitment questions escalate to Zubair. Portal code: ~/workspace/geo-portal/ (localhost for now — needs public hosting before real clients onboard).

New businesses get added here when he picks them. Nothing here overrides his standing rule.

## Org chart (5 roles — each runs as a scheduled agent worker)

| Role | Real-agency equivalent | What it does | How it runs |
|---|---|---|---|
| **Scout** | Lead researcher | Finds new prospects daily, verifies emails from official sites, adds to CRM as NEW | cron `sales-scout-daily` 08:30 PKT |
| **SDR** | Sales dev rep | Writes personalized first-touch emails + follow-up sequences, stages Gmail drafts | on demand in chat (drafts first) |
| **Inbox Watcher** | BDR | Checks replies from tracked prospects 2x/day, updates CRM, drafts responses (never sends) | cron `sales-inbox-triage` every 12h |
| **CRM Keeper** | Sales ops | Owns the pipeline files, statuses, logs every touch | via the two crons + chat updates |
| **Analyst** | RevOps | Weekly report: reply rates, channel performance, what to double down on | weekly summary in chat (Mondays) |
| **Drafts Manager** | Sales ops | Daily drafts review: lists every Gmail draft, flags dead-project + staging duplicates as do-not-send, user picks which to send | cron `drafts-review-daily` 20:00 PKT |
| **Networker** | SDR (social) | 5 LinkedIn connection requests/day with personalized notes: Bio-AI researchers, regulatory pros, agency owners, ORIC people | cron `linkedin-connections-daily` 18:00 PKT |
| **Strategist** | RevOps | Weekly numbers review: if a channel/angle gets ~0 replies after 2 waves, proposes a concrete change (new niche, angle, or channel) — he approves before any change executes | cron `sales-strategy-review` Mon 10:00 PKT |
| **Client Success** | Account manager | In-portal AI agent handles GEO client onboarding, questions, report explanations 24/7; escalates pricing/commitments to Zubair; Zubair approves every money decision | portal code + owner dashboard "Client Inbox" |

## Channel playbook (zero-budget — what actually works here)

| Channel | Status | Notes |
|---|---|---|
| Cold email (Gmail) | ✅ LIVE | PK wave 17 + Gulf wave 17 done; follow-up sequences. ~500/day Gmail limit; keep volume human. |
| Follow-up sequences | ✅ LIVE | Threaded replies, 5–7 day gaps. Oct 6 Gulf wave scheduled. |
| Lead research | ✅ LIVE | Official sites only; drop unverifiable emails (never guess addresses). |
| LinkedIn outreach | ⚠️ MANUAL-GATED | Posts work (his approval). Connection DMs = his account, automation-risky — drafts prepared, he sends or approves. |
| Reddit hiring-watch | ✅ LIVE | Every 6h, silent unless match. |
| Website contact forms | ✅ AVAILABLE | Used as fallback (e.g. SAMI contact form). |
| Cold calling (voice AI) | ❌ NOT AVAILABLE | No voice-call capability in this setup. If he wants it: needs a paid calling service (e.g. Twilio + voice AI) — his call on budget. |
| WhatsApp bulk outreach | ❌ NOT AVAILABLE | Needs WhatsApp Business API (paid + setup). 1:1 from his phone is manual. |
| Paid ads | ❌ NO BUDGET | He runs zero-investment. Revisit if he approves spend. |

## Operating rules (non-negotiable)
1. **Nothing outbound without his explicit go-ahead in his own words** ("send all", "bhej do", "post kardo"). Standing exceptions: none for sales — every wave is approved per wave (he may grant wave-scoped advance approval as he did for the Gulf wave).
2. Every email on real verified data. No invented addresses, no fake claims about the product.
3. One follow-up per prospect per wave; skip anyone who replied, bounced, or opted out.
4. Log every touch in the CRM the same day it happens.
5. Weekly numbers every Monday: sent / replies / meetings / proposals / won.

## Improvement loop (his order 2026-10-01)
- Weekly strategy review (cron sales-strategy-review, Mondays): honest numbers per channel; if ~0 replies after 2 waves, propose a concrete change (new niche/angle/channel) — he approves before it executes.
- Job hunt broadened 2026-10-01: Track B added to daily-job-applications — apply at his level even where no degree required (AI automation, Python dev, data analyst, chatbot dev, research assistant, remote OK). Max 4/day across tracks.
- LinkedIn connections: 5/day with personalized notes (cron linkedin-connections-daily 18:00 PKT) — Bio-AI researchers, regulatory pros, agency owners, ORIC people. Safety cap; stop on any LinkedIn warning.
- Login-needed list (his gates, he does himself via takeover): YouTube Studio sign-in (video #1 publish blocked, awaiting his "done"); Namecheap account creation + card payment ($1.18 domain checkout parked); GulfTalent re-login (daily-job-applications cron failed 2026-09-30); any new job portal as the scout finds it.

## PharmaReg Growth Engine roles (added 2026-10-08 — PharmaReg-dedicated expansion)

| Role | Real-agency equivalent | What it does | How it runs |
|---|---|---|---|
| **Content Creator** | Content marketer | Drafts ONE LinkedIn post/day for PharmaReg: DRAP/SFDA/EDE compliance tips, audit insights, myth-busting. Saves to `crm/pharmareg-linkedin-posts-drafts.md`. NEVER publishes — every post's exact text goes to Zubair for approval first | cron `pharmareg-content-daily` ~09:00 PKT |
| **Lead Miner** | Lead researcher (PharmaReg) | Mines 5–10 NEW pharma-manufacturer leads/day (PK + Gulf): company, QA/RA head if findable, verified email from official site only, source. Appends to `pipeline-pharmareg.md` as NEW. Research-only — never contacts anyone | cron `pharmareg-lead-mine-daily` ~10:00 PKT |
| **Outreach SDR** | Sales dev rep (PharmaReg) | Writes personalized first-touch + follow-up email sequences from mined leads, stages Gmail drafts. Sends ONLY on his per-wave "send all" | on demand in chat (drafts first, never auto-send) |

These three run alongside (not replacing) the existing Scout/SDR/Inbox Watcher/CRM Keeper/Analyst roles. All PharmaReg engine output lives under `crm/pharmareg-*`.

## Pipeline stages
NEW → CONTACTED → REPLIED → MEETING → PROPOSAL → WON / LOST (or OPTED-OUT)

## CRM files
- `crm/pipeline-pharmareg.md` — PharmaReg AI prospects
- `crm/pipeline-agency.md` — Agency prospects (PK + Gulf)
- `crm/pipeline-geo.md` — GEO Visibility Portal prospects (NEW 2026-10-01)
- `crm/log.md` — every touch, dated
