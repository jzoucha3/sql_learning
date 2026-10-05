What about how to delete data?

`
DELETE FROM invoices
WHERE invoice_id = 
(SELECT *
FROM clients
WHERE name = 'MyWorks')
;
`

Let's say you want to restore databases to its original state
Just re-execute the script used to create the databases