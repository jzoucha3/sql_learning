# Retrieving Data with Specific Pattern
`SELECT FROM customers WHERE last_name LIKE 'b%;'`
- LIKE identifies all where last_name start with b
- % says pattern can have any amount of characters before, after or between (depends on placement)
- The number of _ underscores around the character you look up tells sql there are exactly that many characters around the specific pattern you search for

# Practice
- Get the customers whose addresses contain TRAIL or AVENUE, then separately whose phone numbers end with 9
`SELECT * FROM customers WHERE address LIKE '%trail%' OR LIKE '%avenue%';`
`SELECT * FROM customers WHERE address LIKE '%9';`
