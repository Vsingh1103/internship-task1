# internship-task1
creating database and tables

In this repo i have created a database name of e_commerce in which multiple table is created names as Customer,Product,Orders,OrderDetails and Payment
Primary Keys(PK):-Customer(CustomerID),Product(ProductID,)Orders(OrderID),OrderDetails(OrderDetailID) and Payment(PaymentID).

Foreign Keys(FK):-
Orders.CustomerID → Customer.CustomerID,OrderDetails.OrderID → Orders.OrderID,OrderDetails.ProductID → Product.ProductID,Payment.OrderID → Orders.OrderID


-- Customer Table

CREATE TABLE Customer (CustomerID INT PRIMARY KEY,Name VARCHAR(100),Email VARCHAR(100) UNIQUE,Phone VARCHAR(15),Address VARCHAR(255)
);

-- Product Table

CREATE TABLE Product (ProductID INT PRIMARY KEY,Name VARCHAR(100),Price DECIMAL(10,2),Stock INT
);

-- Order Table

CREATE TABLE Orders (OrdersID INT PRIMARY KEY,CustomerID INT,OrderDate DATE,FOREIGN Key(CustomerID) REFERENCES Customer(CustomerID)
);

-- OrderDetails Table

CREATE TABLE OrderDetails (OrderDetailID INT PRIMARY KEY,OrdersID INT,ProductID INT,Quantity INT,
FOREIGN KEY (OrdersID) REFERENCES Orders(OrdersID),
FOREIGN KEY (ProductID) REFERENCES Product(ProductID)
);

-- Payment Table

CREATE TABLE Payment (PaymentID INT PRIMARY KEY,OrderID INT UNIQUE,Amount DECIMAL(10,2),PaymentDate DATE,PaymentMethod VARCHAR(50),
FOREIGN KEY (OrdersID) REFERENCES Orders(OrdersID)
);
