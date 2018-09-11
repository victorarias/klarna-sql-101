# Binosaur SQL 101

SQL is a programming language that allows you to query data at a database. Below you can find a description of its main parts with some examples.

Assume you have the following two tables for the examples:

#### table name: dinosaurs
| id | name   | diet | country_id |
| --- | --- | --- | ---
| 1 | Tove   | vegab | 1
| 2 | Kevin  | vegetarian | 1
| 3 | Victor | vegetarian | 2
| 4 | Elvin  | omnivore   | 3

#### table name: countries
| id | name | continent
|--- | --- | ---
| 1  | Sweden | Europe
| 2  | Brazil | South America
| 3  | Venezuela | South America

## The SQL SELECT Statement

The SELECT statement is used to select data from a database. For example, in order to display all dinousaur names and diets you do:

Example:

```sql
SELECT name, diet
FROM dinosaurs;
```

## The SQL WHERE Clause

The WHERE clause is used to filter records. For example, in order to find all records from `dinosaurs` that have a `vegan` diet you do:

Example:

```sql
SELECT name, diet
FROM dinosaurs
WHERE diet = 'vegan';
```

## The 

