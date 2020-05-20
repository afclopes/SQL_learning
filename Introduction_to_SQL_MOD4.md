### Ordering results

Using the keyword ORDER BY, enquiries can be ordered in ascending or descending order. By default, this is done in ascending order, 
the reverse can be enquired when using the keyword DESC. This order can refer to numbers but can also be applied to words and letters 
following the alphatet.

Example #1:
```sql
SELECT name FROM people
ORDER BY name;
```
Example #2:
```sql
SELECT title
FROM films
WHERE release_year IN (2000, 2012)
ORDER BY release_year;
```
Remember that `IN (2000, 2012)` refers to looking at either year 2000 or year 2012.

Example #3:
```sql
SELECT *
FROM films
WHERE release_year <> 2015
ORDER BY duration;
```

Ordering columns can also be done on multiple columns at a time. When you define which columns you want to be ordered, then this will 
be done one at a time according to the order they appear in the enquiry. The second column you order on only steps in when the first 
column is not decisive to tell the order.

Example #1:
```sql
SELECT birthdate, name
FROM films
ORDER BY birthdate, name;
```

### Grouping results

The keyword GROUP BY allows columns to be grouped according to traits in other columns. This keyword is often used together with 
aggregate functions like MAX(), or COUNT(), and also with other keywords like ORDER BY, where ORDER BY always goes after GROUP BY.

Example:
```sql
SELECT release_year, country, MAX(budget)
FROM films
GROUP BY release_year, country
ORDER BY release_year, country;
```

### Keyword: HAVING

Similar To WHERE in which you can state conditions but this time you can also use aggregate functions to state these conditions.

Example:
```sql
SELECT COUNT release_year
FROM films
GROUP BY release_year
HAVING COUNT(title) >200;
```

Other keywords like GROUP BY and ORDER BY need to be used before HAVING.


### Summary

You can only use keywords like GROUP BY and WHERE which use columns that you have SELECTed for.

```sql
SELECT release_year, country, MAX(budget) #show me column x, y, and z, where z is a calculation based on column w
FROM films # take this data from table a
GROUP BY release_year, country # organise the data I want based on this column
ORDER BY release_year, country; #organise the column I wanted according to these other columns
```


Example including most of what we learnt:

```sql
SELECT release_year, AVG(budget) AS avg_budget, AVG(gross) AS avg_gross
FROM films
WHERE release_year > 1990
GROUP BY release_year
HAVING AVG(budget) > 60000000
ORDER BY AVG(gross) DESC;
```

Another example including most of what we learnt:

```sql
SELECT country, AVG(budget) AS avg_budget, AVG(gross) AS avg_gross-- select country, average budget, average gross

FROM films-- from the films table

GROUP BY country-- group by country 

HAVING count(title) > 10-- where the country has more than 10 titles

ORDER BY country-- order by country

LIMIT 5-- limit to only show 5 results

```

### Getting data from multiple tables

To combine data from more than one table, you can use the keyword JOIN, and combine based on a common column. For example:

```sql
SELECT title, imdb_score
FROM films
JOIN reviews
ON films.id = reviews.film_id
WHERE title = 'To Kill a Mockingbird';
```

