### Calculations

In SQL we can also perform calculations on data found in the database. This is possible with aggregate functions. Some of the aggregate 
functions available are:
- AVG(): averages values
- MAX(): finds maximum value
- MIN(): finds minimum value
- SUM(): adds numeric values
- arithmetics with: +, -, *, /

Note: when dividing in SQL using integer numbers, the results will always come back as integer numbers too, unless you specify 
otherwise. Eg.:

```sql
SELECT (4/3);
``` 
The answer will be 1.

But if you specify that you want the numbers shown as decimals, you can do:

```sql
SELECT (4/3) AS result;
```
The answer here will be 1.333

Another way to insure that the result will include decimals is to use decimal numbers in your calculation, eg.:
```sql
SELECT (4/3.0);
```
The answer will be 1.333

Example:
```sql
SELECT MAX(duration)
FROM films;
```

These aggregate functions can be used together with other keywords, such as WHERE, LIKE.

Example #1:
```sql
SELECT SUM(gross)
FROM films
WHERE release_year >= 2000;
```

Example #2:
```sql
SELECT AVG(gross)
FROM films
WHERE title LIKE 'A%';
```

```sql
SELECT MAX(gross)
FROM films
WHERE release_year BETWEEN 2000 AND 2012;
```

### Aliasing with AS

This allows you to temporarily asign a name to something. Eg.:
```sql
SELECT title, (gross - budget) AS net_profit
FROM films;
```

Another example:
```sql
SELECT AVG(duration) / 60.0 AS avg_duration_hours
FROM films;
```
Note: you need to add the spaces around `/`.

Multiplications and divisions are often carried out before addition and substraction. In order for additions and substractions to
 be carried out before, they must be within brackets. When there are more than more multiplication and/or divisions in a calculation, 
 these are done in order.


