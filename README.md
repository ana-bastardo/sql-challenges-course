# sql-challenges-course

SQL practice repository: joins, subqueries, CTEs, and window functions
solved and documented with reasoning, alternative approaches, and notes
on mistakes/debugging.

## Challenges Index

| # | Challenge | Topic | Level |
|---|-----------|-------|-------|
| 01 | [Distinct replacement cost](challenges/01-distinct-replacement-cost.md) | DISTINCT | Simple |
| 02 | [Case + group by cost ranges](challenges/02-case-group-by-cost-ranges.md) | CASE + GROUP BY | Moderate |
| 03 | [Join category length](challenges/03-join-category-length.md) | JOIN | Moderate |
| 04 | [Join group by movies per category](challenges/04-join-groupby-movies-per-category.md) | JOIN & GROUP BY | Moderate |
| 05 | [Join group by actor movie count](challenges/05-join-groupby-actor-movie-count.md) | JOIN & GROUP BY | Moderate |
| 06 | [Left join unassigned addresses](challenges/06-leftjoin-unassigned-addresses.md) | LEFT JOIN & FILTERING | Moderate |
| 07 | [Join group by sales by city](challenges/07-join-groupby-sales-by-city.md) | JOIN & GROUP BY | Moderate |
| 08 | [Join group by revenue by country/city](challenges/08-join-groupby-revenue-by-country-city.md) | JOIN & GROUP BY | Moderate–Difficult |
| 09 | [Subquery avg revenue per staff](challenges/09-subquery-avg-revenue-per-staff.md) | Uncorrelated subquery | Difficult |
| 10 | [Extract + subquery avg Sunday revenue](challenges/10-extract-subquery-avg-sunday-revenue.md) | EXTRACT + Uncorrelated subquery | Difficult–Very difficult |
| 11 | [Correlated subquery movies above avg length](challenges/11-correlated-subquery-movies-above-avg-length.md) | Correlated subquery | Difficult–Very difficult |
| 12 | [Subquery avg customer lifetime value](challenges/12-subquery-avg-customer-lifetime-value.md) | Uncorrelated subquery | Very difficult |
| 13 | [Correlated subquery payments by category](challenges/13-correlated-subquery-payments-by-category.md) | Correlated subquery | Very difficult |
| 14 | [Bonus: nested subquery top revenue per category](challenges/14-bonus-nested-subquery-top-revenue-per-category.md) | Correlated + uncorrelated (nested) | Extremely difficult |

## Tech used

- PostgreSQL (managed via pgAdmin 4)

## Structure

Each challenge is documented in a single markdown file containing:
- **Problem** — paraphrased task and relevant schema
- **Solution** — commented SQL query
- **Result** — the answer obtained
- **Notes** — reasoning, alternative approaches, mistakes made

## License

MIT — see [LICENSE](LICENSE)
