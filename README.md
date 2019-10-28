# MySQL coding style

The following document is currently work in progress.

## Common

* Language keywords MUST be written in UPPER CASE format.
* Table and column names MUST be written as they are defined in the database.
* Line length MUST be maximum 80 characters in length, everything longer than that MUST be split into multiple lines.

### Indentation

* Indentation MUST be performed using spaces and not tabs.
* Indent size MUST be 4 spaces.

### Aliases

* MUST use the AS keyword.
* MUST be camelCase.

### Subqueries and other expressions

* MUST be surrounded with parenthesis.
* MUST be aliased.

## Inserts

### INSERT INTO clause

* Table name MUST be specified inline with the INSERT INTO clause
* Opening parenthesis which holds the column names MUST be specified inline with the INSERT INTO clause separated by space after table name.
* Column name MUST be specified on a separate line below the INSERT INTO clause, indented.
* Column separator - COMMA - MUST be placed after the column name.
* Closing parenthesis which holds the column names MUST be specified on a new line below the last specified column name.

Example:
```
INSERT INTO people (
  firstName,
  lastName,
  birthDate
)
```

### VALUES clause

* VALUES clause MUST BE specified in a new row
* Opening parenthesis which holds the column values MUST be inline with the VALUES keyword, separated by a single space.
* Column values MUST be specified on a separate line, indented.
* Column separator - COMMA - MUST be placed after the column value.
* Closing parenthesis which holds the column values MUST be specified on a new line below the last specified column value.

```
VALUES (
  'Nikola',
  'Tesla',
  '1856-07-10'
)
```

## Updates

## Selects

### SELECT clause

* Column name MUST be specified inline with the SELECT keyword when selecting a single column.

  Example:
  ```
  SELECT birthDate
  FROM people
  ```

* Column name MUST be specified on a separate line below the SELECT keyword, indented, when selecting multiple columns.
* Column separator - COMMA - MUST be placed after the column name.

  Example:
  ```
  SELECT
    firstName,
    lastName,
    birthDate
  FROM people
  ```

### FROM clause

* Table name MUST be specified inline with the FROM keyword.
* Table name MUST have an alias when JOIN clauses are defined.
* From clause MUST consist of only one table. Usage of implicit JOIN statements is prohibited.

### JOIN clause

* Inner join MUST be defined using INNER JOIN keyword, the usage of short JOIN keyword variant is prohibited. 
* Left/Right outer joins MUST be defined using LEFT/RIGHT JOIN keyword, the usage of long oboslete LEFT/RIGHT OUTER JOIN keyword is prohibited.
* Joined tables MUST have an alias.

### WHERE clause, HAVING clause

* Short conditions SHOULD be specified inline.
* The AND/OR operator MUST be positioned at the beginning of the line.
* Long conditions MUST be split on multiple lines.

  Example:
  ````
  WHERE
    column_a IS NULL
    AND column_b = 3
    AND column_c = 4
  ````
  
* Conditions which have complex logic must be surrounded by parenthesis.

  Example:
  ````
  WHERE
    (
      column_a = 5
      AND column_b = 1
    )
    OR (
      column_c = 7  
      AND (
        column_d = 1
        AND column_e IS NULL
      )
    )
  ````

### GROUP BY clause

* Column name MUST be the same as defined in the SELECT clause.
* Column name MUST be specified inline with the GROUP BY keyword when grouping by a single column.
* Column name MUST be specified separately on a new line, indented below the GROUP BY keyword, when grouping by multiple columns.
* Column separator - COMMA - MUST be positioned after the column and not before.

### ORDER BY clause

* Order direction keyword - ASC / DESC - MUST be specified inline with the column name.
* Order direction keyword MUST not be omitted.
* Column name MUST be specified inline with the ORDER BY keyword when ordered by a single column.
* Column name MUST be specified separately on a new line, indented below the ORDER BY keyword, when ordered by multiple columns.
* Column separator - COMMA - MUST be positioned after the column and not before.

### LIMIT clause

* Limit value MUST be defined inline with the LIMIT keyword.
* LIMIT clause MUST not contain an OFSET, use OFSET clause for defining one.

### OFSET clause

* Ofset value MUST be defined inline with the OFSET keyword.
