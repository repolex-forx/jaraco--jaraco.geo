# Repolex Knowledge Graph of jaraco/jaraco.geo

RDF knowledge graph data for [jaraco/jaraco.geo](https://github.com/jaraco/jaraco.geo), parsed by [repolex](https://repolex.ai).

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
rlex download jaraco/jaraco.geo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d1f8b597ed6353acc61fba5bfef791be540eebe6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d1f8b597ed6353acc61fba5bfef791be540eebe6
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a5b8f620e0ea067eb59e9ea2efb0ff4297b96d0.nq.gz
│   ├── 0affcad6b71129ded3fb780456c27dc27368c50b.nq.gz
│   ├── 1f2aa7533b0423a8eb943f6f4ec02498e39581a0.nq.gz
│   ├── 23e15a5ab3b428163053d652b853a414b45859bb.nq.gz
│   ├── 240329c3604d8ead4c10aa8c88352caa8e4ce7b2.nq.gz
│   ├── 2e3f4dd791a6372b427d618eb0baa8c4dc58e5f0.nq.gz
│   ├── 304196f81e11a168c9894f966e4a617ebf4ed53c.nq.gz
│   ├── 4c0031bb884937a75c44aff0ac46c4f3336a682b.nq.gz
│   ├── 526f9f1cc79a94a0d04a432c059b23ab148edd37.nq.gz
│   ├── 54c9000ec94341dd65c2053251b85b124017b9b5.nq.gz
│   ├── 54cc8303b22089e12053e552d4e6cb852a865b8a.nq.gz
│   ├── 577e87a793a20e413f7321f4f17ec1eba2ea1962.nq.gz
│   ├── 5bdc232005af9be104a00437ae9bc64417a4c1cc.nq.gz
│   ├── 5c05f9e27d57a4b7a3c3a9fdfecf8cddb8be499f.nq.gz
│   ├── 6c2992b2f1f2b865066f08ac99ea938d6ef41847.nq.gz
│   ├── 6dab8d8c8f954449456089435e93a90d11561865.nq.gz
│   ├── 6f1428d5d323e82a3d82228f13b8530edcd94e3e.nq.gz
│   ├── 700235be57c1b2872455c0be5333f59cf568e252.nq.gz
│   ├── 724370638fc188317bbc7dc868f1a571995fd796.nq.gz
│   ├── 763dbc8e7740ca8e2d54089c271d7ae4d124011c.nq.gz
│   ├── 7bb894bffe32e7c733b9cbe544d13f2895c91caa.nq.gz
│   ├── 82a85a7b18940e50af8ca5c118cc1733a4c35889.nq.gz
│   ├── 876fba67337516bc87bf98fd93407ceea0def529.nq.gz
│   ├── 8867082f6e747231657a49fd92180e1e2aae3d1a.nq.gz
│   ├── 9256e818a2777e28cac8a6001dac9fe0b4438fa5.nq.gz
│   ├── 9a0f3bce1395ae3819030b822e5d9076c85068ea.nq.gz
│   ├── 9bf516802e37fdd26fc0a0a0c10cd74941d7be86.nq.gz
│   ├── 9cb480d54e7ce9d585e1e1ced1065d70b2042b95.nq.gz
│   ├── 9f30229dea6e4baa2cd95737c2fdc49f0931cd6e.nq.gz
│   ├── a56e3efc52d6bd43ea9b6e3f2c531ff8eba1f6aa.nq.gz
│   ├── a8ca84ab683250d0a3f2082cf9644c18d0b3a39a.nq.gz
│   ├── bde9c89edd5994d0405ec9b03487a7ccd8f6278c.nq.gz
│   ├── e05a3d4a2ab888e32952006d8cd380864368db5f.nq.gz
│   ├── efcb8cbc2043faa7caf4f92fc7488bd6914c934c.nq.gz
│   └── f559258cf2b4ee189dd0ced91e5d3d87ebecd8b6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d1f8b597ed6353acc61fba5bfef791be540eebe6.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 41 files
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

[jaraco/jaraco.geo](https://github.com/jaraco/jaraco.geo)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
