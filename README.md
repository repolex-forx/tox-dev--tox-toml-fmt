# Repolex Knowledge Graph of tox-dev/tox-toml-fmt

RDF knowledge graph data for [tox-dev/tox-toml-fmt](https://github.com/tox-dev/tox-toml-fmt), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download tox-dev/tox-toml-fmt
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5125f601c3e134347288c3d42f3b34298b7cf1be
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5125f601c3e134347288c3d42f3b34298b7cf1be
│           └── chunk-001.nq.gz
├── blob
│   ├── 10e740e9f7957eda52d55a88e3dafb2521a260ce.nq.gz
│   ├── 1a1b2a5d87fffa385960ae8a744ad0e3ed92ea78.nq.gz
│   ├── 2a327285e108cb98478afd9370282f47c9b69760.nq.gz
│   ├── 364982344fbd94d55705e1f27a9a87abaa255333.nq.gz
│   ├── 3fdfeb9b4b2c569f8decb9b17103b1864adb89e4.nq.gz
│   ├── 4425c229252139bd2641fda4badd61ca3cf27f6c.nq.gz
│   ├── 5968e5bcc55e7d0e43554bfb3203512e1e1fe0d0.nq.gz
│   ├── 720c7384c6195b916c795feaddb08bbe023d183c.nq.gz
│   ├── 9ba8cd21878e485d74d17c46150b9384360a3209.nq.gz
│   ├── 9d1e0987bfc323000b570d680343f00c53ddbc3d.nq.gz
│   ├── a7751edfc032aece3739cc030c2f7a686d2a2555.nq.gz
│   ├── c98c76a3070e33e2d90d0939f19a32375ef2110a.nq.gz
│   └── ddaf560052214777439227677bc6930fb2e6908e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5125f601c3e134347288c3d42f3b34298b7cf1be.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[tox-dev/tox-toml-fmt](https://github.com/tox-dev/tox-toml-fmt)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
