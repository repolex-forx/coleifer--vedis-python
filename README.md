# Repolex Knowledge Graph of coleifer/vedis-python

RDF knowledge graph data for [coleifer/vedis-python](https://github.com/coleifer/vedis-python), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/vedis-python
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cef7f6b80498976a0e51bae1f3898983b027dfe1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cef7f6b80498976a0e51bae1f3898983b027dfe1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0617d3029b80f2ada9c76449d578a9c6820c4fd7.nq.gz
│   ├── 1156dae80463fd710d80ea8604d1ba3887d4d7d6.nq.gz
│   ├── 1f3cb0552c784d8a1c12fc05f728468fd32196f2.nq.gz
│   ├── 2299f64ae0a06cf6f8b956a56e2d4f4517a29c3b.nq.gz
│   ├── 254873a3fbf21a3e4f4de29a696d14f66a2028fc.nq.gz
│   ├── 52c2817c16d7d224f3bae340ec29525ee9e5426e.nq.gz
│   ├── 55efaa52d2daf8cddde1dd2536a95556749ba6fe.nq.gz
│   ├── 5cec0d9ce776a9412d787b9c6f6af7c4a7154288.nq.gz
│   ├── 808065fbfd8d9b30a053f4f69aa7f57696e44157.nq.gz
│   ├── 9232b7f5d48b5c71d19c3427ca4d803cd3267b67.nq.gz
│   ├── 9d8f87853b903a15255a52b6c51864fa91d082ec.nq.gz
│   ├── a9a34d99e99df441e2ce900b5535277fed50f9e5.nq.gz
│   ├── aa66cd71018bbc43e21415c7753527057ccc031b.nq.gz
│   ├── c3ac60742508b7f0f2c833dbbae82e7614beab6e.nq.gz
│   ├── c6336b0ac046fc1b014d25a3d0dde0c97da767dd.nq.gz
│   ├── d45787c69d69a75f291e1028644669f86fb52b23.nq.gz
│   ├── e9f294dd4e94df9a38a9ac18598420d329a1253d.nq.gz
│   ├── ecf4b0605884c739a3e019995e74504cfe99b2dd.nq.gz
│   └── ff41d0fe81df93fe4ad5f6eebc0bfdb271eca600.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cef7f6b80498976a0e51bae1f3898983b027dfe1.nq.gz
├── issue
│   └── issue.nq.gz
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
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[coleifer/vedis-python](https://github.com/coleifer/vedis-python)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
