# Repolex Knowledge Graph of jupyterhub/jupyterhub-deploy-docker

RDF knowledge graph data for [jupyterhub/jupyterhub-deploy-docker](https://github.com/jupyterhub/jupyterhub-deploy-docker), parsed by [repolex](https://repolex.ai).

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
rlex download jupyterhub/jupyterhub-deploy-docker
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e2b79700d32662403ad951a13f19030864ad581a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e2b79700d32662403ad951a13f19030864ad581a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0dc89813dc10ed07777226c26d348a19ce3afb93.nq.gz
│   ├── 1b8087bc3a015e5ac545cd3cc04780556d1ad70b.nq.gz
│   ├── 460421cf5fcc30e1669a62443346cf194ebf5809.nq.gz
│   ├── 4d6a59f45d7e62f8bfcbcf3473a84740e9b0ef70.nq.gz
│   ├── 5072f5c59d1e46f4bbf3630d50927a84b6ad3576.nq.gz
│   ├── 8124dd0e3db2049c65bb5776876e7343cac560b0.nq.gz
│   ├── 9e57aa90765e075ae7d168193d004ac38454c254.nq.gz
│   ├── a76395562314b661b2598f377b47fb2c5ab9a60a.nq.gz
│   ├── ac28a1317de255ffe99107f6c59ae3dba02bab63.nq.gz
│   ├── ad0635fb1729c6d3f6bea968329a4f70ca79bdd2.nq.gz
│   ├── af5af5eef19c8fc1272000d389bdbf63d2545459.nq.gz
│   ├── c2f2e7aacfe513641c9bd4e8ef990e4182fb8038.nq.gz
│   ├── c9457822f6071f6db1fc62d7fce5293be25adbe9.nq.gz
│   └── e5de3387a261c666cff02979c52c32f680e83965.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e2b79700d32662403ad951a13f19030864ad581a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[jupyterhub/jupyterhub-deploy-docker](https://github.com/jupyterhub/jupyterhub-deploy-docker)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
