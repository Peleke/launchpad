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

## What We Have (Receipts)

<div class="grid grid-cols-2 gap-8 mt-4">
<div>

<v-click>

### <span class="green">Verified</span>

- Princeton CS, edX Principal ($60MM+ ARR), AWS SA
- qortex, bilrost, Vindler, qortex-observe, cadence
- STRIDE threat model + 5 PoC exploits
- 20+ Agent Skills (buildlog extraction)
- This entire validation pipeline

</v-click>

</div>
<div>

<v-click>

### <span class="red">Still Needed</span>

- Published articles (15 drafts in queue)
- Published STRIDE findings
- 30 days learning-loop data
- Course-specific audience (0 today)
- Testimonials (pre-launch = zero)

</v-click>

</div>
</div>

---
layout: center
transition: slide-up
---

## The Ask

<v-click>
<p class="stat-big">3 articles by April 1.</p>
</v-click>

<v-click>
<p class="stat-big" style="font-size:2.2rem;">Workshop by April 15.</p>
</v-click>

<v-click>
<p class="stat-big" style="font-size:2.2rem;">15 presale students or kill.</p>
</v-click>

<v-click>

<p class="text-lg mt-8">Review the landing page on Vercel preview</p>
<p class="text-lg">Review the full pitch deck in the Obsidian vault</p>

</v-click>

<v-click>
<p class="muted text-sm mt-8">Every number in this deck traces back to a signal scan, decision log, or persona extract.</p>
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
