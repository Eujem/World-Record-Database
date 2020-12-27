
# Query

> SELECT country.CountryName, IFNULL(countrylanguage.Language, 'N/A') AS OfficialLanguage
### FROM country
### LEFT JOIN countrylanguage
### ON country.Code = countrylanguage.CountryCode
### AND countrylanguage.IsOfficial = 'T'
### ORDER BY country.CountryName;



# Output

![](/images/query1.png)


[Go Back](/README.md/)
