# Shortening Multiple Conditions
- Cannot uses multiple conditions after a boolean whose return is either TRUE or FALSE
`SELECT * FROM Customers WHERE state = 'VA' OR state = 'GA' OR state = 'FL'`

- Rather than repeating the column and condition through OR expansion, can use IN
`SELECT * FROM Customers WHERE state IN ('VA', 'GA', 'FL)

- Use IN when you what to compare an attribute with a list of values
- You can also put numbers inside the paratheses in which case you don't need quotes

