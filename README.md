# Repolex Knowledge Graph of messense/rustc-test

RDF knowledge graph data for [messense/rustc-test](https://github.com/messense/rustc-test), parsed by [repolex](https://repolex.ai).

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
rlex download messense/rustc-test
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c2b517fbc900ed837cc4dfc3253de630beab0227
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c2b517fbc900ed837cc4dfc3253de630beab0227.nq.gz
│   └── repolex
│       └── c2b517fbc900ed837cc4dfc3253de630beab0227
│           └── chunk-001.nq.gz
├── blob
│   ├── 077b394547cec257938a6adc596f647cb8e3b3c7.nq.gz
│   ├── 130792fa5d7e707bd077f0e48c942176d8e201f6.nq.gz
│   ├── 16fe87b06e802f094b3fbb0894b137bca2b16ef1.nq.gz
│   ├── 1fb840520a6567e41d4f3de7a854da7ac6e44d7c.nq.gz
│   ├── 2902c7308ccce5a0336ef777f4d5db12592e4a2c.nq.gz
│   ├── 297bb72aecb2f7362202dcb81f6e145b5d45f14a.nq.gz
│   ├── 31aa79387f27e730e33d871925e152e35e428031.nq.gz
│   ├── 31e234d981800a331a0330947d953b2d386fe3b9.nq.gz
│   ├── 3e57f9a0c78c2b5d15f5745b2f83c448b075155a.nq.gz
│   ├── 5113766f4b0439f11f31e35acf8896eb1e395f1e.nq.gz
│   ├── 57b6d1a02021fcede8492caf2bea175107edf625.nq.gz
│   ├── 5a1e8c2aa3d1e3f37fa826383223e775789622db.nq.gz
│   ├── 5b75d2f367fff3ef09c332e6882c60fbffc4012e.nq.gz
│   ├── 6524f40fa529279c10986c01cf654611a412c515.nq.gz
│   ├── 65e05e53a6efce476be500fb6def44ab29209146.nq.gz
│   ├── 6acfca6828aa0ea156ab8d1f8781382072bd6f43.nq.gz
│   ├── 6f46f7255a47ed3c17f9f0b681e158d6773853b9.nq.gz
│   ├── 6fa369298416b575d7febc1c6bfe5e882a4a8e1a.nq.gz
│   ├── 874ecc3764572b8f328a81f368a0f98cd567e7ae.nq.gz
│   ├── 8e7bd8de924993150917dd9ef7e041411d3b4138.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── b0aefbb6d3ec5c5b4a1bb0110ebb2bfccc8f871d.nq.gz
│   ├── b7f00c4c86cdf27f61416b98c5461276989ee80e.nq.gz
│   ├── d7c41660ac897065b61b148a12088f050ff79012.nq.gz
│   ├── def9225f15b6adebff00b325f005a18404b782fe.nq.gz
│   └── f77a23e6875b2c1b6a65e1d00a9169c8872fec47.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── c2b517fbc900ed837cc4dfc3253de630beab0227.nq.gz
├── filetree
│   └── c2b517fbc900ed837cc4dfc3253de630beab0227.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 36 files
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

[messense/rustc-test](https://github.com/messense/rustc-test)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
