# Selecting Columns from Multiple Tables
`
SELECT * 
FROM sql_store.orders
INNER JOIN sql_store.customers ON sql_store.orders.customer.id = sql_store.customers.customer.id
`
- JOIN can be written by itself as INNER is default
- ON is the condition by which tables are joined and the column chosen needs to exist in both
- Whichever table you list first is what the set of columns will be with other added onto the end
- If you want to show the column values of the one you chose to condition on, qualify it with the specific table you would like to pull it from
- You may also shortern the query using aliases for the tables in use

# Note above we are inferring we didn't do USE command on sql_store, here inferring we did
`
SELECT * order_id, orders.customer_id, first_name, last_name 
FROM orders o
INNER JOIN customers c
    ON o.customer.id = c.customer.id
`

# Exercises
- Look at the order_items table. Write a table that joins this table with the products table so for each order return both the product_id as well as its name followed by quantity and unit price from the order items table. Also use aliases to shortern
`
SELECT order_id, o.product_id, quantity, o.unit_price, quantity_in_stock, name 
FROM sql_store.order_items o 
INNER JOIN sql_store.products p 
    ON o.product_id = p.product_id;
`