# Contributing to From 1 to Prod

Thanks for wanting to contribute.

## How to Help

**Found a bug in a module?** Open an issue with the module number and what went wrong. Include your OS, terminal, and any error output.

**Disagree with the module sequence?** Open a discussion. I'm genuinely interested in hearing why. The sequence (Linux -> Scripting -> Docker -> CI/CD -> Terraform -> Serverless -> Monitoring -> K8s) is intentional but not sacred.

**Want to add content?** PRs welcome for:
- Fixing typos or unclear instructions
- Adding alternative approaches (e.g., "here's how to do this step on Windows/WSL")
- Improving test coverage
- Adding Architecture Decision Records to `docs/decisions/`

**Want to add a module?** Open an issue first to discuss. Each module must build on the previous ones and use the same application.

## Code Style

- Shell scripts: ShellCheck-clean, POSIX-compatible where possible
- Python: Black-formatted, type hints preferred
- Terraform: `terraform fmt` applied
- All code: meaningful variable names, comments where the WHY isn't obvious

## Pull Request Process

1. Fork the repo
2. Create a branch from the relevant module branch (not `main`)
3. Make your changes
4. Run `make test` to verify
5. Open a PR with a clear description of what changed and why
