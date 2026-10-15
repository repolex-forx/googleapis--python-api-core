# Repolex Knowledge Graph of googleapis/python-api-core

RDF knowledge graph data for [googleapis/python-api-core](https://github.com/googleapis/python-api-core), parsed by [repolex](https://repolex.ai).

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
rlex download googleapis/python-api-core
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── daf3040befffb7dd9629c43c4201e6e4db693b15
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── daf3040befffb7dd9629c43c4201e6e4db693b15
│           └── chunk-001.nq.gz
├── blob
│   ├── 79e7428a521830174c9bdae25e6361efe8cd4e2c.nq.gz
│   ├── 8b58ae9c01ae3b07eeba325544a99071e0713f31.nq.gz
│   ├── 8b6a7614d1ec58dddcee62d703a8eff9af1b9ca7.nq.gz
│   └── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── daf3040befffb7dd9629c43c4201e6e4db693b15.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 12 files
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

[googleapis/python-api-core](https://github.com/googleapis/python-api-core)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
