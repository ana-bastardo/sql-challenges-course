# Challenge 06: Left join unassigned addresses

**Level:** Moderate
**Topic:** LEFT JOIN & FILTERING

## Problem
Find addresses that are not associated with any customer, and count
how many there are.

## Solution
````sql
SELECT COUNT(*) AS nr_addresses
FROM(
SELECT address, first_name, last_name FROM address a
LEFT JOIN customer c
ON a.address_id = c.address_id
WHERE c.address_id IS NULL) AS sub;
````

## Result
**4** addresses are not associated with any customer.

## Notes
- Used a `LEFT JOIN` from `address` to `customer` so that addresses
  without a matching customer still appear in the result, with NULLs
  in the customer columns.
- Initially filtered on `first_name IS NULL AND last_name IS NULL`,
  which worked but indirectly relied on unrelated columns being NULL.
  Switched to `c.address_id IS NULL`, the actual join key, which is
  a more direct way to detect unmatched rows.
- Wrapped the filtered query in a subquery to apply `COUNT(*)`on top
  of the filtered result set.
