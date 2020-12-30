[World Record Database](/README.md/#World-Record-Database)

## Query 1

#### SELECT country.CountryName, IFNULL(countrylanguage.Language, 'N/A') AS OfficialLanguage
#### FROM country
#### LEFT JOIN countrylanguage
#### ON country.Code = countrylanguage.CountryCode
#### AND countrylanguage.IsOfficial = 'T'
#### ORDER BY country.CountryName;

## Output

![](/images/query1.png)


[Go Back](/README.md/#Query-1)


## Query 2

#### SELECT country.CountryName AS Country, city.CityName AS City
#### FROM country
#### INNER JOIN city
#### ON country.Code = city.CountryCode
#### AND country.CountryName = 'Philippines'

## Output

![](/images/query2.png)

[Go Back](/README.md/#Query-2)

## Query 3

#### SELECT COUNT(DISTINCT Region) AS Total_Count_of_Regions
#### FROM country

## Output

![](/images/query3.png)

[Go Back](/README.md/#Query-3)

## Query 4

#### SELECT CountryName, Population,
#### ROW_NUMBER() OVER(ORDER BY Population DESC) RANK
#### FROM country
#### LIMIT 10;

## Output

![](/images/query4.png)

[Go Back](/README.md/#Query-4)

## Query 5

#### SELECT country.CountryName, COUNT(countrylanguage.Language) AS LanguageCount
#### FROM country
#### LEFT JOIN countrylanguage
#### ON country.code = countrylanguage.CountryCode
#### GROUP BY countrylanguage.CountryCode
#### ORDER BY LanguageCount DESC

## Output

![](/images/query5.png)

[Go Back](/README.md/#Query-5)


## Query 6

#### SELECT DISTINCT SurfaceArea, CountryName 
#### FROM country e1 
#### WHERE 2 = (SELECT count(DISTINCT SurfaceArea) 
#### FROM country e2 
#### WHERE e1.SurfaceArea <= e2.SurfaceArea);

## Output

![](/images/query6.png)

[Go Back](/README.md/#Query-6)

## Query 7

#### SELECT distinct SurfaceArea, CountryName
#### FROM country e1 
#### where 1 = (select count(distinct SurfaceArea) 
#### country e2 
#### WHERE e1.SurfaceArea >= e2.SurfaceArea);

## Output

![](/images/query7.png)

[Go Back](/README.md/#Query-7)

## Query 8

#### SELECT CONCAT( CountryName, ', ' , Continent, ', ' , Region, ', ' , GovernmentForm, ', ' , HeadOfState)
#### AS CompleteInformation
#### FROM country
#### LIMIT 20;

## Output

![](/images/query8.png)

[Go Back](/README.md/#Query-8)

## Query 9

#### SELECT country.CountryName, city.CityName, city.Population,
#### RANK() OVER(PARTITION BY country.CountryName ORDER BY city.Population DESC) Rank
#### FROM country
#### RIGHT JOIN city
#### ON country.Code = city.CountryCode
#### ORDER BY country.CountryName,
#### Rank;

## Output

![](/images/query9.png)

[Go Back](/README.md/#Query-9)

## Query 10

#### SELECT CityName, Population,
#### CASE 
#### WHEN Population > 500000 THEN 'This city has a population of More than 500,000'
#### ELSE 'This city has a population of less than or equal to 500,000'
#### END AS PopulationCheck
#### FROM city

## Output

![](/images/query10.png)

[Go Back](/README.md/#Query-10)

## Query 11

#### SELECT Region, COUNT( Region) as Countries_in_this_Region
#### FROM country
#### GROUP BY Region

## Output

![](/images/query11.png)

[Go Back](/README.md/#Query-11)

## Query 12

#### SELECT CountryName, Region, Continent, HeadOfState 
#### FROM country
#### WHERE HeadOfState IS NUL

## Output

![](/images/query12.png)

[Go Back](/README.md/#Query-12)

## Query 13

#### SELECT CountryName, Continent, Region, Population, GovernmentForm
#### FROM country
#### WHERE CountryName LIKE 'a%';

## Output

![](/images/query13.png)

[Go Back](/README.md/#Query-13)

## Query 14

#### SELECT * FROM city
#### JOIN countrylanguage
#### WHERE city.CountryCode = countrylanguage.CountryCode

## Output

![](/images/query14.png)

[Go Back](/README.md/#Query-14)

## Query 15

#### SELECT COUNT(DISTINCT CountryName) AS TotalCountry, COUNT(DISTINCT Region) AS TotalRegion, COUNT(DISTINCT GovernmentForm) AS TotalGovernmentForm,
#### SUM(Population)
#### FROM country;

## Output

![](/images/query15.png)

[Go Back](/README.md/#Query-15)

## Query 16

#### SELECT country.CountryName, AVE(city.Population) AS AverageCityPopulation
#### FROM city
#### RIGHT JOIN country
#### ON city.CountryCode = country.Code
#### GROUP BY CountryCode;

## Output

![](/images/query16.png)

[Go Back](/README.md/#Query-16)

## Query 17

#### SELECT country.Continent, city.Name
#### FROM city
#### RIGHT JOIN country
#### ON city.CountryCode = country.Code
#### WHERE country.Continent = 'Asia';

## Output

![](/images/query17.png)

[Go Back](/README.md/#Query-17)

## Query 18

#### UPDATE country
#### SET HeadOfState = 'Rodrigo R. Duterte'
#### WHERE CountryName = 'Philippines';

## Output

![](/images/query18.png)

[Go Back](/README.md/#Query-18)

## Query 19

#### SELECT country.CountryName, COUNT(city.CountryCode) AS NumberOfCities
#### FROM country
#### LEFT JOIN city
#### ON country.Code = city.CountryCode
#### GROUP BY country.CountryName

## Output

![](/images/query19.png)

[Go Back](/README.md/#Query-19)

## Query 20

#### SELECT COUNT(Language) AS TotalLanguage, COUNT(CASE IsOfficial WHEN 'T' THEN 1 ELSE NULL END) AS OfficialLanguage,
#### COUNT(CASE IsOfficial WHEN 'F' THEN 1 ELSE NULL END) AS NotOfficial
#### FROM countryLanguage

## Output

![](/images/query20.png)

[Go Back](/README.md/#Query-20)
