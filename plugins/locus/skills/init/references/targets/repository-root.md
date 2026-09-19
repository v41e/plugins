# Repository Root

Use this destination when the knowledge surface is repository-wide.

## Workflow

1. Inspect source-of-truth files such as manifests, build config, package directories, and existing docs.
2. Identify important source configuration, generators, grouping directories, real package boundaries, and canonical directories.
3. Keep `README.md` human-facing, keep durable depth in it or linked `docs/`,
   and keep `AGENTS.md` a concise semantic and procedural entrypoint.
4. Follow the shared structure contract in `SKILL.md`.
5. Expand grouping directories only to their direct package or plugin boundaries.
6. At the root, list and route to those direct boundaries without describing
   their internal components, commands, or workflows. Let each child README and
   AGENTS pair own that detail.
7. Use only the root pair when no independent child boundary exists.
8. Describe a generated boundary in `AGENTS.md` only when it changes how agents should edit the repository.
9. During Refresh, move content to its current owner and avoid duplicating
   durable explanations in `AGENTS.md`.

## Work Tracking

Add this optional section only when the repository's owning GitHub Project can
be verified from repository remotes or existing tracker documentation.

- Link the owning Project by stable name and URL.
- Omit the whole section when no owning Project is verified.
- Omit Milestones when the repository does not use them.
- When milestones are used, describe the stable naming or selection convention,
  not the moving current milestone.
- For unassigned release work, inspect open milestones and prefer the next
  relevant one according to that convention.

## Files

| Document          | Path              | Template                                                                  |
| ----------------- | ----------------- | ------------------------------------------------------------------------- |
| `README.md`       | `README.md`       | [README.md](../../assets/templates/repository-root/README.md)             |
| `AGENTS.md`       | `AGENTS.md`       | [AGENTS.md](../../assets/templates/repository-root/AGENTS.md)             |
| `ARCHITECTURE.md` | `ARCHITECTURE.md` | [ARCHITECTURE.md](../../assets/templates/repository-root/ARCHITECTURE.md) |

## Guidance

### README

- Keep it focused on what the repository is, its important structure, how to get started, and where the canonical root docs live.
- In a package or plugin repository, use a compact Overview list or table for direct children and link their README when useful. Keep `Structure` at directory boundaries and defer child details.
- Prefer links to existing canonical docs over duplication.
- Choose setup and usage steps for the actual repository type; omit inapplicable
  installation or environment steps.

### AGENTS

- Keep it short, additive, and agent-only.
- Include the operational essence agents need before acting: source layout, commands, verification, generated boundaries, protected paths, and docs-to-read triggers.
- Keep repository-wide rules at the root and route package- or plugin-specific work to the owning child `AGENTS.md`.
- Put local boundaries and canonical local documentation links in `Structure`.
- `Commands` lists entrypoints; `Verification` explains coverage and necessary extra
  checks from task definitions and CI. Keep it brief and repository-specific.
- Keep dependency links with their `Tech Stack` or architecture owner; retain
  relevant version/mode constraints and when to consult them. Use optional `References`
  for useful sources without an existing owner. Follow `SKILL.md` source guidance.
- Do not copy README prose; repeat only stable facts that change agent behavior.
- Include Work Tracking only under the verified conditions above.
- Add deployment safety and sharp edges only when they materially help.
- Select any additional sections using the optional-section criteria in `SKILL.md`.

### ARCHITECTURE

- Create it only when the user explicitly requests it or the repository has non-obvious cross-package, polyglot, runtime, data, deployment, or security relationships.
- Do not create it merely because a repository has large files.
- Keep all eight numbered template sections in order with stable numbering.
  Leave an inapplicable section empty or say so briefly.
- Use it to explain subsystem relationships, major flows, and high-level boundaries; keep path inventory in `README.md` and `AGENTS.md`.
- State system scope and consequential constraints in the overview; add a short
  Terminology subsection only for unfamiliar local terms. Keep project identity
  in the introduction and README, and moving roadmap items in their tracker.
- Keep component technologies with `Core Components`; use
  `External Integrations / APIs` for external services, their purpose, and
  integration contracts. Avoid a separate technology inventory.
  Describe actual storage and delivery surfaces, including files, local tools,
  libraries, and plugins; do not assume a cloud service or database.
- Keep `References` for verified sources recording why the design was chosen,
  such as decision records or evaluated alternatives. When none is verified,
  leave it empty or state that briefly. Technology and API documentation belongs
  with the relevant component, store, deployment surface, or external integration.
