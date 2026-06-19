# Challenge 04: Join group by movies per category

**Level:** Moderate
**Topic:** JOIN & GROUP BY

## Problem
Create an overview of how many movies exist in each category, and
identify which category has the most films.

## Solution
````sql
SELECT c.name, COUNT(f.title) FROM film f
INNER JOIN film_category fc
ON f.film_id = fc.film_id
INNER JOIN category c
ON fc.category_id = c.category_id
GROUP BY c.name
ORDER BY COUNT(f.title) DESC;
````

## Result
**Sports**, 74 titles: The most common category.

## Notes
- Joined `film`, `film_category`, `category` to connect each film to
  its category name, since category isn't stored directly on `film`.
- Used `COUNT(f.title)` rather than `COUNT(*)` to be explicit about
  counting films specifically, though `COUNT(*)` would give the same
  result here, since the join produces exactly one row per film/category
  pair.
- Grouped and ordered by `c.name` and its count to surface the most
  common category at the top.
