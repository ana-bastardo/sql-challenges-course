# Challenge 01: Distinct replacement costs

**Level:** Simple
**Topic:** DISTINCT

## Problem
List all the different replacement costs charged for films, and identify the lowest one.

## Solution

```sql
SELECT DISTINCT replacement_cost
FROM film
ORDER BY replacement_cost ASC
LIMIT 1;
```

## Result
**9.99** - the lowest replacement cost in the dataset.

## Notes
- My first approach was to use `SELECT DISTINCT MIN(replacement_cost) FROM film`,
  but `MIN()` already collapses everything to a single value, so `DISTINCT`
  becomes redundant, although it was the actual concept being tested.
- The version above lists every distinct cost first (the actual point of
  the exercise), then `ORDER BY ... LIMIT 1`) can pull the
  lowest from that list without resulting to `MIN()`.
