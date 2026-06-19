# Challenge 05: Join group by actor movie count

**Level:** Moderate
**Topic:** JOIN & GROUP BY

## Problem
List actors with their first and last names and the number of movies
each one appears in. Identify which actor appears in the most movies.

## Solution
````sql
SELECT first_name, last_name, COUNT(*) AS total_films
FROM actor a
INNER JOIN film_actor fa
ON a.actor_id = fa.actor_id
INNER JOIN film f
ON fa.film_id = f.film_id
GROUP BY first_name, last_name
ORDER BY COUNT(*) DESC;
````

## Result
**Susan Davis**, 54 movies: The actor appearing in the most films.

## Notes
- Joined `actor` → `film_actor` → `film` to connect actors to their films,
  since the relationship is many-to-many via the `film_actor` bridge table.
- Grouped by both `first_name` and `last_name` together, since neither
  alone uniquely identifies an actor.
