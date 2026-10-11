# Repolex Knowledge Graph of certifi/gocertifi

RDF knowledge graph data for [certifi/gocertifi](https://github.com/certifi/gocertifi), parsed by [repolex](https://repolex.ai).

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
rlex download certifi/gocertifi
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 431795d63e8d175f8ce1325a674698adf81e96a7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 431795d63e8d175f8ce1325a674698adf81e96a7
│           └── chunk-001.nq.gz
├── blob
│   ├── 14e2f777f6c395e7e04ab4aa306bbcc4b0c1120e.nq.gz
│   ├── 372fd9f4b296b2ab4e4ac7422dc2cda7919f67a1.nq.gz
│   ├── 6d045a2aeacca3e6243ba4dd3ad8299c3219152e.nq.gz
│   ├── 70be286dc3aaffe52bc374de703cebcfd6626011.nq.gz
│   ├── 955f7f25b94d4c6ca64b5b5aee88006aeab1e557.nq.gz
│   ├── 9c860301dc8da06b990f1310b66a9da99be15bb9.nq.gz
│   ├── e55167e9a8824a95ca45100524c8d30c3edd1957.nq.gz
│   └── ee7caafd7ca1c1100e5852b285e21e1451827376.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 431795d63e8d175f8ce1325a674698adf81e96a7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 16 files
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

[certifi/gocertifi](https://github.com/certifi/gocertifi)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
