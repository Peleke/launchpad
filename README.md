# From 1 to Prod

<!-- IMAGE_INTENT: Isometric dark-background illustration showing a progressive pipeline from a simple terminal/Linux icon on the left flowing through containers, CI/CD gears, cloud infrastructure, monitoring dashboards, to a Kubernetes cluster on the right. Teal and blue accent colors. Clean, technical, minimal.
     PROMPT: isometric technical illustration, dark navy background, progressive DevOps pipeline flowing left to right, Linux terminal icon, Docker container, CI/CD gear mechanism, AWS cloud, Grafana dashboard, Kubernetes wheel, connected by glowing teal pipeline lines, clean minimal style, no text, 1280x640
     DIMENSIONS: 1280x640 -->

> **"I don't want another random list of videos/courses to watch. I need: STRUCTURE. ACTIONABLE sequence. REAL capstone projects end to end that simulate real production DevOps architecture."** -- r/devops

One real app. Eight modules. From Linux to production Kubernetes. No videos to watch -- code to ship.

## The Problem

You have done 50 tutorials. You can spin up a Docker container. You can follow a Terraform walkthrough. But hand you a blank terminal and ask you to deploy a 3-tier app to production? You freeze.

This repo fixes that.

## What This Is

A progressive capstone project. One user-facing, 3-tier application that evolves through 8 modules:

| Module | Branch | What You Build | Time |
|--------|--------|---------------|------|
| 01: Linux Fundamentals | `01-linux` | Working dev environment, SSH, file permissions | 4-6 hrs |
| 02: Scripting | `02-scripting` | Bash + Python automation: backup, health check, deploy | 4-6 hrs |
| 03: Docker | `03-docker` | Containerized 3-tier app with Docker Compose | 6-8 hrs |
| 04: CI/CD | `04-cicd` | GitHub Actions pipeline that tests locally first | 6-8 hrs |
| 05: Terraform | `05-terraform` | AWS infrastructure as code: VPC, subnets, RDS, ECS | 8-10 hrs |
| 06: Serverless | `06-serverless` | Lambda, API Gateway, SQS/SNS, DynamoDB | 6-8 hrs |
| 07: Monitoring | `07-monitoring` | Prometheus + Grafana dashboards, alerting, runbook | 6-8 hrs |
| 08: Kubernetes | `08-kubernetes` | K8s deployment + serverless vs K8s decision framework | 8-10 hrs |

**Why Kubernetes is Module 8, not Module 1:** If you learn K8s first, you use K8s for everything. If you learn serverless first (Module 6), you learn when K8s is the right call and when it isn't. That distinction is what separates the candidate who gets hired from the 11 who don't.

## Quick Start

```bash
git clone https://github.com/Peleke/from-1-to-prod.git
git checkout 01-linux
cat README.md  # Each module has its own guide
```

Each module branch has:
- A README with step-by-step instructions
- Tests that validate each milestone (`make test`)
- The complete code from all prior modules

## Portfolio-Ready at Every Checkpoint

Stop after Module 3 and you have a containerized 3-tier app.
Stop after Module 4 and you have full CI/CD.
Stop after Module 5 and you have production IaC on AWS.
Every checkpoint is a portfolio piece.

## The Decision Framework: Serverless vs Kubernetes

This is free. This is the 80% that matters.

**Use serverless when:**
- Request volume is bursty or unpredictable
- Individual functions do one thing (< 15 min execution)
- You want zero infrastructure management
- Your team is small (< 5 engineers)
- Cold start latency is acceptable for your use case

**Use Kubernetes when:**
- You need persistent connections (WebSockets, gRPC streaming)
- You have steady, predictable traffic at scale
- You need fine-grained control over networking, storage, and scheduling
- Your team has dedicated platform/infra engineers
- You're running stateful workloads that need custom orchestration

**Use both when:**
- Event-driven async processing (Lambda) + steady API traffic (K8s)
- Background jobs (Lambda) + real-time serving (K8s)
- Most production systems at scale use both -- the question is which workload goes where

The full decision framework with real-world case studies is in Module 8: [`docs/serverless-vs-k8s.md`](docs/serverless-vs-k8s.md)

## Project Structure

```
from-1-to-prod/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── .github/
│   ├── workflows/ci.yml
│   └── ISSUE_TEMPLATE/
├── app/
│   ├── frontend/           # React/Vue/Svelte frontend
│   ├── api/                # Node/Python/Go API server
│   ├── database/           # Schema, migrations, seeds
│   └── docker-compose.yml  # Local development environment
├── scripts/                # Module 2: Automation scripts
├── infrastructure/
│   ├── terraform/          # Module 5: AWS IaC
│   ├── serverless/         # Module 6: Lambda + API Gateway
│   └── kubernetes/         # Module 8: K8s manifests
├── monitoring/             # Module 7: Prometheus + Grafana
├── tests/                  # Unit, integration, E2E
└── docs/                   # ADRs, module guides, decision frameworks
```

## Prerequisites

- Basic programming ability (any language)
- A computer with terminal access
- An AWS account (free tier is sufficient)
- No prior DevOps experience required

## Who Built This

I learned DevOps by shipping real things, not by watching courses.

- Built a 24-week cybersecurity program at a company doing $60MM+ ARR
- Built production systems: Qortex, MindMirror, Interlinear
- Every example in this repo comes from real engineering decisions

This repo is free because the best way to prove you can teach something is to give it away and let the work speak.

## Community

Building in the open is good. Building with peers is better.

The Skool community is where builders doing this capstone get:
- Peer code review on every module checkpoint
- Weekly office hours for production debugging
- Advanced challenges beyond the 8 modules
- Direct access to the builder

[Join the community](#) or [get notified when new modules drop](#).

## Contributing

Found a bug? Open an issue.
Disagree with the module sequence? Start a discussion.
Built something cool on top of this? Submit a PR.

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

MIT. Use it, fork it, build on it. Attribution appreciated but not required.
