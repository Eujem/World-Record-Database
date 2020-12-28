
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
