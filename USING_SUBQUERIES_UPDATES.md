How can subqueries be used in update statements?

What if you don't know the client_id, just the name and want to update all invoices where that name can be used to traced back to the id?
`
UPDATE invoices
SET 
    payment_total = invoice_total * 0.5,
    payment_date = '2019-03-01'
WHERE client_id = 
    (SELECT client_id
    FROM clients
    WHERE name = 'MyWorks')
`
The set up is similar to the updated with a WHERE clause expect we put a subquery in () so that runs first to return the id associated with the known name, then puts that into the main update query

What if we want to update based on a value that appears in many rows?
'
UPDATE invoices
SET 
    payment_total = invoice_total * 0.5,
    payment_date = '2019-03-01'
WHERE client_id IN 
    (SELECT client_id
    FROM clients
    WHERE state IN ('CA', 'NY'))
'
Good practice is to run the subquery first to see what it returns
Check if that is correct then place it in as a subquery

EXERCISES
For orders table in sql_store database, write a query to update the comments col for customers who have more then 3000 points and regard them as gold customers.
`
UPDATE orders
SET
    comments = 'gold customer'
WHERE customer_id IN 
    (SELECT customer_id
    FROM customers
    WHERE points > 3000)
;
`