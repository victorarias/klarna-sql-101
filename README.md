# Binosaur SQL 101

SQL is a programming language that allows you to query data at a database. Below you can find a description of its main parts with some examples. Assume you have the following two tables that you want to query:

#### table name: dinosaurs
| id | name   | diet | country_id |
| --- | --- | --- | ---
| 1 | Tove   | vegan | 1
| 2 | Kevin  | vegetarian | 1
| 3 | Victor | vegan | 2
| 4 | Elvin  | omnivore   | 3

#### table name: countries
| id | name | continent
|--- | --- | ---
| 1  | Sweden | Europe
| 2  | Brazil | South America
| 3  | Venezuela | South America

## The SELECT statement

The SELECT statement is used to select data from a database. For example, in order to display all dinousaur names and diets you do:

Example:

```sql
SELECT name, diet
FROM dinosaurs;
```

## The WHERE clause

The WHERE clause is used to filter records. For example, in order to find all records from `dinosaurs` that have a `vegan` diet you do:

Example:

```sql
SELECT name, diet
FROM dinosaurs
WHERE diet = 'vegan';
```

## The LEFT JOIN clause

The LEFT JOIN clause is used to join two tables together over a key/condition. For example, you can use it to join the tables `dinosaurs` and `countries` so we can display the continent of each dinosaur.

Example:

```sql
SELECT dinosaurs.name, countries.continent
FROM dinosaurs
LEFT JOIN countries ON dinosaurs.country_id = countries.id;
```

## The GROUP BY clause and aggregation functions

Imagine that you want to **count** how many dinosaurs we have. For that you can use the COUNT aggregation function. Here is an example of how to do that:

```sql
SELECT countries.continent, COUNT(*)
FROM dinosaurs;
```

Now lets say that you want to **count** those dinosaurs but per continent, so you know how many of them are on each continent. Now armed with the COUNT function you just need to add the GROUP BY clause. Here is an example of how to do that:

```sql
SELECT countries.continent, COUNT(*)
FROM dinosaurs
LEFT JOIN countries ON dinosaurs.country_id = countries.id
GROUP BY countries.continent;
```

There are other very handy aggregation functions, like for example the `SUM`. With it you can sum the values of each record instead of just counting how many rows you have. Can you think of an example of how this can be useful?
