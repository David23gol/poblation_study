SELECT Name, Code, Region, Population
FROM country
WHERE Continent = 'Asia'
ORDER BY Population DESC
LIMIT 10;

SELECT Region, SUM(Population) AS total_poblacion
FROM country
WHERE Continent = 'Asia'
GROUP BY Region
ORDER BY total_poblacion DESC;

SELECT Region,
       SUM(Population) AS total_poblacion,
       ROUND(SUM(Population) * 100 / 
             (SELECT SUM(Population) FROM country WHERE Continent = 'Asia'), 2) AS porcentaje
FROM country
WHERE Continent = 'Asia'
GROUP BY Region
ORDER BY porcentaje DESC;
