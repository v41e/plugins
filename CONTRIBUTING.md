# Contributing

Use this guide for workflow, commands, and contribution expectations.

## Getting Help

Before opening an issue, check [SUPPORT](SUPPORT.md) for support channels and
escalation paths.

## Security

If you discover a security issue, follow [SECURITY](SECURITY.md). Do not file
public issues for security-sensitive problems.

## Development Workflow

Keep temporary drafts, specs, plans, and working notes out of permanent Git
history unless repository instructions require them. Reconcile durable content
into its owner; capture rationale and verification in issues or PRs.

AI-assisted contributions follow the same standards, checks, and review
requirements as any other contribution. Contributors remain responsible for
understanding and verifying their changes.

### Versioning

This project follows [Semantic Versioning](https://semver.org).

### Branching Model

This project uses [git-flow-next](https://git-flow.sh):

- **`main`**: production-ready releases
- **`develop`**: integration and alpha releases
- **`feature/*`** and **`bugfix/*`**: work targeting `develop`
- **`release/*`**: release preparation from `develop`
- **`hotfix/*`**: production fixes from `main`
- **`support/*`**: maintenance for older releases

### Git Worktrees

Use [Git worktrees](https://git-scm.com/docs/git-worktree) for parallel feature
work without switching the main checkout.

## Style Guide

Follow
[Google's Markdown guide](https://google.github.io/styleguide/docguide/style.html),
with local conventions and tool configuration taking precedence. Use title case
headings and compact tables. See [AGENTS.md](AGENTS.md#checks) for check and fix
commands.

## Code Standards

- **Simplicity**: reuse existing procedures and keep responsibilities, inputs,
  outputs, and permission boundaries clear. Preserve validation and error
  handling.
- **Documentation**: keep topic knowledge in its owner under `docs/`; update
  README navigation and AGENTS instructions when their scope changes. Preserve
  declared root architecture and community-policy owners.
- **Diagrams**: use [Mermaid](https://mermaid.js.org) for embedded Markdown
  diagrams and [D2](https://d2lang.com) for richer diagram source files.

## Review

Follow
[Google's review guidance](https://google.github.io/eng-practices/review/reviewer/)
for correctness, design, simplicity, verification, readability, and
documentation. Obtain independent review of material drafts and changes against
their intent, applicable standards, and exact revision. Resolve supported
findings and refresh affected review after corrections before the human
checkpoint. Humans own merge and release decisions.

## Pull Requests

- **Commits**: follow
  [Conventional Commits](https://www.conventionalcommits.org).
- **Scope**: keep each PR focused; explain its intent and link relevant issues.
- **Verification**: run the affected `AGENTS.md` commands and include evidence.
- **Documentation**: update durable guidance when commands, behavior, or package
  boundaries change.
- **Target**: use `develop` for feature work and `main` for hotfixes.

## License

By contributing to this repository, you agree that your contributions will be
licensed under the [LICENSE](LICENSE).

## Code of Conduct

This project is released with a
[Contributor Code of Conduct](CODE_OF_CONDUCT.md). By participating in this
project you agree to abide by its terms.
