Combining columns across multiple databases
`
USE sql_inventory;

SELECT *
FROM order_items oi
JOIN sql_inventory.products p
    ON oi.products_id = p.products_id
;
`
These are duplicate tables from separate databases which you can combine
Order items and products have the same information up to the selected column

You may also join a table with itself through an inner join
`
USE sql_hr;

SELECT *
FROM employees e
JOIN employees m
    ON e.reports_to = m.employee_id
`
Writing a query to join the table with itself so we can query a employee with their manager

Now let's write a query to only select the name of the employee and their manager
`
USE sql_hr;

SELECT *
    e.employee_id,
    e.first_name,
    m.first_name AS manager -- We have prefixes to start because all those exists in both tables
FROM employees e
JOIN employees m
    ON e.reports_to = m.employee_id
`

Now how would you join more than two tables?
When you want corresponding info from multiple places
`
USE sql_store;

SELECT *
    o.order_id,
    o.order_date,
    c.first_name,
    c.last_name,
    os.name AS status
FROM orders o
JOIN customers c
    ON o.customers_id = c_customers_id
JOIN order_statuses os
    ON o.status = os.order_statuses_id
`
This is a total of three tables joined at specific colummns given prefixes

EXERCISES
Write a query and join the payments table with the payment_methods table as well as the clients tabel from sql_invoicing.
Produce a report that shows the payments with more detail such as the name of the client and the payment method.

`
USE sql_invoicing;

SELECT 
c.name, 
p.date, 
p.amount, 
pm.name as method
FROM clients c 
JOIN payments p      
    ON c.client_id = p.client_id 
JOIN payment_methods pm
    ON p.payment_method = pm.payment_method_id
;
`