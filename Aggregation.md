# [Japan Population](https://www.hackerrank.com/challenges/japan-population/problem?isFullScreen=false)

Query the sum of the populations for all Japanese cities in **CITY**. The COUNTRYCODE for Japan is **JPN**.

**Input Format**

The **CITY** table is described as follows:

| **Field** | **Type** |
|-----:|---------------|
|ID|Number|
|NAME|VARCHAR2(17)|
|COUNTRYCODE|VARCHAR2(3)|
|DISTRICT|VARCHAR2(20)|
|POPULATION|NUMBER|

### Solution: 

```sql
SELECT SUM(Population)
FROM CITY
WHERE COUNTRYCODE = "JPN";
```
-------------------------------------------

# [Weather Observation Station 13](https://www.hackerrank.com/challenges/weather-observation-station-13/problem?isFullScreen=false)

Query the sum of Northern Latitudes (LAT_N) from **STATION** having values greater than **38.7880** and less than **137.2345**. Truncate your answer to **4** decimal places.

**Input Format**

The **STATION** table is described as follows:

| **Field** | **Type** |
|-----:|---------------|
|ID|Number|
|CITY|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_N|NUMBER|

where LAT_N is the northern latitude and LONG_W is the western longitude.

### Solution: 

```sql
SELECT TRUNCATE(SUM(LAT_N),4)
FROM STATION
WHERE LAT_N > 38.7880 AND LAT_N < 137.2345;
```

-------------------------------------------

# [The Count Function](https://www.hackerrank.com/challenges/revising-aggregations-the-count-function/problem?isFullScreen=false)

Query a count of the number of cities in **CITY** having a Population larger than **100,000**.

**Input Format**

The **CITY** table is described as follows:

| **Field** | **Type** |
|-----:|---------------|
|ID|Number|
|NAME|VARCHAR2(17)|
|COUNTRYCODE|VARCHAR2(3)|
|DISTRICT|VARCHAR2(20)|
|POPULATION|NUMBER|

### Solution:

```sql
SELECT COUNT(*) AS DISTRICT
FROM CITY
WHERE Population > 100000;
```
---------------------------------------------

# [Revising Aggregations - Averages](https://www.hackerrank.com/challenges/revising-aggregations-the-average-function/problem?isFullScreen=false)

Query the average population of all cities in **CITY** where District is **California**.

**Input Format**

| **Field** | **Type** |
|-----:|---------------|
|ID|Number|
|NAME|VARCHAR2(17)|
|COUNTRYCODE|VARCHAR2(3)|
|DISTRICT|VARCHAR2(20)|
|POPULATION|NUMBER|

### Solution:

```sql
SELECT AVG(POPULATION) AS AVERAGE_CALIFORNIA
FROM CITY
WHERE DISTRICT = 'California';
```
-------------------------------------------
# [The Blunder](https://www.hackerrank.com/challenges/the-blunder/problem?isFullScreen=false)

Samantha was tasked with calculating the average monthly salaries for all employees in the **EMPLOYEES** table, but did not realize her keyboard's **0** key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.

Write a query calculating the amount of error (i.e.:  ***actual - miscalculated*** average monthly salaries), and round it up to the next integer.

**Input Format**

The **EMPLOYEES** table is described as follows:

| **Field** | **Type** |
|-----:|---------------|
|ID|INTEGER|
|NAME|STRING|
|SALARY|INTEGER|

**Note**: Salary is per month.

**Constraints**
$`1000 < Salary < 10^5.`$

### Solution:

```sql
SELECT CEIL(AVG(salary) - AVG(REPLACE(Salary, '0', '')))
FROM EMPLOYEES;
```

--------------------------------------------------

# [Top Earners](https://www.hackerrank.com/challenges/earnings-of-employees/problem?isFullScreen=false)

We define an employee's total earnings to be their monthly ***salary x months*** worked, and the maximum total earnings to be the maximum total earnings for any employee in the **Employee** table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as  space-separated integers.

**Input Format**

The **Employee** table containing employee data for a company is described as follows:

| **Column** | **Type** |
|-----:|---------------|
|EMPLOYEE_ID|INTEGER|
|NAME|STRING|
|MONTHS|INTEGER|
|SALARY|INTEGER|

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

### Solution: 

```sql 
SELECT months*salary, count(*)
FROM employee
GROUP BY months*salary
ORDER BY months*salary DESC
limit 1;
```

--------------------------------------------------

# [Weather Observation Station 2](https://www.hackerrank.com/challenges/weather-observation-station-2/problem?isFullScreen=false)

Query the following two values from the **STATION** table:

The sum of all values in LAT_N rounded to a scale of 2 decimal places.
The sum of all values in LONG_W rounded to a scale of 2 decimal places.

**Input Format**

The **STATION** table is described as follows:

| **Field** | **Type** |
|-----:|---------------|
|ID|Number|
|CITY|VARCHAR2(17)|
|STATE|VARCHAR2(3)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Output Format**
Your results must be in the form:

`lat lon`

where ***lat*** is the sum of all values in LAT_N and ***lon*** is the sum of all values in LONG_W. Both results must be rounded to a scale of 2 decimal places.

### Solution: 
```sql 
SELECT ROUND(SUM(LAT_N),2), ROUND(SUM(LONG_W),2)
FROM STATION;
```
