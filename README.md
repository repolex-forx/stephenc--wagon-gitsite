# Repolex Knowledge Graph of stephenc/wagon-gitsite

RDF knowledge graph data for [stephenc/wagon-gitsite](https://github.com/stephenc/wagon-gitsite), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download stephenc/wagon-gitsite
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8d21ce43189ba226de09c3ecb44eead0f0bf4f20
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 8d21ce43189ba226de09c3ecb44eead0f0bf4f20.nq.gz
│   └── repolex
│       └── 8d21ce43189ba226de09c3ecb44eead0f0bf4f20
│           └── chunk-001.nq.gz
├── blob
│   ├── 16b12d32be02bb704360f911c10bf7b0bcff007d.nq.gz
│   ├── 1c26bbc5264fcc943ad7b5a0f1a84daece211f34.nq.gz
│   ├── 1e5e00fc77378a6b02a8a160ed62fffe9238aee3.nq.gz
│   ├── 26ad7f0b59987a627dcc5f00c7a75ad052878bc5.nq.gz
│   ├── 3f999fc88b360074e41f38c3b4bc06ccb3bb7cf8.nq.gz
│   ├── 4a4568b3e07875ed80278aaf1eb21d88af25766c.nq.gz
│   ├── 52e85a430af9da4dfb217d71b4d6f3a1d4a4b571.nq.gz
│   ├── 532993e424f425593ba6adf684d90bbb33347986.nq.gz
│   ├── 5beac166dd79c5872b6ad3c3c8826781b74ef564.nq.gz
│   ├── 5fe1845a4d636abe00a052c4629d4ad8259c21e5.nq.gz
│   ├── 61132ef2b01806f6122c31d173c98e01e499b9a0.nq.gz
│   ├── 6287f72bd08a870908e7361d98c35ee0d6dcbc82.nq.gz
│   ├── 6ea9e5161615fcf6cdb0d194d913139c26fa417a.nq.gz
│   ├── 873bbb52cb9768103c27fbb9a9bac16ac615fce5.nq.gz
│   ├── bebb6622847234ffb08801d1be891d4fe8ebaad1.nq.gz
│   ├── c6cb9ad7ce438a798426703e86a7ffc197d51dbb.nq.gz
│   ├── c814867a13deb0ca7ea2156c6ca1d5a03372af7e.nq.gz
│   ├── c982168bf240caf9fbedfe644dfc1dae245145ec.nq.gz
│   └── e3dc7c56cdcf36bcac19827f3aed9e422f1f497a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8d21ce43189ba226de09c3ecb44eead0f0bf4f20.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

## Source repository

[stephenc/wagon-gitsite](https://github.com/stephenc/wagon-gitsite)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
