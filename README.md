# Repolex Knowledge Graph of sanic-org/simple-tox-action

RDF knowledge graph data for [sanic-org/simple-tox-action](https://github.com/sanic-org/simple-tox-action), parsed by [repolex](https://repolex.ai).

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
rlex download sanic-org/simple-tox-action
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 645bfc92ceac1f4f089e3d95048ec0d967f155ce
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 645bfc92ceac1f4f089e3d95048ec0d967f155ce
│           └── chunk-001.nq.gz
├── blob
│   ├── 0477c49de1fdd1c5a3928d5535d5ccc20b6f9a4e.nq.gz
│   ├── f3b34a3c31ffe4485662134b639eb700829ae4fe.nq.gz
│   └── fdde0b12696b71a4e8eb26af6a03b27084ffcd46.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 645bfc92ceac1f4f089e3d95048ec0d967f155ce.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 9 files
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

[sanic-org/simple-tox-action](https://github.com/sanic-org/simple-tox-action)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
