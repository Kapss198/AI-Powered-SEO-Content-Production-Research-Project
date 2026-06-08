# AI-Powered SEO Content Production — Research Project

**Author:** Kapil  
**Topic:** AI-Powered SEO Content Production  
**Purpose:** Portfolio project for 100Hires Junior Growth Marketing Specialist role  
**Status:** Phase 1 — Expert Research & Source Collection 

---

## Why This Topic

I chose **AI-Powered SEO Content Production** because it sits directly at the intersection of what 100Hires needs:

- 100Hires produces blog articles, comparison pages, and landing pages — all SEO content
- The role explicitly requires using Claude Code and AI tools daily with judgment on top
- AI-powered SEO is one of the fastest-moving areas in marketing right now, with genuine complexity that rewards research over shortcuts
- A well-built playbook here would be directly usable, not just theoretical

The goal of this research is not to collect 10 names from a Google search. It is to find the people whose *actual methods* can form the backbone of a real content production system.

---

## Repository Structure

```
/
├── README.md                          ← You are here
└── research/
    ├── sources.md                     ← 10 experts with full annotations & YouTube links
    ├── linkedin-posts/                ← Posts organized by author
    │   ├── ross-simmonds/
    │   ├── aleyda-solis/
    │   ├── lily-ray/
    │   ├── kevin-indig/
    │   ├── koray-tugberk-gubur/
    │   ├── bernard-huang/
    │   ├── kyle-roof/
    │   ├── nick-jordan/
    │   ├── brendan-hufford/
    │   └── mordy-oberstein/
    ├── youtube-transcripts/           ← Transcripts fetched via Supadata API
    └── other/                         ← Newsletters, podcasts, webinars
```

---

## The 10 Experts — Quick Overview

I selected these 10 people based on a specific filter: **they have to actually do the thing, not just write about it.** Every person on this list either runs an agency that produces SEO content at scale, built a tool that powers AI SEO workflows, or has a documented track record of measurable results.

| # | Expert | Role | Signal |
|---|--------|------|--------|
| 1 | **Ross Simmonds** | Founder, Foundation Marketing | "Create Once, Distribute Forever" framework; B2B SaaS content at scale |
| 2 | **Aleyda Solis** | Founder, Orainti | SEOFOMO newsletter (45k subs); Crawling Mondays YouTube; AI search practitioner |
| 3 | **Lily Ray** | VP SEO Strategy, Amsive | Leading authority on E-E-A-T + AI content quality; speaks at MozCon, SMX |
| 4 | **Kevin Indig** | Growth Advisor (ex-Shopify, G2) | Runs Growth Memo; pioneered SEO at major SaaS companies |
| 5 | **Koray Tugberk GUBUR** | Founder, Holistic SEO | Created Topical Authority concept; builds AI agents for semantic SEO |
| 6 | **Bernard Huang** | Co-Founder, Clearscope | Built the AI content optimization tool used by Adobe, HubSpot, Shopify |
| 7 | **Kyle Roof** | Co-Founder, Page Optimizer Pro | US patent for SEO testing; 400+ algorithm experiments |
| 8 | **Nick Jordan** | Founder, Content Distribution | Grew 6 websites from 0 → 100k+ organic/month; hundreds of pages/month |
| 9 | **Brendan Hufford** | Founder, Growth Sprints | B2B SaaS AEO + SEO; tracks AI visibility across ChatGPT/Perplexity |
| 10 | **Mordy Oberstein** | Head of SEO Brand, Wix | Data-driven research across millions of sites on AI content signals |

Full annotations, links, and why each was chosen: [`/research/sources.md`](./research/sources.md)

---

## How I Did the Research

I used Claude Code (Opus 4.8) with live web search to identify, validate, and collect content from each expert. My process:

1. **Started broad** — searched for "best AI SEO content production experts 2025–2026" and reviewed multiple aggregator lists
2. **Applied a practitioner filter** — cut anyone who is primarily a journalist, agency blogger, or tool vendor with no track record of actually doing the work
3. **Validated recency** — confirmed each expert had published original content on AI + SEO in 2024–2026
4. **Fetched YouTube transcripts** — used the Supadata API to retrieve full transcripts of 2–4 videos per expert
5. **Collected LinkedIn posts** — manually captured highest-signal posts per expert
6. **Checked multiple channels** — confirmed LinkedIn, YouTube, or newsletter presence for each person

**What I rejected:**
- Generic "top 10 SEO experts" lists that include people famous for 2015-era SEO, not AI-era content production
- Tool vendors who only talk about their own product
- People with large followings but no documented client results or methodology

---

## YouTube Transcripts Collected

Transcripts fetched via Supadata API and stored in `/research/youtube-transcripts/`:

| Expert | Videos Transcribed |
|--------|--------------------|
| Ross Simmonds | 3 videos |
| Aleyda Solis | 1 video |
| Lily Ray | 3 videos |
| Kevin Indig | 3 videos |
| Koray Tugberk GUBUR | 3 videos |
| Bernard Huang | 3 videos |
| Kyle Roof | 3 videos |
| Nick Jordan | 3 videos |
| Brendan Hufford | 1 video |
| Mordy Oberstein | 2 videos |

---

## What Comes Next (Phase 2)

The next phase will extract themes from the collected transcripts and LinkedIn posts. Themes to extract:

1. **Workflow design** — how do you actually structure an AI content production pipeline?
2. **Quality control** — how do you fact-check and improve AI output without spending more time than you saved?
3. **Topical authority** — how do you structure a content library so that Google sees you as an expert, not a content farm?
4. **AEO / GEO** — how do you optimize for AI-generated answers, not just blue links?
5. **Measurement** — what metrics actually matter when most clicks are zero-click?

---

## Commit Log

- `2026-06-09` — Initial repo setup, directory structure created
- `2026-06-09` — Added `/research/sources.md` with 10 experts, full annotations, YouTube links
- `2026-06-09` — Added `README.md` with project overview and methodology
- `2026-06-09` — Added `/research/other/additional-sources.md` (newsletters, podcasts, webinars)
- `2026-06-09` — Fetched YouTube transcripts via Supadata API — stored in `/research/youtube-transcripts/`
- `2026-06-09` — Added LinkedIn posts per expert in `/research/linkedin-posts/`

---

## Tools Used

- **Claude Code (Anthropic, Opus 4.8)** — research, web search, transcript collection, writing
- **Supadata API** — YouTube transcript extraction
- **GitHub** — version control and public portfolio
