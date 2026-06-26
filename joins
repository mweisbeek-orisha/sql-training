# Joining tables together
You can put as much data in a table as you like and also add as much columns as you like. Of course, there are some boundaries, but you will not easily encounter these.

But sometimes the data that you want to see is in another table. How can you put all of these data into one overview?

## LEFT JOIN & INNER JOIN
Then LEFT JOIN and INNER JOIN will become your friends.

### Required data: INNER JOIN
You usually want to match data that are also in another table. Then you use INNER JOIN. In that case the same data has to exist in both tables.

This query will only show Customers who have ordered one or more products.
```sql
SELECT * 
FROM Customers
INNER JOIN Orders ON Orders.CustomerId = Customers.Id
```
For performance reasons (and to make the best match) it is good when you join tables where both columns have the same type (like INTEGER or UNIQUEIDENTIFIER).

You can make this query more readable by using aliases:
```sql
SELECT * 
FROM Customers c
INNER JOIN Orders o ON o.CustomerId = c.Id
```

When you do not tell which columns you want to see (using *), SQL Server will give you all of the columns of all of the tables in the query.
To select only specific columns (or in a specific order) 
```sql
SELECT c.Name, o.OrderDate, o.OrderTotal
FROM Customers c
INNER JOIN Orders o ON o.CustomerId = c.Id
ORDER BY o.OrderDate DESC
```
This will give you the name of the customer, the date the order has been placed and the total order revenue.
All of these orders are listed with the latest order on top (hence the keyword DESC, short for descending).

### Optional data: LEFT JOIN
But sometimes the data does not need to be available in the other table. Then you can use LEFT JOIN (that is actually a LEFT OUTER JOIN).

```sql
SELECT * 
FROM Customers
LEFT JOIN Orders ON Orders.CustomerId = Customers.Id
```

The above query looks like the ones from above, but this query will give you ALL of the customers (!), regardless of whether they placed an order. When a customer has placced an order you will see that data. 
But when a customer did not place an order you will see the customer's data, but the order-related columns are empty. Sometimes that is what you want to achieve, depending on what kind of overview you would like to create. 

## INNER JOIN, LEFT (OUTER) JOIN, RIGHT (OUTER) JOIN, FULL (OUTER) JOIN, CROSS JOIN, SELF JOIN
I know there are also other variants like RIGHT (OUTER) JOIN, et cetera. But using the 2 variants from this article I can tackle most table joins. So to make things easy, those are what I use.
