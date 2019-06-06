# MySQL coding style

The following document is currently work in progress.

## Common

* Language keywords MUST be written in UPPER CASE format.
* Table and column names MUST be written as they are defined in the database.
* Statement length should be maximum of 120 characters, everything longer than that should be split into multiple rows.

Indentation

* Use spaces, not tabs.
* 1 TAB is equal to 4 spaces.
* The following are considered FIRST level statements: 
  SELECT, INSERT, UPDATE, DELETE 
  and MUST not start indented.
* The following are considered SECOND level statements: 
  INTO, FROM, JOIN, WHERE, GROUP BY, HAVING, ORDER BY, LIMIT, OFSET
  and should be indented by exactly 1 TAB from the FIRST level statement.
* Each sublevel MUST be indented by exactly 1 TAB.

Aliases

* MUST use the AS keyword.
* MUST be camelCase.

Subqueries and other expressions

* MUST be surrounded with parenthesis.
* MUST be aliased.

## Inserts

## Updates

## Selects

SELECT statement

* When selecting a single column:
  * column name SHOULD be on the same line as the SELECT keyword.
* When selecting multiple columns:
  * each column name MUST be on a separate line indented.
  * comma separator SHOULD be at the end of the line.

FROM statement

* Tables MUST be specified on the same line as the FROM keyword.
* Usage of implicit JOIN aka specifing multiple comma separated tables in FROM statement is prohibited. 
  Use explicit JOIN statement instead.
* When dealing with multiple tables using JOIN operations, the most important table SHOULD be specified in the FROM clause, 
  the rest should be part of the JOIN.
* Tables MUST be aliased when combined with JOIN operations.

JOIN statement

* Inner join MUST be defined as INNER JOIN, the usage of short JOIN variant is prohibited.
* Left/Right outer join MUST be defined as LEFT/RIGHT JOIN, the usage of long oboslete LEFT/RIGHT OUTER JOIN variant is prohibited.
* Joined tables MUST be aliased.

WHERE statement, HAVING statement

* Short equality conditions MAY be put on the same line as the WHERE keyword.
* Long conditions MUST be placed on a new line, indented.
* Long complex conditions MUST be grouped using parenthesis.
* The AND/OR operator SHOULD be at the beginning of the line.

GROUP BY statement

* Grouping by a single column SHOULD be specified on the same line as the GROUP BY keyword
* Grouping by a multiple columns:
  * Each column MUST be specified on a new line, indented.
  * Each column, except for the last, MUST have the comma separator at the end of the line and not at the beginning.
* Column name MUST be the same case as defined in SELECT.

ORDER BY statement

* ASC / DESC order MUST be defined after the column name
* Ordering by a single column SHOULD be specified on the same line as the ORDER BY keyword
* Ordering by a multiple columns:
  * Each column MUST be specified separately on a new line, indented.
  * Each column, except for the last, MUST have the comma separator at the end of the line and not at the beginning.
  
LIMIT statement

* Limit value MUST be defined on the same line as the LIMIT keyword
* MUST not contain an OFSET, use OFSET statement for defining one

OFSET statement

* Ofset value MUST be defined on the same line as the OFSET keyword
