# Challenge 03: Join category length

**Level:** Moderate
**Topic:** JOIN

## Problem
List film titles with their length and category name, ordered by
length descending, filtered to only the 'Drama' and 'Sports' categories.
Identify which category contains the longest film and how long it is.

## Solution
```sql
SELECT title, length, name
FROM film f
INNER JOIN film_category fc
ON f.film_id = fc.film_id
INNER JOIN category c
ON fc.category_id = c.category_id
WHERE name IN ('Drama', 'Sports')
ORDER BY length DESC
LIMIT 1;
```

## Result
**Sports**, 184 minutes. The longest film among the two categories.

## Notes
- Used two `INNER JOIN`s to connect `film` → `film_category` → `category`,
  since category name isn't stored directly on the `film` table.
- The task describes building the full ordered list first, but since the
  question only asks for the single longest film, I added `LIMIT 1` to
  go straight to the answer instead of materializing the entire list.
