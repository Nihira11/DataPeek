# DataPeek

Know what's inside a public dataset before you download it.

DataPeek checks public datasets and surfaces the details that decide whether one is actually usable (row/column counts, missing values, date range and granularity, licence) before you spend time downloading and loading a file that turns out to be useless. Available through an MCP server for agents and a small web UI for humans.

Status: **early / v0** – validating the idea before building out full coverage

## Why

Dataset search today is text search (Google Dataset Search, Kaggle, HuggingFace, government portals). None of it indexes the thing that actually decides usability: shape, structure, and licence. You guess keywords, open ten tabs, download, and find out. Coding agents hit this harder. No structured index to query, so they guess at URLs and return datasets that don't exist.

## What it does (v0)

- A small, hand-checked set of public datasets, profiled for structure
- One search page + one dataset detail page
- One MCP tool agents can use to search
- Per dataset: rows/cols, column names/types, missing values, date range and frequency, file format, licence, signup requirement, last-checked date

## What it explicitly does not do

- Host or mirror dataset files
- Clean, transform, or version data
- Try to cover every dataset on the internet
- Judge whether data is "good," only whether it's structurally usable

## Tech (planned)

Python · Postgres + pgvector · DuckDB · sentence-transformers · FastAPI · MCP Python · SDK · Next.js

## License

MIT – see [LICENSE](./LICENSE)
