# v41e Plugins

Public Agent Plugins and Codex marketplace metadata for v41e.

## Overview

The marketplace distributes two independently installable plugins:

| Plugin                           | Purpose                                                                                          |
| -------------------------------- | ------------------------------------------------------------------------------------------------ |
| [Locus](plugins/locus/README.md) | Discover, initialize, track, and distill knowledge and active work across owned destinations.    |
| [Iter](plugins/iter/README.md)   | Brief current project work, execute authorized changes, or dispatch across saved Codex projects. |

## Structure

- [`plugins/`](plugins/): installable plugin packages:
  - [`locus/`](plugins/locus/): Locus knowledge lifecycle plugin
  - [`iter/`](plugins/iter/): Iter engineering operations plugin
- [`ARCHITECTURE.md`](ARCHITECTURE.md): repository relationships and distribution boundaries
- [`AGENTS.md`](AGENTS.md): repository operating contract

## Getting Started

### Installation

Point a compatible client at the selected package root under [`plugins/`](plugins/)
using the client's installation process.

With Codex:

```sh
codex plugin marketplace add https://github.com/v41e/plugins
codex plugin add locus@v41e
codex plugin add iter@v41e
```

Start a new task after installation or upgrade so the plugin skills are loaded.

## Contributing

Please read the [CONTRIBUTING](CONTRIBUTING.md) guide for workflow and
contribution expectations.

## License

This project is licensed under the terms of the [LICENSE](LICENSE).
