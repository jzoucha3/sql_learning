# Searching for Complex Patterns
- The regular expression command allows us to search for more complex patterns with less lines than combining LIKE
- '^' signals what you are searching for begins with what follows
- '$' signals what you are searching for ends with what is before
- `l` is a pipe orperator signaling an OR within
- '[]' can be put anywhere around a certain string to signal a search for values in which any of the characters within the brackets can be around the specific charater string (depends on placement)
- `[-]` same as above but shorthand for if you want to use a sequence like all characters a-c

# Examples
`SELECT * FROM customers WHERE REGEXP 'field';`
`SELECT * FROM customers WHERE REGEXP '^field';`
`SELECT * FROM customers WHERE REGEXP 'field$';`
`SELECT * FROM customers WHERE REGEXP 'field|rose|smith;`
`SELECT * FROM customers WHERE REGEXP '[aeh]field';` 
`SELECT * FROM customers WHERE REGEXP 'field[ytn]';`
`SELECT * FROM customers WHERE REGEXP '[a-h]field';`
- You may also combine any of these for your use case

# Pratice
- Get the customers whose first names are ELKA or AMBUR,
 then last names end with EY or ON,
 then lastnames start with MY contains SE,
 then last names contain B followed by R or u
`SELECT * FROM customers WHERE first_name REGEXP 'elka|ambur';`
`SELECT * FROM customers WHERE last_name REGEXP 'ey$|on$';`
`SELECT * FROM customers WHERE last_name REGEXP 'myY|se';`
`SELECT * FROM customers WHERE last_name REGEXP 'b[ru];`
