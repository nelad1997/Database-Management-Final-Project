# Database Management — Final Project

Technion **Database Management** course final project. It covers a single media-streaming
domain (Movies, Actors, Users, and watch history) twice: first as a pure relational
design, then as a Django web application built on top of the same data.

The project is split into two independent parts:

| Part | Folder | What it is |
|------|--------|------------|
| **A** | [`Part-A-SQL/`](Part-A-SQL/README.md) | ERD → relational schema → SQL views & queries |
| **B** | [`Part-B-Django/`](Part-B-Django/README.md) | Django app exposing the database through web pages |

## Directory map

```
.
├── Part-A-SQL/            # Relational modeling & SQL
│   ├── ERD/               # ERD diagram
│   ├── schema/            # DDL (table definitions)
│   ├── queries/           # Answer queries + view definitions
│   └── 2024S_Project_A.pdf
└── Part-B-Django/         # Django web application
    ├── Contents_App/      # Django app (models, views, urls)
    ├── templates/         # HTML pages
    ├── static/            # CSS & images
    ├── sql/               # SQL view definitions used by the app
    └── 2024S_Project_B.pdf
```

See each part's own `README.md` for details and run instructions.
