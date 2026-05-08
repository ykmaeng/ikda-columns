# Ikda Columns

Daily/weekly columns for the Ikda (읽다) language-learning app.

Each column is a single topic available at all 6 reading levels (Lv.1–Lv.6).
Columns are first-person observational essays, not factual reporting.

## Structure

```
index.json                 # Registry: list of all columns + publish dates
YYYY-MM-DD-{slug}.json     # Single column file: 6 ReadingPassage entries (one per level)
```

## How the app uses these files

The Ikda mobile/desktop app fetches files from this repo via the jsDelivr CDN:

```
https://cdn.jsdelivr.net/gh/ykmaeng/ikda-columns@main/index.json
https://cdn.jsdelivr.net/gh/ykmaeng/ikda-columns@main/{file}.json
```

On every app launch, the app refreshes its local cache from these URLs. New
columns appear without requiring an app update from the App Store / Play Store.

## Scheduled publishing

`publishDate` in each column's first passage controls when it becomes visible
to users:

* `publishDate` ≤ today → visible
* `publishDate` > today → hidden (will appear automatically on that day)

This means columns can be written days or weeks in advance, pushed once, and
they will roll out on schedule with no further work.

## License

Content © Ikda. Available publicly only because the app reads it directly.
