# Part B — Django Web Application

A Django app that puts a web front end over the movie/actor/user database: it runs the
assignment's reporting queries and lets the user add actors to movies and record watch
events.

## Contents

```
Part-B-Django/
├── 2024S_Project_B.pdf   # Assignment specification
├── Contents_App/         # The Django app
│   ├── models.py         # DB models (managed = False — map to an existing DB)
│   ├── views.py          # Request handlers; run raw SQL via connection.cursor()
│   ├── urls.py           # URL routing
│   └── admin.py / apps.py / tests.py
├── templates/            # HTML pages rendered by the views
├── static/               # CSS and images
└── sql/
    └── view_quries.sql   # SQL views the app's queries depend on
```

## Routes (`Contents_App/urls.py`)

| Path | View | Purpose |
|------|------|---------|
| `/` | `index` | Home page |
| `/Query_Results` | `Query_Results` | Runs the 3 report queries (top-genre stats, improved-movie actors, top watchers per country) |
| `/Add_Actor_to_Movie` | `add_Actor` | Adds an actor to a movie, with validation (movie exists, not already cast, salary within budget) |
| `/Record_Watching` | `record_watching` | Records a watch event with date/rating, with validation |

## Database

Models use `managed = False` and `db_table` mappings, so they bind to an **existing**
database rather than creating tables. The views in `sql/view_quries.sql`
(`betweenTop20`, `ImprovedMovies`, `ActorInImproved`, etc.) must exist in that database —
the report queries in `Contents_App/views.py` select from them.

## Running

```bash
# from Part-B-Django/
python manage.py runserver
```

Then open http://127.0.0.1:8000/. Requires a configured database connection (see the
project's `settings.py`) and the SQL views from `sql/view_quries.sql` loaded into it.

> Note: this folder contains the app, templates, and static assets but not a `manage.py`
> / settings module — run it from within the surrounding Django project that hosts
> `Contents_App`.
