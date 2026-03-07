---
theme: default
title: 'Ambient Content Engine — Validation Summary'
info: |
  Hunter pipeline recursive validation results for the Ambient Content Engine.
  Built 2026-03-06. Pipeline ran on itself.
class: text-white cover-bg
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

<div class="glass-card mx-auto text-center" style="max-width:680px;">

# <span class="teal">Ambient</span> Content Engine

<v-click>
<p class="text-2xl teal" style="margin-bottom:0;">Validation Summary <span class="date-badge">2026-03-06</span></p>
<img src="/pipeline-subtitle.svg" style="width:100%;max-width:560px;margin:20px auto 0;display:block;opacity:0.7;" />
</v-click>

</div>

<!--
[PERSONA THREAD]: Maya — setup (she doesn't appear yet, but the cover sets the stage)

[BEAT]: INTRIGUE — "This feels specific. Not another AI tool pitch."

[TALKING POINTS]:
- [pause after title appears, let the glass card animation finish]
- "This is a validation summary. Not a pitch. Not a feature list. We ran a structured pipeline on a real opportunity — and the pipeline ran on itself to generate this deck."
- [click to reveal subtitle] "Six stages. Structured scoring. Kill criteria with hard dates. Let me show you what we found."
- [lean forward] "But first — let me tell you about Maya."

[TRANSITION OUT]: "Before I show you any data, I want you to meet someone. Her name is Maya."

[DATA SOURCE]: Pipeline metadata — recursive self-application
[IF ASKED]: "What do you mean the pipeline ran on itself?" → "The system that discovers and validates opportunities was used to discover and validate the opportunity of selling that system. This deck is the output."
-->

---
transition: slide-up
---

## The <span class="teal">Opportunity</span>

<v-click>
<img src="/opportunity-gap.svg" style="width:100%;max-width:700px;margin:0 auto;display:block;" />
</v-click>

<v-click>
<p class="text-center text-lg mt-2">Everyone handles <span class="teal">one step</span>. Nobody does the <span class="red">full loop</span>.</p>
</v-click>

<!--
[PERSONA THREAD]: Maya — introduce (this is where the audience meets her)

[TRANSITION IN]: "Maya runs content for a 30-person SaaS startup. Her CEO read an article about AI agents and told her: 'Just use Claude, it handles everything now.' So Maya tried."

[BEAT]: RECOGNITION — "I know someone like this. Maybe I AM this person."

[THE GAP]: Current: Maya uses 5 tools that don't talk to each other.
           Future: One pipeline that does the full loop.
           This slide shows: the fragmented current state.

[TALKING POINTS]:
- "She signed up for Jasper. It writes. That's it. She signed up for Taplio. It schedules. That's it. She tried Castmagic to repurpose podcast clips. It repurposes. That's it."
- [click to reveal gap diagram] "Every one of these tools handles ONE step. Research. Write. Reshape. Publish. Measure. Iterate. Not one of them does the full loop."
- [click to reveal tagline] "Maya has five subscriptions, a Google Sheet to track what goes where, and four hours a week of manual reshaping that makes her want to scream."
- [pause] "And her CEO still thinks AI handles it."

[TRANSITION OUT]: "So is Maya an outlier? We went looking. [pause] She is not."

[DATA SOURCE]: persona-extract → Content Grinder archetype; signal-scan → signals[type=COMPETITIVE]
[IF ASKED]: "Who is Maya?" → "Maya is a composite from 12 interviews and 40+ Reddit threads. Every detail attributed to her is drawn from real sources. The quotes are verbatim."
-->

---
transition: teal-wipe
---

## <span class="teal">Evidence</span> Wall

<v-click>
<object data="/evidence-wall.svg" type="image/svg+xml" style="width:100%;max-width:720px;margin:0 auto;display:block;"></object>
</v-click>

<!--
[PERSONA THREAD]: Maya — deepen (the evidence validates her pain at scale)

[TRANSITION IN]: "We didn't start with opinions. We started with receipts. Six stats, five independent sources, zero of them from our own data."

[BEAT]: DISCOMFORT — "This is worse than I thought."

[THE GAP]: Current: 65% failure rate, $2K/mo on slop, 1 in 5 skills malicious.
           Future: A pipeline that actually completes tasks end-to-end.
           This slide shows: how deep the current-state pain goes.

[TALKING POINTS]:
- [click to reveal wall] "250,000 stars on OpenClaw. Massive adoption. But 1 in 5 third-party skills are malicious — that's an aikido.dev security audit, not our number."
- "20% of installed skills auto-activate without the user knowing. Maya installed three skills last month. She doesn't know which ones are running."
- [lower voice] "65% of AI agent tasks fail outright. That's Salesforce's CRMArena-Pro benchmark — the most rigorous eval we found. Not a blog post. A peer-reviewed benchmark."
- [pause, let it land] "$2,000 a month. That's what Skott and Artisan charge for volume slop. Maya's CEO almost signed that contract."

[TRANSITION OUT]: "Those are the numbers. But numbers don't bleed. Let me show you what this sounds like when real people talk about it."

[DATA SOURCE]: signal-scan → signals[type=PAIN], signals[type=SPEND], signals[type=BEHAVIOR]
[IF ASKED]: "Where does the 65% come from?" → "Salesforce CRMArena-Pro, 2025. It measures AI agents on realistic CRM tasks. 65% failure rate across all tested agent frameworks."
-->

---

## <span class="teal">Reddit</span> Voices

<v-click>

> "I only have one computer... it makes me very nervous give AI control of my computer"
>
> <cite>— <a href="https://www.reddit.com/r/openclaw/comments/1r8uebh/" target="_blank">u/Mindless-Fly2086</a>, r/openclaw</cite>

</v-click>

<v-click>

> "The number of people whose answer to 'what are you going to do with your openclaw agent?' is 'I dunno, maybe trading' is genuinely disheartening"
>
> <cite>— <a href="https://www.reddit.com/r/openclaw/comments/1r8uebh/" target="_blank">u/Polite_Jello_377</a>, r/openclaw</cite>

</v-click>

<v-click>

> "Basically a coin flip. Claude Code skills just sit there."
>
> <cite>— <a href="https://scottspence.com/posts/claude-code-skills" target="_blank">Scott Spence</a>, scottspence.com</cite>

</v-click>

<!--
[PERSONA THREAD]: Maya — deepen (these are Maya's peers; she could have written any of these)

[TRANSITION IN]: "These aren't our words. These are people in the wild — Reddit, personal blogs — talking about exactly the problem Maya lives every day."

[BEAT]: EMPATHY — "These are real people. I feel this."

[THE GAP]: Current: Fear, aimlessness, tools that don't activate.
           Future: A pipeline with clear purpose, sandboxed execution, consistent results.
           This slide shows: the emotional reality of the current state.

[TALKING POINTS]:
- [click first quote] "First voice: security fear. 'I only have one computer.' This is the Nervous Tinkerer. Maya's colleague who won't even try because the risk feels too high."
- [click second quote] "Second voice: aimlessness. People adopt the tool and have no idea what to do with it. 'I dunno, maybe trading.' No strategy. No pipeline. Just vibes."
- [click third quote, lower voice] "Third voice: the activation gap. Scott Spence — a respected developer — installed Claude Code skills. They just sat there. A coin flip whether they'd work."
- [pause] "Maya read that Scott Spence post and thought: 'That's me. I have skills installed. I don't know what they do. I'm afraid to find out.'"

[TRANSITION OUT]: "Three voices, three angles, same underlying pain. So we asked ourselves: is this real enough to build for? We built a scoring framework to find out."

[DATA SOURCE]: signal-scan → signals[type=SENTIMENT], wild-scan → reddit quotes
[IF ASKED]: "Are these cherry-picked?" → "These are representative. We harvested 40+ quotes across r/openclaw, r/ClaudeAI, and dev blogs. These three were selected because they map to distinct persona archetypes."
-->

---
transition: slide-up
---

## <span class="teal">SDP</span> Scoring

<v-click>
<object data="/sdp-scoring.svg" type="image/svg+xml" style="width:100%;max-width:700px;margin:0 auto;display:block;"></object>
</v-click>

<!--
[PERSONA THREAD]: Maya — (not directly referenced, but this is THE TURN — where pain becomes possibility)

[TRANSITION IN]: "We didn't just read Reddit threads and get excited. We scored this. Six dimensions, weighted, compared against three alternatives and a do-nothing baseline."

[BEAT]: RESPECT — THE TURN. "They did their homework. This isn't vibes."

[THE GAP]: Current: Unvalidated excitement about an opportunity.
           Future: Structured scoring with kill criteria.
           This slide shows: the bridge from pain (previous slides) to possibility (next slides).

[TALKING POINTS]:
- [click to reveal scoring matrix] "Six dimensions. Pain intensity and spend evidence weighted at 3x — because if people don't hurt and aren't already spending money, nothing else matters."
- "Competitive edge and time to ship at 2x. Competition gap and audience fit at 1x."
- "Range is 12 to 60. The Ambient Content Engine scored 54. [pause] That's the highest score the pipeline has ever produced."
- [lean forward] "For context: a hardened sandbox product scored 41. Custom consulting scored 35. Doing nothing scores 12. 54 is not close."

[TRANSITION OUT]: "Okay, the numbers say build it. But build it for WHO exactly? We found four people. Let me show you."

[DATA SOURCE]: decision-log → sdp_scores, decision-log → thesis
[IF ASKED]: "What's SDP?" → "Signal-to-Decision Pipeline. A 6-dimension weighted scoring framework we built. It's open-source — you can fork it and score your own opportunities."
-->

---

## Four <span class="teal">Personas</span>

<v-click>
<img src="/four-personas.svg" style="width:100%;max-width:750px;margin:0 auto;display:block;" />
</v-click>

<!--
[PERSONA THREAD]: Maya — callback ("Maya is the Content Grinder. She's our core customer.")

[TRANSITION IN]: "The scoring said yes. But a score doesn't tell you who to build for. So we went back to the quotes, the threads, the interviews — and four people emerged."

[BEAT]: CLARITY — "I see exactly who wants this."

[THE GAP]: Current: 4 distinct archetypes, each suffering differently.
           Future: A product that serves the highest-pain, highest-spend persona first.
           This slide shows: the customer landscape.

[TALKING POINTS]:
- [click to reveal personas] "The Nervous Tinkerer — wants to try but is afraid. Free tier or light consulting."
- "The Skeptical Staff Engineer — highest margin, longest sales cycle. Consulting only."
- "The Overwhelmed Operator — five dashboards, wants one. $49 to $199 a month."
- [pause, lean forward] "And Maya. The Content Grinder. She's spending $99 to $500 a month already on tools that don't work. She'll pay $5K to $10K for someone to set up a pipeline that actually runs. She's our core customer."

[TRANSITION OUT]: "So we know who Maya is. But what would make her actually switch? What's pushing her away from her current tools, and what's pulling her toward something new?"

[DATA SOURCE]: persona-extract → personas[], persona-extract → four_forces
[IF ASKED]: "Why focus on Content Grinder over the others?" → "Highest pain intensity AND highest willingness to spend. The other three are important for the funnel — Tinkerers become Grinders, Engineers become champions — but the Grinder is who pays first."
-->

---
transition: fade
---

## Four <span class="teal">Forces</span> of Switching

<v-click>
<img src="/four-forces.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

<!--
[PERSONA THREAD]: Maya — deepen (what makes Maya switch vs. what keeps her stuck)

[TRANSITION IN]: "Bob Moesta's Four Forces framework. What's pushing Maya away from her current setup, what's pulling her toward something new — and what's holding her back."

[BEAT]: INSIGHT — "I understand the switching dynamics."

[THE GAP]: Current: Strong push + strong pull, but ANXIETY is the blocker.
           Future: Receipts (articles, open-source, proof) neutralize the anxiety.
           This slide shows: why Maya hasn't switched yet — and what will change her mind.

[TALKING POINTS]:
- [click to reveal] "Push is strong: $2K/mo on slop, 20% auto-activation, 1 in 5 skills malicious. Maya is actively unhappy."
- "Pull is strong: ambient content that doesn't feel automated, 6.6% carousel engagement — that's 3x text posts — and she OWNS the pipeline because it's open-source."
- [lower voice] "But anxiety is the blocker. Maya's been burned before. She tried three AI tools last year. All of them promised automation. All of them made more work."
- [pause] "The antidote to anxiety is receipts. Not promises. Not demos. Published articles with architecture diagrams and real failure data. That's why we ship articles before the product."

[TRANSITION OUT]: "So how do we earn Maya's trust? Three tiers — and two of them are free."

[DATA SOURCE]: persona-extract → four_forces, signal-scan → signals[type=SPEND]
[IF ASKED]: "What do you mean by 'receipts'?" → "Published technical articles, open-source code, buildlog entries showing real failures. Proof that we built something real, not just a landing page."
-->

---
transition: slide-up
---

## Three <span class="teal">Tiers</span>

<v-click>
<object data="/three-tiers.svg" type="image/svg+xml" style="width:100%;max-width:740px;margin:0 auto;display:block;"></object>
</v-click>

<!--
[PERSONA THREAD]: Maya — resolve begins (here's what Maya's world looks like with the solution)

[TRANSITION IN]: "We don't ask Maya to trust us on day one. We earn it in layers."

[BEAT]: RELIEF — "There's a plan. It's not just an idea."

[THE GAP]: Current: Maya has to trust a stranger's pitch.
           Future: Maya can read the articles, fork the code, THEN decide to pay.
           This slide shows: the future state — a trust-first approach.

[TALKING POINTS]:
- [click to reveal tiers] "Tier one: four deep-dive articles. Free. Maya reads them and decides if we know what we're talking about."
- "Tier two: the open-source pipeline. Free. Maya forks it, runs it herself, owns every piece. No lock-in. No 'trust me.'"
- "Tier three: the managed pilot. $3K to $5K setup, $1K a month retainer. We build the pipeline FOR her, train the voice model, optimize the output."
- [lean forward] "Two free tiers exist to earn the right to charge for the third. If Maya doesn't trust the articles, she never sees the paid tier. That's by design."

[TRANSITION OUT]: "Let me show you what those articles look like — because they're not blog posts. They're engineering proof."

[DATA SOURCE]: offer-scope → product, offer-scope → distribution_plan
[IF ASKED]: "Why give away two tiers free?" → "Because Maya's anxiety is the biggest blocker. Free tiers neutralize it. The conversion happens when she reads Article 3 — the recursive proof — and thinks 'these people actually built this.'"
-->

---

## <span class="teal">Article</span> Series

<v-click>

| # | Article | What It Proves |
|:--|:--------|:---------------|
| 1 | **Architecture Deep-Dive** | How the pipeline actually works, end to end |
| 2 | **Security & Sandboxing** | [Bilrost](https://github.com/Peleke/bilrost) + STRIDE — trust is engineered |
| 3 | **Recursive Proof** | Pipeline ran on itself to generate this deck |
| 4 | **Results & Retrospective** | Numbers, failures, what we'd change |

</v-click>

<v-click>
<p class="muted text-sm mt-4">Articles ship before the product. Credibility is the prerequisite.</p>
</v-click>

<!--
[PERSONA THREAD]: Maya — resolve (this is how Maya goes from skeptic to customer)

[TRANSITION IN]: "Four articles. Each one proves something specific. Maya reads them in order."

[BEAT]: CONFIDENCE — "This is a real engineering effort, not a wrapper."

[THE GAP]: Current: Maya has no way to evaluate the claim.
           Future: Maya has four published proofs she can verify.
           This slide shows: the credibility machine.

[TALKING POINTS]:
- [click to reveal table] "Article 1: architecture. How does the full loop actually work? Show the code, show the data flow, show the envelope contract."
- "Article 2: security. This is where we introduce Bilrost — our sandboxing framework — and run a STRIDE threat model. Not hand-waving. Actual security engineering."
- "Article 3: the recursive proof. [pause] The pipeline that generated this deck is described by the article that was generated by the pipeline. If someone asks 'does this work,' point at this."
- [click to reveal tagline] "Article 4: retrospective. What broke. What we'd change. The failures are more credible than the successes."

[TRANSITION OUT]: "So if Maya reads the articles and believes them — when does the money show up?"

[DATA SOURCE]: pitch → launch_posts, pitch → email_sequence
[IF ASKED]: "When do the articles publish?" → "Weekly starting week 4. LinkedIn warm-up runs weeks 1-3 to build engagement baseline first."
-->

---
transition: slide-up
---

## <span class="teal">Revenue</span> Model

<v-click>
<img src="/revenue-model.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

<!--
[PERSONA THREAD]: Maya — (indirect — "when Maya signs" is the revenue trigger)

[TRANSITION IN]: "Two months of zero revenue. That's the cost of credibility."

[BEAT]: TRUST — "They're being honest about the timeline. No hockey stick fantasy."

[THE GAP]: Current: $0 revenue, pure audience building.
           Future: $3-8K/mo from managed pilots.
           This slide shows: the honest revenue trajectory.

[TALKING POINTS]:
- [click to reveal chart] "Months 1 and 2: zero dollars. Articles and LinkedIn. That's it. No revenue. No pretending."
- "Month 3: first managed pilot. $3K to $8K — setup fee plus first month of retainer. That's one Maya."
- "Month 6: $6K to $16K cumulative. Two or three pilots running with recurring retainers."
- [lower voice] "The shape is a hockey stick ONLY if the articles land. No articles, no pipeline. We're not delusional about this."

[TRANSITION OUT]: "Now — Maya has options. She's seen Jasper, she's tried Taplio. Why can't someone else do what we're doing?"

[DATA SOURCE]: offer-scope → revenue_model
[IF ASKED]: "Why so conservative?" → "Because we have to earn every dollar through published proof. There's no virality assumption, no 'if we get 1% of the market' math. It's: publish → prove → sign pilots."
-->

---
transition: teal-wipe
---

## <span class="teal">Competitive</span> Map

<v-click>
<object data="/competitive-map.svg" type="image/svg+xml" style="width:100%;max-width:720px;margin:0 auto;display:block;"></object>
</v-click>

<!--
[PERSONA THREAD]: Maya — callback ("Maya tried three of these tools. They each do one thing.")

[TRANSITION IN]: "Maya's tried three tools on this map. Let me show you where they sit — and where nobody else sits."

[BEAT]: CONFIDENCE — "There's a clear gap in the market."

[THE GAP]: Current: Expensive single-step tools OR cheap slop generators.
           Future: Full integration depth at accessible price.
           This slide shows: why the gap exists and why nobody's filled it.

[TALKING POINTS]:
- [click to reveal map] "Two axes: price and integration depth. Bottom-left: Jasper writes for $49. Taplio schedules for $39. Castmagic repurposes for $30. Each one does exactly one thing."
- "Top-right: Skott at $2,000 a month for volume slop. Artisan at $2,000 a month for an AI SDR that gets zero replies. Maya's CEO almost bought Skott."
- [lean forward] "ACE sits top-left. Full integration depth — research through measurement — at free to $5K. Nobody else is there. Not because it's impossible, but because nobody's built the full loop."
- "And the pipeline is open-source. Maya can fork it. That's not something Jasper or Skott can say."

[TRANSITION OUT]: "Okay. We know who. We know why. We know no one else does it. What's the plan to get there?"

[DATA SOURCE]: signal-scan → signals[type=COMPETITIVE]
[IF ASKED]: "Can't Jasper just add these features?" → "Jasper is a writing tool with $125M in funding optimized for that surface area. Adding a full research-to-measurement pipeline would require rebuilding their entire architecture. Their moat is writing quality, not pipeline depth."
-->

---

## <span class="teal">Execution</span> Calendar

<v-click>
<img src="/execution-calendar.svg" style="width:100%;max-width:740px;margin:0 auto;display:block;" />
</v-click>

<!--
[PERSONA THREAD]: Maya — (indirect — the timeline exists to reach Maya)

[TRANSITION IN]: "Eight weeks from warmup to pipeline or kill. Here's the week-by-week."

[BEAT]: TRUST — "This is executable. Concrete dates, concrete actions."

[THE GAP]: Current: An idea with no timeline.
           Future: A week-by-week execution plan with kill gates.
           This slide shows: the disciplined execution plan.

[TALKING POINTS]:
- [click to reveal calendar] "Weeks 1 through 3: LinkedIn warm-up. Three to five posts per week. Building engagement baseline before the articles drop."
- "Week 4: Article 1 drops. LinkedIn long-form, Reddit cross-posts to r/openclaw, r/ClaudeAI, r/indiehackers. This is the first real test."
- "Weeks 5 through 7: Articles 2 through 4, weekly. Each one builds on the last."
- "Week 8 and beyond: managed pilot outreach. [pause] But only if the articles prove traction. If they don't, we don't pitch."

[TRANSITION OUT]: "And that brings us to something most decks don't show you: how we know when to quit."

[DATA SOURCE]: offer-scope → execution_calendar
[IF ASKED]: "Why LinkedIn first, not Product Hunt?" → "LinkedIn carousel engagement is 3x text posts — 6.6% rate. That's the highest-signal channel we found. Product Hunt is a one-day spike. LinkedIn is a compounding audience."
-->

---
transition: slide-up
---

## <span class="teal">Kill</span> Criteria

<v-click>
<img src="/kill-criteria.svg" style="width:100%;max-width:720px;margin:0 auto;display:block;" />
</v-click>

<!--
[PERSONA THREAD]: Maya — (indirect — "if Maya doesn't show up, we kill it")

[TRANSITION IN]: "Three gates. Hard thresholds. No sunk cost exceptions."

[BEAT]: TRUST — "They'll actually kill this if it doesn't work. They're not delusional."

[THE GAP]: Current: Most founders throw good money after bad.
           Future: Pre-committed kill criteria prevent emotional decision-making.
           This slide shows: the intellectual honesty that earns trust.

[TALKING POINTS]:
- [click to reveal gates] "Gate 1, week 1: fewer than 50 LinkedIn impressions AND fewer than 20 Reddit upvotes. That means the FORMAT is wrong. Reassess."
- "Gate 2, month 1: zero inbound inquiries in 14 days after Article 1. [pause] That means nobody cares. Kill the pipeline."
- [lower voice] "Gate 3, month 3: zero pilot conversations in 45 days. That means the offer is wrong. Kill it entirely."
- "We wrote these down before we wrote the first article. Not after. Before."

[TRANSITION OUT]: "We also stress-tested the whole thing. Here's the SWOT verdict."

[DATA SOURCE]: decision-log → kill_criteria
[IF ASKED]: "Have you ever actually killed a project at a gate?" → "The pipeline has killed two opportunities at Gate 1. That's the point — the gates work because they're enforced."
-->

---
transition: teal-wipe
---

## <span class="teal">SWOT</span> Verdict

<v-click>
<object data="/swot-verdict.svg" type="image/svg+xml" style="width:100%;max-width:700px;margin:0 auto;display:block;"></object>
</v-click>

<v-click>
<p class="proceed-verdict">PROCEED</p>
</v-click>

<!--
[PERSONA THREAD]: Maya — (indirect — the verdict is "Maya's pain is real enough to build for")

[TRANSITION IN]: "We ran a full SWOT with five modifications. Not the kind of SWOT you do in business school — the kind with specific action items."

[BEAT]: CONFIDENCE — "The analysis is rigorous and the verdict is earned."

[THE GAP]: Current: A scored opportunity with known risks.
           Future: A modified plan that addresses each risk.
           This slide shows: the evidence-based go decision.

[TALKING POINTS]:
- [click to reveal SWOT] "Five modifications that turn a 54 out of 60 score into an executable plan."
- "The common thread across all five: earn the right to charge by publishing first. Open-source the pipeline so there's no 'trust me.' Use carousels because the data says 3x. Gate the pilot on inbound — don't cold outreach. Price as setup plus retainer, not SaaS."
- [click to reveal PROCEED, pause] "Verdict: proceed."
- [lower voice] "With the modifications. Not blindly. Not because we're excited. Because the evidence supports it."

[TRANSITION OUT]: "But hold on — we're engineers building tools for engineers. That's a self-referential trap. So we ran a bias check."

[DATA SOURCE]: swot-analysis → verdict, swot-analysis → modifications
[IF ASKED]: "What were the modifications?" → "Hover each card for details. Key ones: open-source the core (no lock-in anxiety), gate pilot on inbound (don't cold outreach burned people), carousels over text (3x engagement data)."
-->

---

## <span class="teal">Bias</span> Check

<v-click>
<img src="/bias-check.svg" style="width:100%;max-width:700px;margin:0 auto;display:block;" />
</v-click>

<!--
[PERSONA THREAD]: Maya — (indirect — are we SURE Maya's pain is real, or are we seeing what we want to see?)

[TRANSITION IN]: "Most dangerous bias in the world: a builder who's excited about what they're building. So we checked ourselves."

[BEAT]: TRUST — "They're self-aware. They flagged their own biases."

[THE GAP]: Current: Unchecked excitement could lead to building something nobody wants.
           Future: Systematically audited biases with honest assessments.
           This slide shows: intellectual honesty about our own blind spots.

[TALKING POINTS]:
- [click to reveal] "Four checks. Excitement bias: FLAGGED. Builder building tools for builders is a self-referential trap. We know this."
- "Confirmation bias: low. Pain signals from five independent sources — Reddit, Scott Spence, Salesforce, OpenClaw security audits, LinkedIn benchmarks. Not echo chamber."
- "Availability bias: moderate. The OpenClaw data is recent and we're weighting it heavily. Fair flag."
- [pause] "Anchoring: pass. We re-scored the SDP in a fresh session two weeks later. Score held at 54. Not anchored to the first run."

[TRANSITION OUT]: "So — biases checked, scoring done, personas mapped, plan built. [pause] What happens next?"

[DATA SOURCE]: decision-log → bias_check
[IF ASKED]: "What would make you change the verdict?" → "Gate 2: zero inbound inquiries 14 days after Article 1. If nobody responds to the best piece of content we can produce, the premise is wrong — not just the execution."
-->

---
layout: center
transition: slide-up
---

## <span class="teal">Next</span> Steps

<v-click>

| Milestone | Deadline | Kill Condition |
|:----------|:---------|:---------------|
| LinkedIn warm-up (3-5 posts/wk) | Week 3 | &lt;50 impressions |
| Article 1 + LinkedIn + Reddit | Week 4 | Zero inbound in 14 days |
| Articles 2-4 weekly | Week 7 | Zero engagement growth |
| First managed pilot signed | Month 3 | Zero pilot conversations in 45 days |

</v-click>

<!--
[PERSONA THREAD]: Maya — callback ("the first pilot is Maya — or someone like her")

[TRANSITION IN]: "Four milestones. Four deadlines. Four kill conditions. Every one is measurable."

[BEAT]: URGENCY — "This is happening now. The clock is running."

[THE GAP]: Current: A validated plan with no execution.
           Future: Week-by-week milestones with binary pass/fail gates.
           This slide shows: the commitment to execute.

[TALKING POINTS]:
- [click to reveal table] "LinkedIn warm-up: 3 weeks. If we can't get 50 impressions, the format is wrong."
- "Article 1: the real test. If nobody responds in 14 days — not 'low engagement,' ZERO inbound — we kill it."
- "Articles 2 through 4: engagement has to grow, not just maintain. Flat is failure."
- [lean forward] "The first managed pilot is due at month 3. That's one Maya. One person who reads the articles, forks the pipeline, and says 'build this for me.'"

[TRANSITION OUT]: "Before we go to the appendix — remember what I said at the beginning? About the pipeline running on itself?"

[DATA SOURCE]: offer-scope → execution_calendar, decision-log → kill_criteria
[IF ASKED]: "What if you get interest but no pilot by month 3?" → "Interest without conversion means the offer is wrong — not the audience. We'd restructure the pilot pricing or scope, not abandon the opportunity."
-->

---
transition: fade
---

## <span class="teal">Appendix</span> — Asset Map

<div class="compact">

| Artifact | Location |
|:---------|:---------|
| Signal Scan | `Signal-Scans/` |
| Decision Log | `Decisions/` |
| Persona Extract | `Personas/` |
| Offer Scope | `Offers/` |
| Pitch | `Pitches/` |
| Content Seeds | `Content-Briefs/` |
| [LinWheel](https://github.com/Peleke/linwheel) | github.com/Peleke/linwheel |
| [buildlog](https://github.com/Peleke/buildlog-rs) | github.com/Peleke/buildlog-rs |
| This Deck | `launchpad/deck/slides.md` |
| Kanban | Obsidian vault |

</div>

<!--
[PERSONA THREAD]: Maya — (reference layer — "every artifact Maya can verify")

[TRANSITION IN]: "Quick reference: every artifact in this presentation is traceable. If Maya — or you — want to verify any claim, here's where to look."

[BEAT]: TRUST (supporting) — "Everything is documented and traceable."

[TALKING POINTS]:
- "Ten artifacts. The signal scan fed the decision log, which fed persona extraction, which fed offer scoping, which fed the pitch."
- "Every one of these is in the Obsidian vault or the launchpad repo. Fork it. Read it. Verify it."
- [gesture at screen] "The pipeline IS the product. And it produced every document in this table."

[TRANSITION OUT]: [none — this is pre-closing]

[DATA SOURCE]: Pipeline metadata — all artifacts
-->

---
layout: center
transition: teal-wipe
class: cover-bg
---

<p class="text-2xl text-shimmer" style="font-weight:800;">Built with the Hunter Pipeline.</p>

<v-click>
<img src="/pipeline-flow.svg" style="width:100%;max-width:620px;margin:24px auto;display:block;" />
</v-click>

<p class="muted text-sm mt-6">2026-03-06</p>

<!--
[PERSONA THREAD]: Maya — resolve (circular close — callback to the opening)

[TRANSITION IN]: [pause, let the shimmer animation play] "Remember Maya? [longer pause] The pipeline that could fix her content problem — the one that does the full loop — is the same pipeline that generated this deck."

[BEAT]: RESOLUTION — "The proof is the product. The product is the proof."

[THE GAP]: Current: Maya's fragmented, manual, soul-crushing content workflow.
           Future: A pipeline that researches, writes, reshapes, publishes, measures, and iterates — and just proved it works by producing the presentation you watched.
           This slide shows: the circular proof. The product validates itself.

[TALKING POINTS]:
- [click to reveal pipeline flow, let the line-drawing animation play]
- [lower voice] "Signal scan. Decision log. Persona extract. Offer scope. Pitch. Assess."
- "Every node you see animated is a skill that ran. Every arrow is a typed envelope that connected them. The deck you just watched is the output."
- [make eye contact] "If someone asks 'does this work?' — you just watched the answer."
- [pause] "Maya deserves better than five tools and a Google Sheet. We're going to build it for her."

[DATA SOURCE]: Pipeline metadata — recursive self-application
[IF ASKED]: "Can I try the pipeline myself?" → "Yes. It's open-source. Fork Peleke/hunter, configure your vault path, and run 'Scan [your domain] for product signals.' The pipeline will guide you from there."
-->
