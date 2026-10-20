# Repolex Knowledge Graph of klen/muffin-docker

RDF knowledge graph data for [klen/muffin-docker](https://github.com/klen/muffin-docker), parsed by [repolex](https://repolex.ai).

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
rlex download klen/muffin-docker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 702e0d0a03178d7aecf1620bd3c2ddae17d0c637
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 702e0d0a03178d7aecf1620bd3c2ddae17d0c637
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ddcdae108b995e2e3a365d8f8822dccc1d8b574.nq.gz
│   ├── 2471213d202698a55e0477a657105f54e29cccd5.nq.gz
│   ├── 2e55a336c3be74eddf1693d4edf0db07e44f007b.nq.gz
│   ├── 5b2b3419ca944d229eae0bc07863dae17355a158.nq.gz
│   ├── 77692247d474c548058ecc4a5f1fe7e53f3100be.nq.gz
│   ├── 78269be990cf17362b5bc6bda75717785b8b1e33.nq.gz
│   ├── 7a04732593a06a700f1152f19bc3741e6ea6230a.nq.gz
│   ├── 7a14ce77a162a11f261accd84a849029e8a940ec.nq.gz
│   ├── 893eba7919c2e6eb728fb626033d56ce82b47b4d.nq.gz
│   ├── 8c5984ead0b03e3a6410a3a02266b947920cd84f.nq.gz
│   ├── 904efd9d512c95f2c371e9289d99e1d338ffe2c9.nq.gz
│   ├── a0411b6aa205dc636076fdf20682e12cbfde8dfa.nq.gz
│   ├── a42cb28b1cacd4c6b411504f3e811420d7d706a9.nq.gz
│   ├── c5b436b2d72cc59ca6d75b8aa8c32dc4dd0a8262.nq.gz
│   ├── c7a03e5e34d39b30a547d67263265594edc52b37.nq.gz
│   ├── d212ebdc630b2220377081597d006c643d9c69e1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── fd5a1a8e135ee2dc31e7da95a29b77dfec290a99.nq.gz
│   └── fe621a6e884f0da66beaaf3774c29040e88d3e89.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 702e0d0a03178d7aecf1620bd3c2ddae17d0c637.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 26 files
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

[klen/muffin-docker](https://github.com/klen/muffin-docker)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
