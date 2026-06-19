# Challenge 02: CASE + GROUP BY cost ranges

**Level:** Moderate
**Topic:** CASE + GROUP BY

## Problem
Categorize films into "low" (9.99–19.99), "medium" (20.00–24.99), and
"high" (25.00–29.99) replacement cost groups, and count how many films
fall into each group.

## Solution
````sql
SELECT price_category, COUNT(*)
FROM (
	SELECT *,
	CASE
		WHEN replacement_cost BETWEEN 9.99 AND 19.99 THEN 'low'
		WHEN replacement_cost BETWEEN 20.00 AND 24.99 THEN 'medium'
		WHEN replacement_cost BETWEEN 25.00 AND 29.99 THEN 'high'
		ELSE 'to analyze'
	END AS price_category
	FROM film) AS sub
GROUP BY price_category
ORDER BY price_category ASC;
````

## Result
**514** films in the "low" group (out of 1000 total: 514 low, 250 medium, 236 high).

## Notes
- Used a subquery to tag each film with a `price_category` via `CASE`,
  then grouped on that derived column in the outer query.
- Added an `ELSE 'to analyze'` catch-all as a sanity check, rather than
  silently misclassifying rows that don't match any defined range.
