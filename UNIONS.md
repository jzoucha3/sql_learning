We can use UNION when we want to combine rows from multiple tables

`
SELECT 
    order_id,
    order_date,
    'Active' AS status
FROM orders
WHERE order_date >= '2019-01-01'
UNION
SELECT 
    order_id,
    order_date,
    'Archived' AS status
FROM orders
WHERE order_date < '2019-01-01';
`
UNION from same table

`
SELECT first_name
FROM customers
UNION
SELECT name
FROM shippers
`
UNION from separate tables

UNIONs must be from tables with the same amount of columns
Whatever is used in the first query becomes the name of the returned column unless aliased

EXERCISES
Return records to obtain the customer_id, name and points with corresponding statuses. Those with less than 2000 points are bronze
Those with 2000 =< 3000 are silver
Those with > 3000 are gold
Sort by first name

`
SELECT 
    customer_id, 
    first_name, 
    last_name, 
    points, 
    'Bronze' AS status 
FROM customers 
WHERE points > 2000 
UNION 
SELECT 
    customer_id, 
    first_name, 
    last_name, 
    points, 
    'Silver' AS status 
FROM customers 
WHERE points >= 2000 AND points < 3000 
UNION 
SELECT 
    customer_id, 
    first_name, 
    last_name, 
    points, 
    'Gold' AS status 
FROM customers 
WHERE points < 3000 
ORDER BY first_name;
`