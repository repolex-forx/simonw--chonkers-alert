# Repolex Knowledge Graph of simonw/chonkers-alert

RDF knowledge graph data for [simonw/chonkers-alert](https://github.com/simonw/chonkers-alert), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/chonkers-alert
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8088a62caed59e1fa5876223ebaedcc3761d3876
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8088a62caed59e1fa5876223ebaedcc3761d3876
│           └── chunk-001.nq.gz
├── blob
│   ├── 294ef129e42665a2d3639237d16cd817916490fb.nq.gz
│   ├── 34e0c72bfcdeb30b5a36449e09c0dd8d8db9355d.nq.gz
│   ├── 7294f89436d358dbcb41176a024b2254f2453a55.nq.gz
│   ├── 857ec01dba0f9bdf86e3cef8cf57a35a756587ea.nq.gz
│   ├── 91e3001e7349436c31359641f21c5f1c0b7190d8.nq.gz
│   ├── 9f04432c6544c2d8721d8a874352fa217a7436d3.nq.gz
│   ├── baff17b9c85f9819a7afd9606970f27c6e6c3825.nq.gz
│   ├── bfb728d6853dc7570b5d4e51f631311a860205eb.nq.gz
│   ├── d341d9961b47c762248fb3656663927703c08543.nq.gz
│   └── e2438352a8e5c765c09ad536764020bcbcc44514.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8088a62caed59e1fa5876223ebaedcc3761d3876.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 17 files
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

[simonw/chonkers-alert](https://github.com/simonw/chonkers-alert)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
