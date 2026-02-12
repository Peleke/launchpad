# Launchpad

This repo is your product launch surface. Each branch is a complete, deployable product skeleton. Main is the index. Vercel auto-deploys every branch as a preview URL you can share.

## What This Repo Does

You have a pipeline that takes a product idea from signal scan through persona research, offer scoping, and pitch generation. The pitch skill produces 1,300+ lines of launch material: landing page copy, platform-specific posts, a GitHub README, a 5-email nurture sequence, an hour-by-hour launch checklist, A/B test specs, and kill criteria.

Launchpad is where all of that becomes real. When the pitch skill runs, it:

1. **Creates a branch** named after the product (e.g., `devops-decision-kit`)
2. **Scaffolds the full product directory** with README, templates, examples, docs, issue templates, LICENSE, CONTRIBUTING.md
3. **Generates a hero image** via ComfyUI (or leaves an HTML comment with the image intent for later)
4. **Splits the email sequence** into individual files in `emails/` (ready to paste into ConvertKit/Buttondown)
5. **Opens a PR against main** so you can review every file line-by-line, leave comments, and have the agent fix feedback

Meanwhile, in your Obsidian vault, the pitch skill simultaneously deploys:
- **Content seeds** to `Writing/Content-Briefs/` (one per platform: Reddit, LinkedIn, Twitter)
- **A launch checklist kanban** to `Admin/Product-Discovery/Pitches/` (Pre-Launch, Launch Day, Week 1, Ongoing columns with dated tasks)
- **Review reminder tasks** appended to the pitch document (Week 1, Month 1, Month 3 review dates with `#hunter/review` tags, queryable by Obsidian Tasks)

The result: after one pitch run, you have a reviewable PR on GitHub, a deployable preview on Vercel, content seeds in your vault ready for editing, a kanban board for launch execution, and timed review reminders so you check the numbers instead of rationalizing them.

## The Review Workflow

This is how you go from "pitch generated" to "product shipped":

**Step 1: Open the PR.** The pitch skill opens a PR (e.g., [#1](https://github.com/Peleke/launchpad/pull/1)) with every generated file. The PR body includes a review checklist and links to all upstream pipeline artifacts (offer spec, persona, SWOT, decision log, signal scan).

**Step 2: Review line-by-line.** Read the README as a buyer would. Read the emails as a recipient would. Comment on anything that feels wrong, weak, or off-voice. GitHub's PR review UI is your editing surface.

**Step 3: Fix feedback.** Tell the agent (via Telegram, Claude Code, or however you talk to it) to address your PR comments. It pushes fixes to the same branch. The PR updates. Repeat until clean.

**Step 4: Check the Vercel preview.** Every branch auto-deploys to a preview URL. Open it. See how the README renders. Share the preview URL with a trusted friend for a gut check.

**Step 5: Merge when ready.** Merging the PR means the product structure is approved. The branch stays alive for future updates (template improvements, README iterations, new content).

**Step 6: Execute the kanban.** Open the launch checklist in Obsidian. It has every pre-launch, launch-day, and post-launch task with dates. Check them off as you go.

## What Lives Where

| Artifact | Location | Purpose |
|----------|----------|---------|
| Product skeleton (README, templates, emails) | Branch on this repo | The deployable product |
| PR for review | This repo, against main | Your editing and approval surface |
| Vercel preview | Auto-deployed per branch | Shareable preview URL |
| Content seeds (Reddit, LinkedIn, Twitter posts) | Obsidian `Writing/Content-Briefs/` | Raw posts for you to edit before publishing |
| Launch checklist kanban | Obsidian `Admin/Product-Discovery/Pitches/` | Day-by-day execution plan |
| Review reminders | Appended to pitch doc in Obsidian | Timed tasks so you check kill criteria on schedule |
| Full pitch document (all 7 phases) | Obsidian `Admin/Product-Discovery/Pitches/` | The source of truth for all generated material |
| Upstream pipeline artifacts | Obsidian `Admin/Product-Discovery/` subfolders | Signal scan, decision, persona, SWOT, offer spec |

## Deploy-Only Mode

Already have a pitch document but the artifacts were never split out? The pitch skill has a deploy-only mode that reads an existing pitch doc from the vault and deploys all the artifacts without re-generating content.

Trigger it with: `/pitch --deploy-only devops-decision-kit-pitch-2026-02-08`

It parses the pitch by section headers, checks what has already been deployed (skips duplicates), and writes only what is missing. You get a deployment report showing what was created and where.

## Vercel Setup

Vercel is connected to this repo. Configuration is in `vercel.json` on main. Every branch gets a preview deployment automatically. No build step needed (static files only). The preview URL pattern is `https://launchpad-{branch-slug}.vercel.app` or similar.

To share a product preview with someone before launch, send them the Vercel preview URL for that branch.

## Products

| Branch | Product | Price | Status | PR | Preview |
|--------|---------|-------|--------|----|---------|
| [`devops-decision-kit`](https://github.com/Peleke/launchpad/tree/devops-decision-kit) | The DevOps Decision Kit | $29 | spec | [#1](https://github.com/Peleke/launchpad/pull/1) | TBD |
| [`from-1-to-prod`](https://github.com/Peleke/launchpad/tree/from-1-to-prod) | From 1 to Prod | $49-99/mo | spec | [#2](https://github.com/Peleke/launchpad/pull/2) | [Preview](https://launchpad-git-from-1-to-prod-kwayet-fs-projects.vercel.app) |

## The Pipeline Behind This

```
signal-scan → decision-log → persona-extract → swot-analysis → offer-scope → pitch → launchpad
                                                                                 ↓
                                                                          Obsidian vault
                                                                          (seeds, kanban,
                                                                           review tasks)
```

Each skill in the pipeline produces structured output that feeds the next. By the time the pitch skill runs, it has persona pain stories, SWOT risk analysis, offer positioning, and kill criteria to draw from. The pitch assembles all of that into launch-ready materials. Launchpad is where those materials become reviewable, deployable, and shareable.

The pipeline skills live in [`Peleke/skills`](https://github.com/Peleke/skills) (see PR [#7](https://github.com/Peleke/skills/pull/7) for the latest pitch extensions including deploy-only mode).

## License

MIT
