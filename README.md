# SQL reporting kit: daily totals with an index, checked by query plan

A daily sales report grouped by date and region. The index covers the filter and the grouping columns, and the test asks SQLite's query planner whether it actually uses that index. The same approach applies to the SQL Server reports this kind of work usually feeds.

- `reports.py`: schema, `daily_totals`, `add_index`, `plan`
- `test_reports.py`: totals match hand-computed values; the plan uses the index after it is created

Money is stored as integer cents, so totals never suffer from floating-point rounding.

Run: `python3 -m unittest`

---
Part of a set of five small demos modeled on the lead and client operations behind [LebiNova](https://lebinova.com). The stubbed SMS sender, LLM and data mean this is a design demo, not client work. See all five: https://github.com/ali-khaled-949/lebinova-demos
