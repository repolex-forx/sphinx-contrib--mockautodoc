# Repolex Knowledge Graph of sphinx-contrib/mockautodoc

RDF knowledge graph data for [sphinx-contrib/mockautodoc](https://github.com/sphinx-contrib/mockautodoc), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/mockautodoc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9503134d022e93fe95646254fefee0095db16151
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9503134d022e93fe95646254fefee0095db16151
│           └── chunk-001.nq.gz
├── blob
│   ├── 21799b6277a03bebd8d3616c4950138a66693223.nq.gz
│   ├── 25c5c37f32e055c81289668ba32d07cd0d1374bb.nq.gz
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 42a41e2e7f4e107830689f2da7fe3f54595bb848.nq.gz
│   ├── 83033deacc0b7fe1d9aa7aa182520b530b7f987b.nq.gz
│   ├── 8c070d53476aeee1d11ecf02cbf003851141cf01.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── a4c7077401ffef1782b4e5779e7468a61b379273.nq.gz
│   ├── bca19ea3b946f32cd194da221bd3af3dfacaa50a.nq.gz
│   ├── c6e8c824c6df487a3f7f7191c832f2cbc1b14f36.nq.gz
│   ├── cd4f0a764ca7bd4401951c16e9bd88b0341a5a51.nq.gz
│   ├── e0dafce3f89e25966a83fe2822e9a8fad4b4f57b.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9503134d022e93fe95646254fefee0095db16151.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 19 files
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

[sphinx-contrib/mockautodoc](https://github.com/sphinx-contrib/mockautodoc)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
