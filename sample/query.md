
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

## Query 4

#### SELECT CountryName, Population,
#### ROW_NUMBER() OVER(ORDER BY Population DESC) RANK
#### FROM country
#### LIMIT 10;

## Output

![](/images/query5.png)

[Go Back](/README.md/#Query-5)


## Query 4

#### SELECT CountryName, Population,
#### ROW_NUMBER() OVER(ORDER BY Population DESC) RANK
#### FROM country
#### LIMIT 10;

## Output

![](/images/query6.png)

[Go Back](/README.md/#Query-6)

## Query 4

#### SELECT CountryName, Population,
#### ROW_NUMBER() OVER(ORDER BY Population DESC) RANK
#### FROM country
#### LIMIT 10;

## Output

![](/images/query7.png)

[Go Back](/README.md/#Query-7)

## Query 4

#### SELECT CountryName, Population,
#### ROW_NUMBER() OVER(ORDER BY Population DESC) RANK
#### FROM country
#### LIMIT 10;

## Output

![](/images/query8.png)

[Go Back](/README.md/#Query-8)

## Query 4

#### SELECT CountryName, Population,
#### ROW_NUMBER() OVER(ORDER BY Population DESC) RANK
#### FROM country
#### LIMIT 10;

## Output

![](/images/query9.png)

[Go Back](/README.md/#Query-9)

## Query 4

#### SELECT CountryName, Population,
#### ROW_NUMBER() OVER(ORDER BY Population DESC) RANK
#### FROM country
#### LIMIT 10;

## Output

![](/images/query10.png)

[Go Back](/README.md/#Query-10)
