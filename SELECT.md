# SELECT STATEMENT
`SELECT * FROM <your_table>`;
- SELECT retrieves data from the table within a db
- * chooses all columns
- FROM specifies the table
- In this case we have two clauses, SELECT and FROM

# Adding Clauses
`SELECT * FROM <table> WHERE <column> = <condition> ORDER BY <column condition>`
- WHERE identifies specific column and you may give a condition for the value of that condition (like 1)
- ORDER BY provides the data queried listed in order of the column condition specified 
- The placement of clauses matters, base the structure off the targeted data you want

# Arithmatic Operations
- You may also apply arithmatic operations to query data based on data you have
`SELECT last_name, first_name, points, points+10 AS 'inflated price'
FROM customers`
- +10 creates and produces a column of data that adds 10 to the points column that exists in customers and is associated with first and last names
- You may use addition `+`, subtraction `-`, multiplication `*`, division `/` and module (remainder after division) %
- Order of operation for math isn't sequential like the commands, it follows arithmatic order of operations (use paratheses if needed)
- AS creates an alias for the data created from math applied to the original data, quotes are needed when alias has spaces

# DISTINCT SELECT
`SELECT DISTINCT <column> FROM <table> `
- DISTINCT retrives the unique list of the values in the column selected

# Practice
- Write a command which return all the product names with unit price and a unit price increased by 10%
`SELECT name, unit_price, unit_price * 1.1 AS '<alias>' FROM products`
