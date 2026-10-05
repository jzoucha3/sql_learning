Natural joins are another way to join two tables but shouldn't be used over other methods

`
SELECT
    o.order_id,
    c.first_name
FROM orders o
NATURAL JOIN customers c
`
Will join tables based on common columns automatically, but in a more complex db sql can guess where to join wrong