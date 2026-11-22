# Repolex Knowledge Graph of rust-lang/jobserver-rs

RDF knowledge graph data for [rust-lang/jobserver-rs](https://github.com/rust-lang/jobserver-rs), parsed by [repolex](https://repolex.ai).

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
rlex download rust-lang/jobserver-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4bcd123ffc997020367416a970ae20577a76a583
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4bcd123ffc997020367416a970ae20577a76a583.nq.gz
│   └── repolex
│       └── 4bcd123ffc997020367416a970ae20577a76a583
│           └── chunk-001.nq.gz
├── blob
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 2758e319c68eb66b5709cbe4f42118f79092d8c2.nq.gz
│   ├── 324c57f7ddc8eb75127670990db579b1e4870f43.nq.gz
│   ├── 39e0ed6602151f235148e6c08413aa7eda5b9038.nq.gz
│   ├── 45d57b0b58154f3927a8dde7671bcbe4d839ff55.nq.gz
│   ├── 4ba0dbf2272119c85ce3c37748e30fe90beaceee.nq.gz
│   ├── 4faac5b8803a4ce49ad06f089457876f6ce7c992.nq.gz
│   ├── 550f658a13a34d875d40c50a3f002c5bd5ac1f95.nq.gz
│   ├── 70ea218fc7e170ed3e2f58619a4c66149fcba71e.nq.gz
│   ├── 7377d37597f73d1edf3cdffd383e41cb04d68f2b.nq.gz
│   ├── 7a60242ba63b46d382a95f625add6f66373353fb.nq.gz
│   ├── 7ebdeabbe4ae86dcf544cf95edbb787b00fb7493.nq.gz
│   ├── b61a10aeaf1fce19527b4c3fd668e7c293ff9f31.nq.gz
│   ├── bdac3384fc7ff21ffe2f6777b8c1cf41e810eac2.nq.gz
│   ├── d705bf1b9f25c4b13c4a34fa71298fb354106db6.nq.gz
│   ├── df230909c6a2b40940c1ea8111f315ca0c689cea.nq.gz
│   ├── ec38f2fc1e982a451e85162a9b84bd281c511bad.nq.gz
│   ├── f10a10c195c77e5091b7169abe2415a46657aff1.nq.gz
│   ├── f2e163624066068be83b9efeb00c4db85837c420.nq.gz
│   └── f3baaf048e8a317b7cad980dc4f74844fca7b3fd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 4bcd123ffc997020367416a970ae20577a76a583.nq.gz
├── filetree
│   └── 4bcd123ffc997020367416a970ae20577a76a583.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 30 files
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

[rust-lang/jobserver-rs](https://github.com/rust-lang/jobserver-rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
