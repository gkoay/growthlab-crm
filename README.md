# GrowthLab CRM — MVP v1.0

> A unified contact database and pipeline management system for GrowthLab's three growth motions: Self-serve, Events, and Enterprise.

## The Problem

GrowthLab has no system of record. Event attendees, free signups, and Enterprise interest live scattered across Luma, the app database, email, and spreadsheets. There's no deduplication, no categorization, and no way to see the full picture.

## The Solution

A single-page CRM that:
- **Deduplicates** contacts on email — one person, one record
- **Categorizes** every contact by source, persona, track, and lifecycle stage
- **Visualizes** three distinct pipelines (Self-serve, Events, Enterprise) over one database
- **Segments** contacts with universal filtering across any combination of attributes
- **Reports** baseline metrics — counts by source, persona, track, and geography

## Key Features

### Dashboard
- Real-time KPI cards: total contacts, new this week, Enterprise pipeline, Pro customers
- Bar charts: contacts by source, track, persona, and geography
- Recent contacts table

### Contacts
- Full contact table with search (name, email, company)
- Multi-dimensional filters: source, persona, track, lifecycle stage
- Click-to-view contact detail with activity log
- CSV export capability (UI ready)

### Pipeline
- Kanban-style pipeline views for each track
- Self-serve: Lead → Signed up → Activated → PQL → Pro customer
- Events: Lead → Registered → Attended → Re-engaged
- Enterprise: Lead → In conversation → Qualified
- Drag-and-drop ready architecture (UI placeholder)

### Segments
- Pre-built segments: All Founders, Enterprise Pipeline, Singapore Investors, PQLs & Pro Customers, India Contacts, Event Attendees
- One-click segment drill-down with export
- Custom segment builder (v1.1 placeholder)

## Architecture

| Decision | Rationale |
|---|---|
| Single HTML file | Zero dependencies, instant deploy, works offline |
| In-memory data layer | Fast for hackathon; swap to API when ready |
| Schema-driven flexibility | Adding persona/source values is trivial; no config UI needed |
| Track-based pipeline views | Queries over one table, not separate stores |
| Dedup-on-write pattern | Built into the data model from day one |

## GrowthLab Brand

- **Primary:** Green (#22c55e / #16a34a) — matches GrowthLab's identity
- **Surface:** Warm whites and greens for a clean, professional feel
- **Typography:** Inter — modern, readable, startup-friendly

## Roadmap

| Version | Features |
|---|---|
| **v1.0** ✅ | Contact database, dedup, categorization, pipeline views, segments, dashboard |
| **v1.1** | Luma API integration, behavioral data feed, custom segment builder, CSV import |
| **v2** | Enterprise deal mechanics, conversion automation, health scoring |
| **v3** | Advocacy/referral tracking, multi-user roles |

## Technical Notes

- **34KB** single file — loads instantly
- **20 seed contacts** with realistic activity data across all three tracks
- **7 ingestion sources** modeled: Event/Workshop, Content download, Social referral, App signup, Newsletter, Inbound Enterprise, Manual
- **4 persona types**: Founder, Student, Investor, Organization
- **10 lifecycle stages** across three tracks

## Open Questions (from PRD)

1. **Custom build rationale** — strategic (shared data layer) vs operational (cost)?
2. **Behavioral event emission** — can the app emit these events today?
3. **Luma API** — registration only, or attendance too?
4. **Existing marketing tools** — should CRM feed them or replace them?
5. **Primary user** — founder, community manager, or future BD hire?

---

Built with ❤️ for GrowthLab
