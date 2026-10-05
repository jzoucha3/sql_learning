How would I update a single record?

`
UPDATE invoices
SET payment_total = 10, payment_date = ''2019-03-01'
WHERE invoice_id = 1
;
`

What if you updated the wrong record. Need to update then change the other back
`
UPDATE invoices
SET payment_total = DEFAULT, payment_date = ''NULL'
WHERE invoice_id = 1
;

UPDATE invoices
SET 
    payment_total = invoice_total * 0.5,
    payment_date = '2019-03-01'
WHERE invoice_id = 3
;
`

How would you update multiple records in a single query?
`
UPDATE invoices
SET 
    payment_total = invoice_total * 0.5,
    payment_date = '2019-03-01'
WHERE client_id IN (3, 4) -- col chosen as it appears multiple tables
;
`

EXERCISES
Write a sql statement to give any customers born before 1990 50 extra points
`
UPDATE customers 
SET points = points + 50 
WHERE birth_date < '1990-01-01';
`