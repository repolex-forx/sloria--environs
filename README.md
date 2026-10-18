# Repolex Knowledge Graph of sloria/environs

RDF knowledge graph data for [sloria/environs](https://github.com/sloria/environs), parsed by [repolex](https://repolex.ai).

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
rlex download sloria/environs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d65f5d16155f6653569f8319b458484ff27be297
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d65f5d16155f6653569f8319b458484ff27be297
│           └── chunk-001.nq.gz
├── blob
│   ├── 218b03f3fa0fcca2f3135a8ff5ad5e8e5cb4c976.nq.gz
│   ├── 224fa948490753d4827f8f29b71c7349bfe8f820.nq.gz
│   ├── 2a6afbeead3b0bb873ecfbb22a707bafcbc8f01c.nq.gz
│   ├── 2b4faff88b9d1deb6fcf966a56979a36756b2c58.nq.gz
│   ├── 311a8756ed9a636fe0f08c2e00f10f936961857a.nq.gz
│   ├── 3d36af68548bc67e50f5a58c101dee40fef9fe6d.nq.gz
│   ├── 55d31195c2fbb497914e93fd8a478fcb2140cd0a.nq.gz
│   ├── 59704707542a7b0edae4a2e9059fa285251d9f5e.nq.gz
│   ├── 634ea73edcbc564ce72af70ae5a998db2c0b3e54.nq.gz
│   ├── 6601f2bf9895761c46fd29f048956f52e433edbf.nq.gz
│   ├── 6ae4ceda1902a5e8a8d31edd7794c1b9d77ce279.nq.gz
│   ├── 70f9d7cdb584ca14c9c38d00d5bc514d158810a3.nq.gz
│   ├── 7baf13c79709a858b286a4ceed045ab4aa1fe814.nq.gz
│   ├── 8365523bbeb52a99d85d1a61fc7372eee4b7bef0.nq.gz
│   ├── 89bc7d250e54d6b868842dd37461f987771d38c6.nq.gz
│   ├── 8aa96572e168c835f646763376cdd44c3591d5fb.nq.gz
│   ├── 96b4795515ed2d72f1667d48c82d5ef8e3b14267.nq.gz
│   ├── 9c067bae1e4b47b4521fd63d34d9ccbe02acaaa5.nq.gz
│   ├── 9dec1ef0848d7927733be0e9f25e2be538ea6ea7.nq.gz
│   ├── c9333cf6f576a7fa9dab2a324b1b902bf3504cc7.nq.gz
│   ├── cad5edce19f70b9ef93858ea44dd961ebe7b5ae5.nq.gz
│   ├── d4480e7cb0d946252b7af5c230199e8808918dd6.nq.gz
│   ├── da9c516dd744b6c88dd8c91f58f7bcf8f7e8341b.nq.gz
│   ├── e36d1dd6d500be8306605efe11d984ffb240dd1b.nq.gz
│   ├── e5aff4f83af864a6415aebc309885d1e32c3c63a.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb8783f93b59121ce26ad283ae2e61694416ce8e.nq.gz
│   ├── f40ce91be5fa3ae6afbf5457462f0d87000e4f1b.nq.gz
│   ├── f51e020f3b1a4eb5f1936a14cd53d08f2738c67b.nq.gz
│   ├── f62feb5860753513402d010061681240272051f5.nq.gz
│   └── fe95e258fed330699fcaf3d7f2e57e396fa6915b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d65f5d16155f6653569f8319b458484ff27be297.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[sloria/environs](https://github.com/sloria/environs)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
