# Repolex Knowledge Graph of pallets/.github

RDF knowledge graph data for [pallets/.github](https://github.com/pallets/.github), parsed by [repolex](https://repolex.ai).

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
rlex download pallets/.github
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 06702680f531ba49dc901b584479048ab55724f1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 06702680f531ba49dc901b584479048ab55724f1
│           └── chunk-001.nq.gz
├── blob
│   ├── 17cd6bed3c0392591e65e57162f8203094d98097.nq.gz
│   ├── 31954510b7067fc761286583173a0bdaf03f066a.nq.gz
│   ├── 4e3616333c0242605106e6820c04f05e85003ea8.nq.gz
│   ├── 703b4fbb4c5518ecdf14074ce3d23c431c2eda0d.nq.gz
│   └── a51ce41a726db60f4ef8b0252c79dbf542e09485.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 06702680f531ba49dc901b584479048ab55724f1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 13 files
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

[pallets/.github](https://github.com/pallets/.github)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
