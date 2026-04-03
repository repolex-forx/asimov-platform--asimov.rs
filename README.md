# Repolex Knowledge Graph of asimov-platform/asimov.rs

RDF knowledge graph data for [asimov-platform/asimov.rs](https://github.com/asimov-platform/asimov.rs), parsed by [repolex](https://repolex.ai).

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
lexq download asimov-platform/asimov.rs
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── blob
│   ├── 192e2efaf0363a94232dd7c9fa80bd3f32a2f205.nq.gz
│   ├── 2391f73aa051d3804285ce744f2e9a1c7e08993d.nq.gz
│   ├── 271649cf062bfb396d429c714d1c73eff4b0e5d6.nq.gz
│   ├── 3b8fc947067ef21e4e348122eb8bb47d9e029838.nq.gz
│   ├── 41da2fe59a195a2532bdfbb75c5683ba5a027e0c.nq.gz
│   ├── 71c6626bae8fcf3939a226fdd2facc15c179fbe1.nq.gz
│   ├── 9691e57b149fe3263b03afce29c7865989697fdc.nq.gz
│   ├── 9de1571d1bd59cb3afc7e96b52a2e81d3b865226.nq.gz
│   ├── b1eec7f00ae168c83c5c9786ace5765c3fae5dda.nq.gz
│   ├── b7a0b6d09cedae685c6a128e0ba016bd9c467e5d.nq.gz
│   ├── d2d774d685a805fac62723c16262a6ba9ded7549.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ec50a64ded33981836d5e4a10ec60f3501f1ce74.nq.gz
│   ├── eed41a7f07589d8cc63b8acf41782101488abb49.nq.gz
│   └── efb98088164f5786b17e83ed384971fc3c74f93c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0fc8aa99177a56c593dcd0a3e58cd54b940a1877.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

8 directories, 21 files
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

[asimov-platform/asimov.rs](https://github.com/asimov-platform/asimov.rs)

---
*Parsed on 2026-04-03 by [repolex](https://repolex.ai)*
