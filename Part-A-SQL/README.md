# Part A — Relational Modeling & SQL

The relational half of the project: model the media-streaming domain, translate it into a
schema, and answer the assignment questions with SQL views and queries.

## Contents

```
Part-A-SQL/
├── 2024S_Project_A.pdf   # Assignment specification
├── ERD/
│   └── ERD.pdf           # Entity–Relationship diagram + design assumptions
├── schema/
│   └── schema.sql        # DDL: CREATE TABLE statements (the relational schema)
└── queries/
    ├── views.py          # VIEWS_DICT — view definitions per question (Q3, Q4)
    └── queries.py        # QUERY_ANSWERS — final answer queries per question (Q3, Q4)
```

## Overview

- **`schema/schema.sql`** — defines the core tables: `Content` and its subtypes `Movie`
  and `Song`, the `Content_Man`/`Actor`/`Artist` hierarchy, and relationships such as
  `Performed_By`, with primary/foreign keys and `ON DELETE CASCADE`.
- **`queries/views.py`** — each question's answer is built up from a chain of helper
  **views** (e.g. for Q3: `onTimeActor` → `allMovieActors` → `profitablemovies` →
  `atleastTwo`), stored as a Python dict keyed by question.
- **`queries/queries.py`** — the **final SELECT** for each question, run on top of the
  views above (e.g. Q3 aggregates actor counts and average salaries per movie).

The Python files just hold the SQL as strings (a dict per file); the logic is the SQL.

## Running

Create the schema, then the views, then the queries, against your SQL Server / relational
database:

1. Execute `schema/schema.sql` to create the tables.
2. Run each view in `queries/views.py` **in order** (later views depend on earlier ones).
3. Run the matching query from `queries/queries.py` to produce the answer.
