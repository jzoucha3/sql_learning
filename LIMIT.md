# When you only want to query a limited amount of records
`
SELECT * 
FROM customers 
LIMIT 3
`
- You receive all columns but only up to 3 rows

# What if you want to show a limit per page of query but then also skip some set amount of records 
`
SELECT * 
FROM customers 
LIMIT 6, 3
-- page 1: 1 - 3
-- page 2: 4 - 6
-- page 3: 7 - 9 
`
- The first number after the LIMIT clause is the "offset" telling sql to skip the first x amount of records then pick the next y records

# IMPORTANT NOTE
- LIMIT clause should ALWAYS come at the end of a query

# Exercises
- Get the top three loyal customers (those which have more points than anyone else)
`
SELECT * 
FROM sql_store.customers 
ORDER BY points DESC 
LIMIT 3;
`