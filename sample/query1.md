
# Query

### SELECT country.CountryName, countrylanguage.Language AS OfficialLanguage
### FROM country
### LEFT JOIN countrylanguage
### ON country.Code = countrylanguage.CountryCode
### AND countrylanguage.IsOfficial = 'T'
### ORDER BY country.CountryName;


# Output

![](images/query1.png)
