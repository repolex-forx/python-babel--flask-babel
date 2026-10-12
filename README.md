# Repolex Knowledge Graph of python-babel/flask-babel

RDF knowledge graph data for [python-babel/flask-babel](https://github.com/python-babel/flask-babel), parsed by [repolex](https://repolex.ai).

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
rlex download python-babel/flask-babel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 869715cfea201086d70d945fadc32ab13bbd6b68
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 869715cfea201086d70d945fadc32ab13bbd6b68
│           └── chunk-001.nq.gz
├── blob
│   ├── 041aa3ca6e78e1d4fb22788fe5533dc457509e35.nq.gz
│   ├── 084c23d7b9ab89fc688b25b9654cd8f39d3f46b6.nq.gz
│   ├── 107d6adcc3cb00da54241bb11666b5c4c3a4ae4b.nq.gz
│   ├── 118032e3d22a307a29af7db206814776f9c122b1.nq.gz
│   ├── 16a03fa414ce1bd36a092c44b1acbf224fc69783.nq.gz
│   ├── 17c592917e8d23f67430e95ab02d0139aa0023d7.nq.gz
│   ├── 1808a1e2f5e4ce0b68d7265b567fd846a2ea6b8e.nq.gz
│   ├── 18371bdadabd4a7d815609479f34292158ff290d.nq.gz
│   ├── 1a984a97ba71481b64f8b5258c47a2daf987cdac.nq.gz
│   ├── 2119f51099bf37e4fdb6071dce9f451ea44c62dd.nq.gz
│   ├── 3e2acc142b835d3599d3caa9b43cc135436b46fd.nq.gz
│   ├── 46bd272501276b4a8a8f0148e2e9399e81dc4263.nq.gz
│   ├── 4b4858b610718528c79c2155ae9c7f3ee0750949.nq.gz
│   ├── 4ccc9e7c493b982f30c9c168661ef10e4a16d48a.nq.gz
│   ├── 4fd47ecadb7740070f5a83de073ce9bc02f5621c.nq.gz
│   ├── 56180026fd02e51851c288febc5bb1f5cd0fa528.nq.gz
│   ├── 562f7eb602f1966cfa4276aaf8d5956959091acc.nq.gz
│   ├── 58b0bbdd31a85680304171fc79e811ced1904483.nq.gz
│   ├── 6609ab153066d548f3c28cdeac679d1c69a71ac1.nq.gz
│   ├── 6b61f543adf75b2631f88e50aee165ab43eb8731.nq.gz
│   ├── 6d6ea80715ac1c4d4fdbbe91b1600d5d65c7f1d4.nq.gz
│   ├── 7b5465da6ab8d73d7cd6ea6458750483b86336ec.nq.gz
│   ├── 8a99d74d9511ef68440b50845c68204a5504a54d.nq.gz
│   ├── a2ee470c3138a7163d9e046b2bd29c3b5d9c6bbb.nq.gz
│   ├── b6455490102083514267fd732cb730c802c81388.nq.gz
│   ├── bf7b494fc7044e1395c1c821f2babc309277bf78.nq.gz
│   ├── c25155ffe1d6726cc941bed49ae14108416a031a.nq.gz
│   ├── cae4987b6cc11e7970a903295fbfca94b0883985.nq.gz
│   ├── cd86779dd9c53fd4ac4a14a921a96b5539d7ee2b.nq.gz
│   ├── d4bb2cbb9eddb1bb1b4f366623044af8e4830919.nq.gz
│   ├── e0ea0d38db600047cf0a3a6f6f54e47112f47cee.nq.gz
│   ├── e53d60f7a8acb8ba0380716591e5b5c162b19acd.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eab917761280c56c5967fce4bcee7fa9ca783b31.nq.gz
│   └── f0234b326f94f1f420103b7ba1017f58dbe99417.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 869715cfea201086d70d945fadc32ab13bbd6b68.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 43 files
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

[python-babel/flask-babel](https://github.com/python-babel/flask-babel)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
