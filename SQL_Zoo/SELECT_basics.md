## World 

| name         | continent | area   | population | gdp           |
|--------------|-----------|--------|------------|---------------|
| Afghanistan  | Asia      | 652230 | 25500100   | 20343000000   |
| Albania      | Europe    | 28748  | 2831741    | 12960000000   |
| Algeria      | Africa    | 2381741| 37100000   | 188681000000  |
| Andorra      | Europe    | 468    | 78115      | 3712000000    |
| Angola       | Africa    | 1246700| 20609294   | 100990000000  |

1. WHERE clause to show the population of 'Germany'

SELECT population FROM world
WHERE name = 'Germany'

2. Show the name and the population for 'Sweden', 'Norway' and 'Denmark'.

SELECT name, population FROM world
WHERE name IN ('Sweden', 'Norway', 'Denmark');

3. The country and the area for countries with an area between 200,000 and 250,000.

SELECT name, area FROM world
WHERE area BETWEEN 200000 AND 250000

4. Show the name, continent and population of all countries

SELECT name, continent, population FROM world

5. Show the name for the countries that have a population of at least 200 million. 200 million is 200000000, there are eight zeros.

SELECT name FROM world
WHERE population = 64105700

6. Give the name and the per capita GDP for those countries with a population of at least 200 million.

SELECT name, gdp / population AS per_capita_gdp
FROM world
WHERE population >= 200000000

7. Show the name and population in millions for the countries of the continent 'South America'. Divide the population by 1000000 to get population in millions.

SELECT name, population/1000000 
FROM world
WHERE continent = 'South America'

8. Show the name and population for France, Germany, Italy

SELECT name, population
FROM world
WHERE name IN ('France', 'Germany', 'Italy')

9. Show the countries which have a name that includes the word 'United'

SELECT name
FROM world
WHERE name LIKE'%United%'

10. Show the countries that are big by area or big by population. Show name, population and area.
Two ways to be big: A country is big if it has an area of more than 3 million sq km or it has a population of more than 250 million.

SELECT name, population, area
FROM world
WHERE area > 3000000 OR population > 250000000

