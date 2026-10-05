Similar to INNER JOINs, can use OUTERs between two tables

`
SELECT
    c.customer_id,
    c.first_name,
    o.order_id,
    sh.name AS shipper
FROM customers s
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
LEFT JOIN shippers sh
    ON o.shipper_id = sh.shipper_id
ORDER BY c.customer_id
`
As best practice, order tables to follow use LEFT JOINs

EXERCISES
For columns order date, order id, first name, shipper and status. Use OUTER to join the information from the tables

`
SELECT
    o.order_date, 
    o.order_id, 
    o.shipped_date,
    c.first_name AS customer,
    sh.name AS shipper,
    os.name AS status
FROM orders o
JOIN customers c
    ON c.customer_id = o.customer_id
LEFT JOIN shippers sh 
    ON o.shipper_id = sh.shipper_id
LEFT JOIN order_statuses as os
    ON o.status = os.order_status_id
;
`
