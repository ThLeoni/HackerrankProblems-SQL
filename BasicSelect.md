# [Revising the Select Query I](https://www.hackerrank.com/challenges/revising-the-select-query/problem?isFullScreen=true)

Query all columns for all American cities in the **CITY** table with populations larger than 100000. The **CountryCode** for America is USA.

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
SELECT (*)
FROM CITY
WHERE POPULATION > 100000 AND CountryCode = 'USA';
```
-------------------------------------------
# [Revising the Select Query II](https://www.hackerrank.com/challenges/revising-the-select-query-2/problem?isFullScreen=true)

Query the **NAME** field for all American cities in the **CITY** table with populations larger than 120000. The CountryCode for America is USA.

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
SELECT NAME
FROM CITY
WHERE POPULATION > 120000 AND COUNTRYCODE = 'USA';
```
-------------------------------------------
# [Select All](https://www.hackerrank.com/challenges/select-all-sql/problem?isFullScreen=true)

Query all columns (attributes) for every row in the **CITY** table.

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
SELECT (*)
FROM CITY;
```
-------------------------------------------
# [Select By ID](https://www.hackerrank.com/challenges/select-by-id/problem?isFullScreen=true)

Query all columns for a city in **CITY** with the ID 1661.

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
SELECT (*)
FROM CITY
WHERE ID = 1661;
```
-------------------------------------------
# [Japanese Cities' Attributes](https://www.hackerrank.com/challenges/japanese-cities-attributes/problem?isFullScreen=true)

Query all attributes of every Japanese city in the **CITY** table. The **COUNTRYCODE** for Japan is JPN.

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
SELECT (*)
FROM CITY
WHERE COUNTRYCODE = 'JPN';
```
-------------------------------------------
# [Japanese Cities' Names](https://www.hackerrank.com/challenges/japanese-cities-name/problem?isFullScreen=true)

Query the names of all the Japanese cities in the **CITY** table. The **COUNTRYCODE** for Japan is JPN.

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
SELECT NAME
FROM CITY
WHERE COUNTRYCODE = 'JPN';
```
-------------------------------------------
# [Weather Observation Station 1](https://www.hackerrank.com/challenges/weather-observation-station-1/problem?isFullScreen=true)

Query a list of CITY and STATE from the STATION table.
The STATION table is described as follows:

| **Field** | **Type** |
|-----:|---------------|
|ID|Number|
|NAME|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

### Solution:
```sql
SELECT CITY, STATE
FROM STATION;
```
-------------------------------------------
# [Weather Observation Station 3](https://www.hackerrank.com/challenges/weather-observation-station-3/problem?isFullScreen=true)

Query a list of **CITY** names from **STATION** for cities that have an even **ID** number. Print the results in any order, but exclude duplicates from the answer.

The **STATION** table is described as follows:

| **Field** | **Type** |
|-----:|---------------|
|ID|Number|
|NAME|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

### Solution:
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE ID % 2 = 0;
```
-------------------------------------------
# [Weather Observation Station 4](https://www.hackerrank.com/challenges/weather-observation-station-4/problem?isFullScreen=true)

Find the difference between the total number of **CITY** entries in the table and the number of distinct **CITY** entries in the table.

The **STATION** table is described as follows:

| **Field** | **Type** |
|-----:|---------------|
|ID|Number|
|NAME|VARCHAR2(21)|
|STATE|VARCHAR2(2)|
|LAT_N|NUMBER|
|LONG_W|NUMBER|

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

For example, if there are three records in the table with **CITY** values 'New York', 'New York', 'Bengalaru', there are 2 different city names: 'New York' and 'Bengalaru'. The query returns 1, because
`total number of records - number os unique city names = 3 - 2 = 1`

### Solution:
```sql
SELECT COUNT(CITY) - COUNT(DISTINCT CITY)
FROM STATION;
```
-------------------------------------------
