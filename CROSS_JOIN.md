Use CROSS JOINs to combine or JOIN every record from the first table with every record in the second table.

`
SELECT 
    c.first_name AS customer,
    p.name AS product
FROM customers c
CROSS JOIN products p
SORT BY c.first_name
;
`
You can also implicitly write it by typing multiple tables in the FROM clause, use explicit to be more clear.
You would use cross joins in the case of wanting all cases while association either doesn't matter or you know rows would already line up.

EXERCISES
Do a CROSS JOIN between shippers and products using the implicit and explcit methods
`
SELECT * FROM shippers sh, products p;
`
`
SELECT * FROM shippers sh CROSS JOIN products p;
`