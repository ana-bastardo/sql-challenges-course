# Challenge 07: Join group by sales by city

**Level:** Moderate
**Topic:** JOIN & GROUP BY

## Problem
Determine which city (where the customer lives, not the store) has
the highest total sales amount.

## Solution
````sql
SELECT ct.city, SUM(p.amount)
FROM payment p
INNER JOIN customer c
ON p.customer_id = c.customer_id
INNER JOIN address a
ON a.address_id = c.address_id
INNER JOIN city ct
ON ct.city_id = a.city_id
GROUP BY ct.city
ORDER BY SUM(p.amount) DESC;
````

## Result
**Cape Coral**: Total amount of 221.55, the city with the most sales.

## Notes
- Chained four tables to trace the path from `payment` to the customer's
  actual city: `payment` » `customer` » `address` » `city`. Each table
  bridges one relationship, since payment doesn't store city directly.
- Grouped and ordered by total amount descending to surface the top
  city directly.
