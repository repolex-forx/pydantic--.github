# Repolex Knowledge Graph of pydantic/.github

RDF knowledge graph data for [pydantic/.github](https://github.com/pydantic/.github), parsed by [repolex](https://repolex.ai).

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
rlex download pydantic/.github
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 31399f9034a545b94e0df43776fa2e46bdcac133
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 31399f9034a545b94e0df43776fa2e46bdcac133
│           └── chunk-001.nq.gz
├── blob
│   ├── 19453b3b5e22ddd100f36d7298a74fbb90358692.nq.gz
│   ├── 8917885cd2da286d2d00ee02802002d69c628cb6.nq.gz
│   └── f1c8f6a889239bfe348f4135a1efee52cc3cec98.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 31399f9034a545b94e0df43776fa2e46bdcac133.nq.gz
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

[pydantic/.github](https://github.com/pydantic/.github)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
