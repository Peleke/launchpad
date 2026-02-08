# Email 3: Story / Credibility

**Subject**: The deploy that mass-deleted production records at Qortex
**Send**: Day 4
**Job**: Build trust through shared experience

---

Hey,

I want to tell you about a production decision I got wrong and what it taught me about infrastructure choices.

At Qortex, we were building a complex backend system with multiple services, real-time processing, and a data layer that had to handle significant throughput. Early on, I made the classic mistake: I cargo-culted an architecture pattern from a company 50x our size.

I looked at how large-scale systems handled similar problems, read the blog posts, watched the conference talks, and implemented a version of their infrastructure. It worked -- in staging. In production, the complexity we imported created debugging nightmares. When something went wrong, nobody on the team (including me) could trace the issue through all the layers we had introduced. We had infrastructure we could not reason about.

The lesson was painful and specific: **the right infrastructure decision is not "what does Netflix use?" It is "what can my team operate, debug, and maintain at 2am when something breaks?"**

That experience is why Section 2 (the IaC Tool Decision) and Section 3 (Container Orchestration) both start with team size and operational capacity -- not with feature comparisons. The first question is never "which tool is better?" The first question is "which tool can your team actually run?"

It is also why every decision tree in the kit includes a "When to Switch" section. The goal is to make a reversible decision fast, not a perfect decision never. We eventually right-sized our architecture at Qortex, but only after burning weeks we did not have.

This is the stuff that comparison blog posts never tell you. They compare features. They do not tell you that choosing the "better" tool can be the wrong decision if your team cannot operate it.

That thinking is baked into every section of the Decision Kit.

-- Peleke
