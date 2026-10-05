What if we want to get all records for coresponding relationships within the same table

`
USE sql_hr;

SELECT
    e.employee_id,
    e.first_name,
    m.first_name AS manager
FROM employees e
LEFT JOIN employees m
    ON e.reports_to = m.employee_id
`

JOIN conditions can make queries longer and hard to read
But if what we are joining use the same column names, we can elicit USING command
`
SELECT
    o.order_id,
    c.first_name
    sh.name AS shipper
FROM orders o
JOIN customers c
    -- ON o.customer_id = c.customer_id
    USING (customer_id)
LEFT JOIN shippers sh
    USING (shipper_id)
;
`

What about the case where we have multiple columns in our join condition?
This would be the case for composite primary keys which are comprised of multiple columns that make it uniquely identifiable.
`
SELECT *
FROM order_items oi
JOIN order_item_notes oin
    -- ON oi_order_id = oin.order_id AND oi.product_id = oin.prodduct_id
    USING (order_id, product_id)
`

EXERCISES
For the sql invoicing database, we want to write a query which returns the payments from the payments table with the date, client, amount and payment made.

`
SELECT 
    c.name AS client, 
    p.amount, 
    p.date, 
    pm.name AS method 
FROM payments p 
JOIN clients c USING (client_id) 
LEFT JOIN payment_methods pm 
    ON pm.payment_method_id = p.payment_id;
`