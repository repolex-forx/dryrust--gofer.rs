# Repolex Knowledge Graph of dryrust/gofer.rs

RDF knowledge graph data for [dryrust/gofer.rs](https://github.com/dryrust/gofer.rs), parsed by [repolex](https://repolex.ai).

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
rlex download dryrust/gofer.rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── eb9b23e537db4e586f21a53ad380526fda69a35c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── eb9b23e537db4e586f21a53ad380526fda69a35c.nq.gz
│   └── repolex
│       └── eb9b23e537db4e586f21a53ad380526fda69a35c
│           └── chunk-001.nq.gz
├── blob
│   ├── 02a53589b617dddcbe17a52d3758b69df7adbef2.nq.gz
│   ├── 04396cf7015a74fee1f6140eba53ac2b8a8a1c40.nq.gz
│   ├── 0ea3a944b399d25f7e1b8fe684d754eb8da9fe7f.nq.gz
│   ├── 1070564e7c42d00860ea5ccddcd9f4391c9a9b4a.nq.gz
│   ├── 13edb27f8341a15f7ef6805243c5be8572913129.nq.gz
│   ├── 280fb8d04170d32ee9c5f1537fb204382a2602ff.nq.gz
│   ├── 4255a99e2a619b4edd399a2184cfba49455fba57.nq.gz
│   ├── 4f11644397e7d16b78b9af9a9f4280686e6830a3.nq.gz
│   ├── 4f6c20f06f3972d198e9c70e2c4c0d09689c135a.nq.gz
│   ├── 596228914bfd665a9c8e82fd9c9323a4dd1c3a2b.nq.gz
│   ├── 5f5cf896c81688e4360b37f1bcda92f7bc6f7423.nq.gz
│   ├── 6a8d2273fd7339fbed0399515f64c10debd65a84.nq.gz
│   ├── 6d152a668ac66544ec49a88cc0b147781dd628f7.nq.gz
│   ├── 75055bfd32283a4e4924086eced5472e1387c65e.nq.gz
│   ├── 75e3b65f99b29f48ab230e3eab3de8d0b7a9229f.nq.gz
│   ├── 775b37f2025b0b0c44365b5ed0671d9f24131855.nq.gz
│   ├── 7ed1f8ca7c71d1049029ce735d7f0d31b2adf44a.nq.gz
│   ├── 82b976fa966281afdee2965166715120b2e20e7a.nq.gz
│   ├── 8a953032c29ed9961d08efab1a4221cd747a3e5e.nq.gz
│   ├── a0c6e25dc0dca4b211209cc69e09c02525dd0da7.nq.gz
│   ├── a21a46f20781ef6808c85bf83afc49fe90f51a6a.nq.gz
│   ├── a718674ce58c2cb835775828c8a323d259c0848c.nq.gz
│   ├── ad292f06e70b29acd64d2caf6780ad7e110d9dbb.nq.gz
│   ├── ad338d33523cdc2d9fd8faf6c11dc386936b5b2f.nq.gz
│   ├── af9908b08f4b33c32a0080af73f53bc0fa0cdce4.nq.gz
│   ├── b6428f2e4f04bc4c3554da62495e1849dd0809c4.nq.gz
│   ├── c7504b17b600cacd0a72d17b05bb8dae214c4791.nq.gz
│   ├── c855717f2b02c1175498cd516e3d3a0be53b742a.nq.gz
│   ├── c8e9ebd2c2ad0f02789cef8cf3d1e1d0f9af3082.nq.gz
│   ├── d428484740a9dfff1672e2c5c6a3e748fba796c4.nq.gz
│   ├── deec34427e287f93ce43af2bd2e6687e20932002.nq.gz
│   ├── e1fdaeb4df03b655a0b69f13ec8df1d78bb36790.nq.gz
│   ├── e3e57a8ce4ccbf74759a6df8fa4a3980ff1c9209.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e94d007030c7f349ab7a49bf213a046e494b7efe.nq.gz
│   └── efb98088164f5786b17e83ed384971fc3c74f93c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── eb9b23e537db4e586f21a53ad380526fda69a35c.nq.gz
├── filetree
│   └── eb9b23e537db4e586f21a53ad380526fda69a35c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 46 files
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

[dryrust/gofer.rs](https://github.com/dryrust/gofer.rs)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
