# Repolex Knowledge Graph of asottile/rubyvenv

RDF knowledge graph data for [asottile/rubyvenv](https://github.com/asottile/rubyvenv), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/rubyvenv
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 950bc54c9e3f406f7e574aabdcef6cded74ee32c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 950bc54c9e3f406f7e574aabdcef6cded74ee32c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0833183b4b36f1da722cb77cf1fca83b5cd4dcd5.nq.gz
│   ├── 0c5a37eb0adeb312718e533d0a4fbcbea6880056.nq.gz
│   ├── 212b3ea38b977d7853b41901eac5978fb486c2a0.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 5370c9485451439199ab7ab9ba30c95d9a046275.nq.gz
│   ├── 56c2c6ee316227caadf3ce0cec1f342f6d41f5b2.nq.gz
│   ├── 790b98e7065ea9d0f2b9d8c3ffeea3bedfc13b0f.nq.gz
│   ├── 8228d5e6d032de2f97c52ab93ff12334ac01d714.nq.gz
│   ├── 855495383b010b7f87fb811a9adf194ecab50ad6.nq.gz
│   ├── a5bd4fbb8f1cdf434ca145bfb68e7c3651eaa793.nq.gz
│   ├── b1447c3015af9511f2dee402ca4b5ad62adf5dce.nq.gz
│   ├── ce53accc83186664d2ba45bf342fdea4f2c114e2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e93335c39fe998575311ebfcd0b35641e56ec4c8.nq.gz
│   └── ff41a76b8e1e27461e5821cc946d0e7062ca00d7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 950bc54c9e3f406f7e574aabdcef6cded74ee32c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 23 files
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

[asottile/rubyvenv](https://github.com/asottile/rubyvenv)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
