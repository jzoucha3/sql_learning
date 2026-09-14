# Filtering Data with WHERE
- This presents a condition to be evaluated when iterating all the data in a table
- Only those meeting the criteria are retrieved

# Operators
>
>=
<
<=
=
!= or <>


`SELECT * FROM Customers WHERE state = 'VA`
- Strings or textual values require quotes (single or double both work)

# Practice
- Retrieve teh orders placed this year (assume this year is 2018)
`SELECT order_id FROM orders WHERE shipped_date >= '2018-01-01'`
