## #1
Update item price with SKU `AROG-001` to `14000000`.


update items set price '14000000' where name='Asus ROG Stryx'

## #2
Find all users who have never logged in.


select * from users where last_login is not null;

## #3
Find all items that contains "mac"


SELECT * FROM items WHERE name like '%mac%';

## #4
Count all paid orders with SKU `IPHX-001`.


SELECT * FROM orders WHERE status='paid';

## #5
Find lowest price of all items.


SELECT name, price FROM items WHERE price = (SELECT MIN(price) FROM items);

## #6
Find highest price of all items.


SELECT name, price FROM items WHERE price = (SELECT MAX(price) FROM items);

## #7
Find average price of all items.


SELECT AVG(price) AS AVERAGEPRICE FROM items;

## #8
Find all orders made in February 2018.


SELECT id,user_id,item,shipping_address,notes,payments,total FROM orders WHERE MONTH(created_at) =2 AND YEAR(created_at) =2018;

## #9
Find all orders made between 1st March to 15th March.


SELECT * FROM orders WHERE created_at >='2018-03-01 23:53:00.000' AND created_at <= '2018-03-15 23:58:00.000';

## #10
Find all items was sold in February 2018.


SELECT * FROM orders WHERE created_at >='2018-02-01 23:53:00.000' AND created_at <= '2018-02-30 23:58:00.000' AND status='paid';

## #11
Find all paid orders in March 2018.


SELECT * FROM orders WHERE created_at >='2018-03-01 23:53:00.000' AND created_at <= '2018-03-30 23:58:00.000' AND status='paid';

## #12
Sum all total orders, with status canceled – made by user with ID 1.


select total from orders where status='canceled' and user_id=1;
select sum(total) from orders where status='canceled' and user_id=1;

## #13
Sum all total orders, with status paid – made by user with ID 3.


SELECT total FROM orders WHERE status='paid' and user_id=3;
SELECT SUN(total) FROM orders WHERE status='paid' and user_id=1;

## #14
Find all paid orders with courier ID 2 made by user ID 1.


SELECT * FROM orders WHERE courier_id =2 and user_id=1;

## #15
Find all orders that contains SKU `IPHX-001`.


SELECT * FROM orders WHERE item like '%IPHX-001%';