How to insert, update and delete data

Attribures include col, type (want to use varchar for strings to allow variable length), identifier for key, not null, autoincrement (like increasing by 1 for new), etc and defaults for empty
You will want to check these before inserting data as keys must be unique and certain columns only take certain types of data

Inserting data into columns
`
INSERT INTO customers (
first_name,
last_name,
birth_date,
address,
city,
state)
VALUES ( 
'John', 
'Smith', 
'1990-01-01',
'address',
''city',
'state'
)
; 
`
Generate or give specific values for every col in this table
Those that allow NULL, have DEFAULT, or autoincrement need not be filled
Inserted values can be listed in any order to change order so long as the order matches in the query
These will append to the end of the database


Inserting multiple rows
`
INSERT INTO shippers (name) 
VALUES ('Shipper1'),
('Shipper2')
;
`

EXERCISES
Insert three rows in the products table
`
DESC product; -- obtain table column description and requirements

INSERT INTO products 
    (name, 
    quantity_in_stock, 
    unit_price) 
VALUES 
    ('keyboard', 5, 32.14), 
    ('mouse', 3, 14.02), 
    ('speaker', 8, 51.98)
;
`