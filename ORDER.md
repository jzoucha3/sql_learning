# How to sort data

`
SELECT * FROM customers ORDER BY first_name
`
- Ascending by default but can use `DESC` after target 
- Can also sort by multiple conditions

`
SELECT * FROM customers ORDER BY state, first_name
`
-in mysql vs other dbm, can sort by any column whether it is next to SELECT command or not

`
SELECT  first_name, last_name FROM customers ORDER BY state DESC, first_name DESC
`
- Can also sort be alias

`
SELECT first_name, last_name, 10 AS points FROM customers ORDER BY points, first_name
`
- Can also sort by column positions (like a matrix)

`
SELECT first_name, last_name, 10 AS points FROM customers ORDER BY 1, 2
`
- Should be avoided though because if you add columns the commands no longer work

# Exercises
- Write a query for all the items with order_id 2 and sort them by their total price in descending order
`
SELECT *, unit_price * quantity AS 'total_price' FROM order_items WHERE order_id = 2 ORDER BY 'total_price';
`
