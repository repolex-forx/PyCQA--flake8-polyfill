# Repolex Knowledge Graph of PyCQA/flake8-polyfill

RDF knowledge graph data for [PyCQA/flake8-polyfill](https://github.com/PyCQA/flake8-polyfill), parsed by [repolex](https://repolex.ai).

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
rlex download PyCQA/flake8-polyfill
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b98e6f4f6cc90334f4d7040745aee91b4021cc42
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b98e6f4f6cc90334f4d7040745aee91b4021cc42
│           └── chunk-001.nq.gz
├── blob
│   ├── 053148f848642cb6c79ecb61968f0a9d3fea8bb4.nq.gz
│   ├── 0c0cc53e53402740c0cfb72900f8f001cf7e51d9.nq.gz
│   ├── 1e4f96abcdad30ce1a652e39a8ab6a2d4eb1e282.nq.gz
│   ├── 212b309f3bd1a4c33e64090f812344b3f2e20101.nq.gz
│   ├── 32c9e4ff18b209e04b85d3cc065c021ddcfb2701.nq.gz
│   ├── 429826f9e80c5a7ea1abcaaa0e84331f1f97ffa3.nq.gz
│   ├── 4b8291e43a7be657e4a73b1e9c928c357f8e077f.nq.gz
│   ├── 529ecd514bb676965bcc3d035bc1d297fc5068d3.nq.gz
│   ├── 57ec501d4d07a765591f5f0784fdf71db806de1e.nq.gz
│   ├── 6446078062c4579ddc5c735390d563a1d84bfbc2.nq.gz
│   ├── 646f00148d1cacf5c0bc2269d05064c1b7b01d4c.nq.gz
│   ├── 6ad1f190a25e4e7b7d6b3fc07e5ed7d1ef1ee72b.nq.gz
│   ├── 96b10e779d1665af2fced16e91e8466e631d5a16.nq.gz
│   ├── a7f020499608ef8ba0903151dea612ed13807508.nq.gz
│   ├── aab1e01a738eb7f186a58f6a58890527b75f219a.nq.gz
│   ├── ab7de3922c29436de130e7476890408aa3203e7e.nq.gz
│   ├── b265aa2cc39a52cd65d6eb5e2f41f83a60229ae6.nq.gz
│   ├── c644e741ca6c3ae6cf0ebb9c839bf490a24071f1.nq.gz
│   ├── d32256f8414e13779595b6b94b8a6bedd99a0868.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f778dd4eb8f4f0728e1b8bbaa165a4cccc23e450.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b98e6f4f6cc90334f4d7040745aee91b4021cc42.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[PyCQA/flake8-polyfill](https://github.com/PyCQA/flake8-polyfill)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
