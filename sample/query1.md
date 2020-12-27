
## Query

SELECT country.CountryName, countrylanguage.Language AS OfficialLanguage
FROM country
LEFT JOIN countrylanguage
ON country.Code = countrylanguage.Language
AND countrylanguage.IsOfficial = 'T';

## Output

![](images/query1.png)
