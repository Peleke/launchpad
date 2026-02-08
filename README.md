# launchpad

Product sketches and launch-ready structures. Each branch is a deployable product skeleton.

## How It Works

- **`main`** — This index. Lists all products and their status.
- **Each branch** — A complete product structure: directory layout, file manifest, README, templates, and deployment-ready scaffolding.

## Products

| Branch | Product | Price | Status | Pipeline Ref |
|--------|---------|-------|--------|--------------|
| `devops-decision-kit` | The DevOps Decision Kit | $29 | `spec` | [Pitch](https://github.com/Peleke/product-lab/tree/devops-decision-kit) |

## Pipeline

Products flow through the [hunter pipeline](https://github.com/Peleke/hunter):

```
signal-scan → decision-log → persona-extract → swot-analysis → offer-scope → pitch → HERE
```

Each branch is created by the `pitch` skill's Product Structure Sketch (Phase 3a). The structure is immediately ready to build from.

## License

MIT
