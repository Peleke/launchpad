# buildlog Positioning Canvas

**Date**: 2026-03-14
**Framework**: Dunford "Obviously Awesome" (8-phase)
**Product**: buildlog v0.22.0
**Status**: Draft — pre-landing-page-rewrite

---

## Phase 1: Competitive Alternatives

What does the target customer *actually do today* instead of buildlog?

| Alternative | Type | What they get | What they miss |
|---|---|---|---|
| Edit CLAUDE.md / .cursorrules by hand | DIY | Some improvement, fast to start | No measurement, no feedback, rules accumulate without pruning |
| Do nothing — start every session fresh | Inaction | Zero overhead | Repeat mistakes every session, no compound improvement |
| CodeRabbit / Codacy / SonarQube | Indirect (static analysis) | Catches bugs at review time | Reviews code, not agent instructions. No learning loop. |
| Notion / Guru / Tettra | Indirect (knowledge management) | Centralized docs | Storage without measurement. You can document patterns forever and never know if they help. |
| Mem0 / Letta (MemGPT) | Direct-ish (agent memory) | Persistent memory across sessions | Memory without measurement. Stores everything, validates nothing. |
| LangSmith / Weights & Biases | Indirect (observability) | Traces, latency, cost tracking | Observes execution, doesn't close the loop back to instructions. |

**Key insight**: Nobody measures whether agent instructions actually reduce mistakes. Every alternative is capture-only, review-only, or memory-without-measurement.

---

## Phase 2: Unique Attributes

| Attribute | vs Alternatives | Classification |
|---|---|---|
| Closed-loop measurement (Repeated Mistake Rate) | No alternative measures rule effectiveness over time | **Truly unique** |
| Thompson Sampling rule selection (Beta-Bernoulli bandit) | No alternative uses statistical methods for agent instruction selection | **Truly unique** |
| Gauntlet credit system (solves credit assignment) | CodeRabbit reviews but doesn't attribute which rule prevented which mistake | **Truly unique** |
| Posterior convergence tracking (per-rule alpha/beta/mean history) | LangSmith has metrics but not per-rule convergence curves | **Truly unique** |
| Bragi LLM prose detection (27 rules from ACL/COLING/PNAS research) | No alternative detects LLM-generated prose patterns in engineering docs | **Truly unique** |
| Multi-agent render (same rules → 6 agent formats) | Each tool is agent-specific, nothing cross-renders | **Best in class** |
| Ambient MCP capture (36 tools, zero ceremony) | Mem0 requires explicit API calls | **Best in class** |

**Advancing**: All 7 (5 truly unique + 2 best in class)

---

## Phase 3: Value Articulation

**Lead message**: Closed-loop measurement (highest intensity, most differentiated)

| Attribute | Functional (what can they DO?) | Emotional (how do they FEEL?) | Social (how do others SEE them?) |
|---|---|---|---|
| **Closed-loop RMR** | Know which rules reduce mistakes. Drop the rest. | Stop guessing. Start knowing. | "We measure our agent's improvement rate." |
| **Thompson Sampling** | Rules that work get surfaced automatically. | The system learns so you don't babysit. | "Our rules are statistically validated." |
| **Gauntlet credits** | Every citation traces to a specific review finding. | No more "does this even do anything?" | Show receipts when asked "how do you know?" |
| **Posterior tracking** | Watch rule confidence converge or stall over time. | See the math working (or not). | Dashboard you can screenshot for a standup. |
| **Bragi** | Catch LLM-generated prose before it ships. | Your docs sound like you, not ChatGPT. | Colleagues stop asking "did an AI write this?" |
| **Multi-agent render** | Switch from Claude to Cursor, keep everything. | Not locked in. | — |
| **Ambient MCP** | Install once, works everywhere, zero ceremony. | Just works. | — |

---

## Phase 4: Target Customer (ICP)

### Primary ICP

A **senior/staff engineer or technical founder** who:
- Uses AI coding agents daily (Claude Code, Cursor, Copilot)
- Has already edited CLAUDE.md or .cursorrules at least once
- Suspects their manual rules are mostly vibes
- Ships code to production (not hobby/learning projects)
- Values empiricism — wants data over opinions
- Python-literate (buildlog is Python, installs via pip/uv)

**Specificity test**: Can you find 10 in 30 minutes?
→ Yes. Search Twitter/X for "CLAUDE.md tips", ".cursorrules", "AI coding agent setup". Anyone sharing their agent instruction files publicly is in the ICP.

### Anti-ICP (who this is NOT for)

- Students learning to code (adds complexity, not value — just use the agent)
- Engineers who don't use AI coding agents (no base behavior to optimize)
- "Just make it work" pragmatists who consider measurement overhead
- Teams looking for enterprise observability (use LangSmith/Datadog)
- People who want a GUI (buildlog is CLI-first, MCP-native)

### Investor Narrative

The ICP today is the technical founder / senior IC who manually tunes agent instructions. This market is small but growing explosively — every new AI coding tool user eventually edits their instruction file. buildlog is the measurement layer that sits below all of them. Market unlock: when companies start standardizing agent instruction management across teams (not individuals).

---

## Phase 5: Market Category

| Candidate | Recognized by ICP? | Makes unique attributes feel important? | Sets expectations we can exceed? | Commodity? | Verdict |
|---|---|---|---|---|---|
| "AI coding tools" | Yes | No (too broad) | No (competes with Cursor/Copilot) | Yes | Reject |
| "Developer productivity" | Yes | No (commodity bucket) | No | Yes | Reject |
| "Agent memory" | Sort of | Partially (implies storage) | Yes (we exceed by adding measurement) | No | Maybe |
| "Agent instruction optimization" | Not yet | Yes | Yes | No | **Subcategory candidate** |
| "Engineering judgment transfer" | No | Yes | Yes | No | New category — too abstract |

**Selected**: Subcategory — **"agent learning tools"** or **"AI agent optimization"**

Sits in the "developer tools" mental bucket but with a modifier that signals measurement + feedback loop. Not trying to create a new category (expensive, requires market education). Instead: "you know what agent instructions are — this makes them measurably better."

For the landing page, don't use the category label at all. Just describe what it does: "Make your AI agent measurably better over time."

---

## Phase 6: Emotional Hooks

### Primary Hook: Relief

Pain is acute and specific. Every engineer who has edited CLAUDE.md and wondered "is this even doing anything?" has felt this frustration. They've accumulated 50 rules with no idea which ones help.

**Relief hook**: *"Stop guessing which rules work."*

### Secondary Hook: Aspiration

For engineers who don't yet feel the pain but want to level up their AI workflow.

**Aspiration hook**: *"Your agent gets better every session — automatically."*

### Anti-Messaging (NEVER use these)

1. "AI-powered" — buildlog IS the AI tool, not meta-AI
2. "10x developer" — cringe, engineers hate this
3. "Revolutionize your workflow" — empty hype, says nothing
4. "Thought leadership" — wrong audience entirely
5. "Enterprise-grade" — nobody buying this is enterprise yet
6. "Unlock the power of..." — filler, no information
7. "Seamless" — overused, meaningless
8. "Game-changer" — red flag for engineers
9. "Intelligent" / "Smart" — let them judge, don't self-describe
10. "Content" or "publishing" — that's linwheel's lane, not buildlog's

### Bragi Self-Check

The landing page copy itself must pass bragi rules:
- No em-dash waterfalls
- No throat-clearing ("It's worth noting...")
- Vary sentence length (burstiness)
- No performative self-answered questions
- No staccato negation lists

---

## Phase 7: Expansion Sequence

| Stage | Timeframe | Message | Discipline |
|---|---|---|---|
| **Now** | Launch – month 3 | "Measure whether your agent rules work. Open source, MIT, `pip install buildlog`." | Sell the loop. Don't mention qortex, linwheel, or the ecosystem. Single-project, single-developer value only. |
| **Next** | Months 4-12 | "Cross-project learning. Rules that work in one repo propagate." | Introduce qortex backend. Cross-consumer credit propagation. Multi-project dashboards. |
| **After** | Year 2+ | "The ambient engineering layer: capture → learn → publish → distribute." | Full ecosystem: buildlog → linwheel bridge. A.C.E. narrative. Team/org features. |

**Current landing page should be 100% "Now" stage messaging.**

---

## Phase 8: Competitive Moats

| Moat | Type | Current Strength | Messaging Order |
|---|---|---|---|
| Closed-loop measurement (nobody else does this) | Technical | Emerging | **First conversation** |
| Thompson Sampling + gauntlet credits (statistical rigor) | Technical | Moderate | **First conversation** |
| 27 bragi rules from peer-reviewed research | Data | Emerging | **First conversation** |
| Multi-agent render (not locked to one tool) | Technical | Thin | Second conversation |
| Emission protocol (integration seam) | Technical | Thin | Investor only |
| Cross-project rule propagation (via qortex) | Network | None yet | Investor only |
| Community-contributed seed rules | Network | None yet | After launch |

**First conversation moats** (what the landing page leads with):
1. You can measure whether your rules work (RMR)
2. The system selects rules statistically (Thompson Sampling)
3. LLM prose detection catches slop in your docs (Bragi)

---

## Landing Page Hero (Derived)

> **Make your AI agent measurably better over time**
>
> buildlog captures what your agent gets right and wrong, selects which rules to keep, and proves it with data. Rules that help get promoted. Rules that don't get dropped. The loop runs itself.

## Section Flow (Derived)

1. **Hero** — problem + install + stats
2. **The Problem** — you edit CLAUDE.md by hand and hope for the best
3. **How it works** — the 6-step loop (capture → extract → select → render → measure → update)
4. **The Stack** — flip cards for each component (updated for v0.22)
5. **Review Gauntlet + Bragi** — new section, key differentiator
6. **Agent targets** — multi-agent render (updated paths)
7. **Current limits** — honest, updated (remove solved problems)
8. **FAQ** — updated for v0.22
9. **CTA** — GitHub + Docs + PyPI
