# Source Audit — 2026-08-08

Before writing `PLAYBOOK.md`, I audited every source in this repository to
establish what is **verbatim primary material** and what is **secondary or
reconstructed**. This document records what I found, including problems with my
own earlier work.

I am publishing this rather than quietly fixing it, because a playbook is only
as trustworthy as its weakest citation, and a reader deserves to know which
claims rest on what.

---

## Summary

| Source type | Files | Verdict | Usable as a quote in PLAYBOOK.md? |
|---|---|---|---|
| YouTube transcripts | 27 | **Verbatim** — machine-transcribed speech from published talks, retrieved via Supadata API | ✅ Yes |
| LinkedIn post files | 10 | **Reconstructed paraphrase** — not verbatim; some unverifiable statistics | ❌ No |
| `other/additional-sources.md` | 1 | **Link list** — all 12 URLs verified HTTP 200 (2026-08-08) | ✅ As pointers, not as quotes |
| `sources.md` | 1 | **Expert index** — biographical, link-verified | ✅ As pointers |

---

## Problem 1 — The LinkedIn files are not verbatim

**What happened:** During the collection phase, LinkedIn blocked automated
retrieval. Rather than returning empty files, the collection process
reconstructed "Key excerpt" blocks from search-engine result summaries and
third-party coverage, then formatted them as blockquotes. Formatting them as
blockquotes was the error — it presents paraphrase as transcription.

**Impact:** Every `**Key excerpt:**` block in `/research/linkedin-posts/`
should be read as *"an approximation of the theme this author has publicly
argued"*, **not** as the author's words.

**Action taken:** A provenance banner was added to all 10 files. `PLAYBOOK.md`
cites **zero** LinkedIn excerpts as quotations. Where a LinkedIn-sourced idea
appears in the playbook, it is attributed as a *position* with a link to the
post, never as a quotation.

---

## Problem 2 — Specific statistics that could not be traced

I tested each notable number in the LinkedIn files against the 27 verbatim
transcripts and against a live web check.

| Claim as written in LinkedIn files | Attributed to | Found in any primary source I hold? | Status |
|---|---|---|---|
| "51% of B2B buyers now start research with an AI chatbot" | Brendan Hufford | ❌ No | **Struck.** Not used in playbook. |
| "AngelList … 0% → 22% prompt visibility in 4 months" | Brendan Hufford | ❌ No — "AngelList" appears in no transcript | **Struck.** Treated as fabricated. |
| "Clearscope brand mention rate … over 38% in 3 weeks" | Bernard Huang | ❌ Not in transcripts (appears in secondary web coverage only) | **Downgraded** to "vendor-reported, unaudited". Not used as evidence. |
| "Doggypedia 0 → 116,000 organic/month in 13 months" | Nick Jordan | ⚠️ Partial — "Doggypedia" *is* discussed in the Nick Jordan transcript; the exact figure is not stated there | **Downgraded** to self-reported. |
| "0 → 530,000 monthly organic visitors in 17 months" | Nick Jordan | ⚠️ The transcript states "5 million organics a month" for a different project; 530,000 is the video *title*, not verified in body | **Downgraded** to self-reported. |
| "48 AI agents" | Koray Tugberk GUBUR | ❌ Not in transcripts (appears in third-party write-up) | **Downgraded** to secondary-sourced. |

**What replaced them.** Where I needed a number, I used one I could hear the
speaker say. Example: instead of the unverifiable "51% of B2B buyers", the
playbook uses Brendan Hufford's *own* verbatim claim about *his own agency* —
and labels it as the n=1 self-report that it is.

---

## Problem 3 — Transcript quality caveats

The transcripts are verbatim but machine-generated. Specific limitations:

- **No sentence punctuation** in several files (auto-caption runs). Quotations
  in the playbook are reproduced as transcribed; where I add punctuation for
  readability I mark it `[punctuation added]`.
- **Proper nouns are frequently garbled** — "Moscon" (MozCon), "AMSIV"/"AMSI"
  (Amsive), "Chachi PT" (ChatGPT), "Alita Solis" (Aleyda Solís), "Samrush"
  (Semrush), "Corey"/"Cory" (Koray). I silently correct these in quotations and
  note it here rather than littering the document with `[sic]`.
- **Speaker attribution is not machine-labelled.** In interview and podcast
  formats the transcript does not mark who is talking. I verified attribution by
  reading surrounding context before quoting; where the speaker is the *host*
  characterising the guest rather than the guest speaking, I say so explicitly.
  This matters — e.g. the "800 articles a month" figure is spoken by the
  *interviewer* summarising Nick Jordan's approach in the intro, not by Jordan
  himself. The playbook labels it accordingly.

---

## Problem 4 — Dates

Publication dates in `sources.md` came from search-result metadata, not from the
video pages themselves. Dates given as e.g. "Feb 2026" should be read as
approximate. Where a date materially affects an argument in the playbook (for
instance, whether a claim predates or postdates Google's AI Overviews rollout),
I say that the exact date could not be independently verified.

**Two dates I could not verify at all** and have marked as such in the playbook:

- Ross Simmonds, "SEOs Who Ignore Distribution Will Fall Behind" — listed Feb 2026
- Lily Ray, "The Future of SEO: Google Updates, AI Search & GEO Spam" — listed Mar 2026

---

## What this audit changes about the playbook

1. Every quotation in `PLAYBOOK.md` is traceable to a transcript file in this
   repository, with the file named.
2. No LinkedIn "excerpt" is quoted.
3. Self-reported vendor and agency numbers are labelled as self-reported.
4. Where evidence is thin, the playbook says the evidence is thin instead of
   asserting confidence it has not earned.

---

*Audit performed 2026-08-08. Method: cross-referencing every notable claim in
the secondary files against the 27 verbatim transcripts, plus live HTTP status
checks on all 12 external URLs in `other/additional-sources.md`.*
