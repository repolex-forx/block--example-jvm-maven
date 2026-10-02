# Repolex Knowledge Graph of block/example-jvm-maven

RDF knowledge graph data for [block/example-jvm-maven](https://github.com/block/example-jvm-maven), parsed by [repolex](https://repolex.ai).

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
rlex download block/example-jvm-maven
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c81186ee2ed932998686b0fb17a45c8a2b9481c9
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── c81186ee2ed932998686b0fb17a45c8a2b9481c9.nq.gz
│   └── repolex
│       └── c81186ee2ed932998686b0fb17a45c8a2b9481c9
│           └── chunk-001.nq.gz
├── blob
│   ├── 0287f9ba00e7e2508eb5df4027ba55edeef20a53.nq.gz
│   ├── 098903cf6994dba9ce0f1663cefd1469f9c0aa82.nq.gz
│   ├── 108eee06857ae8b4088160fb0e3c46effe61680b.nq.gz
│   ├── 1286c83cc7e895a3eb86b8b383f6845908faa5e9.nq.gz
│   ├── 2034b66e2be18eb13638e32b7b0e06626abae6b4.nq.gz
│   ├── 24fa85e3456ac350e55b8283ef7ca183d53452d4.nq.gz
│   ├── 2b31fb8de933ecc26f3c236af34a6c8988eca031.nq.gz
│   ├── 33b73350ec9463f074164d13a02e5bb9006630d2.nq.gz
│   ├── 3828c67ea495883fe9e42db0d3bc5f1c8ea35ae5.nq.gz
│   ├── 383f4511d444516caed0fd113ee8a2b640cd2290.nq.gz
│   ├── 3c190bd0aec423c023532fd91b82025c4bfeb820.nq.gz
│   ├── 3f9dc50ecc2888253cecfa72d7578403b970f877.nq.gz
│   ├── 4c8ef8f4f46651135fd61d041214a95b74402d94.nq.gz
│   ├── 4d266cdd09d0e84f4071d9777a8f7fcf87b3c780.nq.gz
│   ├── 536827da52d1904d70b1641066a79d63de50e62d.nq.gz
│   ├── 5793e2e547655d6b3a95b7067e196a311bf63c74.nq.gz
│   ├── 60aee5710affc64ce16eb26fb1b4ef3636eb5bf2.nq.gz
│   ├── 76603e48a4a40d4305cae173860789edd43eed20.nq.gz
│   ├── 7e724f738256df5481f1bed164e11b6401296db4.nq.gz
│   ├── 7fef769248e85eab6c828b9f2f7b802296cddadc.nq.gz
│   ├── 846a53ead675286cecf8cbd76ebde9240fe17f86.nq.gz
│   ├── 9fc6ce74fff9eafa6fd3ed7b9c97bef6f027f8cf.nq.gz
│   ├── a4c198407535fd0a7e56e9fad0e12e6e5c30f5ab.nq.gz
│   ├── a6bd52cbbf7fe653f40a49ca7396d66d3de29788.nq.gz
│   ├── aa2f1a03131611ba349c0df1b737341d9626806a.nq.gz
│   ├── b8e821860d83644bfbb205068e569da6ace84d48.nq.gz
│   ├── c0742c6b7c4c8f66c4de05966b1f163dbe63456b.nq.gz
│   ├── ce03a4c5571954b0aa16809aa486d4f5372f21ae.nq.gz
│   ├── d1c65f97cba19b149f3d4ea27e9cf9a15bec2e97.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e72f9edf20af1ca1e484c19b1855920845ed6b90.nq.gz
│   ├── e889550ba4cbc92a720527042e5f6e7a303bfcbc.nq.gz
│   ├── ebd7b4b0300fddfdf851cf298b77a1a204a99361.nq.gz
│   ├── fa8456f6890f60c1ac332140212f5a95d48fc5ea.nq.gz
│   └── fe28214d3352b0ed40820a4999317694c8b1ef57.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── c81186ee2ed932998686b0fb17a45c8a2b9481c9.nq.gz
├── filetree
│   └── c81186ee2ed932998686b0fb17a45c8a2b9481c9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 45 files
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

[block/example-jvm-maven](https://github.com/block/example-jvm-maven)

---
*Parsed on 2026-10-02 by [repolex](https://repolex.ai)*
