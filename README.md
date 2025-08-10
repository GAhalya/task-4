## MySQL's built-in sample database queries

## Tables Used:
country
city
(Loaded from MySQL's built-in sample database)

## a) Basic SQL Clauses
**SELECT**: Retrieve specific columns
## Query :
SELECT name, continent, population FROM country;

**WHERE**: Filter population > 100 million
## Query :
SELECT name, continent, population FROM country
WHERE population > 100000000;

**GROUP BY**: Group population by continent
## Query :
SELECT continent, SUM(population) AS TotalPopulation
FROM country
GROUP BY continent;

**ORDER BY**: Sort countries by population descending
## Query :
SELECT name, population FROM country
ORDER BY population DESC;

## b) Joins

**INNER JOIN**: Match cities with their countries
## Query :
SELECT city.name AS cityname, country.name AS countryname
FROM city
INNER JOIN country ON city.countrycode = country.code;

**LEFT JOIN**: All cities, even if no matching country
## Query :
SELECT city.name, country.name
FROM city
LEFT JOIN country ON city.countrycode = country.code;

**RIGHT JOIN**: All countries, even if no matching city
## Query :
SELECT city.name, country.name
FROM city
RIGHT JOIN country ON city.countrycode = country.code

## c) Subqueries
## Query :
SELECT name, population FROM country
WHERE population > (SELECT AVG(population) FROM country);

## d) Aggregate Functions
## SUM :
## Query :
SELECT region, SUM(gnp) AS totalgnp
FROM country
GROUP BY region;

## AVG :
## Query :
SELECT continent, AVG(lifeexpectancy) AS avglifeexpectancy
FROM country
GROUP BY continent;
