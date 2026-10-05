What if you want insert data into multiple tables?

Imagine you want to insert child data into the parent table
`
INSERT INTO orders (customer_id, order_date, status)
VALUES (1, '2019-01-02', 1);

SELECT LAST INSERT ID() -- returns last inserted id

INSERT INTO order_items
VALUES 
    (LAST_INSERT_ID(), 1, 1, 2.95),
    (LAST_INSERT_ID(), 1, 2, 3.95)
    ;
`
In this case we added an order to the orders table then since that was the parent table of order_items we could then use the primary key order_id as the corresponding column to insert two items in the order_items table which are associated to that same order since it is the child table to the orders table.
You would see x+1 amount of orders in the orders table then two items added to the order_items table with order_id = x+1

What if we want to copy data from one table to another
`
CREATE TABLE order_archived AS 
SELECT * FROM orders
`
Creates a copy of the orders table and names it order_archived
Although in the copy there would be no primary key'ed col or autoincrement
Must supply values for each in the copy

What if you want to only copy a subset from a table?
`
INSERT INTO orders_archived

SELECT *
FROM orders
WHERE order_date < '2019-01-01'
;
`
Here we are using a SELECT statement as a subquery in a statement to copy a subset of data and paste it into a created table

EXERCISES
For sql invoicing table, say we want to copy the records and put them into a new table called invoice_archive but instead of having a client_id we want to have client name so you want to join that table with the clients table then use that query as a subquery in a create table statement
We also only want the invoices that have a payment (have a payment date)
`
CREATE TABLE invoice_archive AS
SELECT
    i.invoice_id,
    c.name AS client,
    i.invoice_total,
    i.payment_total,
    i.invoice_date,
    i.due_date,
    i.payment_date
FROM invoices AS i
JOIN clients AS c
    USING (client_id)
WHERE i.payment_due IS NOT NULL
;
`