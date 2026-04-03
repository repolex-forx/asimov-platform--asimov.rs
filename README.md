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
│   ├── 0269ef180666f30c009d110a72d482d9436f6589.nq.gz
│   ├── 04d9fb66d3a7cba9adc8fe7fd38bc814394cc1cc.nq.gz
│   ├── 05d02e477363e703414590d13f30d830359c1332.nq.gz
│   ├── 09e18ebfb907be73ecda2c98bd33b3124f897005.nq.gz
│   ├── 0bd52e9e1944a103ad1fdf746d6dee1ed789ca06.nq.gz
│   ├── 1540d9e4bb6f41257b3a209c2db2223c4b7c15c0.nq.gz
│   ├── 156c539b1214a204ede6762e642a5982ab7aadf8.nq.gz
│   ├── 192e2efaf0363a94232dd7c9fa80bd3f32a2f205.nq.gz
│   ├── 1e4fddcd2e59dc842aad8e61475e2ac9c1af2ddc.nq.gz
│   ├── 2391f73aa051d3804285ce744f2e9a1c7e08993d.nq.gz
│   ├── 271649cf062bfb396d429c714d1c73eff4b0e5d6.nq.gz
│   ├── 28b0bee090e1f8f10b5d7eaeaa5a1cba77a1c0e7.nq.gz
│   ├── 30abf5ba954d1d8438ff89c40434d74b7678ca5d.nq.gz
│   ├── 3a83769c42c34792c27b7093c8a6acd56b6c965d.nq.gz
│   ├── 3b8fc947067ef21e4e348122eb8bb47d9e029838.nq.gz
│   ├── 41da2fe59a195a2532bdfbb75c5683ba5a027e0c.nq.gz
│   ├── 4dcda7bdb7040fb50f83da07bb55cbda1e2c3b78.nq.gz
│   ├── 6593c980549c752ec463a966cceebaa7eac615eb.nq.gz
│   ├── 71c6626bae8fcf3939a226fdd2facc15c179fbe1.nq.gz
│   ├── 899e23545323c4cf19c2a871264b643304f96517.nq.gz
│   ├── 9349df1464d1bb82c072b1e53281c32d400e2419.nq.gz
│   ├── 9691e57b149fe3263b03afce29c7865989697fdc.nq.gz
│   ├── 9de1571d1bd59cb3afc7e96b52a2e81d3b865226.nq.gz
│   ├── b1eec7f00ae168c83c5c9786ace5765c3fae5dda.nq.gz
│   ├── b7a0b6d09cedae685c6a128e0ba016bd9c467e5d.nq.gz
│   ├── b9c08a23045837939b35f4a87b038f67d3df269b.nq.gz
│   ├── c0a7bd6524ed2b0887c091b712060251d4b1e46a.nq.gz
│   ├── d2d774d685a805fac62723c16262a6ba9ded7549.nq.gz
│   ├── df96b8189a1134dc2d16279ac47e17213ef1fbe9.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ec50a64ded33981836d5e4a10ec60f3501f1ce74.nq.gz
│   ├── eed41a7f07589d8cc63b8acf41782101488abb49.nq.gz
│   ├── efb98088164f5786b17e83ed384971fc3c74f93c.nq.gz
│   ├── f9823a22e492e0d9fee940192a552032718e1f95.nq.gz
│   └── ff2c51de5bf797eb23023b3cf85cc4f255eef019.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   ├── 0fc8aa99177a56c593dcd0a3e58cd54b940a1877.nq.gz
│   └── b9bc6afd6e81bb636ad3c76601e6fad2558c7cda.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

8 directories, 42 files
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
