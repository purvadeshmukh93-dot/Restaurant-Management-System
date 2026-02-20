**RESTAURANT MANAGEMENT SYSTEM**
Project Overview-
The project manages:
1. Customers
2. Orders
3. Menu items
4. Reservations
5. Payments

DATABASE NAME- Restaurant     

1. Customers Table
CREATE TABLE Customers(customer_id INT PRIMARY KEY AUTO_INCREMENT, 
name VARCHAR(100) NOT NULL, phone VARCHAR(15), 
email VARCHAR(100),
signup_date DATE)
);
 
2. Staff Table 
CREATE TABLE Staff(
staff_id INT PRIMARY KEY AUTO_INCREMENT,
name VARCHAR(100),role VARCHAR(50),
salary DECIMAL(10,2),
hire_date DATE)
);

3. Orders Table 
CREATE TABLE Orders(
order_id INT PRIMARY KEY AUTO_INCREMENT,
customer_id INT,staff_id INT,dish_name VARCHAR (100), 
quantity INT, total_amount DECIMAL(10,2), 
FOREIGN KEY (customer_id) REFERENCES Customers(customer_id),
FOREIGN KEY (staff_id) REFERENCES Staff(staff_id)
);

4. Payments Table
CREATE TABLE Payments (
    payment_id INT PRIMARY KEY AUTO_INCREMENT,
    order_id INT,
    payment_method VARCHAR(50),
    amount_paid DECIMAL(10,2)
);


