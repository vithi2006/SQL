![sql9](https://github.com/user-attachments/assets/3ee68033-5329-4343-aee7-bf26d61b4da7)
This is work that I did in MySQL during my Data Technician Skills Bootcamp.

This work used the world_db dataset embedded in this SQL file:[Uploading world db (1).sql…]()

## Task 1 - Count cities in USA
SELECT COUNT(*) AS city_count
FROM city
WHERE CountryCode = (
    SELECT Code FROM country WHERE Name = 'United States'
);
 
![sql1](https://github.com/user-attachments/assets/cca9e543-778b-4b8c-9cc9-9d94081a0fe9)

Task 2 - Country with Highest Life Expectancy

SELECT Name, LifeExpectancy
FROM country
WHERE LifeExpectancy IS NOT NULL
ORDER BY LifeExpectancy DESC
LIMIT 1;

![sql2](https://github.com/user-attachments/assets/5e46c476-0984-4f63-8599-78766e4b3f1c)

Task 3 - New Year promotion: featuring cities with 'New' in their names


SELECT Name, CountryCode
FROM city
WHERE Name LIKE '%New%';

![sql3](https://github.com/user-attachments/assets/04c4e74a-f350-4ff6-82d1-9415bf4d9544)

Task 4 - Display columns with limit (first 10 rows)

SELECT Name, CountryCode, Population
FROM city
ORDER BY Population DESC
LIMIT 10;
![sql4](https://github.com/user-attachments/assets/31d28fda-aab4-40f5-b2e7-7ce6cc787ff2)


Task 5 5.	Cities with Population Larger than 2,000,000


SELECT Name, CountryCode, Population
FROM city
WHERE Population > 2000000
ORDER BY Population DESC;
![sql5](https://github.com/user-attachments/assets/edb1a795-3ca5-43d1-a1a8-9e425e858ad0)


6.	Cities Beginning with 'Be' Prefix

   SELECT city.Name AS City, country.Name AS Country
FROM city
JOIN country ON city.CountryCode = country.Code
WHERE city.Name LIKE 'Be%';

![sql6](https://github.com/user-attachments/assets/568eab1e-a921-41cc-88c9-2878e6426279)


7.	Cities with Population Between 500,000-1,000,000

SELECT Name, CountryCode, Population
FROM city
WHERE Population BETWEEN 500000 AND 1000000
ORDER BY Population DESC;

![sql7](https://github.com/user-attachments/assets/a6c97026-940e-418d-892c-abd9db17f715)


8.8.	Display Cities Sorted by Name in Ascending Order

SELECT Name, CountryCode, Population
FROM city
ORDER BY Name ASC;

![sql8](https://github.com/user-attachments/assets/a0db2613-7214-4633-82c9-7c5797ca78d5)



9.	Most Populated City

SELECT Name, CountryCode, Population
FROM city
ORDER BY Population DESC
LIMIT 1;

![sql9](https://github.com/user-attachments/assets/4dbeb540-8bf0-4c45-9568-894b55cf139f)


10.	 City Name Frequency Analysis: Supporting Geography Education

    SELECT Name AS City, COUNT(*) AS Frequency
FROM city
GROUP BY Name
ORDER BY Name ASC;
![sql10](https://github.com/user-attachments/assets/adc6914f-46b8-4c0a-9d5b-f111f6ce4745)



