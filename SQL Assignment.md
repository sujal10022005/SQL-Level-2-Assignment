# SQL Assigment 24-04-2024

 ### Table Creation

    USE sampleSQL;

    CREATE TABLE orders(
    order_id VARCHAR(45),first_name VARCHAR(255), last_name VARCHAR(255),
    product_name VARCHAR(255), product_description TEXT,
    product_returnable VARCHAR(50), seller VARCHAR(255),
    total INT, date DATE, order_status VARCHAR(50), address TEXT
    );

### Adding Table Entries

    INSERT INTO orders
    (order_id, first_name, last_name, product_name, product_description, product_returnable, seller, total, date, order_status,city, state, pincode)
    VALUES
    ('O1', 'John', 'Doe', 'One Plus Nord', 'Red Mobile Phone', 'No', 'Seller_Z', 20001, '2022-08-15', 'Approved', 'Indore', 'MP', '452001'),
    ('O2', 'John', 'Doe', 'Air Jordans', 'Shoes', 'Yes', 'Nike', 25000, '2022-08-15', 'Approved', 'Indore', 'MP', '452001'),
    ('O3', 'Mary', 'Ann', 'One Plus Nord', 'Red Mobile Phone', 'No', 'Seller_Z', 20000, '2022-08-15', 'Approved', 'Pune', 'MH', '410014');

## Assignment Tasks :

### 1. CHECKING STATUS OF ORDER by ORDER ID
    SELECT order_id, order_status
    FROM orders
    WHERE order_id = '02';

### 2. TOTAL AMOUNT OF MY ORDERS

    SELECT SUM(total) as total_amount
    FROM orders;

### 3. UPDATING ONE OF ORDER'S CITY/ADDRESS
    UPDATE orders
    SET address = REPLACE(address, '452001, Indore, MP', '450001, Khandwa MP')
    WHERE order_id = '03';  
    SELECT * FROM orders WHERE order_id = '03';


### 4. CHANGING PRODUCT DESCRIPTION
    UPDATE orders
    SET product_description = 'New Product Description', total = 30000
    WHERE order_id = 'O2';

### 5. DISPLAYING RETURNABLE PRODUCTS
    SELECT * FROM orders
    WHERE product_returnable = 'Yes';

