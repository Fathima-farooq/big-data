count(*) – Returns the count of all rows in a table including rows containing NULL values.

count(expr) – Returns the total number of rows for expression excluding null.

count(DISTINCT expr[, expr]) – Returns the count of distinct rows of expression (or expressions) excluding null values.
```bash

jdbc:hive2://> select count(*) from employee;
+------+
| _c0  |
+------+
| 7    |
+------+
jdbc:hive2://> select count(salary) from employee;
+------+
| _c0  |
+------+
| 5    |
+------+
select count(distinct gender, salary) from employee;
+------+
| _c0  |
+------+
| 4    |
+------+
```

Hive Sum of a Column and sum of Distinct Columns

Syntax: sum(col)
Syntax: sum(DISTINCT col)
Return: DOUBLE

Returns the total sum of the elements in the group or the sum of the distinct values of the column in the group.
```bash

jdbc:hive2://> select sum(salary) from employee;
+---------+
|   _c0   |
+---------+
| 110000  |
+---------+
jdbc:hive2://> select sum(distinct salary) from employee;
+---------+
|   _c0   |
+---------+
| 100000  |
+---------+
jdbc:hive2://> select age,sum(salary) from employee group by age;
+-------+--------+
|  age  |  _c1   |
+-------+--------+
| NULL  | NULL   |
| 20    | 40000  |
| 30    | 20000  |
| 40    | 20000  |
| 41    | 30000  |
+-------+--------+
```

Hive Average (Avg) of a Column & Average of Distinct Column

Syntax: avg(col)
Syntax: avg(DISTINCT col)
Return: DOUBLE

Returns the average of the elements in the group or the average of the distinct values of the column in the group.
```bash
jdbc:hive2://> select avg(salary) from employee group by age;
+-------------+
|     _c0     |
+-------------+
| 22000.0000  |
+-------------+
jdbc:hive2://> select avg(distinct salary) from employee group by age;
+-------------+
|     _c0     |
+-------------+
| 25000.0000  |
+-------------+
jdbc:hive2://> select age,avg(salary) from employee group by age;
+-------+-------------+
|  age  |     _c1     |
+-------+-------------+
| NULL  | NULL        |
| 20    | 40000.0000  |
| 30    | 10000.0000  |
| 40    | 20000.0000  |
| 41    | 30000.0000  |
+-------+-------------+
```

min(col) – Get Minimum value of a column
Returns the minimum of the column in the group.
Return: DOUBLE
```bash

jdbc:hive2://> select min(salary) from employee;
+--------+
|  _c0   |
+--------+
| 10000  |
+--------+
```

max(col) – Get Maximum value of a column
Returns the maximum value of the column in the group.
Return: DOUBLE
```bash

jdbc:hive2://> select max(salary) from employee;
+--------+
|  _c0   |
+--------+
| 40000  |
+--------+
```