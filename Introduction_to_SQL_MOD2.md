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
 
 `SELECT * FROM films WHERE release_year = 2000 \\
 AND country ='China';`

#### WHERE plus OR

Allows us to enquiry about situations where some but not all conditions must be met:

Similar to when using WHERE plus AND, each condition needs to be placed in a new line like:

`SELECT * FROM films WHERE release_year =2000
OR release_year = 1970;`

This can also be taken to the next level when you mix WHERE, AND plus OR, eg:

`SELECT * FROM films
WHERE (release_year = 1970 OR release_year = 2000)
AND (certification = 'PG' OR certification ='R')`

