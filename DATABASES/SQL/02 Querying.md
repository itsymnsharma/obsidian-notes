## Running a DBMS Program

- We will run a sqlite program on a db and make queries on it

```
sqlite3 longlist.db
```

- This tells to run the sqlite program on longlist.db

## SELECT

- What data is actually in our database? To answer this, we will use our first SQL keyword, `SELECT`, which allows us to select some (or all) rows from a table inside the database.

```
SELECT * FROM "longlist";
```

- - means all rows and columns
- This selects all the rows from the table called `longlist`.
- The output we get contains all the columns of all the rows in this table, which is a lot of data.

```
SELECT "title" FROM "longlist";
```

- This selects a particular column, say the title, from the table.

```
SELECT "title", "author" FROM "longlist";
```

- It is good practice to use double quotes around table and column names, which are called SQL identifiers. 
- SQL also has strings and we use single quotes around strings to differentiate them from identifiers.

## LIMIT

- If a database had millions of rows, it might not make sense to select all of its rows, we might want to merely take a peek at the data it contains. 
- We use the SQL keyword `LIMIT` to specify the number of rows in the query output.

```
SELECT "title" FROM "longlist" LIMIT 10;
```

- This query gives us the first 10 titles in the database.
- The titles are ordered the same way in the output of this query as they are in the database.

## WHERE

- It is used to select rows based on a condition
- It will output the rows for which the specified condition is true.

```
SELECT "title", "author" FROM "longlist" WHERE "year" = 2023;
```

- It gives us the titles and authors for the books long listed in 2023.
- Below are the operators used to specify conditions in SQL 
    - Equal to (=)
    - Not equal to (!= or <>)
    - NOT
- We can even use Logical Operators like below to combine conditions in SQL
    - AND
    - OR

```
SELECT "title", "author" FROM "longlist" WHERE "format" != "hardcover";
```

```
SELECT "title", "author" FROM "longlist" WHERE "format" <> "hardcover";
```

```
SELECT "title", "author" FROM "longlist" WHERE NOT "format" = "hardcover";
```

```
SELECT "title", "author" FROM "longlist" WHERE "year" = 2022 OR "year" = 2023;
```

```
SELECT "title", "author" FROM "longlist" WHERE ("year" = 2022 OR "year" = 2023) AND "format" != "hardcover";
```

## NULL

- It is possible that tables may have missing data
- `NULL` is a type that indicates that certain data does not have a value or does not exist in the table
- For example, the books in our database have a translator along with an author. However, only some of the books have been translated to English. For other books, the translator value will be `NULL`
- Conditions used with NULL are
    - is NULL
    - is NOT NULL

```
SELECT "title", "translator" FROM "longlist" WHERE "translator" is NULL;
```

- This selects the books for which translators doesn't exist

```
SELECT "title", "translator" FROM "longlist" WHERE "translator" is NOT NULL;
```

- This selects the books for which translators do exist.

## Like

- Used to select data that roughly matches the specified string
- e.g. `LIKE` could be used to select books that have a certain word or phrase in their title.
- `Like` is combined with below operators
    - % - Matches any characters around a given string
    - _ - Matches a single character

```
SELECT "title" FROM "longlist" WHERE title LIKE "%love%";
```

- select the books with the word “love” in their titles
- `%` matches 0 or more characters, so this query would match book titles that have 0 or more characters before and after “love” — that is, titles that contain “love”.

```
SELECT "title" FROM "longlist" WHERE title LIKE "The%";
```

- select the books whose title begin with “The”,
- may also return books whose titles begin with “Their” or “They”. 
- To select only the books whose titles begin with the **word** “The”, we can add a space.

```
SELECT "title" FROM "longlist" WHERE title LIKE "The %";
```

- In cases where we are unsure of the spelling of book like given that there is a book in the table whose name is either “Pyre” or “Pire”, we can select it by running 

```
SELECT "title" FROM "longlist" WHERE title LIKE "P_re";
```

- _ is used for single characters so if we knew there was a book in the table whose title begins with “T” and has four letters in it, we can try to find it by running

```
SELECT "title"  FROM "longlist" WHERE "title" LIKE 'T____';
```

## Ranges

- We can also use the operators `<`, `>`, `<=` and `>=` in our conditions to match a range of values.

```
SELECT "title", "author" FROM "longlist" WHERE "year" >= 2019 AND "year" <= 2022;
```

- Another way to get the same results is using the keywords `BETWEEN` and `AND` to specify inclusive ranges.

```
SELECT "title", "author" FROM "longlist" WHERE "YEAR" BETWEEN 2019 AND 2022;
```

## ORDER BY

- `ORDER BY` keyword allows us to organise the returned rows in some specified order.
- By Default, `ORDER BY` chooses ascending order by default

```
SELECT "title", "rating" from "longlist" ORDER BY "rating" LIMIT 10;
```

- selects the bottom 10 books in our database by rating because `ORDER BY` chooses ascending order by default.

```
SELECT "title", "rating" FROM "longlist" ORDER BY "rating" DESC LIMIT 10;
```

- select the top 10 books by rating and also include number of votes

```
SELECT "title", "rating", "votes" FROM "longlist" ORDER BY "rating" DESC, "votes" DESC LIMIT 10;
```

## Aggregate Functions

- `COUNT`, `AVG`, `MIN`, `MAX`, and `SUM` are called aggregate functions and allow us to perform the corresponding operations over multiple rows of data.
- Each of the following aggregate functions will return only a single output—the aggregated value.
- To find the average rating of all books in the database, use `AVG`

```
SELECT AVG("rating) FROM "longlist";
```

- To round the average rating to 2 decimal points, use `ROUND`

```
SELECT ROUND(AVG("rating"), 2) from "longlist";
```

- To rename the column in which the results are displayed, use `AS`

```
SELECT ROUND(AVG("rating), 2) AS "Average Rating" from "longlist";
```

- To select the maximum rating in the database, use `MAX`

```
SELECT MAX("rating") FROM "longlist";
```

- To select the minimum rating in the database, use `MIN`

```
SELECT MIN("rating") FROM "longlist";
```

- Using `MAX` with the title column would give you the “largest” (or in this case, last) title alphabetically. Similarly, `MIN` will give the first title alphabetically.
- To count the total number of votes in the database, use `COUNT`

```
SELECT COUNT("votes") FROM "longlist";
```

- To count the number of books in our database, use `COUNT` with `*` to select every row and column from the database. 

```
SELECT COUNT(*) FROM "longlist";
```

- `COUNT` function does not count `NULL` values.

- To count distinct numbers of publishers, use `DISTINCT`

```
SELECT COUNT(DISTINCT "publisher") FROM "longlist";
```