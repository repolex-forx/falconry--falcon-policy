# Repolex Knowledge Graph of falconry/falcon-policy

RDF knowledge graph data for [falconry/falcon-policy](https://github.com/falconry/falcon-policy), parsed by [repolex](https://repolex.ai).

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
rlex download falconry/falcon-policy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3777dfb2838bdf22f881c4e020e19d50dcb9fbe5
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3777dfb2838bdf22f881c4e020e19d50dcb9fbe5
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d5ac4af3d1883f3fa536af11f65993145a9facc.nq.gz
│   ├── 113294a5f18d979085b4ad570d8a22a8e4eabd58.nq.gz
│   ├── 1a489ead26e4938db1493ba707aaa73a50b7095f.nq.gz
│   ├── 26944dc70c0ceec92a89eff86fbc2085603cc4ba.nq.gz
│   ├── 3c6e79cf31da1c0433d2fa666bf50b53f6359f26.nq.gz
│   ├── 57ab56a6aae1abaee7c64a52320530270e88c11b.nq.gz
│   ├── 661e2e1c0bcb9a1dba3d4e4bb5cd7e124c6fb382.nq.gz
│   ├── 6a26fd0b58ed8517e4b38c002d5b0f5de2d21f8b.nq.gz
│   ├── 7f777d68579b17dc3dc7c9add624f48aa949d17d.nq.gz
│   ├── 875c4df1aa3ced05574239a047abd04ce096930a.nq.gz
│   ├── 95f477da46eaa2653b32cd5cd3a6994769f63b8d.nq.gz
│   ├── a014b24bd90b75620df39e3ca2e0180581830ab4.nq.gz
│   ├── e6086409cc39556a450247e66219814fadb03501.nq.gz
│   ├── e67928d5ed4db64d3393c2ced09e78bf1b0df18d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f162f5c20b299e301cef851258c95df0c0378e74.nq.gz
│   └── fe4270da4fab96c9cfc6f2d8de8ff44ac3a850d9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3777dfb2838bdf22f881c4e020e19d50dcb9fbe5.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[falconry/falcon-policy](https://github.com/falconry/falcon-policy)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
