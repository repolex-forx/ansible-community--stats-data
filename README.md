# Repolex Knowledge Graph of ansible-community/stats-data

RDF knowledge graph data for [ansible-community/stats-data](https://github.com/ansible-community/stats-data), parsed by [repolex](https://repolex.ai).

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
rlex download ansible-community/stats-data
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 3dc4e8ca23e8b9f251707b2255ed21bbc1160472
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 3dc4e8ca23e8b9f251707b2255ed21bbc1160472
│           └── chunk-001.nq.gz
├── blob
│   ├── 083809260326ccf20ed2a4825b6aacca5bd4fea5.nq.gz
│   ├── 0885eb06e43b23e5ae3dff4af4188d0b61385c8e.nq.gz
│   ├── 34d1fd5c500309b3f1fad9c6c8bfafc1b0eb89df.nq.gz
│   ├── 4261b2738d708a4a7b41edda81194a02f2da93c4.nq.gz
│   ├── 4df2b3a31cf154e0470cfd8a24f22f19d0b0a78d.nq.gz
│   ├── 4ec1d62feadf226f482af19d9a7df13bb6b52e55.nq.gz
│   ├── 5b25a0a7ec5ae0a3bb962627eafc086fe6561986.nq.gz
│   ├── 900e2dc312651da5dcd7c54d15dc0514206b821b.nq.gz
│   ├── 9c2e9801a54d63861af2b37c0d9c6cd488129a14.nq.gz
│   ├── a0a0fdb390079c0c59bddb3596626c655fbcc5a1.nq.gz
│   ├── e83436a3e91c411cd8248fbcb264b123dcb748f2.nq.gz
│   ├── eed99cff210e477b382770bef090b65c6930899a.nq.gz
│   └── f2a390c592c4974e97d53c77a1a6fc1c65a82f6b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 3dc4e8ca23e8b9f251707b2255ed21bbc1160472.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 20 files
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

[ansible-community/stats-data](https://github.com/ansible-community/stats-data)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
