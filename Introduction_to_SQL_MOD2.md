## Filtering


To filter through datasets, the most important keyword that you will need is WHERE. You need to know a few things to use WHERE:
- it will always come after the keyword FROM
- comparison operators can be used and these are:
  - `=` equal
  - `<>` not equal
  - `<` less than
  - `>` greater than
  - `<=` less than or equal to
  - `>=` greater than or equal to
- can be used to filter numbers, names (marked in single quotes ' ' ) and even datas in ISO format ('2001-12-30')

### WHERE plus other keywords


#### WHERE plus AND


WHERE keyword can be used together with the AND keyword. This allows us to specify more than one condition to be selected. In fact,
with AND, you can select multiple conditions. The important thing to remember here, is that every new condition needs to be specified
 on a separate line, eg.:
 
 ```sql
 SELECT * FROM films WHERE release_year = 2000 
 
 AND country ='China';```


#### WHERE plus OR


Allows us to enquiry about situations where some but not all conditions must be met:

Similar to when using WHERE plus AND, each condition needs to be placed in a new line like:

`SELECT * FROM films WHERE release_year =2000

OR release_year = 1970;`


#### WHERE plus IN


In order to avoid repetition and long enquiries with OR, we can simplify an enquiry as such:

`SELECT title FROM films

WHERE release_years IN (1970, 1980, 1990, 2000);`


#### Mixing with WHERE


This can also be taken to the next level when you mix WHERE, AND plus OR, eg:

`SELECT * FROM films

WHERE (release_year = 1970 OR release_year = 2000)

AND (certification = 'PG' OR certification ='R')`


#### BETWEEN


There is another way that we can do the following:
`SELECT title FROM films

WHERE release_year >=1994

AND release_year <= 2000;`

This other way uses the keyword BETWEEN:
`SELECT title FROM films

WHERE release_year BETWEEN 1994 AND 2000;`

But in this case the values included in BETWEEN are included in the results too.

BETWEEN can be used together with AND and OR to make multiple conditions for our enquiry. Eg.:
`SELECT title FROM films

WHERE release_year BETWEEN 1994 AND 2000

AND (language = 'Spanish' OR language='French');`


#### NULL and IS NULL keywords


NULL represents a missing value. To check whether a value is missing, you can enquire for data which have null values using 
IS NULL. Alternatively, you can enquire for data that does not contain any missing values by using IS NOT NULL. For example:

`SELECT title FROM films

WHERE release_year IS NOT NULL;`


#### LIKE and NOT LIKE


These keywords allow you to search for specific text. Using wildcards such as `%` you can search for zero, one or more characters. Eg. `Data%` can give results that are Data, DataC, DataCamp, DataMind. While the wildcard `_` allows you to search for just one character. Eg. `Data_` can give results like DataC, Data1, and `Dat_` can give Data and Date. Similar can be done with NOT LIKE, but in inverse.

Example #1:
`SELECT name FROM people

WHERE name LIKE 'B%';`

Example #2:
`SELECT name FROM people

WHERE name LIKE '_r%';`

Example #3:
`SELECT name FROM people

WHERE name NOT LIKE 'A%';`
