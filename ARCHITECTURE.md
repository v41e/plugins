# Architecture

This document provides a high-level overview of the **v41e Plugins repository**
architecture.

## 1. High-Level System Overview

The repository distributes instruction-driven plugins that run in the user's
agent client. It hosts no application service or shared execution runtime.
The marketplace routes installation; each package owns its behavior and context.

```mermaid
flowchart LR
  catalog["Marketplace catalog"] --> plugins["Plugin packages"]
  plugins --> client["Compatible agent clients"]
```

## 2. Core Components

### 2.1. Public Marketplace

- **Technology**: [Codex marketplace JSON metadata](https://developers.openai.com/plugins/build/plugins#marketplace-metadata).
- **Responsibility**: distribute public plugins from one Git repository.
- **Key interactions**: resolves catalog entries to packages under `plugins/`.

### 2.2. Plugin Packages

- **Technology**: [Agent Plugins 1.0.0](https://raw.githubusercontent.com/agentplugins/agent-plugins-spec/refs/heads/main/spec/1.0.0.md)
  packages with Codex compatibility metadata in `.codex-plugin/plugin.json`.
- **Responsibility**: own each plugin's manifests, skills, documentation, and behavior.
- **Key interactions**: compatible clients load the selected package; package
  details remain inside its owning directory.
- **Versioning**: every plugin manifest shares the repository version.

Plugin-specific documentation stays inside the distributed package's `docs/`.

### 2.3. Skill Contracts

The implementation is Markdown following the [Agent Skills format](https://agentskills.io/llms.txt).
Skills are callable entrypoints. Modes select alternative operations; workflows
order lifecycle stages; stages identify required evidence and a transition gate.
Each uses `Purpose`, `Input`, `Workflow`, `Output`, and `Rules`, with routing
inside the relevant section. Using skills are concise inventories of purpose,
skills, and requirements.

Platform adapters map logical concepts to concrete tools, commands, and remote
surfaces. Integration adapters map observed conditions to installed skills.
Conditional capability tables use `When`, `Capability`, and `Result`; schemas
and inventories keep columns appropriate to their content. Mappings preserve
the selected operation's scope and approval gates.
Target references describe destination structure and templates.

Locus owns content placement and discovery. Iter owns work records and gates,
repository briefs, bounded maintenance runs, and explicitly requested sequential
project-task dispatch. The owning project context and installed engineering
skills supply implementation and review methods. Both packages remain
independently installable.

## 3. Data Stores

No runtime data store is bundled. Knowledge maps, work artifacts, and task state
remain in their selected destinations, GitHub, or the host client.

## 4. External Integrations / APIs

- **GitHub**: hosts distribution, CI, and releases. Skills also use GitHub tools
  or the CLI for Issues, Projects, and pull requests; the
  [Iter tracking adapter](plugins/iter/skills/track/references/platforms/github.md)
  and [Iter maintenance adapter](plugins/iter/skills/maintain/references/platforms/github.md)
  define the applicable mappings and write boundaries.
- **Codex desktop**: Iter's skill-local
  [Brief mapping](plugins/iter/skills/brief/references/harnesses/codex.md) and
  [Orchestrate adapter](plugins/iter/skills/orchestrate/references/harnesses/codex.md)
  map read-only evidence and authorized dispatch to host-provided task tools.
  Live schemas own invocation details; discovery does not authorize dispatch.

The packages bundle no MCP server or standalone API client. Integrations use
capabilities and authenticated access supplied by the execution environment.

## 5. Deployment & Infrastructure

- **Distribution**: public Git repository containing installable plugin packages.
- **Codex delivery**: marketplace catalog under `.agents/`.
- **Other clients**: direct installation from a compatible package under `plugins/`.
- **CI/CD**: GitHub Actions checks JSON syntax, diff whitespace, and pull-request
  titles, and applies the shared stale-item policy. Release Please opens version
  pull requests against `main`; merging one creates a `vX.Y.Z` tag and GitHub
  Release without publishing to a package registry.

## 6. Security Considerations

- Repository contents are public; private maps, credentials, and personal facts
  must remain outside it.
- Marketplace, manifest, and plugin changes affect the distributed trust surface
  and require review.
- External actions remain subject to caller authorization, repository policy,
  and host permissions; authenticated access alone does not authorize a write.

## 7. Development & Testing Environment

Validate repository metadata using the root [`AGENTS.md`](AGENTS.md) command.
Follow the owning plugin's `AGENTS.md` for package-level checks and
[`CONTRIBUTING.md`](CONTRIBUTING.md) for the repository workflow.

Codex loads an installed copy of each plugin. Refresh that installation and
reload the client when evaluating changed skills; editing the source checkout
alone does not update the installed copy.

## 8. References

No separate architecture decision records are maintained. Format and integration
contracts are linked from their owning sections above.
