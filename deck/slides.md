---
theme: default
title: 'Production Agent Engineering — Validation Summary'
info: |
  Hunter pipeline validation results for Production Agent Engineering cohort + security workshop.
  Built 2026-03-05.
class: text-white
layout: cover
background: '#0d1117'
drawings:
  persist: false
transition: slide-left
css: unocss
fonts:
  sans: Inter
  mono: Fira Code
  provider: google
---

# Production Agent Engineering

<v-click>
<p class="text-2xl coral">Validation Summary — 2026-03-05</p>
</v-click>

<v-click>
<p class="muted text-sm mt-8">Hunter Pipeline: signal-scan → decision-log → persona-extract → offer-scope → pitch → assets</p>
</v-click>

<!--
This deck walks through the full output of running the hunter pipeline against ourselves. Six stages, structured scoring, kill criteria with dates attached. Everything traces back to a signal scan or a direct quote.
-->

---
transition: slide-up
---

## The Opportunity

<v-click>
<img src="/opportunity-gap.svg" style="width:100%;max-width:700px;margin:0 auto;display:block;" />
</v-click>

<v-click>
<p class="text-center text-lg mt-2">Every course teaches how to <span class="coral">build</span> an agent. Nobody teaches why <span class="red">90% die in production</span>.</p>
</v-click>

<!--
The left side is commoditized. Andrew Ng, Udemy, Anthropic Academy, Skool communities. The right side is what actually happens when you deploy. RAND Corporation found 80-90% of AI projects fail to reach production. The gap between "build a demo" and "operate at 2 AM when it breaks" is where we sit.
-->

---
transition: fade
---

## Evidence Wall

<v-click>
<img src="/evidence-wall.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

<!--
37 signals from the scan. Five independent sources confirmed the same pain point: engineers can build agents but can't debug them in production. The Carnegie Mellon stat (agents wrong ~70% of the time) and the MIT stat (95% of businesses found zero value from AI) are the anchors. The 94% skills gap number comes from an industry survey of engineering leaders.
-->

---

## Reddit Voices

<v-click>

> "The worst part is I can't figure out WHERE things go wrong. Is it the retrieval? The tool selection? The synthesis?"
>
> <cite>— r/AI_Agents (10 upvotes)</cite>

</v-click>

<v-click>

> "Frameworks get you to a demo, but prod failure modes are mostly systems problems"
>
> <cite>— u/Santoshr93, r/ExperiencedDevs</cite>

</v-click>

<v-click>

> "No, but many will pretend they did to sell their services"
>
> <cite>— r/AI_Agents (20 upvotes), on "Has anyone actually deployed agents to production?"</cite>

</v-click>

<!--
These are direct quotes with source URLs. The first captures the observability gap. The second reframes agents as systems problems, not AI problems. The third is the trust problem: the format itself (online AI course) triggers contempt because of how many people have been burned.
-->

---
transition: slide-up
---

## SDP Scoring

<v-click>
<img src="/sdp-scoring.svg" style="width:100%;max-width:700px;margin:0 auto;display:block;" />
</v-click>

<!--
Six weighted dimensions. Pain intensity at 3x, spend evidence at 3x, competitive edge match at 2x, time to ship at 2x, competition gap and audience fit at 1x each. Range is 12 to 60. The cohort scored 50. Highest score the pipeline has produced on anything we've tested. "Do nothing" scored 20 as a baseline sanity check.
-->

---

## Three Personas

<v-click>
<img src="/three-personas.svg" style="width:100%;max-width:750px;margin:0 auto;display:block;" />
</v-click>

<!--
Each persona has minimum three pain stories with direct quotes and engagement metrics. The Midnight Firefighter is highest volume and strongest immediate pain. The Reluctant Architect is harder to convert but higher lifetime value. The Security-Conscious Lead opens the consulting path at 5K-15K per engagement.
-->

---
transition: fade
---

## Four Forces of Switching

<v-click>
<img src="/four-forces.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

<!--
Push is strong: production failures, 2 AM debugging, no traces. Pull is strong: receipts-first credibility, published exploits, open-source reference systems. Inertia is moderate: engineers learn on the job and distrust courses. Anxiety is the blocker. The trust deficit in AI education is deep enough that the format itself repels the target buyer. That's why the articles ship before the product.
-->

---

## Two Offers

<v-click>
<img src="/two-offers.svg" style="width:100%;max-width:740px;margin:0 auto;display:block;" />
</v-click>

<!--
Offer A is the four-week cohort on Maven. Architecture decisions, OTel instrumentation, statistical testing, STRIDE modeling. 749 founding, 997 after. Offer B is the three-hour STRIDE workshop at 497 plus consulting audits. The workshop was originally a separate opportunity that scored 45/60, so we absorbed it as a second offer tier.
-->

---
transition: slide-up
---

## The Curriculum Stack

<v-click>
<img src="/curriculum-stack.svg" style="width:100%;max-width:650px;margin:0 auto;display:block;" />
</v-click>

<!--
Week 1 is OpenTelemetry for agent systems. Instrument, trace, diagnose. Week 2 is statistical testing for non-deterministic behavior. Week 3 is the STRIDE threat modeling module, built from the actual exploits we published. Week 4 is proving value or killing the project with data. Each week has a reference implementation students can fork.
-->

---

## Revenue Model

<v-click>
<img src="/revenue-model.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

<!--
Four revenue streams. The cohort is the anchor at roughly 100K annual. Enterprise team licenses add 30 to 50K. STRIDE workshops at 30K. Security audits at 60-80K, which is the highest margin stream. Combined range is 220-260K. Next slide breaks down the unit economics.
-->

---
transition: fade
---

## Competitive Map

<v-click>
<object data="/competitive-map.svg" type="image/svg+xml" style="width:100%;max-width:720px;margin:0 auto;display:block;"></object>
</v-click>

<!--
Two axes: price and depth. Bottom-left is commoditized: Ng, Anthropic Academy, Udemy. Middle is Skool communities and IndyDevDan. Hamel Husain owns evals and sits mid-high on depth. We sit top-right: production depth at 749-997. The gap between Husain and us is that his curriculum covers evals but not the production engineering layer underneath. The buyers overlap but the depth doesn't.
-->

---

## Execution Calendar

<v-click>
<img src="/execution-calendar.svg" style="width:100%;max-width:740px;margin:0 auto;display:block;" />
</v-click>

<!--
Six weeks from signal to kill-or-scale. Articles by March 8. LinWheel series and public repo by March 15. Workshop landing page March 22. Free workshop March 29. Presale opens April 5. Kill decision April 14. If we hit 15 presales, cohort 1 runs April 21 through May 18.
-->

---
transition: slide-up
---

## Kill Criteria

<v-click>
<img src="/kill-criteria.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

<!--
Three gates. Gate 1 at week 1: fewer than 5 enrollments triggers a contingency plan. Gate 2 at month 1: fewer than 15 enrollments kills the cohort. Gate 3 at month 3: less than 15K combined revenue kills the business line entirely. The pivot trigger is enterprise demand exceeding individual demand, which would flip us to an enterprise-first model.
-->

---
transition: fade
---

## Bias Check

<v-click>
<img src="/bias-check.svg" style="width:100%;max-width:700px;margin:0 auto;display:block;" />
</v-click>

<!--
Mandatory check on every decision log. Confirmation bias: warning, because excitement may inflate our perceived edge. Availability and anchoring: both pass, data held up across re-scoring. Excitement bias: flagged. The evidence is real but it's private. Fifteen draft articles, production systems in private repos, STRIDE findings unpublished. The score looks great and the proof is invisible. That's why we publish first.
-->

---
transition: slide-up
---

## Revenue Breakdown

<v-click>

| Stream | Unit Economics | Annual Estimate |
|---|---|---|
| **Cohort** (4 runs × 25 seats × $997) | $997/seat | ~$100K |
| **Enterprise licenses** | team pricing | $30–50K |
| **STRIDE workshops** (4 × $7.5K) | $497/seat or $7.5K private | ~$30K |
| **Security audits** (6–8 × $10K) | $5K–15K/engagement | $60–80K |
| | **Combined** | **$220–260K** |

</v-click>

<v-click>
<p class="muted text-sm mt-4">Assumes 4 cohort runs/year with 60% fill rate after founding cohort.</p>
</v-click>

<!--
The 60% fill rate assumption is conservative. Maven's top courses run at 80%+ after the first two cohorts. The founding cohort at 749 is a loss leader to generate testimonials and case studies. Full price is 997. Enterprise pricing is TBD but the pilot conversations start after cohort 1.
-->

---
layout: center
transition: slide-up
---

## Next Steps

<v-click>

| Milestone | Deadline | Kill Condition |
|---|---|---|
| 3 articles published | April 1 | Reassess timeline |
| Free workshop shipped | April 15 | Kill if no traction |
| 15 presale students at $749 | April 14 | Kill cohort |
| $15K combined revenue | July 15 | Kill business line |

</v-click>

<!--
Four milestones, four deadlines, four consequences. The articles are the prerequisite for everything downstream. Without published receipts, the landing page is a brochure for someone nobody trusts yet. The presale threshold is the real gate: 15 students at 749 or we don't build.
-->

---
transition: fade
---

## Appendix — Asset Map

| Artifact | Location |
|---|---|
| Signal Scan | `Signal-Scans/production-agent-engineering.md` |
| Decision Log | `Decisions/production-agent-engineering.md` |
| Persona Extract | `Personas/production-agent-engineering.md` |
| Offer Scope | `Offers/production-agent-engineering.md` |
| Pitch | `Pitches/production-agent-engineering.md` |
| Content Seeds | `Content-Briefs/*.md` |
| Landing Page | `launchpad/index.html` (Vercel preview) |
| This Deck | `launchpad/deck/slides.md` |
| Kanban | Obsidian vault — Product-Discovery board |
| PR | `github.com/Peleke/launchpad` — `production-agent-engineering` |

<p class="muted text-sm mt-4">All artifacts generated by the hunter pipeline: signal-scan → decision-log → persona-extract → offer-scope → pitch → assets</p>

<!--
Every artifact is in the Obsidian vault or the launchpad repo. The Kanban board tracks status across the pipeline stages. The PR has the full diff.
-->

---
layout: center
transition: fade
---

<p class="text-2xl" style="color:#eee0cc;">Built with the hunter pipeline.</p>

<p class="muted mt-4">signal-scan → decision-log → persona-extract → offer-scope → pitch → assets</p>

<p class="muted text-sm mt-8">2026-03-05</p>

<!--
The pipeline that generated this deck is the same pipeline we're teaching. The course sells the method by demonstrating it. If someone asks "does this work," we point at the deck they just watched.
-->
