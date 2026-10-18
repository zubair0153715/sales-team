# PharmaReg Growth Engine — Operating Manual

Full-power AI sales & marketing machine for PharmaReg AI (https://pharmareg-ai.fastapicloud.dev).
Built 2026-10-08 on Zubair's order: "full power do… daily posting… leads har jagah se."

Target: pharma manufacturers in **Pakistan + Gulf (UAE, Saudi Arabia, Qatar)**.

## The machine (3 dedicated roles + existing team)

| Role | Cadence | Output |
|---|---|---|
| Content Creator | Daily ~09:00 PKT (`pharmareg-content-daily`) | 1 LinkedIn post draft → `crm/pharmareg-linkedin-posts-drafts.md` |
| Lead Miner | Daily ~10:00 PKT (`pharmareg-lead-mine-daily`) | 5–10 NEW leads → `pipeline-pharmareg.md` (NEW) |
| Outreach SDR | On demand | Personalized email sequences → Gmail drafts |
| Scout / Inbox Watcher / Analyst / Strategist | Existing crons | Unchanged |

## Approval gates (NON-NEGOTIABLE)

1. **Outreach waves:** nothing sends without his per-wave go-ahead in his own words ("send all", "bhej do"). Wave-scoped approvals never generalize.
2. **LinkedIn posts:** exact post text shown before publishing; publishes ONLY on his explicit approval per post. The content cron DRAFTS, never publishes.
3. **Emails:** verified addresses only (verbatim from official sites). No guessed addresses. One follow-up per prospect per wave; skip replied/bounced/opted-out.
4. **No WhatsApp bulk** — needs his WhatsApp Business API setup (pending on him).
5. **No paid ads** — zero budget. Revisit only on his explicit spend approval.
6. **No cold calling** — no voice-call capability in this setup.

## Funnel (expert decision, 2026-10-08)

Free self-audit (/audit, no signup) → **first document fix free** (/portal/remediation) → paid single audit ($800–1,200) → quarterly retainer ($3,000–5,000) ∥ SaaS self-serve (Free / Pro $49 / Enterprise $199).

The free audit is the lead hook (zero friction). Remediation is the upsell, not the hook.

## Lead rules

- Source map: `crm/pharmareg-lead-sources.md`. Research-only: never contact, never fill forms.
- Never re-add a company already in the pipeline. Mark email verification status honestly.
- LinkedIn as a source needs HIS login (expired — pending on him). Directories + official sites are the real sources; LinkedIn scraping is unreliable.

## Files

- `TEAM.md` — org chart (engine roles appended 2026-10-08)
- `crm/pipeline-pharmareg.md` — the pipeline (CONTACTED / NEW / logs)
- `crm/pharmareg-lead-sources.md` — every free lead source, PK + Gulf
- `crm/pharmareg-linkedin-posts-week1.md` — first 7 post drafts
- `crm/pharmareg-linkedin-posts-drafts.md` — rolling daily drafts (content cron appends here)
- `PHARMAREG-ENGINE.md` — this manual

## Honest limits

- LinkedIn outreach/publishing needs his login + his exact-text approval. Until then: drafts only.
- Lead volumes are mined, not guaranteed — quality over quantity; every email verified before any wave.
- Zero human replies so far across all waves; the Strategist's Monday review will call for a channel/angle change if this persists.
