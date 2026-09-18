#  Retrieving Recrods for Missing Attributes
`SELECT * FROM customer WHERE phone IS NULL
`
# This one looks for records with missing attribute

` SELECT * FROM customer WHERE phone IS NOT NULL`
# This one is the complement, so you get records of all without missing (with a phone)

# EXERCISES
- Get the orders that are not shipped
`
SELECT * FROM order_items WHERE shipped_date IS NULL
`