
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

