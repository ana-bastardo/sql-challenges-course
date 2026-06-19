# Challenge 08: Join group by revenue by country/city

**Level:** Moderate–Difficult
**Topic:** JOIN & GROUP BY

## Problem
Determine revenue (sum of amount) grouped by country and city, and
identify which country/city combination has the least sales.

## Solution
````sql
SELECT ct.city, co.country, SUM(p.amount)
FROM payment p
INNER JOIN customer c
ON p.customer_id = c.customer_id
INNER JOIN address a
ON a.address_id = c.address_id
INNER JOIN city ct
ON ct.city_id = a.city_id
INNER JOIN country co
ON ct.country_id = co.country_id
GROUP BY ct.city, co.country
ORDER BY SUM(p.amount) ASC;
````

## Result
**United States, Tallahassee**: Total amount of 50.85, the lowest
revenue among all country/city combinations.

## Notes
- Extended the same join chain from challenge 7 (`payment` » `customer`
  » `address` » `city`) by one more table, `country`, to get the full
  "country, city" grouping the task asked for.
- Grouped by both `ct.city` and `co.country` together, since city names
  can repeat across different countries (grouping by city alone could
  merge unrelated places with the same name).
- Used `ORDER BY SUM(p.amount) ASC` instead of `DESC` here, since the
  question asks for the least sales, not the most.
