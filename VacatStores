--create a customer table using the copy command method--
create table Customer(
	customer_id varchar primary key,
	customer_name varchar,
	segment varchar,
	age int,
	country varchar,
	city varchar,
	state varchar,
	postal_code int,
	region varchar
);

--load data into the customer table using the copy command method--
copy customer 
from 'C:\Program Files\PostgreSQL\Customer.csv' delimiter ',' csv header;

--query the customer table to validate--
select *
from customer;

--Extracting data for all states excluding Utah and Nebraska
select 
	customer_id,
	segment,
	age,
	state,
	region
from customer
where state not in ('Utah','Nebraska');
	

--create a product table--
create table Product(
	Product_ID varchar primary key,
	Category varchar,
	Sub_Category varchar,
	Product_Name varchar
);

--load data into the product table using the copy command method--
copy product
from 'C:\Program Files\PostgreSQL\Product.csv' delimiter ',' csv header;


--query the product table to validate--
select *
from product;


--create the sales table using the copy command method--
create table Sales(
	Order_Line int primary key,
	Order_ID varchar,
	Order_Date date,
	Ship_Date date,
	Ship_Mode varchar,
	Customer_ID varchar,
	Product_ID varchar,
	Sales float,
	Quantity int,
	Discount float,
	Profit float,
	foreign key (customer_id) references customer(customer_id),
	foreign key (product_id) references product(product_id)
);

--load data into the sales table using the copy command method--
copy sales
from 'C:\Program Files\PostgreSQL\sales (cleaned).csv' delimiter ',' csv header

--query the sales table to validate--
select *
from sales;


--Extracting all orders from 2015 to 2017
select *
from sales
where order_date between '01-01-2015' and '31-12-2017';
