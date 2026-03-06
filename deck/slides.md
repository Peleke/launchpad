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

---
transition: fade
---

## Evidence Wall

<v-click>
<img src="/evidence-wall.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

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

---
transition: slide-up
---

## SDP Scoring

<v-click>
<img src="/sdp-scoring.svg" style="width:100%;max-width:700px;margin:0 auto;display:block;" />
</v-click>

---

## Three Personas

<v-click>
<img src="/three-personas.svg" style="width:100%;max-width:750px;margin:0 auto;display:block;" />
</v-click>

---
transition: fade
---

## Four Forces of Switching

<v-click>
<img src="/four-forces.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

---

## Two Offers

<v-click>
<img src="/two-offers.svg" style="width:100%;max-width:740px;margin:0 auto;display:block;" />
</v-click>

---
transition: slide-up
---

## The Curriculum Stack

<v-click>
<img src="/curriculum-stack.svg" style="width:100%;max-width:650px;margin:0 auto;display:block;" />
</v-click>

---

## Revenue Model

<v-click>
<img src="/revenue-model.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

---
transition: fade
---

## Competitive Map

<v-click>
<img src="/competitive-map.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

---

## Execution Calendar

<v-click>
<img src="/execution-calendar.svg" style="width:100%;max-width:740px;margin:0 auto;display:block;" />
</v-click>

---
transition: slide-up
---

## Kill Criteria

<v-click>
<img src="/kill-criteria.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

---
transition: fade
---

## Bias Check

<v-click>
<img src="/bias-check.svg" style="width:100%;max-width:700px;margin:0 auto;display:block;" />
</v-click>

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

<v-click>
<p class="muted text-sm mt-6">Every threshold has a date and a consequence. Not "reassess if things don't go well."</p>
</v-click>

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

---
layout: center
transition: fade
---

<p class="text-2xl" style="color:#eee0cc;">Built with the hunter pipeline.</p>

<p class="muted mt-4">signal-scan → decision-log → persona-extract → offer-scope → pitch → assets</p>

<p class="muted text-sm mt-8">2026-03-05</p>
