# Combination Operators
- AND, OR and NOT are ways to combine conditions
- AND means both conditions have to be met
- OR means either conditions can be met to retrieve
- NOT means return data which are complements (negatio) to the argument
- There is a hierarchy among these with AND taking precedent of OR so use () when needed

`SELECT * FROM Customers WHERE birth_date > '1990-01-01' OR points > 1000`
-  returns all columns from customers table where the birthdate column value is after 1990 or (along with) where points are above 1000

# Practice
- From the order_items table, get the items for order #6 where the total price is greater than 30
`SELECT product_id FROM order_items WHERE order_id = 6 AND (unit_price * quantity) > 30`
