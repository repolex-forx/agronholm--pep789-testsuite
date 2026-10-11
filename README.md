# Repolex Knowledge Graph of agronholm/pep789-testsuite

RDF knowledge graph data for [agronholm/pep789-testsuite](https://github.com/agronholm/pep789-testsuite), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/pep789-testsuite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5f0c7df0cad1cc902a85d8941c07ad265c1ed639
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5f0c7df0cad1cc902a85d8941c07ad265c1ed639
│           └── chunk-001.nq.gz
├── blob
│   ├── 33218ca9bba566a28d54167a996fcee5e45f15d8.nq.gz
│   ├── 39c8c17a3320742eefb6559894502920acd20a7a.nq.gz
│   ├── bfd81e997166efef9edd5d8b7d9d140ca8f5d8b1.nq.gz
│   └── ee7984dc65ec772e945c26250ec43f1e53762c59.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5f0c7df0cad1cc902a85d8941c07ad265c1ed639.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 10 files
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

[agronholm/pep789-testsuite](https://github.com/agronholm/pep789-testsuite)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
