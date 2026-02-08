# The DevOps Decision Kit

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

**Stop reading comparison blog posts. Start making infrastructure decisions.**

You know what Terraform, Pulumi, ECS, EKS, GitHub Actions, and Datadog are. You do not know which one to use for YOUR team, YOUR budget, and YOUR stack. Every comparison post ends with "it depends" without telling you what it depends on.

This repo contains decision trees for the 5 infrastructure choices that paralyze most DevOps engineers. Answer a few questions about your situation. Get a specific recommendation with reasoning. Deploy from the companion templates.

**Before:** Three weeks of comparison blog posts. Still cannot decide. Copies Terraform from a Medium article written for a company 100x your size.

**After:** 15 minutes. One decision. Justified reasoning you can explain to your team. A deployable template to start building today.

---

## What's In This Repo

```
devops-decision-kit/
├── decision-trees/          # Decision frameworks for 5 infrastructure choices
│   ├── 00-quick-start/      # 4-question master tree -> your first decision in 15 min
│   ├── 01-iac-tool/         # Terraform vs. Pulumi vs. CDK vs. CloudFormation
│   ├── 02-container-orchestration/  # ECS vs. EKS vs. Docker vs. Lambda
│   ├── 03-cicd-pipeline/    # GitHub Actions vs. GitLab CI vs. Jenkins vs. CircleCI
│   ├── 04-monitoring-stack/ # Prometheus+Grafana vs. Datadog vs. CloudWatch vs. New Relic
│   └── 05-ai-infrastructure-review/ # 15 checks before terraform apply on AI code
├── templates/               # Deployable infrastructure code for each recommendation
│   ├── terraform/           # ECS Fargate, EKS, Lambda templates
│   ├── pulumi/              # Python ECS, TypeScript EKS templates
│   ├── cicd/                # GitHub Actions and GitLab CI workflows
│   └── monitoring/          # Prometheus+Grafana stack, CloudWatch alarms
├── examples/                # End-to-end architecture examples by team profile
│   ├── small-team-aws/      # 3-person team, AWS, $500/mo budget
│   ├── mid-team-multi-cloud/# 8-person team, AWS+GCP
│   └── solo-engineer-startup/# Solo engineer, startup, minimal budget
└── docs/                    # Getting started, methodology, FAQ
```

---

## Quick Start: Your First Decision in 15 Minutes

Answer these four questions:

### 1. How many engineers manage your infrastructure?

| Answer | Go to |
|--------|-------|
| Just me (solo) | Continue to Q2 |
| 2-3 engineers | Continue to Q2 |
| 4-10 engineers | Continue to Q3 |
| 10+ engineers or multiple teams | Your IaC tool is **Terraform**. [Read why](decision-trees/01-iac-tool/decision-tree.md#large-teams). Continue to Q4. |

### 2. What programming language does your team use daily?

| Answer | IaC Recommendation |
|--------|-------------------|
| Python | **Pulumi** (Python SDK) -- define infra in a language you already know |
| TypeScript / JavaScript | **CDK** (if AWS-only) or **Pulumi** (TypeScript SDK, if multi-cloud) |
| Go | **Pulumi** (Go SDK) |
| Java / C# / Other | **Terraform** (HCL) -- purpose-built for infra, no language bias needed |
| No strong preference | **Terraform** (HCL) -- the constraints of a DSL are a feature for infra |

### 3. Do you need multi-cloud support?

| Answer | IaC Recommendation |
|--------|-------------------|
| Single cloud (AWS/GCP/Azure) | **CDK** (if AWS + TypeScript team) or **Terraform** (otherwise) |
| Multi-cloud or hybrid | **Terraform** (broadest provider coverage) or **Pulumi** (better language support) -- decide based on Q2 |

### 4. What existing infrastructure do you have?

| Answer | Recommendation |
|--------|---------------|
| Greenfield (nothing exists) | Use whatever Q1-Q3 recommended. Start clean. |
| Existing CloudFormation | Consider **CDK** (compiles to CFN) as a migration path |
| Existing Terraform | **Stay on Terraform** unless you have a strong reason. Migration costs are real. |
| Existing ClickOps (manual) | **Terraform import** (most mature tooling as of 2026) |

---

## IaC Decision Tree (Full)

This is the complete Infrastructure-as-Code decision tree. It is free. Use it.

### The Decision Matrix

```
                              Team Size?
                    /            |            \
                Solo/Small    Mid (4-10)    Large (10+)
                   |              |              |
            Daily Language?   Multi-cloud?   -> Terraform
              /  |  |  \       /      \         (ecosystem +
            Py  TS  Go  None  Yes     No        hiring pool)
            |   |   |    |    |       |
         Pulumi |  Pulumi TF  TF or  CDK(AWS+TS)
         (Py)   |  (Go)      Pulumi  or TF
                |
          CDK(AWS-only)
          or Pulumi(TS)
```

### Decision Details

#### Solo / Small Team (1-3 engineers)

**If your team writes Python daily -> Pulumi (Python SDK)**

Why: Pulumi lets you define infrastructure using real Python -- with loops, conditionals, type checking, and your existing IDE setup. For a small team, the ramp-up speed of using a familiar language outweighs Terraform's larger ecosystem. You will be writing `for` loops over subnets, not copy-pasting HCL blocks.

When to reconsider: If you hire and your new engineers do not know Python, or if you find yourself fighting Pulumi's state management on complex multi-stack deployments. Terraform's state management is more battle-tested at scale.

Template: [`templates/pulumi/python-ecs/`](templates/pulumi/python-ecs/)

**If your team writes TypeScript daily -> CDK (AWS-only) or Pulumi TypeScript SDK (multi-cloud)**

Why: CDK compiles to CloudFormation, giving you the tightest AWS integration and the ability to use every CloudFormation feature on day one. If you are AWS-only, CDK is the path of least resistance. If you need GCP or Azure, Pulumi's TypeScript SDK gives you the same language benefits without the AWS lock-in.

When to reconsider: CDK's CloudFormation dependency means you are subject to CFN deployment limits and debugging CFN stack failures (which are famously opaque). If you hit CFN pain, Pulumi TypeScript is the natural migration.

Template: [`templates/pulumi/typescript-eks/`](templates/pulumi/typescript-eks/)

**If your team writes Go daily -> Pulumi (Go SDK)**

Why: Same reasoning as Python. Use the language your team knows. Pulumi's Go SDK is well-maintained and Go's type system catches infrastructure misconfigurations at compile time.

When to reconsider: Pulumi's Go SDK has a smaller community than the Python/TypeScript SDKs. If you are blocked on a provider issue, check community activity before committing.

**If no strong language preference -> Terraform (HCL)**

Why: HCL is a domain-specific language built for infrastructure. It is declarative by design, which prevents the "I accidentally wrote an infinite loop in my infrastructure code" class of bugs. For a team without existing language preferences, the constraint of a DSL is a feature -- it forces infrastructure-appropriate patterns. Terraform also has the largest ecosystem: the module registry, provider coverage, and community support are unmatched.

When to reconsider: If your team grows and wants to share logic between application code and infrastructure code, or if HCL's limited programming constructs (no real functions, limited loops before 1.x) frustrate your team.

Template: [`templates/terraform/aws-ecs-fargate/`](templates/terraform/aws-ecs-fargate/)

#### Mid-Size Team (4-10 engineers)

The team-size dynamics shift at 4+ engineers. Code review, module sharing, and onboarding new engineers matter more than individual productivity.

**Single cloud -> Evaluate CDK vs. Terraform**

- CDK if: your team is TypeScript-heavy, you are AWS-only, and you want the tightest cloud integration.
- Terraform if: you want provider-agnostic patterns (useful even within a single cloud for portability), or your team is not TypeScript-heavy.

**Multi-cloud -> Terraform or Pulumi**

- Terraform if: you need the broadest provider coverage and want the largest hiring pool.
- Pulumi if: your team has a strong language preference (Python/TS/Go) and values using general-purpose languages over HCL.

#### Large Team (10+ engineers)

**Default: Terraform.**

At this scale, ecosystem matters more than language elegance. Terraform gives you: the largest hiring pool (most DevOps job postings list Terraform), the most mature module registry, battle-tested state management patterns (remote state, workspaces, state locking), and the broadest provider coverage. The HCL learning curve is a one-time cost that pays dividends in team scalability.

### The Reversibility Check

**This is the part no comparison post covers.**

Every IaC tool has migration paths to every other IaC tool:
- Terraform -> Pulumi: `pulumi import` can read Terraform state files
- CDK -> Terraform: Export CloudFormation, import into Terraform
- Pulumi -> Terraform: Export state, import resources
- Any tool -> Any tool: At worst, you `import` existing cloud resources into the new tool

**None of these decisions are permanent.** The real cost of switching is not technical -- it is the team knowledge and module library you have built. That cost grows over time, which is why making a good-enough decision now matters more than making a perfect decision in three months.

**Rule of thumb:** If you are spending more than one week deciding, you are overthinking it. Pick the option that matches your team's existing skills. Build for 6 months. Revisit with real production data. The data will make the next decision obvious.

---

## Container Orchestration Preview: "Do You Actually Need Kubernetes?"

Before you decide between ECS and EKS, answer this question honestly:

### The Kubernetes Necessity Check

| Question | If Yes | If No |
|----------|--------|-------|
| Do you have 3+ microservices that need independent scaling? | K8s might be justified | Skip K8s |
| Does your team have at least one engineer with production K8s experience? | K8s might be justified | Skip K8s |
| Is your monthly cloud budget above $5,000? | K8s is financially viable | ECS Fargate or Lambda |
| Do you need multi-cloud workload portability? | K8s is the only real option | Cloud-native services are fine |
| Are you running ML/AI workloads that need GPU scheduling? | K8s (EKS) for GPU node pools | Probably do not need K8s |

**If you answered "No" to 3+ of these questions: you do not need Kubernetes.**

Use ECS Fargate (for container workloads) or Lambda (for event-driven workloads). You will save money, operational complexity, and late-night debugging sessions.

**The number most people do not know:** EKS costs $2,400/year just for the control plane ($0.10/hr x 24hrs x 365 days) -- before you run a single container. ECS has no control plane cost. For a small team with a tight budget, that $2,400 buys a lot of ECS tasks.

> The full container orchestration decision tree (including ECS vs. EKS vs. Lambda vs. plain Docker branching by workload type, team experience, and budget) is in the complete Decision Kit.

---

## What the Full Kit Includes

The free content in this repo covers the complete IaC decision tree, the "Do you need Kubernetes?" analysis, the Jenkins migration guide, deployable ECS Fargate and Lambda templates, GitHub Actions workflows, and two end-to-end architecture examples.

**The full DevOps Decision Kit ($29) adds:**

- Complete decision trees for container orchestration, CI/CD pipelines, and monitoring stacks
- The 15-point AI infrastructure review checklist (for Copilot/ChatGPT-generated Terraform)
- Cost-at-scale analysis for monitoring stacks (the Datadog pricing surprise)
- Deployable EKS, Pulumi, GitLab CI, and Prometheus+Grafana templates
- "When to switch" reversibility analysis for every decision
- Multi-cloud end-to-end architecture example

One payment. Yours forever. 30-day money-back guarantee.

**[Get the Full DevOps Decision Kit -- $29](link)**

---

## Stay Updated

The infrastructure landscape changes. Decision trees should too.

Sign up for the DevOps Decision Kit newsletter and get:
- Updates when decision trees are revised (new tools, changed pricing, shifted ecosystems)
- One real infrastructure decision breakdown per week -- what was chosen, why, and what happened
- Early access to new decision frameworks before they hit the repo

**[Subscribe for decision tree updates](link)**

No spam. No "10x your DevOps" marketing. Just infrastructure decisions, analyzed.

---

## About the Author

Built by an engineer who designed production infrastructure for:
- **Qortex** -- complex backend systems handling real production traffic
- **MindMirror** -- enterprise federated GraphQL platform + Expo mobile application
- **24-week cybersecurity curriculum** -- built and ran at a company doing $60MM+ ARR

Previously the 13th most popular author on Scotch.io (the go-to frontend education platform before its acquisition). That background means this is not just a practitioner writing docs -- it is a proven technical educator who builds production systems.

Every decision tree in this repo traces back to a real infrastructure decision made under real production pressure. Not hypothetical. Not theoretical. Real teams, real budgets, real consequences.

---

## Contributing

This repo gets better when practitioners share their decisions.

**How to contribute:**

- **Report a scenario the trees do not cover:** Open an issue using the [scenario request template](.github/ISSUE_TEMPLATE/scenario-request.md). Describe your team size, budget, stack, and what you need to decide. I will add a branch or clarify an existing one.
- **Share your decision outcome:** Used a decision tree and deployed? Tell me what happened. Open an issue using the [decision feedback template](.github/ISSUE_TEMPLATE/decision-feedback.md). Real-world feedback makes the trees more accurate.
- **Submit a case study:** If you used the Decision Kit to make an infrastructure choice and have 6+ months of production data, I would love to include your case study (anonymized if needed). This is the highest-value contribution.
- **Fix errors:** Found a factual mistake, outdated pricing, or broken template? PRs welcome.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## License

MIT License. See [LICENSE](LICENSE) for details.

The decision trees, templates, and documentation in this repo are free to use, modify, and share. The [full DevOps Decision Kit](link) is a paid product that includes additional decision trees, templates, and analysis not available in this repo.
