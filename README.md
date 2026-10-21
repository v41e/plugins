# V41e Plugins

Public Agent Plugins and Codex marketplace metadata for v41e.

## Overview

The marketplace distributes three independently installable plugins:

| Plugin | Purpose |
| ------ | ------- |
| [Locus](plugins/locus/README.md) | Find authoritative content and write knowledge in its proper owner. |
| [Iter](plugins/iter/README.md) | Brief project work, track its evidence, maintain authorized changes, or dispatch project-owned tasks. |
| [Forma](plugins/forma/README.md) | Design code structure and refactor existing code with practical maintainability guidance. |

## Structure

- [`plugins/`](plugins/): installable plugin packages:
  - [`locus/`](plugins/locus/): Locus content ownership plugin
  - [`iter/`](plugins/iter/): Iter work tracking and maintenance plugin
  - [`forma/`](plugins/forma/): Forma code design and refactoring plugin
- [`.agents/plugins/marketplace.json`](.agents/plugins/marketplace.json):
  package discovery catalog
- [`release-please-config.json`](release-please-config.json) and
  [`.release-please-manifest.json`](.release-please-manifest.json): shared
  release configuration and version
- [`.github/workflows/`](.github/workflows/): repository checks and release
  automation
- [`ARCHITECTURE.md`](ARCHITECTURE.md): repository relationships and
  distribution boundaries
- [`AGENTS.md`](AGENTS.md): repository operating contract

## Getting Started

### Prerequisites

Use an agent client that supports Agent Plugins v1 and Agent Skills. The Codex
commands below require a CLI installation with plugin support.

### How to Use

Point a compatible client at the selected package root under
[`plugins/`](plugins/) using the client's installation process.

With Codex:

```sh
codex plugin marketplace add https://github.com/v41e/plugins
codex plugin add locus@v41e
codex plugin add iter@v41e
codex plugin add forma@v41e
```

Install the plugins you need. Follow the client's reload process after
installation or updates; restart the desktop app for Codex desktop use.

## Contributing

Please read the [CONTRIBUTING](CONTRIBUTING.md) guide for details on how to
contribute. Pull requests, bug reports, and feature requests are welcome!

## License

This project is licensed under the terms of the [LICENSE](LICENSE).
