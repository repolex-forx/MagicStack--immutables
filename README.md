# Repolex Knowledge Graph of MagicStack/immutables

RDF knowledge graph data for [MagicStack/immutables](https://github.com/MagicStack/immutables), parsed by [repolex](https://repolex.ai).

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
rlex download MagicStack/immutables
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1317f9d607b2a540aca37716e902adba56925a99
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1317f9d607b2a540aca37716e902adba56925a99
│           └── chunk-001.nq.gz
├── blob
│   ├── 039be94af203f4ad725843fd6261188428076851.nq.gz
│   ├── 09f275d483d522a479b4b738b0de6240f0f658df.nq.gz
│   ├── 102c31639181b360ba16c4117407c6df751b17b5.nq.gz
│   ├── 11526d29c94de02df3f19e5e94fcdccdeabe4d78.nq.gz
│   ├── 210f55b2bf56495659ebb947339bfbd9185ec5cb.nq.gz
│   ├── 24d3a6bb9fc8970c0ed1f068e4922f03846e0a94.nq.gz
│   ├── 256f46775a148b4dea8fb918934f370b4d8f6fef.nq.gz
│   ├── 2594d887b8d257be33b01a39471565247c3dea52.nq.gz
│   ├── 2a87a55aa95c0dcc8b313b3e6b31b45d4fbbc4c7.nq.gz
│   ├── 2ee32f17aada9dd2fa6f654be4f5625befad4886.nq.gz
│   ├── 37b02a4cbc591a078e71ab9fa68430e372ce1804.nq.gz
│   ├── 3baa285d4cb47d68a2fc2f73b2fb9b264e22edbf.nq.gz
│   ├── 3f174b27e07983080fce2f89dd3ca08b5702d7fe.nq.gz
│   ├── 450c5732e04c31167bd68a053e5c554e63747f8b.nq.gz
│   ├── 4622735787cd61379319e5953694394a79f39b76.nq.gz
│   ├── 481d190a515e3c195c78ce882b43b4c5debd86e1.nq.gz
│   ├── 49d8ee1e7c88ebad808bc56b1ba36eb7f5538402.nq.gz
│   ├── 66cecbb0bf94c7786fe3f50e2a19ba5fc4eb9737.nq.gz
│   ├── 6cecfe903236edcf02edc68ab68e65694ceabac2.nq.gz
│   ├── 71e41c930ff56185d0882f77167318a3cd03b17e.nq.gz
│   ├── 7d51e34f97afa63c4a288a7e2f417b3be8c276ef.nq.gz
│   ├── 84eca3199f488a1ab30d8fbac4715bc3890b66d4.nq.gz
│   ├── 8a796ab2c1b38230e828e91e19acf25f6c7285ca.nq.gz
│   ├── 8cfc9c97821a373626bcc24b6f9b667b58f95ec6.nq.gz
│   ├── b648ac92333301658c4f49b315f21130c689c819.nq.gz
│   ├── b8565b0c33c790443e17c91a07f2ace156a9cb4d.nq.gz
│   ├── bf911cf860e014baf72a4f0dcb0e690be0b5f098.nq.gz
│   ├── e14d3210fe4f59df4769b8573abcf6ca899ee6d0.nq.gz
│   ├── e44155791327ec267422336c72e7160b9b2c7a33.nq.gz
│   ├── e5c270cbe42f287ce2ecb7db598b8f25a6e80db3.nq.gz
│   └── e77ff5dfd5170592c5e8db77bb46a148b529dc4f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1317f9d607b2a540aca37716e902adba56925a99.nq.gz
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

[MagicStack/immutables](https://github.com/MagicStack/immutables)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
