# Que 1 : Customers (id, Name), Orders (id, customerId) 
SELECT c.Name
FROM Customers c
LEFT JOIN Orders o ON c.id = o.customerId
WHERE o.id IS NULL;

# Que 2 :  Following tables are given. Delete the rows of duplicate emails.

DELETE FROM Person
WHERE id NOT IN (
    	SELECT MIN(id)
    	FROM Person
    	GROUP BY email
);

# Que 3 : Write an SQL query to find all dates' Id with higher temperatures compared to its previous dates.

SELECT current.id
FROM WeatherTable current
JOIN WeatherTable previous ON current.recordData = DATE_ADD(previous.recordData, INTERVAL 1 DAY)
WHERE current.temperature > previous.temperature;

# Que 4 : From the HR Database, determine the second highest salary of an employee.

SELECT *
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 1;








 


