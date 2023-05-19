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

```mysql
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

```mysql
SELECT TRUNCATE(SUM(LAT_N),4)
FROM STATION
WHERE LAT_N > 38.7880 AND LAT_N < 137.2345;
```
