# Opening mysql
`mysql -u <user> -p`
-u user
-p password
- Passwords can be changed with `passwrd'

# Creating Comments
`--`
- Double dashes indicate to sql what follows on this line is a comment

# White Spaces
- You may put clauses on one line but longer ones are easier to read top to bottom

# Capitals
- You don't need to make syntax capital but it helps to differentiate commands vs what you are querying

# Running Scripts
`SOURCE <path>`
- SORUCE is the command for executing selected file
- ; terminates the command

# Listing DBs in a Server
`SHOWS DATABASES;`
`SELECT DATABASE();`
- To confirm db you're in

# Start Working Within
`USE `<database name>`
`SHOW TABLES`

# Objects of a DB
- Tables store data
- Views virtual tables for viewing how combined tables looked (report generation)
- Stored procedures and functions are little programs inside a db for querying data (returns data we want)

# Relational DB
- Two dbs have a relation if at least one column matches another, thus making an identifier which creates a relationship between the two
