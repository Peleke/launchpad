# Launchpad

Product launch surface for the hunter pipeline. Each branch is a deployable product skeleton with a live landing page. Main is the index.

## How It Works

The hunter pipeline takes a product idea from raw market signals to a live, reviewable landing page:

```
signal-scan → decision-log → persona-extract → offer-scope → pitch → launchpad
                                    ↑                            ↓
                              quote-to-persona            Obsidian vault
                              wild-scan / reddit-harvest  (seeds, kanban, review tasks)
                                    ↑
                              swot-analysis
```

The pitch skill (final step before launchpad) produces the complete launch kit. When it runs Phase 3 (GitHub deployment), it:

1. **Creates a branch** named after the product (e.g., `from-1-to-prod`)
2. **Scaffolds the product directory** — README, emails/, docs/, LICENSE, CONTRIBUTING.md
3. **Generates a landing page** (`index.html`) from the Phase 1 copy — dark theme, mobile responsive, zero dependencies (Phase 3e)
4. **Generates a hero image** via ComfyUI MCP if available, otherwise leaves an HTML comment with the image intent for manual generation later
5. **Splits the email sequence** into individual files in `emails/` (ready to paste into ConvertKit/Buttondown)
6. **Opens a PR against main** with a review checklist and links to all upstream pipeline artifacts

Simultaneously, the pitch skill deploys to the Obsidian vault:
- **Content seeds** to `Writing/Content-Briefs/` (one per platform: Reddit, LinkedIn, Twitter)
- **Launch checklist kanban** to `Admin/Product-Discovery/Pitches/` (Pre-Launch, Launch Day, Week 1, Ongoing columns)
- **Review reminder tasks** appended to the pitch doc (Week 1, Month 1, Month 3 dates with `#hunter/review` tags)

## What You Get After One Pitch Run

- A **PR on GitHub** with every generated file, reviewable line-by-line
- A **live landing page on Vercel** at the branch preview URL — shareable immediately
- **Content seeds** in your vault ready for editing before publishing
- A **kanban board** for launch execution
- **Timed review reminders** so you check kill criteria on schedule

## Review Workflow

**Step 1: Open the PR.** The pitch skill opens a PR (e.g., [#2](https://github.com/Peleke/launchpad/pull/2)) with every generated file. The PR body includes a review checklist and links to upstream artifacts (offer spec, persona, SWOT, decision log, signal scan).

**Step 2: Check the Vercel preview.** Every branch auto-deploys a landing page to its preview URL. Open it. See how the page looks on desktop and mobile. Share the URL for a gut check.

**Step 3: Review line-by-line.** Read the landing page copy as a buyer. Read the README as a developer. Read the emails as a recipient. Comment on anything off-voice or weak.

**Step 4: Fix feedback.** Tell the agent to address your PR comments. It pushes fixes to the same branch. The landing page updates automatically (Vercel redeploys on push). Repeat until clean.

**Step 5: Merge when ready.** Merging the PR approves the product structure. The branch stays alive for future updates.

**Step 6: Execute the kanban.** Open the launch checklist in Obsidian and work through it.

## What Lives Where

| Artifact | Location | Purpose |
|----------|----------|---------|
| Landing page (`index.html`) | Branch on this repo | Live landing page on Vercel |
| Product README | Branch on this repo | GitHub-facing documentation + conversion copy |
| Email sequence | `emails/` on branch | Individual files, paste into email tool |
| PR | This repo, against main | Review and approval surface |
| Vercel preview | Auto-deployed per branch | Shareable landing page URL |
| Content seeds | Obsidian `Writing/Content-Briefs/` | Raw platform posts to edit before publishing |
| Launch checklist kanban | Obsidian `Admin/Product-Discovery/Pitches/` | Execution plan with dated tasks |
| Review reminders | Appended to pitch doc in Obsidian | Timed kill-criteria checks |
| Full pitch (all 7 phases) | Obsidian `Admin/Product-Discovery/Pitches/` | Source of truth for all generated material |
| Upstream artifacts | Obsidian `Admin/Product-Discovery/` subfolders | Signal scan, decision, persona, SWOT, offer spec |

## Deploy-Only Mode

Already have a pitch document but the artifacts were never deployed? The pitch skill has a deploy-only mode:

```
/pitch --deploy-only from-1-to-prod-pitch-2026-02-12
```

It parses the pitch markdown by section headers, checks what's already deployed (skips duplicates), and writes only what's missing. Returns a deployment report.

## Vercel Setup

Vercel is connected to this repo via GitHub integration. Configuration is in `vercel.json` on main.

**How it works:**
- Every push to a branch triggers a preview deployment
- The landing page (`index.html`) is what Vercel serves — not the README
- Preview URLs follow the pattern: `https://launchpad-git-{branch-name}-kwayet-fs-projects.vercel.app`
- No build step needed (static files only)
- SSO protection is disabled so preview URLs are publicly accessible

**Initial setup** (already done for this repo):
1. Run `vercel` from the repo root to link the project
2. The CLI will detect `vercel.json` and connect to GitHub automatically
3. Disable SSO protection via the Vercel API if preview deployments return 401

## Products

| Branch | Product | Price | Status | PR | Preview |
|--------|---------|-------|--------|----|---------|
| [`devops-decision-kit`](https://github.com/Peleke/launchpad/tree/devops-decision-kit) | The DevOps Decision Kit | $29 | spec | [#1](https://github.com/Peleke/launchpad/pull/1) | No landing page (predates Phase 3e) |
| [`from-1-to-prod`](https://github.com/Peleke/launchpad/tree/from-1-to-prod) | From 1 to Prod | $49-99/mo | spec | [#2](https://github.com/Peleke/launchpad/pull/2) | [Preview](https://launchpad-git-from-1-to-prod-kwayet-fs-projects.vercel.app) |
| [`buildlog`](https://github.com/Peleke/launchpad/tree/buildlog) | buildlog | OSS (MIT) | landing page | [#3](https://github.com/Peleke/launchpad/pull/3) | [Preview](https://launchpad-git-buildlog-kwayet-fs-projects.vercel.app) |
| [`qortex`](https://github.com/Peleke/launchpad/tree/qortex) | qortex | OSS (MIT) | landing page | [#4](https://github.com/Peleke/launchpad/pull/4) | [Preview](https://launchpad-git-qortex-kwayet-fs-projects.vercel.app) |

## The Pipeline

The pipeline skills live in [`Peleke/skills`](https://github.com/Peleke/skills). Each skill produces structured output that feeds the next:

| Skill | What It Does | Output |
|-------|-------------|--------|
| `signal-scan` | Harvests pain/demand/spend signals from community data | Scored opportunities with signal taxonomy |
| `wild-scan` / `reddit-harvest` | Extracts direct quotes from Reddit, forums, communities | Scored quotes with engagement metadata |
| `quote-to-persona` | Clusters quotes into behavioral personas | Four Forces personas with pain stories |
| `decision-log` | SDP scoring + bias check + pre-mortem | Go/no-go decision with kill criteria |
| `swot-analysis` | Strengths, weaknesses, opportunities, threats | Risk registry + moat assessment |
| `offer-scope` | Hormozi value equation + positioning + distribution plan | Build spec with price, format, channels |
| `pitch` | Assembles everything into launch-ready materials | 7-phase launch kit (this repo's input) |

## License

MIT
