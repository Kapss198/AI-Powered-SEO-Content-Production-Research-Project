# AI-Powered SEO Content Production Playbook

**Version:** 1.0 · **Author:** Kapil · **Date:** 08 August 2026
**Status:** Operational draft. Sections marked ⚠️ rest on thin evidence — read [§9 Weaknesses](#9-weaknesses-of-this-playbook) before relying on them.

---

## A note on sourcing, up front

Every quotation in this document comes from a machine transcript of a published
talk, stored in [`/research/youtube-transcripts/`](./research/youtube-transcripts/).
Each citation names the file so any claim can be checked against the source text.

**I do not quote the LinkedIn files in this repository.** During collection,
LinkedIn blocked automated retrieval and the "excerpt" blocks in
[`/research/linkedin-posts/`](./research/linkedin-posts/) were reconstructed from
search-result summaries rather than transcribed. Several statistics in them —
including a "51% of B2B buyers" figure and an AngelList case study — could not be
traced to any primary source and are **not used here**. The full audit is in
[`research/SOURCE-AUDIT.md`](./research/SOURCE-AUDIT.md).

Transcripts are auto-generated and mangle proper nouns ("Moscon" → MozCon,
"Alita Solis" → Aleyda Solís, "Samrush" → Semrush). I correct these silently in
quotations and add punctuation where auto-captions omit it. Nothing else is altered.

---

## 1. Introduction

### Purpose

This is an operating manual for producing SEO content with AI assistance at a
rate a small team can sustain, without producing the kind of output that Google's
2024–2025 quality systems demote and that AI answer engines decline to cite.

It exists because the default failure mode is now well documented: AI removes the
cost constraint on publishing, teams respond by publishing more, and the marginal
value of each piece falls to roughly zero. This playbook is structured to prevent
that specific outcome.

### Audience

A growth or content team of 1–5 people who own organic acquisition for a
product, who have access to at least one genuine subject-matter expert, and who
can publish on their own site without a committee.

### Scope

| In scope | Out of scope |
|---|---|
| Blog articles, comparison pages, use-case and solution pages | Paid search, paid social |
| Topic selection through post-publish measurement | Brand/creative campaigns |
| Optimising for both Google results and AI answer citations | Site migrations, replatforming |
| Human review as a production gate | Link buying, PBNs, any grey-hat tactic |

### Goals

1. Publish content that ranks in Google **and** is retrievable by AI answer engines.
2. Keep human effort concentrated where it changes the outcome, not spread evenly.
3. Make quality a **gate** rather than an aspiration — something that blocks a publish.
4. Build a measurement layer for AI visibility, because the traffic metric alone
   is becoming a lagging and partial indicator.

---

## 2. Guiding Principles

These are the positions that recur across independent sources. Where sources
conflict, that conflict is handled in [§7](#7-where-experts-disagree) rather than
smoothed over here.

### 2.1 AI search runs on top of traditional search, not instead of it

This is the single most load-bearing principle in the playbook, and it is the one
with the strongest evidence behind it.

Large language models do not answer from memory when the question is current.
They retrieve. Bernard Huang describes the mechanism concretely:

> "Models, when performing answers for users, will likely ground with Google
> search. And that's because the knowledge cutoff or training data associated
> with models is usually out of date. Therefore, models need to search to
> understand whether or not there are new topics, concepts, trends [...] before
> responding to the end user."

*Source: Bernard Huang, "How To Do AEO: Prompt Research, Query Fan Out, Content" (Clearscope live session), listed Feb 2026 — [`bernard-huang-how-to-do-aeo-prompt-research-query-fan-out-content-live-ses.md`](./research/youtube-transcripts/bernard-huang-how-to-do-aeo-prompt-research-query-fan-out-content-live-ses.md) · https://www.youtube.com/watch?v=RMg2eTZL7Jk*

Lily Ray reports the same mechanism from the retrieval side, citing Britney
Müller's finding that "every single URL that you see in an LLM output actually
comes from a search engine API, Google or Bing," and concluding: "in order to
appear across these different LLMs, you need to appear in search engines first."

*Source: Lily Ray, "GEO, AEO, LLMO: Separating Fact from Fiction" (MozCon 2025 online adaptation), listed Nov 2025 — [`lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md) · https://www.youtube.com/watch?v=2nJkT8zOzcM*

Aleyda Solís states the same conclusion from the technical-SEO side: "The
principles in SEO remain also in AI search."

*Source: Aleyda Solís, "AI Search Crawlability and Why Your Site's Tech Foundations Decide Visibility," listed 2025 — [`aleyda-solis-ai-search-crawlability-and-why-your-site-tech-foundations-de.md`](./research/youtube-transcripts/aleyda-solis-ai-search-crawlability-and-why-your-site-tech-foundations-de.md) · https://www.youtube.com/watch?v=pqrwpXpMM6s*

> **Operating consequence:** Do not build a second content process for "GEO."
> Build one process that produces retrievable content, and add a second
> *measurement* layer. This distinction is the resolution to [Disagreement 2](#72-disagreement-2--is-aeogeo-a-separate-discipline).

### 2.2 Trust is a ranking input, not a brand nicety

Kevin Indig argues that trust has become the core selection criterion in AI
experiences, and grounds it in an unusual source — Google's disclosures under the
US Department of Justice antitrust litigation:

> "Google is [...] more or less forced to explain how they went about ranking for
> many years. And one of the surprising findings is that Google has looked at
> clicks and user behaviour for way longer than we thought."

and:

> "Users select sources or search results based on whether they trust the brand
> or the company, and then whether they think it answers their question. [...]
> One of the big aspects of succeeding in this AI world [...] is really a
> trust-first mindset."

*Source: Kevin Indig, "The SEO Playbook for the AI Age," listed May 2025 — [`kevin-indig-the-seo-playbook-for-the-ai-age-with-kevin-indig.md`](./research/youtube-transcripts/kevin-indig-the-seo-playbook-for-the-ai-age-with-kevin-indig.md) · https://www.youtube.com/watch?v=eepyi-NYFiM*

Indig's assessment of whether the fundamentals shifted with AI: **"that
fundamental is stable."**

### 2.3 AI is acceptable where you have nothing to add, and dangerous where you do

Mordy Oberstein draws the cleanest line in the entire source set. He is not an
AI-content opponent:

> "There's nothing wrong with AI and there's nothing wrong with AI content. It's
> all what you do with [it]."

His test is whether you have information to contribute. On a saturated commodity
topic — his example is how to change a tyre — he is content to let AI handle it:
"there's probably nothing new I can add to that conversation at this point."

The failure case is the inverse, and it is a factual failure rather than a
stylistic one:

> "Take the very same example and let's say there's new technology that emerges,
> in which case the answer to that question changes. AI is not going to know that
> for a while. It's going to have to re-scrape everything, and it's not going to
> know the answer to that until everybody starts updating their content."

*Source: Mordy Oberstein, "SEO Branding and AI Content," listed Jan 2023 — [`mordy-oberstein-seo-branding-and-ai-content-with-mordy-oberstein-head-of-seo.md`](./research/youtube-transcripts/mordy-oberstein-seo-branding-and-ai-content-with-mordy-oberstein-head-of-seo.md) · https://www.youtube.com/watch?v=npmVxc_5Tqo*

He also names the underlying market dynamic honestly — AI writing tools "solve
such a powerful pain point," because "writing content [...] is very, very hard,"
and so adoption will outrun judgement.

> **Operating consequence:** Route topics by information asymmetry. Where you
> hold information the training corpus does not, AI drafts but a human supplies
> the substance. Where you hold nothing, either skip the topic or accept that
> you are producing a commodity and price your effort accordingly. This becomes
> the routing decision in [Step 1](#step-1--topic-selection).

### 2.4 Write atomic answers; do not try to engineer the chunking

Lily Ray's treatment of "chunking" is the most useful debunking in the source set,
because it separates a real practice from a fashionable one:

> "Chunk optimisation isn't really an SEO tactic. It's an AI engineering
> function. Large language models don't see your pretty formatting. They see
> tokens, or tiny units of meaning. They, not you, decide how to slice your
> content. There's not really any cheat code that you can use to chunk your
> content for AI Overviews, because every model chunks differently."

What she says *is* in your control:

> "Create clear, self-contained, atomic answers that stand on their own, whether
> a human being reads them or an AI extracts them."

She further reports that Google's John Mueller characterises optimising pages for
embeddings as "literally [...] keyword stuffing, which is a form of spam in
Google search."

*Source: Lily Ray, MozCon 2025 — [`lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)*

### 2.5 Distribution is part of production, not a downstream afterthought

Ross Simmonds' four-part model — **Research → Creation → Distribution →
Optimisation** — treats distribution as a first-class stage. His argument is that
the platforms now surfacing as AI citations are the ones SEOs dismissed:

> "I was telling people back in 2018, 2019, you need to distribute your content.
> Everybody is getting all excited about Reddit, YouTube, Quora, LinkedIn, all of
> these sites showing up in the citations [...] Everybody in the SEO world said,
> 'This isn't SEO.' Well, welcome to the new age."

*Source: Ross Simmonds, "Content Distribution in the Age of AI," listed Oct 2025 — [`ross-simmonds-content-distribution-in-the-age-of-ai.md`](./research/youtube-transcripts/ross-simmonds-content-distribution-in-the-age-of-ai.md) · https://www.youtube.com/watch?v=VXxFJAg7YJw*

This is independently corroborated by Lily Ray from the retrieval side: LLMs "are
heavily influenced by Wikipedia, Reddit, and YouTube."

### 2.6 The technical floor for AI crawlers is *higher* than for Googlebot

The most concrete, immediately actionable finding in the research, and the one
most likely to be silently costing teams visibility:

> "[Google is] very sophisticated at [rendering] and they render JavaScript [...]
> but the reality is that AI crawlers don't do it at all. So if you rely on
> client-side rendered JavaScript for critical content or navigation and so on —
> well, this is information that AI crawlers won't see."

*Source: Aleyda Solís, "AI Search Crawlability" — [`aleyda-solis-ai-search-crawlability-and-why-your-site-tech-foundations-de.md`](./research/youtube-transcripts/aleyda-solis-ai-search-crawlability-and-why-your-site-tech-foundations-de.md)*

She adds that AI crawler user agents differ from Googlebot's, so allow-listing
must be checked at the hosting and CDN layer separately.

> **Operating consequence:** A site can rank in Google and be invisible to
> ChatGPT for a purely mechanical reason. This is checked once, at
> [Step 0](#step-0--preflight-run-once-then-quarterly), not per article.

---

## 3. The workflow at a glance

```mermaid
flowchart TD
    S0["STEP 0 · Preflight<br/>crawlability, AI user agents, render check"] --> S1
    S1["1 · Topic selection<br/>+ information-asymmetry routing"] --> S2
    S2["2 · Search intent research"] --> S3
    S3["3 · SERP + AI answer analysis"] --> S4
    S4["4 · Entity & topical authority planning"] --> S5
    S5["5 · Content brief"] --> S6
    S6["6 · AI prompting"] --> S7
    S7["7 · Draft generation"] --> S8

    S8["8 · Fact verification"] --> G1{"Gate A<br/>every claim sourced?"}
    G1 -- no --> S8
    G1 -- yes --> S9

    S9["9 · Human editing<br/>expert inserts what AI cannot know"] --> G2{"Gate B<br/>information gain present?"}
    G2 -- no --> KILL["KILL or reroute<br/>do not publish"]
    G2 -- yes --> S10

    S10["10 · SEO optimisation"] --> S11
    S11["11 · Internal linking"] --> S12
    S12["12 · Retrieval test<br/>ORIGINAL - see §8"] --> G3{"Gate C<br/>answerable from passage alone?"}
    G3 -- no --> S9
    G3 -- yes --> S13

    S13["13 · Publishing"] --> S14
    S14["14 · Distribution"] --> S15
    S15["15 · Measurement<br/>rankings + citations"] --> S1

    style KILL fill:#7f1d1d,stroke:#dc2626,color:#fff
    style G1 fill:#78350f,stroke:#f59e0b,color:#fff
    style G2 fill:#78350f,stroke:#f59e0b,color:#fff
    style G3 fill:#78350f,stroke:#f59e0b,color:#fff
    style S12 fill:#1e3a8a,stroke:#3b82f6,color:#fff
```

**Three gates, one kill switch.** The design intent is that Gate B can stop a
piece permanently. A workflow without a kill switch is a publishing schedule, not
a quality system.

---

## 4. Complete Step-by-Step SOP

### Step 0 · Preflight (run once, then quarterly)

| | |
|---|---|
| **Purpose** | Ensure AI crawlers can physically retrieve your content. Skipping this makes every later step worthless for AI visibility. |
| **Expected output** | A signed-off crawlability check; a list of any client-side-rendered critical content. |

**Actions**

- [ ] Confirm critical content and navigation are **server-rendered**, not client-side JS.
- [ ] Allow-list AI crawler user agents at hosting **and** CDN level — these are separate from Googlebot and are commonly blocked by default bot protection.
- [ ] Check `robots.txt` does not block AI user agents you intend to permit.
- [ ] Fetch a representative page with JavaScript disabled. If the body copy vanishes, AI crawlers see nothing.

**Common mistakes**
- Assuming Googlebot's rendering ability generalises. It does not.
- Testing only `robots.txt` while the CDN's bot-protection layer silently 403s AI agents.

> **Sources:** Aleyda Solís, "AI Search Crawlability and Why Your Site's Tech
> Foundations Decide Visibility," listed 2025 —
> [`aleyda-solis-...`](./research/youtube-transcripts/aleyda-solis-ai-search-crawlability-and-why-your-site-tech-foundations-de.md)
> · https://www.youtube.com/watch?v=pqrwpXpMM6s

---

### Step 1 · Topic selection

| | |
|---|---|
| **Purpose** | Choose topics where you can win, and decide *how much human effort* each deserves before any writing starts. |
| **Expected output** | A prioritised topic list, each tagged **A / B / C** by information asymmetry. |

**Actions**

1. Build the candidate list from keyword research, sales-call objections, support tickets, and competitor gaps.
2. Route every topic through the **information-asymmetry test** — the operational form of Mordy Oberstein's argument in [§2.3](#23-ai-is-acceptable-where-you-have-nothing-to-add-and-dangerous-where-you-do):

| Tier | Test | Treatment | Human cost |
|---|---|---|---|
| **A** | We hold data, customer evidence, or practitioner experience the training corpus does not | AI drafts structure only; expert supplies all substance | High — worth it |
| **B** | Well-covered topic, but we have a defensible angle or a fresher fact base | AI drafts; expert adds the differentiator; kill if no differentiator survives editing | Medium |
| **C** | Fully commoditised, we add nothing | Deprioritise. If published for coverage reasons, accept commodity status and spend minimal review | Low |

3. Kill C-tier topics unless they are structurally required to complete a topical cluster ([Step 4](#step-4--entity--topical-authority-planning)).

**Common mistakes**
- Sorting purely by volume and difficulty. That selects for exactly the commodity topics where AI output is worthless.
- Treating tier C as "easy wins." At scale they are the pages that make a site look like a content farm.

**Recommended tools** — any keyword tool you already own (Semrush / Ahrefs / GSC); the routing decision is human.

> **Sources:** Mordy Oberstein, "SEO Branding and AI Content," listed Jan 2023 —
> [`mordy-oberstein-...`](./research/youtube-transcripts/mordy-oberstein-seo-branding-and-ai-content-with-mordy-oberstein-head-of-seo.md)
> · https://www.youtube.com/watch?v=npmVxc_5Tqo
> Kevin Indig, "The SEO Playbook for the AI Age," listed May 2025 —
> [`kevin-indig-...`](./research/youtube-transcripts/kevin-indig-the-seo-playbook-for-the-ai-age-with-kevin-indig.md)

---

### Step 2 · Search intent research

| | |
|---|---|
| **Purpose** | Establish what the searcher actually wants, and which page experience satisfies it. |
| **Expected output** | Intent classification + the page type that matches it. |

Bernard Huang's B2B mapping is the most directly usable framework in the source
set. He sorts B2B queries into four page experiences: **topic clusters**
(everything-you-need-to-know guides), **articles/resources** (how-to,
benefits-of), **comparison pages**, and **use-case / solutions pages**. He also
names the political obstacle honestly — that many B2B software companies "don't
necessarily want to create the [...] top-10 list of email marketing software and
link out to or talk about your competitors," while acknowledging it is
nonetheless effective.

**Actions**
- [ ] Classify intent: informational / commercial-investigation / transactional / navigational.
- [ ] Map to the matching page type above. Mismatches here cannot be fixed by better writing later.
- [ ] For commercial-investigation queries, decide the comparison-page question deliberately rather than by default avoidance.

**Common mistakes**
- Writing a guide for a comparison query. The intent mismatch caps the ceiling regardless of quality.

> **Sources:** Bernard Huang, "How to do B2B Content Strategy & SEO"
> (Clearscope Office Hours), listed 2024 —
> [`bernard-huang-how-to-do-b2b-content-strategy...`](./research/youtube-transcripts/bernard-huang-how-to-do-b2b-content-strategy-and-seo-clearscope-office-hou.md)
> · https://www.youtube.com/watch?v=VNXjG1OZxPw

---

### Step 3 · SERP **and AI answer** analysis

| | |
|---|---|
| **Purpose** | Understand what currently wins — in blue links *and* in the AI answer, which are different competitions. |
| **Expected output** | A SERP summary plus a **query fan-out list** and the domains currently cited. |

This is where the playbook diverges most from a pre-2024 SOP. Run the query
through an AI assistant with reasoning visible and capture the **query fan-out** —
the set of sub-searches the model performs to construct its answer.

Huang's demonstration is instructive: running a supply-chain software query, the
model's fan-out surfaced **G2 and Gartner** as explicitly cited sources, while the
client brand was absent entirely. That absence is the finding — it tells you the
gap is third-party presence, not on-site content.

**Actions**
- [ ] Record the top 10 organic results and the page type of each.
- [ ] Run the query in ChatGPT / Gemini / Perplexity. Capture: which domains are cited, whether you appear, and the fan-out sub-queries.
- [ ] Treat the fan-out list as a **content requirements list** — each sub-query is something your page (or cluster) must answer.
- [ ] Note whether review/aggregator sites (G2, Gartner, Capterra) dominate citations. If they do, on-site content alone will not close the gap.

**Common mistakes**
- Analysing the SERP and stopping. The AI answer is a separate competition with a partly different winner set.
- Running the query once. Citations are volatile; sample a few times.

**Recommended tools** — ChatGPT / Gemini / Perplexity with reasoning shown; Clearscope, Profound, or Peec for citation tracking (vendor-reported efficacy — see [§9](#9-weaknesses-of-this-playbook)).

> **Sources:** Bernard Huang, "How To Do AEO: Prompt Research, Query Fan Out,
> Content," listed Feb 2026 —
> [`bernard-huang-how-to-do-aeo...`](./research/youtube-transcripts/bernard-huang-how-to-do-aeo-prompt-research-query-fan-out-content-live-ses.md)
> · https://www.youtube.com/watch?v=RMg2eTZL7Jk
> Lily Ray, MozCon 2025, on query fan-out as an evolution of People Also Ask and
> long-tail research —
> [`lily-ray-geo-aeo-llmo...`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)

---

### Step 4 · Entity & topical authority planning

| | |
|---|---|
| **Purpose** | Decide the cluster this page belongs to, so coverage compounds instead of scattering. |
| **Expected output** | A topical map: cluster head, supporting pages, and the entities each must cover. |

Koray Tuğberk Gübür's contribution is the underlying model — that authority is
earned by covering a topic completely rather than by publishing individual strong
pages, and that the *sequence* of publication matters. His framing of topical
maps is the most developed treatment available, though it is also the least
accessible: in his own interview the host raises directly that "people say that
you over-complicate things."

Nick Jordan arrives at a compatible conclusion from a purely empirical direction —
his approach is described as winning "authority on the basis of producing a large
volume of content," with heavy emphasis on **internal linking** and **topical
relevance**. I adopt the topical-completeness and internal-linking half of his
model and reject the volume target; the reasoning is in
[Disagreement 1](#71-disagreement-1--volume-versus-selectivity) and
[§8 Rejected](#8-what-i-rejected-and-why).

**Actions**
- [ ] Define the cluster head and the supporting pages required for the cluster to be *complete*, not merely started.
- [ ] List entities (products, standards, competitors, named methods) each page must mention.
- [ ] Sequence publication: foundational/definitional pages before comparative and advanced ones.
- [ ] Merge the [Step 3](#step-3--serp-and-ai-answer-analysis) fan-out queries into the map — see [Original Idea 2](#idea-2--use-query-fan-out-as-the-topical-map-input).

**Common mistakes**
- Publishing the high-volume commercial page first and never completing the cluster beneath it.
- Building the map from keywords alone rather than from entities and questions.

> **Sources:** Koray Tuğberk Gübür, "How Topical Authority SEO Works," listed
> Mar 2024 —
> [`koray-tugberk-gubur-how-topical-authority-seo-works.md`](./research/youtube-transcripts/koray-tugberk-gubur-how-topical-authority-seo-works.md)
> · https://www.youtube.com/watch?v=pIKfKowzauQ
> Nick Jordan, "How Nick Jordan Grows Sites to Over 100k Organic Views a Month
> Without Link Building" —
> [`nick-jordan-how-nick-jordan-grows-sites...`](./research/youtube-transcripts/nick-jordan-how-nick-jordan-grows-sites-to-over-100k-organic-views-a-mon.md)
> · https://www.youtube.com/watch?v=wW_t3btaxAk
> ⚠️ *Attribution note: the "800 articles a month" and "down to 20 articles a
> month" figures are spoken by the host summarising Jordan's method in the
> episode introduction, not by Jordan directly.*

---

### Step 5 · Content brief

| | |
|---|---|
| **Purpose** | Front-load every decision that AI cannot make, so the draft stage is mechanical. |
| **Expected output** | A brief that a competent writer — or a model — could execute without further questions. |

**The brief must contain**

- [ ] Primary query + the fan-out sub-queries from [Step 3](#step-3--serp-and-ai-answer-analysis)
- [ ] Intent classification and page type from [Step 2](#step-2--search-intent-research)
- [ ] Tier (A/B/C) from [Step 1](#step-1--topic-selection) — this sets the review budget
- [ ] **The information-gain requirement, stated explicitly**: what will this page contain that no competing page contains? If this field is empty, the page is not ready to draft.
- [ ] Named author and why they are credible on this topic
- [ ] Entities that must appear
- [ ] Internal links in and out
- [ ] The atomic questions the page must answer in self-contained form

**Common mistakes**
- Treating the brief as a keyword list plus a word count. That produces exactly the interchangeable output that fails Gate B.
- Leaving the information-gain field blank and hoping it emerges in editing. It does not.

> **Sources:** Bernard Huang on information gain, "How to Rank SEO Content in the
> Era of Generative AI," listed Aug 2023 —
> [`bernard-huang-how-to-rank-seo-content...`](./research/youtube-transcripts/bernard-huang-how-to-rank-seo-content-in-the-era-of-generative-ai.md)
> · https://www.youtube.com/watch?v=ZytMamXMG0M
> Lily Ray on atomic answers, MozCon 2025 —
> [`lily-ray-geo-aeo-llmo...`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)

---

### Step 6 · AI prompting

| | |
|---|---|
| **Purpose** | Convert the brief into a draft without importing the model's generic priors. |
| **Expected output** | A draft that is structurally correct and factually flagged. |

**Practice**

- Supply the brief as context rather than describing it. Paste the fan-out queries, the entity list, and the information-gain requirement verbatim.
- Supply *your* raw material — interview notes, product data, support transcripts — and instruct the model to build from it. A model given nothing proprietary can only return the consensus of its training data, which is by definition what every competitor will also produce.
- Instruct the model to **mark every factual claim it cannot support from supplied material**. This turns [Step 8](#step-8--fact-verification) from an open-ended hunt into a checklist.
- Generate section by section against the brief's structure. Whole-article generation reverts to generic shape.

**Common mistakes**
- "Write a 2,000-word article about X." This is the single highest-volume failure mode in AI content production.
- Asking the model for facts it has no way to know — this is where fabrication enters.

⚠️ *Evidence note: no source in this research provides tested prompt templates or
comparative prompt efficacy data. This step is assembled from the sources'
principles plus practical inference, and is the least evidence-backed step in the
playbook.*

---

### Step 7 · Draft generation

| | |
|---|---|
| **Purpose** | Produce a complete draft, understood as raw material rather than as a near-final article. |
| **Expected output** | A sectioned draft with claims flagged for verification. |

Set the expectation explicitly with the team: the draft is the *cheapest* part of
the process and carries the *least* value. The value is added at Steps 8–9. Teams
that treat the draft as 90% done invert the economics that make this workflow
worthwhile.

**Common mistakes**
- Measuring team productivity in drafts produced. It measures the one input that is now nearly free.

---

### Step 8 · Fact verification — **Gate A**

| | |
|---|---|
| **Purpose** | Ensure no unverified claim reaches publication. |
| **Expected output** | Every factual claim either sourced, or cut. Binary. |

**Actions**
- [ ] Take the model's flagged claims plus every statistic, date, name, and citation.
- [ ] Verify each against a primary source. A second AI model is **not** verification — correlated training data produces correlated errors.
- [ ] Cut anything that cannot be sourced. Do not soften it into vagueness; cut it.
- [ ] Pay disproportionate attention to anything recent. Per Oberstein, a change in the underlying facts is precisely where models remain confidently wrong.

> **Practitioner note.** This playbook's own repository is a worked example of
> this failure. During research, unverifiable statistics were formatted as
> quotations and would have propagated into this document had they not been
> caught by exactly this check. See
> [`research/SOURCE-AUDIT.md`](./research/SOURCE-AUDIT.md). The gate is not
> theoretical.

**Common mistakes**
- Verifying with a second LLM.
- Verifying the surprising claims and trusting the mundane ones. Fabrications are usually mundane.

> **Sources:** Mordy Oberstein on AI and newly-changed facts, listed Jan 2023 —
> [`mordy-oberstein-seo-branding...`](./research/youtube-transcripts/mordy-oberstein-seo-branding-and-ai-content-with-mordy-oberstein-head-of-seo.md)

---

### Step 9 · Human editing — **Gate B (kill switch)**

| | |
|---|---|
| **Purpose** | Insert what the model structurally cannot know, and kill pieces where nothing was inserted. |
| **Expected output** | Either a piece carrying genuine information gain, or a killed topic. |

This is the step that determines whether the whole workflow produces an asset or
a liability. Oberstein's formulation is "peer-reviewed, meaning human-reviewed AI
work" — review as a condition of publishing, not a courtesy pass.

**The expert must add at least one of**

| Contribution | Why AI cannot supply it |
|---|---|
| Proprietary data or internal benchmarks | Not in training data |
| First-hand practitioner experience | Not in training data, and E-E-A-T's "Experience" |
| A named, defended opinion | Models regress to consensus |
| Correction of the consensus where it is wrong | Models reproduce the consensus |
| Current information post-dating the corpus | Structurally unavailable |

**Gate B rule:** if the editor cannot point at a specific passage that satisfies
one of these rows, **the piece does not publish.** Reroute to tier C or kill it.

**Common mistakes**
- Editing for tone and calling it review. Rewriting generic content in your voice leaves it generic.
- Allowing "we edited it thoroughly" to substitute for a named contribution.

> **Sources:** Mordy Oberstein, listed Jan 2023 —
> [`mordy-oberstein-seo-branding...`](./research/youtube-transcripts/mordy-oberstein-seo-branding-and-ai-content-with-mordy-oberstein-head-of-seo.md)
> Kevin Indig on trust-first positioning, listed May 2025 —
> [`kevin-indig-the-seo-playbook...`](./research/youtube-transcripts/kevin-indig-the-seo-playbook-for-the-ai-age-with-kevin-indig.md)

---

### Step 10 · SEO optimisation

| | |
|---|---|
| **Purpose** | Apply on-page fundamentals — as a floor, not as the strategy. |
| **Expected output** | An optimised page that would still be worth reading with the optimisation stripped out. |

Kyle Roof's testing work establishes that on-page technical signals carry more
weight than practitioners often assume — he reports maintaining pages ranking in
positions one and two built on placeholder Latin text "with the math done." His
own assessment of that as content advice, unprompted, is that it is "pretty
terrible."

The correct reading: **treat on-page precision as a floor you clear cheaply, not
as a substitute for substance.** Full reasoning in
[Disagreement 3](#73-disagreement-3--do-technical-on-page-signals-outrank-content-quality).

**Actions**
- [ ] Title, H1, headings reflect the query and the atomic questions
- [ ] Entities from [Step 4](#step-4--entity--topical-authority-planning) present
- [ ] Schema appropriate to page type (FAQ, HowTo, Article)
- [ ] Author markup pointing to a real, credentialed profile
- [ ] Answers placed high, in self-contained form
- [ ] **Do not** optimise for embeddings or engineer chunk boundaries ([§2.4](#24-write-atomic-answers-do-not-try-to-engineer-the-chunking))

> **Sources:** Kyle Roof, "EEAT and the Future of SEO with Artificial
> Intelligence," listed 2023 —
> [`kyle-roof-kyle-roof-talks-eeat...`](./research/youtube-transcripts/kyle-roof-kyle-roof-talks-eeat-and-the-future-of-seo-with-artificial-i.md)
> · https://www.youtube.com/watch?v=SniZRx1PXdg
> Lily Ray on embeddings-optimisation as spam, MozCon 2025 —
> [`lily-ray-geo-aeo-llmo...`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)

---

### Step 11 · Internal linking

| | |
|---|---|
| **Purpose** | Make the cluster legible as a structure rather than as a pile of pages. |
| **Expected output** | Every new page integrated into the cluster in both directions. |

Internal linking is one of the few tactics endorsed across otherwise
disagreeing sources — it is central to Jordan's volume model *and* to Gübür's
semantic model, which is reason to weight it.

**Actions**
- [ ] Link up to the cluster head, down to supporting pages, and laterally to siblings
- [ ] Descriptive anchor text — this is a relevance signal, not decoration
- [ ] Retrofit links **from** existing pages **to** the new one. Most teams skip this half and it is where most of the value sits.

---

### Step 12 · Retrieval test — **Gate C** 🔵 *(original — see [§8](#8-my-original-ideas))*

| | |
|---|---|
| **Purpose** | Verify empirically that the page's answers survive extraction, before publishing. |
| **Expected output** | Pass/fail per atomic answer block. |

Full rationale in [§8, Idea 1](#idea-1--the-retrieval-regression-test). In brief:
paste each atomic answer block in isolation into a model with web access
disabled, ask the target question, and check whether it can answer correctly
**from that passage alone**. Failures return to [Step 9](#step-9--human-editing--gate-b-kill-switch).

---

### Step 13 · Publishing

**Actions**
- [ ] Real author byline, real bio, real credentials, linked profile
- [ ] Accurate publish date. **Do not** back-date or bump dates without substantive change — Lily Ray specifically warns against what Google calls "artificial refreshening," noting Google "has ways of demoting this type of content."
- [ ] Confirm the published page is server-rendered ([Step 0](#step-0--preflight-run-once-then-quarterly))

> **Sources:** Lily Ray, MozCon 2025 —
> [`lily-ray-geo-aeo-llmo...`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)

---

### Step 14 · Content distribution

| | |
|---|---|
| **Purpose** | Build the third-party presence that both link-based ranking and citation-based retrieval depend on. |
| **Expected output** | Publication plus a distribution set, executed as one unit of work. |

Ross Simmonds' position is that distribution is not optional follow-up but part
of production. Lily Ray's retrieval-side observation — that LLMs are "heavily
influenced by Wikipedia, Reddit, and YouTube" — supplies the mechanism, and her
caution is worth reproducing: on Reddit "you can get banned if you're being
overly promotional," so contributions should be "authentic," including "honest
conversations when customers have problems with your brand."

**Actions**
- [ ] Reformat for each destination — YouTube, LinkedIn, Reddit, communities. Not link-drops.
- [ ] Where [Step 3](#step-3--serp-and-ai-answer-analysis) showed aggregators (G2, Gartner) dominating citations, treat presence there as a distribution objective in its own right.
- [ ] Produce at least one non-text format. Multimodal retrieval is real and video is disproportionately cited.

**Common mistakes**
- Posting the link and calling it distribution.
- Promotional Reddit activity, which is net-negative and can be account-fatal.

> **Sources:** Ross Simmonds, listed Oct 2025 —
> [`ross-simmonds-content-distribution-in-the-age-of-ai.md`](./research/youtube-transcripts/ross-simmonds-content-distribution-in-the-age-of-ai.md)
> Lily Ray, MozCon 2025 —
> [`lily-ray-geo-aeo-llmo...`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)

---

### Step 15 · Performance measurement

| | |
|---|---|
| **Purpose** | Measure both competitions — ranking and citation — without over-reacting to the smaller one. |
| **Expected output** | A dashboard covering traditional and AI-visibility metrics, with correct proportionality. |

**Traditional** — rankings, organic sessions, conversions, and the
impressions-up/clicks-down divergence Lily Ray calls the "Google Search Console
alligator mouth effect."

**AI visibility** — per Ray's proposed KPI set: branded impressions; share of
voice in AI search; direct and organic clicks to the homepage (LLM
recommendations often produce navigational rather than referral traffic); AI
visibility by topic; and engagement/conversion from AI-sourced traffic, grouped
into a custom GA4 segment.

> **Proportionality warning — this is the number most likely to be misused.**
> Ray reports that grouped LLM referral traffic remains small: Glenn Gabe
> observed roughly 1% on average across his clients, and Amsive "about one to
> maybe now 2%," against organic search that "for many sites could be 30, 40,
> 50% of their overall traffic." She also cites Semrush data indicating ChatGPT
> use *increases* Google usage — from 10.5 to 12.6 sessions per week — and
> Google's Robby Stein describing AI search as "expansionary."
>
> Budget accordingly. AI visibility is strategically important and currently
> small. Both halves of that sentence matter.

**Common mistakes**
- Reallocating budget on the basis of AI-search enthusiasm rather than measured contribution.
- Reading falling clicks as a content failure when impressions are rising — that is often the zero-click shift, not a quality problem.

> **Sources:** Lily Ray, MozCon 2025 (all figures above) —
> [`lily-ray-geo-aeo-llmo...`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)
> Brendan Hufford on click intent, listed 2025 —
> [`brendan-hufford-from-seo-to-aeo...`](./research/youtube-transcripts/brendan-hufford-from-seo-to-aeo-how-answer-engine-optimization-is-replacing.md)
> · https://www.youtube.com/watch?v=lMyYbBHXuG8

---

## 5. Cadence and staffing

Derived from the workflow above rather than from any single source, and offered
as a starting point to be calibrated:

| Team size | Sustainable A/B-tier output | Notes |
|---|---|---|
| 1 generalist | 2–4 pieces / month | Gate B is the bottleneck, and it should be |
| 2–3 with one SME | 6–10 / month | SME time is the constraint, not writing time |
| 5 with dedicated SMEs | 15–25 / month | Beyond this, review quality degrades before volume does |

The constraint is **expert review capacity**, not drafting capacity. Any plan
that treats drafting as the bottleneck is planning against the wrong constraint.

---

## 6. Quick reference checklist

```
PREFLIGHT
  □ Server-side rendering confirmed for critical content
  □ AI crawler user agents allow-listed (host + CDN)

PER PIECE
  □ Tier assigned (A/B/C) by information asymmetry
  □ Intent classified, page type matched
  □ Query fan-out captured; cited domains recorded
  □ Cluster + entities defined
  □ Brief written — information-gain field NOT empty
  □ Proprietary material supplied to the model
  □ Draft generated section-by-section
  □ GATE A · every claim verified against a primary source
  □ GATE B · named expert contribution present — else KILL
  □ On-page fundamentals applied (no embedding-gaming)
  □ Internal links, both directions, retrofitted
  □ GATE C · retrieval test passed
  □ Real author, real date, no artificial refreshening
  □ Distributed in ≥2 formats to ≥2 destinations
  □ Added to ranking + citation tracking
```

---

## 7. Where Experts Disagree

These are real conflicts in the source material, not manufactured ones. In each
case both parties are competent practitioners with evidence, which is what makes
the disagreement worth resolving rather than splitting.

---

### 7.1 Disagreement 1 — Volume versus selectivity

> **The issue:** Should an AI-assisted content operation optimise for throughput
> or for per-piece quality? This determines the entire shape of the workflow.

**Position A — Nick Jordan: win authority through volume.**

Jordan's method is described in the episode introduction as producing "800
articles a month for a website," with the underlying logic that you "win
authority on the basis of producing a large volume of content." The corollary is
explicit and aggressive: "by doing that, you don't have to focus on things like
backlinks and a lot of the on-page technical things." The host notes it has
worked "all the way down to 20 articles a month."

*Source: "How Nick Jordan Grows Sites to Over 100k Organic Views a Month Without Link Building" — [`nick-jordan-how-nick-jordan-grows-sites-to-over-100k-organic-views-a-mon.md`](./research/youtube-transcripts/nick-jordan-how-nick-jordan-grows-sites-to-over-100k-organic-views-a-mon.md) · https://www.youtube.com/watch?v=wW_t3btaxAk*
⚠️ *These figures are spoken by the host characterising Jordan's approach, not by Jordan directly. Weight accordingly.*

**Position B — Mordy Oberstein and Lily Ray: quality is the gate.**

Oberstein's position is conditional rather than anti-volume — AI content is fine
"where there's probably nothing new I can add," and a liability where facts have
changed. Critically, he identifies the mechanism by which volume advice goes
wrong at scale: AI writing tools "solve such a powerful pain point" that adoption
outruns judgement, and the predictable result is people "running listicles [...]
writing very thin content, it's fluff." His prescription is "peer-reviewed,
meaning human-reviewed AI work."

*Sources: [`mordy-oberstein-seo-branding-and-ai-content...`](./research/youtube-transcripts/mordy-oberstein-seo-branding-and-ai-content-with-mordy-oberstein-head-of-seo.md); [`lily-ray-geo-aeo-llmo...`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)*

**Weighing the evidence**

| | Jordan | Oberstein / Ray |
|---|---|---|
| Evidence type | Repeated first-party results across multiple sites | Aggregate observation (Wix scale) + agency client base |
| Verifiable here? | Self-reported, relayed by a host | Self-reported, but multi-site and directionally corroborated |
| Era | Pre-dates AI Overviews and the AI content glut | Spans the transition |
| Falsifiable? | Partly — the sites exist | Weakly |

**My conclusion: adopt Jordan's *architecture*, reject his *volume target and his dismissal of technical SEO*.**

Three reasons.

1. **The strategy is time-indexed and the clock ran out.** Jordan's advantage came from producing more content than competitors could afford to. AI removed that cost asymmetry for everyone simultaneously. A tactic whose entire edge was relative cost cannot survive the cost going to zero across the market. What remains valuable is *why* it worked — topical completeness and internal linking — which is exactly what [Step 4](#step-4--entity--topical-authority-planning) retains.

2. **"You don't need on-page technical" is now falsified by a mechanism that did not exist when he said it.** Aleyda Solís's finding that AI crawlers do not render JavaScript at all means technical retrievability is a *precondition* for AI citation, not an optimisation. Jordan's advice was defensible for Googlebot in 2022. It is not defensible for the retrieval layer in 2026.

3. **Volume was never the causal variable — it was a proxy for coverage.** 800 articles that complete a topic map and 800 that do not produce different outcomes. Once you name the real variable, you can pursue it at 10 articles a month.

**What I take from Jordan anyway:** internal linking discipline and topical relevance, both of which he emphasises and both of which survive into [Steps 4 and 11](#step-4--entity--topical-authority-planning). His observation that he approached SEO "from a fresh perspective" without "Legacy Panda and Penguin" baggage is also a fair critique of the industry's tendency to over-index on historical trauma.

---

### 7.2 Disagreement 2 — Is AEO/GEO a separate discipline?

> **The issue:** Does optimising for AI answers require a distinct process, team,
> and budget — or is it the existing SEO process under a new name?

**Position A — Lily Ray: it is substantially just SEO.**

Ray's MozCon case is the most heavily evidenced argument in the entire research
set, and she assembles it from sources hostile to her own commercial interest:

- Google's Danny Sullivan "confirmed that good SEO is really the same thing as good GEO."
- Google's John Mueller characterises embedding-optimisation as "literally [...] keyword stuffing, which is a form of spam."
- Britney Müller: "every single URL that you see in an LLM output actually comes from a search engine API, Google or Bing."
- On the tactics themselves: chunking is formatting plus schema, which "we've been doing since 2011"; multimodal content, digital PR, and query fan-out all map onto existing practice.
- On magnitude: LLM referral traffic is ~1–2% versus 30–50% from organic.

**Position B — Bernard Huang and Brendan Hufford: the workflow is genuinely new.**

Huang has built a distinct operational process — prompt research, query fan-out
capture, citation tracking — with tooling behind it. His demonstration shows
something a SERP report does not: which domains a model *reasons over* (G2,
Gartner) and whether the brand appears at all.

Hufford makes the strongest business-impact claim in the research, about his own
firm: "we get 90-plus percent of our new business from inbound organic, and we've
seen in this calendar year 2025 [...] close to 60% of the people coming to us —
it used to be 98.9% from Google — it's now answer engines."

*Sources: [`bernard-huang-how-to-do-aeo...`](./research/youtube-transcripts/bernard-huang-how-to-do-aeo-prompt-research-query-fan-out-content-live-ses.md); [`brendan-hufford-from-seo-to-aeo...`](./research/youtube-transcripts/brendan-hufford-from-seo-to-aeo-how-answer-engine-optimization-is-replacing.md)*

**Weighing the evidence**

Hufford's number is the most striking figure in the research and also the one
requiring the most caution. It is **n=1, self-reported, and drawn from the single
most selection-biased population imaginable**: people who find an *AI-SEO
consultancy* are, definitionally, people already using AI tools to search. A
98.9% → 60% shift in that population tells us little about a recruiting product,
a manufacturer, or a healthcare provider. Hufford does not claim otherwise — he
offers it as his own experience — but it circulates as though it were market data.

Ray's evidence is broader, better sourced, includes disconfirming data, and
draws on Google statements against the industry's commercial interest.

**My conclusion: Ray is right about the content process; Huang is right about the measurement layer. Split the question.**

The reason the disagreement persists is that both sides are answering
*different questions* while using the same vocabulary:

| Question | Answer | Whose position |
|---|---|---|
| Do I need a different **content production process**? | **No.** Retrievable content is well-made content. | Ray |
| Do I need different **research inputs**? | **Partly.** Query fan-out reveals what a SERP report does not. | Huang |
| Do I need a different **measurement system**? | **Yes.** Rank tracking cannot see citations. | Huang, Ray (on KPIs) |
| Should I **reallocate significant budget** to AEO today? | **No** — at 1–2% of traffic, build measurement first. | Ray |

This is why the playbook has **one** content workflow and **two** measurement
tracks. Teams that build a parallel "GEO team" are solving an organisational
problem that the evidence does not support.

---

### 7.3 Disagreement 3 — Do technical on-page signals outrank content quality?

> **The issue:** If a page can rank on structural signals alone, how much is
> substance actually worth?

**Position A — Kyle Roof: on-page mechanics are more powerful than admitted.**

Roof won a ranking competition using Lorem Ipsum placeholder text, and reports
this was not a one-off: "I've got several sites still up right now that are Lorem
Ipsum sites, and ranking in the number one spot for their terms [...] they're
just Lorem Ipsum pages with the math done."

Notably, he volunteers the caveat himself. Asked whether this is content advice,
he answers: "maybe not the best advice — no, in fact, it's pretty terrible."

*Source: [`kyle-roof-kyle-roof-talks-eeat-and-the-future-of-seo-with-artificial-i.md`](./research/youtube-transcripts/kyle-roof-kyle-roof-talks-eeat-and-the-future-of-seo-with-artificial-i.md) · https://www.youtube.com/watch?v=SniZRx1PXdg*

**Position B — Huang, Ray, Indig: substance is the differentiator.**

Huang's information-gain thesis holds that content ranks when it adds something
absent from the existing corpus. Indig locates the mechanism in trust as a
selection criterion. Ray's E-E-A-T work makes experience the scarce input.

**My conclusion: Roof is empirically right and strategically obsolete — and the reason is retrieval.**

I want to be careful here, because Roof's methodology is more rigorous than most
of what the industry produces. He runs controlled tests; his critics mostly run
opinions. Dismissing him because his conclusion is unfashionable would be exactly
the failure of skepticism this playbook is trying to avoid.

But three constraints bound the finding:

1. **Regime.** Lorem Ipsum ranking demonstrates that ranking systems can be satisfied structurally in **low-competition, low-YMYL** niches. It does not demonstrate this in competitive commercial verticals, and Roof does not claim it does.

2. **It cannot survive the retrieval layer.** A Lorem Ipsum page can occupy a blue link. It cannot be *cited* by an answer engine, because citation requires the model to extract a proposition and reproduce it. There is nothing to extract. As the retrieval layer takes share — even at Ray's modest 1–2% and rising — the strategy has a structural ceiling that on-page precision cannot raise.

3. **Roof himself does not recommend it.** "It's pretty terrible" advice. His work is a *proof about ranking systems*, not a *content strategy*, and it is frequently cited as though it were the latter.

**Practical resolution:** clear the on-page floor cheaply and precisely — Roof's
work justifies taking it more seriously than "write well and it'll be fine" — and
then compete on substance, because substance is the only input that works in both
competitions.

---

### 7.4 Disagreement 4 — Should you restructure content for LLM ingestion?

> **The issue:** The most common tactical advice in AI-SEO — chunk your content,
> optimise for embeddings, format for machine ingestion. Does it work?

**Position A — the prevailing GEO advice.** Ray catalogues it as the dominant
2025 message: content "must be properly chunked, converted to vector embeddings,
and measured with cosine similarity, or else you'll be invisible in AI search."

**Position B — Ray, citing Google.** Chunking is "an AI engineering function,"
not an SEO one; models "not you, decide how to slice your content," every model
chunks differently and changes it "for speed, accuracy, and cost considerations."
John Mueller equates embedding-optimisation with keyword stuffing.

**My conclusion: side with Ray, but keep the useful half.**

The advice contains a good instruction wrapped in a bad mechanism. The good
instruction — write self-contained answers that survive being lifted out of
context — is real, and is Gate C in this playbook. The bad mechanism — trying to
control tokenisation you cannot observe — is unfalsifiable by construction and
carries live spam risk given Mueller's characterisation.

Adopt the *behaviour* (atomic answers). Reject the *theory* (embedding
engineering). Notably, this is the one place where the playbook's original
contribution — [the retrieval test](#idea-1--the-retrieval-regression-test) —
exists specifically because the good half of this advice had no verification
method attached to it.

---

## 8. What I Rejected and Why

Ideas present in the research that I deliberately excluded.

---

### Rejection 1 — Publishing volume as a primary strategy

**Recommendation rejected:** Win authority by publishing at high volume (800/month
cited, 20/month floor), and de-prioritise backlinks and on-page technical work.

**Source:** Nick Jordan, as characterised in
[`nick-jordan-how-nick-jordan-grows-sites-to-over-100k-organic-views-a-mon.md`](./research/youtube-transcripts/nick-jordan-how-nick-jordan-grows-sites-to-over-100k-organic-views-a-mon.md)

**Why rejected**

- The edge was **cost asymmetry**, and AI eliminated it for all competitors at once. A relative-cost advantage cannot survive the cost collapsing market-wide.
- The technical dismissal is now **affirmatively wrong** for AI retrieval — Solís's rendering finding makes technical retrievability a precondition, not a nicety.
- Volume was a **proxy for coverage**, and coverage can be pursued directly at a tenth of the output.

**Risks of adopting it**
- Site-level quality classification. Mordy Oberstein's account of thin content proliferation describes precisely this pattern.
- Expert review capacity is exceeded, so Gate B silently degrades into rubber-stamping — the failure is invisible until a core update surfaces it.
- Sunk cost in pages that are expensive to audit and awkward to remove.

**Retained:** internal linking discipline; topical relevance as the objective;
the outsider's skepticism toward inherited SEO folklore.

---

### Rejection 2 — On-page mathematics as a content strategy

**Recommendation rejected:** Optimise on-page signals with sufficient precision
that content substance becomes secondary.

**Source:** Kyle Roof,
[`kyle-roof-kyle-roof-talks-eeat-and-the-future-of-seo-with-artificial-i.md`](./research/youtube-transcripts/kyle-roof-kyle-roof-talks-eeat-and-the-future-of-seo-with-artificial-i.md)

**Why rejected**

- **Structurally incompatible with citation.** An answer engine must extract a proposition; optimised-but-empty content offers none. This closes off the fastest-growing retrieval channel permanently.
- **Narrow validity regime** — demonstrated in low-competition, low-YMYL terms.
- **Roof's own assessment**: "it's pretty terrible" as content advice. I am not overriding him; I am agreeing with him.

**Risks of adopting it** — brand damage on any page a human actually reads;
zero defensibility once a competitor publishes substance; direct exposure to
quality-focused core updates.

**Retained:** on-page precision as a cheap floor, and — more valuable — Roof's
insistence on **controlled testing over consensus opinion**. That methodological
stance is the best thing in his body of work and is why Gate C is designed as a
*test* rather than a guideline.

---

### Rejection 3 — Date-bumping for recency

**Recommendation rejected (implicitly, as widespread practice):** refresh publish
dates to signal currency, given that recency influences citation.

**Source:** the practice is widespread; the counter-evidence is Lily Ray,
[`lily-ray-geo-aeo-llmo...`](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md)

**Why rejected** — Ray notes recency genuinely matters for citation, which makes
the temptation real, and then closes it off: she does "not recommend what Google
calls artificial refreshening," believes "Google has ways of demoting this type
of content," and adds that it is "just not that great for users."

**Risk** — the tactic is detectable, the downside is site-level, and the upside
is a signal you can earn honestly by actually updating the page.

---

### Rejection 4 — Vendor-reported citation-lift figures as evidence

**Recommendation rejected:** using self-reported tool-vendor case studies to
justify AEO investment.

**Why rejected** — Several vendor figures circulated in the research phase (see
[`research/SOURCE-AUDIT.md`](./research/SOURCE-AUDIT.md)). They are unaudited,
methodologically undisclosed, and produced by parties selling the solution. They
may well be accurate. They are not *evidence*, and this playbook does not build
recommendations on them. Where citation-tracking tools are named in
[Step 3](#step-3--serp-and-ai-answer-analysis), they are named as options with
that caveat attached.

---

## 9. My Original Ideas

Neither appears in the source material. Both extend it rather than departing from it.

---

### Idea 1 — The Retrieval Regression Test

**Problem.** The research converges on an instruction — Lily Ray's "clear,
self-contained, atomic answers that stand on their own, whether a human being
reads them or an AI extracts them" — and then leaves it as a matter of taste.
Nobody in the source set describes a way to *check* whether a given passage
actually satisfies it. Meanwhile Ray demonstrates that the popular alternative
(engineering chunk boundaries) is both unobservable and possibly spam. So
practitioners are told to hit a target they cannot see.

**Solution.** Test extraction directly, before publishing. For each atomic answer
block:

1. Copy the block **in isolation** — no surrounding page, no title, no context.
2. Paste it into an LLM **with web access disabled**.
3. Ask the target question from the [Step 3](#step-3--serp-and-ai-answer-analysis) fan-out list.
4. Score:

| Result | Meaning | Action |
|---|---|---|
| Answers correctly and completely | Passage is self-contained | **Pass** |
| Answers but omits a key qualifier | Passage leaks context | Revise |
| Cannot answer without the rest of the page | Not atomic | Rewrite |
| Answers *incorrectly* | Passage is actively misleading out of context | **Block — highest priority** |

Run it across the fan-out set and you get a coverage matrix: which of the
questions a model asks are answerable from your page in isolation.

**Why it might work**

- It tests the actual mechanism. Retrieval extracts passages; this evaluates passages under extraction conditions.
- It converts an aesthetic judgement into a **pass/fail gate**, which is what makes it enforceable in a workflow rather than aspirational.
- It respects Ray's constraint. It does not attempt to control chunking — it verifies robustness *across* chunking strategies, which is the part you can actually influence.
- It is nearly free, needs no vendor tooling, and is scriptable via any model API for CI-style regression runs across a whole library.
- The fourth row catches a real and under-discussed risk: passages that are correct in context and wrong out of it. That is a reputational hazard specific to the retrieval era, and no source in this research addresses it.

**Risks and honest limitations**

- ⚠️ **Untested.** I have not run this at scale. It is a reasoned proposal, not a validated method.
- Passing does not imply citation. Retrieval depends on authority, freshness, and competition — this tests only necessary, not sufficient, conditions.
- Model-specific: results vary between models. Mitigate by testing across two or three and treating disagreement as a weak signal.
- Gameable if misapplied — optimising to pass the test could produce stilted, disconnected prose. The test is a floor check, not a writing style.

---

### Idea 2 — Use query fan-out as the topical map input

**Problem.** Two strong ideas in this research never meet. Koray Tuğberk Gübür's
topical maps define what completeness means but are built largely from keyword and
entity analysis — a process his own interviewer notes people find
over-complicated. Bernard Huang's query fan-out reveals exactly which sub-questions
a model considers necessary to answer a topic — but is used almost entirely as a
*post-hoc audit* ("did we get cited?").

The fan-out is a model telling you, explicitly, what it believes a complete
treatment of a topic requires. That is a topical map, generated by the system you
are trying to satisfy.

**Solution.** Invert the sequence. Before planning a cluster:

1. Run the head topic through 2–3 assistants with reasoning visible.
2. Harvest the full fan-out set across runs and models.
3. Deduplicate and cluster the sub-queries.
4. **Assign each cluster to a page.** The fan-out set becomes the cluster's page inventory.
5. Track coverage: fan-out queries with no owning page are gaps, in the specific sense that a model already thinks they matter.

**Why it might work**

- It grounds topical mapping in observed machine behaviour instead of inferred semantics — lowering the expertise barrier that limits adoption of Gübür's method.
- It optimises for both competitions simultaneously: fan-out queries are real user questions, so pages built against them serve traditional search too.
- It gives cluster completeness a **measurable stopping condition**, which topical-map methods generally lack.

**Risks**

- ⚠️ Untested at scale, and fan-out output is volatile between runs — mitigate by sampling repeatedly.
- Risks over-fitting to current model behaviour, which changes without notice.
- Fan-out reflects what models search for, which is not identical to what your buyers need. It supplements commercial judgement; it does not replace it.

---

## 10. Weaknesses of This Playbook

Where this document is weakest, stated plainly.

### 10.1 Untested assumptions

| Assumption | Status |
|---|---|
| Gate B (kill switch) is enforceable in a real team under deadline | **Untested.** The first missed quarter is the real test, and I would expect it to bend. |
| The A/B/C routing produces better allocation than intuition | **Untested.** Plausible, unmeasured. |
| The retrieval test predicts citation | **Untested.** Necessary-condition logic only. |
| Fan-out-derived maps beat keyword-derived maps | **Untested.** |
| The staffing table in [§5](#5-cadence-and-staffing) reflects real capacity | **Inferred, not measured.** Treat as a hypothesis. |

### 10.2 Limitations of the evidence base

- **Almost everything is self-reported.** Roof's controlled testing is the exception, and his conclusions are the ones I largely set aside. The rest is practitioner testimony — valuable, but not experimental.
- **Selection bias in the expert pool.** Every one of the ten makes their living from search being complicated enough to need specialists. None has an incentive to say "do less of this."
- **Vendor incentives.** Huang sells content-optimisation software; Gübür sells a course; Roof sells an on-page tool; Oberstein was employed by a website platform. This does not invalidate their arguments — it means their emphases should be read with the incentive in view.
- **Unequal depth.** Lily Ray's MozCon transcript is dense, current, and heavily evidenced. Only one Aleyda Solís transcript was collected, and her rendering finding — arguably the most actionable item in the entire playbook — rests on a **single source**. Gübür's transcripts are long on philosophy and short on reproducible procedure.
- **Recency skew.** The Oberstein transcripts are from early 2023 and pre-date AI Overviews entirely. His reasoning generalises well, but he is not commenting on the current SERP.
- **Geographic and sector skew.** Anglophone, US/Europe, heavily B2B SaaS. E-commerce, local, and non-English search are underrepresented, and the conclusions should not be assumed to transfer.

### 10.3 What is missing

- **No cost model.** Gate B is expensive and this playbook never quantifies it. The honest version of "kill the piece" is "absorb the sunk cost," and no source addresses when that stops being rational.
- **No treatment of failure recovery** — what to do with an existing library of thin AI content. Prune, improve, or noindex? The research does not answer it and neither do I.
- **No YMYL guidance.** Health, finance, and legal carry materially different risk. This playbook should not be applied there without additional review.
- **Nothing on multilingual production**, where AI assistance is most tempting and quality control hardest.

### 10.4 Where the workflow will fail

1. **No genuine subject-matter expert.** Gate B has no meaning if nobody can supply information the model lacks. The playbook then degrades to a slower way of producing commodity content.
2. **Volume-based targets.** The gates and the quota are in direct conflict, and the quota wins.
3. **Genuinely commoditised categories** where no information asymmetry exists. Here Jordan's rejected model may actually outperform this one — an honest concession.
4. **Rapidly changing subject matter**, where verification cost exceeds drafting savings and AI assistance may be net-negative.

### 10.5 Shelf life

The specific figures — 1–2% LLM referral traffic, the current fan-out behaviour,
which crawlers render JavaScript — will date fastest, plausibly within two
quarters. **The principles should outlive them; the numbers should be
re-measured, not inherited.** Re-verify §2.6 and Step 15 quarterly.

---

## 11. Who I Would Not Recommend Following — and Why

A note on intent: this critiques *the fit between a body of work and this
specific use case*. Everyone here is an accomplished practitioner, and in two of
three cases my objection is one the expert has already voiced themselves.

---

### Primary — Kyle Roof, as a guide to AI content production

**Recommendation:** Do not use as a primary source for content strategy. Do use
for testing methodology.

**Reasoning**

His Lorem Ipsum results are real and, by his account, still live: pages "in the
number one spot for their terms [...] just Lorem Ipsum pages with the math done."
The methodology behind that — controlled tests rather than assertion — is more
rigorous than most of the industry.

The mismatch is with *this* use case:

1. **The strategy cannot produce citable content.** An answer engine must extract a proposition. Structurally optimised, semantically empty pages offer nothing to extract. This is not a quality objection; it is a mechanical one, and it closes off the growing retrieval channel entirely.
2. **He says so himself.** Asked directly whether it constitutes good content advice: "in fact, it's pretty terrible." I am agreeing with him, not contradicting him.
3. **His AI-search read looks weak in hindsight.** In the same interview he characterises ChatGPT as "really just a featured snippet type feature rather than an actual search engine." Given a 2023 date that is a forgivable call, but it means the transcript is not a reliable guide to the current landscape.
4. **Incentive.** His conclusions consistently favour on-page precision; he sells an on-page optimisation tool. Not disqualifying, but relevant to weighting.

**Where he *should* be followed:** test design and healthy skepticism toward
consensus. Gate C is built in his spirit — test the mechanism rather than
trusting the folklore.

---

### Secondary — Nick Jordan, for volume strategy specifically

**Recommendation:** Do not follow the volume model. Do follow the internal-linking
and topical-relevance work.

**Reasoning**

1. **Time-indexed advantage.** The edge was outspending competitors on production. AI removed that asymmetry for everyone at once.
2. **The technical dismissal is now wrong.** "You don't have to focus on [...] on-page technical things" is directly contradicted by Solís's finding that AI crawlers do not render JavaScript. What was survivable for Googlebot is disqualifying for retrieval.
3. **Attribution caution.** The headline figures reach us via a host's summary, not from Jordan. He is on record that the concept works at far lower volumes — the "800 articles" framing may be doing him a disservice.
4. **Era.** The material pre-dates AI Overviews and the AI content glut. It answers a question about a market that no longer exists.

**Where he *should* be followed:** internal linking, topical completeness, and a
useful outsider's impatience with inherited SEO superstition.

---

### Qualified caution — Koray Tuğberk Gübür

**Not a "do not follow" — a caution about cost of adoption.**

His topical-authority framework is the most intellectually serious model in the
research, and the patent-reading approach is genuinely differentiated. Two
practical caveats:

1. **Accessibility.** The over-complication critique is raised in his own interview by the host, and the transcripts bear it out — long on theory, thin on reproducible procedure. A small team will struggle to operationalise it without significant investment.
2. **Incentive.** The framework is also a course product. That does not make it wrong; it does mean complexity is not commercially penalised.

**Recommendation:** adopt the *concept* — coverage completeness and publication
sequence, as in [Step 4](#step-4--entity--topical-authority-planning) — without
committing to the full apparatus. Original Idea 2 is an attempt at a cheaper
route to the same destination.

---

### Whom I would weight most heavily

For balance, the inverse judgement:

| Expert | Why weighted highly |
|---|---|
| **Lily Ray** | Cites disconfirming evidence, sources against her own commercial interest, quantifies magnitude, distinguishes hype from mechanism. The strongest single source in this set. |
| **Aleyda Solís** | The rendering finding is concrete, testable, and immediately actionable. ⚠️ Single transcript — should be corroborated. |
| **Mordy Oberstein** | Provides the routing logic the whole playbook depends on, and is neither an AI booster nor a denier. |
| **Bernard Huang** | The only source demonstrating a reproducible AEO research procedure end to end. |
| **Kevin Indig** | Grounds trust claims in an unusually good source — Google's DOJ disclosures. |

---

## 12. References

All transcripts are in [`/research/youtube-transcripts/`](./research/youtube-transcripts/),
retrieved via the Supadata API. Dates are as listed at collection and, per
[`research/SOURCE-AUDIT.md`](./research/SOURCE-AUDIT.md), were **not independently
verified**; those marked ⚠️ could not be verified at all.

### Primary sources cited in this playbook

| # | Author | Title | Date (listed) | Link |
|---|---|---|---|---|
| 1 | Lily Ray | GEO, AEO, LLMO: Separating Fact from Fiction (MozCon 2025 online adaptation) | Nov 2025 | [YouTube](https://www.youtube.com/watch?v=2nJkT8zOzcM) · [transcript](./research/youtube-transcripts/lily-ray-geo-aeo-llmo-separating-fact-from-fiction-mozcon-2025.md) |
| 2 | Aleyda Solís | AI Search Crawlability and Why Your Site's Tech Foundations Decide Visibility | 2025 | [YouTube](https://www.youtube.com/watch?v=pqrwpXpMM6s) · [transcript](./research/youtube-transcripts/aleyda-solis-ai-search-crawlability-and-why-your-site-tech-foundations-de.md) |
| 3 | Bernard Huang | How To Do AEO: Prompt Research, Query Fan Out, Content (Clearscope live session) | Feb 2026 | [YouTube](https://www.youtube.com/watch?v=RMg2eTZL7Jk) · [transcript](./research/youtube-transcripts/bernard-huang-how-to-do-aeo-prompt-research-query-fan-out-content-live-ses.md) |
| 4 | Bernard Huang | How to do B2B Content Strategy & SEO (Clearscope Office Hours) | 2024 | [YouTube](https://www.youtube.com/watch?v=VNXjG1OZxPw) · [transcript](./research/youtube-transcripts/bernard-huang-how-to-do-b2b-content-strategy-and-seo-clearscope-office-hou.md) |
| 5 | Bernard Huang | How to Rank SEO Content in the Era of Generative AI | Aug 2023 | [YouTube](https://www.youtube.com/watch?v=ZytMamXMG0M) · [transcript](./research/youtube-transcripts/bernard-huang-how-to-rank-seo-content-in-the-era-of-generative-ai.md) |
| 6 | Mordy Oberstein | SEO Branding and AI Content | Jan 2023 | [YouTube](https://www.youtube.com/watch?v=npmVxc_5Tqo) · [transcript](./research/youtube-transcripts/mordy-oberstein-seo-branding-and-ai-content-with-mordy-oberstein-head-of-seo.md) |
| 7 | Kevin Indig | The SEO Playbook for the AI Age | May 2025 | [YouTube](https://www.youtube.com/watch?v=eepyi-NYFiM) · [transcript](./research/youtube-transcripts/kevin-indig-the-seo-playbook-for-the-ai-age-with-kevin-indig.md) |
| 8 | Ross Simmonds | Content Distribution in the Age of AI | Oct 2025 | [YouTube](https://www.youtube.com/watch?v=VXxFJAg7YJw) · [transcript](./research/youtube-transcripts/ross-simmonds-content-distribution-in-the-age-of-ai.md) |
| 9 | Kyle Roof | EEAT and the Future of SEO with Artificial Intelligence | 2023 | [YouTube](https://www.youtube.com/watch?v=SniZRx1PXdg) · [transcript](./research/youtube-transcripts/kyle-roof-kyle-roof-talks-eeat-and-the-future-of-seo-with-artificial-i.md) |
| 10 | Nick Jordan | How Nick Jordan Grows Sites to Over 100k Organic Views a Month Without Link Building | 2023 | [YouTube](https://www.youtube.com/watch?v=wW_t3btaxAk) · [transcript](./research/youtube-transcripts/nick-jordan-how-nick-jordan-grows-sites-to-over-100k-organic-views-a-mon.md) |
| 11 | Brendan Hufford | From SEO to AEO: How Answer Engine Optimization Is Replacing Search for B2B Marketers | 2025 | [YouTube](https://www.youtube.com/watch?v=lMyYbBHXuG8) · [transcript](./research/youtube-transcripts/brendan-hufford-from-seo-to-aeo-how-answer-engine-optimization-is-replacing.md) |
| 12 | Koray Tuğberk Gübür | How Topical Authority SEO Works | Mar 2024 | [YouTube](https://www.youtube.com/watch?v=pIKfKowzauQ) · [transcript](./research/youtube-transcripts/koray-tugberk-gubur-how-topical-authority-seo-works.md) |

### Third parties cited *within* those sources

Reported by the speaker above; I did not independently verify these.

| Attributed to | Claim | Reported by |
|---|---|---|
| Danny Sullivan (Google) | Good SEO is effectively the same as good GEO | Lily Ray |
| John Mueller (Google) | Optimising for embeddings is "keyword stuffing", a form of spam | Lily Ray |
| Britney Müller | Every URL in an LLM output comes from a search engine API (Google/Bing) | Lily Ray |
| Robby Stein (Google) | AI search is "expansionary" — additive to Google search | Lily Ray |
| Glenn Gabe | ~1% of client traffic from LLM referrers | Lily Ray |
| Semrush | Google sessions/week rose 10.5 → 12.6 after ChatGPT adoption | Lily Ray |
| Rand Fishkin / SparkToro | Traditional search usage broadly flat through 2025 | Lily Ray |
| Dana DiTomaso | GA4 methodology for segmenting AI-sourced traffic | Lily Ray |
| Dan Petrovic | GPT-5's dependence on retrieval grounding | Lily Ray |

### Additional collected material — consulted, not quoted

- [`research/sources.md`](./research/sources.md) — index of all 10 experts
- [`research/other/additional-sources.md`](./research/other/additional-sources.md) — 11 newsletters, podcasts, webinars; all URLs verified HTTP 200 on 2026-08-08
- [`research/linkedin-posts/`](./research/linkedin-posts/) — **not quoted**; see [`SOURCE-AUDIT.md`](./research/SOURCE-AUDIT.md)
- 15 further transcripts collected but not cited above

---

*Playbook v1.0 · 08 August 2026 · Kapil*
*Built from 27 verbatim transcripts. Quotations are traceable to named files.
Where evidence is thin, the document says so.*
