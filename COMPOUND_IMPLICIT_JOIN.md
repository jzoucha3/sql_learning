Instead of using a single column for joining, we can use multiple for joining on unique identificaiton in the case of duplication.
We should look for a composite primary key for these cases (unique according to multiple columns)

`
USE sql_store;

SELECT *

FROM order_items oi
JOIN order_item_notes oin
    ON oi.order_id = oin.order_id
    AND oi.product_id = oin.product_id
    ;
`

We can also use the WHERE clause to join tables
`
SELECT *
FROM orders o, customers c
WHERE o.customer_id = c.customer_id
`
Better to use explicit JOIN because it forces you to identify at what columns
Otherwise you will get many more duplicate rows by cross joining (joins everything)

Outer joins allow for the return of records that don't meet conditions
`
SELECT *
    c.customer_id,
    c.first_name,
    o.order_id
FROM customers c
LEFT JOIN orders o # returns all records of given prefixes from the left joining table
    ON c.customer_id = o.customer_id
ORDER BY c.customer_id
`
In this case then, ordering of table joining determines which direction you choose
You may insert 'OUTER' but word is optional given direction determines already

EXERCISES
Produce an OUTER JOIN query that returns product id, name and quantity from order_items table. Need to join products table with order items table to see how many times each product is ordered, even if an item was never ordered.

`
SELECT 
    oi.product_id, 
    p.name, 
    oi.quantity 
FROM order_items oi 
RIGHT JOIN products p 
    ON oi.product_id = p.product_id
;
`