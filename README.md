# Perspective Sort Behavior Repro

This project reproduces an issue where sorting doesn't appear to work as expected when using `group_by` with multiple sort fields.

## Setup

- `group_by`: `["Field_A"]`
- `sort`: `[["Field_C", "asc"], ["Field_B", "desc"]]`
- `aggregates`: `{ Field_B: "sum" }`
- `filter`: `Field_C in ["2025/07/08"]`

## To Run

You must serve the project using a local web server (due to `fetch("data.json")`):

### Using `npx`:

```bash
npx serve .
```

## Note

This is a simplified reproduction of a real case. Reducing it further eliminates the issue, so the example is intentionally kept at this level.

It’s unclear whether the behavior is due to a bug or an edge case from grouping on non-unique Field_A values.
